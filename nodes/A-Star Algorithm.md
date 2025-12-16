---
context:
  - "[[Algorithm]]"
  - "[[Pathfinding]]"
---

# A-Star Algorithm

(A\* Algorithm)

Versatile [[Pathfinding]] and graph traversal algorithm.

---

Given a [[Weighted Graph]], a source node and a goal node, the algorithm can find the shortest path (with respect to the given weights) from the source to the goal.

**Complete**: On finite graphs with non-negative edge weights, A\* is guaranteed to terminate and to find a path if one exists.

**Admissible**: Can guarantee to return an optimal solution. If the heuristic is admissible, then A\* is admissible.

## Heuristics

The algorithm uses [[Heuristic]] functions to guide its search.

A\* selects the path that minimizes:
`F(n) = G(n) + H(n)`
Where `n` is the next node on the path, `G(n)` is the cost of the path from the start node to `n`, and `H(n)` is the estimate of the cheapest path, or distance, from `n` to the goal.

## Bounded Relaxation

While the admissability of A\* can guarantee an optimal solution, it also means that it might have to examine a lot of nodes.

It is possible to 'relax' the admissibility, speeding up the search process at the expense of optimality.

The heuristic function can be modified by [[Scalar]] weights.

See [[Weighted A-Star Algorithm]].

## Pseudocode

```
iterate() {
    if open is empty:
        terminate; // No path found

    current = best cell from open; // Lowest F value

    if current === target:
        terminate; // Path found

    remove current from open;
    add current to closed;

    for each of current.neighbors:
        if neighbor is block or neighbor is in closed:
            continue;

        totalG = current.G + cost to move to neighbor

        if neighbor is not in open:
            add neighbor to open;
            neighbor.parent = current;
            neighbor.G = totalG;
            neighbor.H = heuristic(neighbor, target);
            neighbor.F = neighbor.G + neighbor.H;
        else if totalG < neighbor.G:
                neighbor.parent = current;
                neighbor.G = totalG;
                // Update F because G has changed
                neighbor.F = neighbor.G + neighbor.H;
```

## Implementation

```zig
const Main = struct {
    const cols = 12;
    const rows = 12;
    const max = cols * rows;

    const Neighbors = struct {
        const x: [8]i8 = .{ 1, 1, 0, -1, -1, -1, 0, 1 };
        const y: [8]i8 = .{ 0, 1, 1, 1, 0, -1, -1, -1 };
        const cost: [8]i8 = .{ 10, 14, 10, 14, 10, 14, 10, 14 };
    };

    fn heuristic(start: grid.Cell, target: grid.Cell) i32 {
        return @intCast(@abs(target.x - start.x) + @abs(target.y - start.y));
    }

    fn getBestFromOpen(target: grid.Cell) usize {
        var bestF: i32 = 0x7FFFFFFF;
        var bestIndex: usize = 0;

        for (0..Data.openListCount) |i| {
            const openCell: grid.Cell = Data.openList[i];

            const g: i32 = Data.gCosts[@intCast(openCell.y)][@intCast(openCell.x)];
            const h: i32 = heuristic(openCell, target);
            const f: i32 = (g + h);

            if (f < bestF) {
                bestF = f;
                bestIndex = i;
            }
        }

        return bestIndex;
    }

    const Data = struct {
        const NodeState = enum { Unvisited, Open, Closed };

        var gCosts: [rows][cols]i32 = undefined;
        var parents: [rows][cols]grid.Cell = undefined;
        var nodeStates: [rows][cols]NodeState = undefined;

        var openList: [max]grid.Cell = undefined;
        var openListCount: usize = 0;

        var outPath: [max]grid.Cell = undefined;

        fn reset() void {
            for (0..rows) |y| {
                for (0..cols) |x| {
                    nodeStates[y][x] = .Unvisited;
                    gCosts[y][x] = 0;
                    parents[y][x] = .{ .x = -1, .y = -1 };
                    openListCount = 0;
                }
            }
        }
    };

    fn main(start: grid.Cell, target: grid.Cell, map: [rows][cols]u8, outPath: *[max]grid.Cell, pathLength: *i32) bool {
        Data.reset();

        if (start.x < 0 or start.y < 0 or start.x >= cols or start.y >= rows) {
            @panic("starting cell out of bounds");
        }

        if (target.x < 0 or target.y < 0 or target.x >= cols or target.y >= rows) {
            @panic("target cell out of bounds");
        }

        const xStart_u: usize = @intCast(start.x);
        const yStart_u: usize = @intCast(start.y);

        Data.openList[0] = start;
        Data.nodeStates[yStart_u][xStart_u] = .Open;
        Data.parents[yStart_u][xStart_u] = .{ .x = -1, .y = -1 };
        Data.openListCount = 1;

        while (Data.openListCount > 0) {
            const bestCellIndex: usize = getBestFromOpen(target);
            const current = Data.openList[bestCellIndex];

            Data.openList[bestCellIndex] = Data.openList[Data.openListCount - 1];
            Data.openListCount -= 1;

            Data.nodeStates[@intCast(current.y)][@intCast(current.x)] = .Closed;

            const isSuccess: bool = (current.x == target.x and current.y == target.y);
            if (isSuccess) {
                var length: usize = 0;

                var pathCell: grid.Cell = current;

                while (pathCell.x > -1 and pathCell.y > -1) {
                    Data.outPath[length] = pathCell;
                    const parent: grid.Cell = Data.parents[@intCast(pathCell.y)][@intCast(pathCell.x)];
                    pathCell.x = parent.x;
                    pathCell.y = parent.y;
                    length += 1;
                }

                var i: usize = 0;
                while (i < (length / 2)) : (i += 1) {
                    const temp: grid.Cell = Data.outPath[i];
                    Data.outPath[i] = Data.outPath[length - 1 - i];
                    Data.outPath[length - 1 - i] = temp;
                }

                outPath.* = Data.outPath;
                pathLength.* = @intCast(length);

                return true;
            }

            for (0..8) |i| {
                const neighbor: grid.Cell = .{
                    .x = current.x + Neighbors.x[i],
                    .y = current.y + Neighbors.y[i],
                };

                if (neighbor.x < 0 or neighbor.y < 0) continue;
                if (neighbor.x >= cols or neighbor.y >= rows) continue;

                const x: usize = @intCast(neighbor.x);
                const y: usize = @intCast(neighbor.y);

                const isWall: bool = (map[y][x] > 0);
                if (isWall) continue;

                const state: Data.NodeState = Data.nodeStates[y][x];
                if (state == .Closed) continue;

                const newG: i32 = Data.gCosts[@intCast(current.y)][@intCast(current.x)] + Neighbors.cost[i];

                if (state != .Open) {
                    Data.nodeStates[y][x] = .Open;
                    Data.gCosts[y][x] = newG;
                    Data.parents[y][x] = current;

                    Data.openList[Data.openListCount] = neighbor;
                    Data.openListCount += 1;
                } else if (newG < Data.gCosts[y][x]) {
                    Data.gCosts[y][x] = newG;
                    Data.parents[y][x] = current;
                }
            }
        }

        return false;
    }
};
```

---
aliases:
  - Disk Usage
context:
  - "[[System Software]]"
---

# du

(Disk Usage)

Program that estimates and outputs the space used by files and directories.

---

**Basic Usage**: `du [OPTIONS] [FILE/DIRECTORY...]`

**Common Options**:

| Flag                    | Description                                              |
| ----------------------- | -------------------------------------------------------- |
| `-h`                    | Human-readable sizes (K, M, G)                           |
| `-s`                    | Summary only (total for each argument)                   |
| `-a`                    | Show all files, not just directories                     |
| `-c`                    | Produce a grand total                                    |
| `-d N or --max-depth=N` | Limit directory depth                                    |
| `--exclude=PATTERN`     | Skip files matching pattern                              |
| `-L`                    | Follow symlinks                                          |
| `--apparent-size`       | Show apparent size (file content) rather than disk usage |

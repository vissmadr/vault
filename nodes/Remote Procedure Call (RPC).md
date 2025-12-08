---
aliases:
  - RPC
context:
  - "[[API]]"
---

# Remote Procedure Call (RPC)

Communication mechanism that allows a program to execute a procedure on a remote system as if it were a local function call.

---

Example with `JSON-RPC 2.0`:

```json
{
  "jsonrpc": "2.0",
  "method": "add",
  "params": [4, 7],
  "id": 3
}
```

```json
{
  "jsonrpc": "2.0",
  "result": 11,
  "id": 3
}
```

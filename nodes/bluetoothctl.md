---
context:
    - "[[CLI Application]]"
---

#wip

# bluetoothctl

ad

---

To pair a device from the terminal, run:

```
bluetoothctl
```

Then inside bluetoothctl:

```
power on
agent on
default-agent
pairable on
scan on
```

Wait until your device appears, then use its MAC address:

```
pair AA:BB:CC:DD:EE:FF
trust AA:BB:CC:DD:EE:FF
connect AA:BB:CC:DD:EE:FF
scan off
quit
```

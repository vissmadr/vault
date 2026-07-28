---
context:
  - "[[System Software]]"
  - "[[Linux]]"
---

# rfkill

Linux tool and interface for viewing and changing the radio-blocking state of wireless devices.

---

Commonly controls Wi-Fi, Bluetooth, and mobile broadband devices.

```bash
rfkill list
rfkill block wlan
rfkill unblock wlan
rfkill unblock bluetooth
rfkill unblock all
```

**Soft Block**: Set by software and removable with rfkill unblock.

**Hard Block**: Set by hardware, such as a physical switch or firmware setting, and cannot be removed by rfkill.

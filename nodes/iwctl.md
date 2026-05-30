---
context:
  - "[[CLI Application]]"
  - "[[Linux]]"
---

# iwctl

Interactive [[CLI]] client for controlling `iwd`, the Linux wireless daemon.

---

Useful for connecting to Wi-Fi from a terminal, especially on minimal Linux installs.

Start it:

```sh
iwctl
```

Inside `iwctl`:

```sh
device list
station wlan0 scan
station wlan0 get-networks
station wlan0 connect "SSID"
exit
```

Passphrase is prompted when needed.

One-shot connection:

```sh
iwctl station wlan0 connect "SSID"
```

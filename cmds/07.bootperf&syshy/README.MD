# 🚀 Boot Performance & System Hygiene
**Analyze startup time • Identify slow services • Remove common delays • Maintain SSD health**

---

## 📌 Overview
Modern Linux systems (especially with **systemd**) may experience slow boots due to:

- **Services waiting unnecessarily**
- **Background startup delays**
- **Unoptimized storage maintenance**

This guide helps you:

- 🔍 **Analyze boot performance**
- 🧩 **Identify slow services**
- ⛔ **Remove common boot delays**
- 💽 **Keep SSD performance healthy**

---

## ⏱️ 1) Analyze Total Boot Time (`systemd-analyze`)

### ✅ Command
```bash
systemd-analyze
```

### What this does
Displays total boot time split into:
- **Firmware**
- **Bootloader**
- **Kernel**
- **Userspace**

### Why this is useful
- Shows **where time is being spent**
- Helps confirm whether changes actually improved boot time

### What happens after execution
- Prints boot timing statistics
- **No system changes** are made (read-only)

---

## 🧩 2) Identify Slow Services (`systemd-analyze blame`)

### ✅ Command
```bash
systemd-analyze blame
```

### What this does
- Lists system services ordered by **startup time**
- Highlights what is delaying boot the most

### Why this is useful
- Pinpoints **slow or unnecessary** services
- Helps decide what can be optimized or disabled

### What happens after execution
- Displays a ranked list of services
- **No services are modified**

---

## ⛔ 3) Remove Network Boot Delay (Wait Online Service)

### ✅ Command
```bash
sudo systemctl disable NetworkManager-wait-online.service
```

### What this does
Disables the service that **waits for network connectivity during boot**.

### Why this matters
- This often causes **~5–30s** boot delays
- Most desktop systems don’t need to block boot until network is fully up

### What happens after execution
- Boot continues without waiting for network
- Network still connects normally **after login**

### If you do NOT do this
- Boot may pause until network is fully available
- Slower startup, especially on **Wi-Fi**

### ⚠️ When NOT to disable
Do **not** disable this on systems that require network during boot, such as:
- **Servers**
- Systems using **NFS**
- Systems with **remote mounts** needed at boot

---

## 💽 4) Trim Unused SSD Blocks (`fstrim`)

### ✅ Command
```bash
sudo fstrim -av
```

### What this does
Tells the SSD which blocks are **no longer in use**, helping SSDs manage wear and performance.

### Why this is useful
- SSDs can slow down over time without trimming
- Improves long-term write performance
- Reduces internal SSD fragmentation and wear

### What happens after execution
- Unused blocks are discarded
- SSD health and performance improve (on supported filesystems)

### If you do NOT do this
- SSD performance may degrade over time
- Higher write amplification and wear

> ℹ️ Most modern systems run this automatically via **`fstrim.timer`**, but running it manually confirms support.

---

## 🧠 Important Notes
- **`systemd-analyze`** commands are safe and **read-only**
- Disabling **`NetworkManager-wait-online.service`** affects **boot behavior only**
- `fstrim` is safe on supported filesystems like **ext4**, **btrfs**, **xfs**

---

## ✅ Recommended Workflow (Quick Run)
Run these in order:

```bash
systemd-analyze
systemd-analyze blame
sudo systemctl disable NetworkManager-wait-online.service
sudo fstrim -av
```

🔁 **Reboot** after disabling the wait-online service to measure improvements.

---

## 📌 Summary
| Command / Action | Purpose |
|---|---|
| `systemd-analyze` | Measure total boot time |
| `systemd-analyze blame` | Find slow boot services |
| Disable `NetworkManager-wait-online.service` | Remove common network boot delay |
| `fstrim -av` | Maintain SSD performance & health |
---
## 👉 Next: Curl

- Move to **Curl Cmds**
- **[08.curl](../08.curl/README.MD)**
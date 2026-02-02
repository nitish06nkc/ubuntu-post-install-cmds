# 🗂️ systemd Journal Log Management (`journalctl` / `systemd-journald`)

Keep system logs **useful**, prevent **silent disk bloat**, and reclaim space safely.

---

## 📌 Overview

`systemd-journald` stores system logs (often persistently on disk).  
If unmanaged, journal logs can **grow indefinitely** and quietly consume disk space.

This guide shows how to:
- 🔍 Inspect current journal size
- 🧹 Clean existing logs
- 🧱 Permanently cap future journal growth (correct method)

---

## 🔍 Check Current Journal Disk Usage

```bash
journalctl --disk-usage
```

**What this does**
- Shows total disk space currently used by journal logs

**Why this matters**
- Journal growth isn’t always obvious in day-to-day disk checks
- Logs can become **very large** over time without warning

---

## 🧹 Reduce Existing Log Size (Immediate Cleanup)

```bash
sudo journalctl --vacuum-size=200M
```

**What this does**
- Deletes older journal entries
- Ensures total journal size does not exceed **200 MB**
- Keeps recent/relevant logs intact

**Important**
- Setting config limits does **not** shrink existing logs  
  → this command is what frees space right now.

---

## ⚙️ Permanently Limit Journal Size (Correct Method)

Edit the configuration file:

```bash
sudo nano /etc/systemd/journald.conf
```

Set `SystemMaxUse` under the existing `[Journal]` section:

```ini
[Journal]
#Storage=auto
#Compress=yes
#Seal=yes
#SplitMode=uid
#SyncIntervalSec=5m
#RateLimitIntervalSec=30s
#RateLimitBurst=10000
#SystemMaxUse=
SystemMaxUse=200M
#SystemKeepFree=
#SystemMaxFileSize=
#SystemMaxFiles=100
#RuntimeMaxUse=
#RuntimeKeepFree=
```

**Why this approach is correct**
- The `[Journal]` section already exists
- You keep the default `#SystemMaxUse=` line commented for reference
- You define **one** clear active limit (`SystemMaxUse=200M`)
- Avoids duplication/ambiguity/misplacement → **systemd-safe**

---

## ▶️ Apply the Configuration

Restart journald:

```bash
sudo systemctl restart systemd-journald
```

(Or reboot.)

**After this**
- Journal disk usage is capped at **200 MB**
- Older logs rotate automatically
- Log growth becomes predictable

---

## 🧠 Why This Matters (Long-Term)

Without limits:
- Logs grow endlessly
- Disk space slowly disappears
- Problems show up months later with no obvious cause

With limits:
- Disk usage stays controlled
- Logs remain recent and useful
- Maintenance becomes simple

---

## 🚫 What This Does *Not* Do

- Does **not** disable logging
- Does **not** remove recent/important logs (when used reasonably)
- Does **not** reduce log quality/detail

---

## ✅ Recommended Workflow

```bash
journalctl --disk-usage
sudo journalctl --vacuum-size=200M
sudo nano /etc/systemd/journald.conf
sudo systemctl restart systemd-journald
```

---

## ✅ Summary

| Action | Purpose |
|---|---|
| `journalctl --disk-usage` | Monitor journal size |
| `sudo journalctl --vacuum-size=200M` | Free space immediately |
| Set `SystemMaxUse=200M` | Prevent future bloat |
| Restart `systemd-journald` | Apply changes |
---
## 👉 Next: Boot Performance and System Hygiene

- Move to **Boot Performance and System Hygiene Cmds**
- **[07.bootperf&syshy](../07.bootperf&syshy/README.MD)**
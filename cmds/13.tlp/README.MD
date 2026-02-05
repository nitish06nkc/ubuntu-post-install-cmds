# 🔋 TLP — Advanced Linux Power Management

**Better battery life • Lower heat • Smarter power usage**

TLP is a **set-and-forget** power management tool for Linux laptops. It automatically applies sensible power-saving settings on **battery** and relaxes them on **AC** — no GUI required.

---

## ✅ Why use TLP?

Ubuntu’s default behavior often leaves parts of the system **less optimized for battery** (varies by device), which can lead to:

- 🔻 Faster battery drain (especially while idle)
- 🌡️ Higher temperatures
- 🌀 Fans running more than needed

TLP helps by applying laptop-oriented power tuning automatically.

---

## ⚙️ What TLP manages (high-level)

TLP can optimize power usage across major subsystems, including:

- 🧠 **CPU** frequency & energy policy
- 🧩 **PCIe** runtime power management
- 🔌 **USB** autosuspend
- 💽 **NVMe/SATA** power states
- 📶 **Wi‑Fi** power saving
- 🔊 **Audio** power saving
- 🧷 Disk idle behavior
- 🧰 Laptop-specific ACPI quirks

---

## 🚀 Install & enable (recommended)

### 1) 📦 Install

```bash
sudo apt update
sudo apt install tlp tlp-rdw
```

- **`tlp`** → main power management engine  
- **`tlp-rdw`** → radio device wizard (Wi‑Fi/Bluetooth-related rules)

### 2) ▶️ Enable + start now

```bash
sudo systemctl enable tlp
sudo systemctl start tlp
```


## ⚠️ Important (Ubuntu conflict)

Ubuntu’s **`power-profiles-daemon`** can conflict with TLP (competing CPU/power rules).

If you use TLP, **mask** it so TLP has full control:

```bash
sudo systemctl mask power-profiles-daemon
```

> Note: The “Power Mode” slider in Ubuntu Settings may disappear after masking — **expected**.

---

## 🔌🔋 How it behaves

TLP automatically switches based on power source:

| Power source | Typical behavior |
|---|---|
| 🔌 **AC** | Performance-friendly rules |
| 🔋 **Battery** | More aggressive power saving |

---

## ✅ Verify it’s working

### Quick status

```bash
tlp-stat -s
```

Look for:
- `State = enabled`
- Mode: `AC` or `BAT`

### Full diagnostics

```bash
sudo tlp-stat
```

---

## 🛠️ Optional tuning (advanced)

Defaults are usually enough. If you want to tune:

1) Edit config:
```bash
sudo nano /etc/tlp.conf
```

2) Apply changes:
```bash
sudo systemctl restart tlp
```

Tip: Change only a few options at a time, then re-check with `sudo tlp-stat`.

---

## 🧩 Troubleshooting checklist

If battery life gets worse after updates:

- ✅ TLP enabled: `tlp-stat -s`
- ✅ Conflict removed: `systemctl status power-profiles-daemon`
- ✅ Kernel regressions (try a stable kernel if needed)
- ✅ GPU power state (common with NVIDIA/PRIME)
- ✅ Suspend support (deep sleep vs `s2idle`)

---

## 🗑️ Uninstall / revert to Ubuntu defaults

```bash
# Restore Ubuntu power profiles daemon
sudo systemctl unmask power-profiles-daemon
sudo systemctl enable power-profiles-daemon
sudo systemctl start power-profiles-daemon

# Disable & remove TLP
sudo systemctl disable tlp
sudo apt remove tlp tlp-rdw
sudo apt autoremove
```

---

## 🧾 Command cheat-sheet

```bash
# Install
sudo apt update
sudo apt install tlp tlp-rdw

# Enable & start
sudo systemctl enable tlp
sudo systemctl start tlp

# Avoid Ubuntu conflicts
sudo systemctl mask power-profiles-daemon

# Status / diagnostics
tlp-stat -s
sudo tlp-stat

# Restart after config changes
sudo systemctl restart tlp

# Uninstall / revert
sudo systemctl unmask power-profiles-daemon
sudo systemctl enable power-profiles-daemon
sudo systemctl start power-profiles-daemon
sudo systemctl disable tlp
sudo apt remove tlp tlp-rdw
sudo apt autoremove
```

## 👉 Next: Cloudflare

- Move to **Cloudflare cmds**
- **[14.cloudlfare](../14.cloudlflarewarp/README.MD)**


# 🔋 Power Profiles (`powerprofilesctl`)

Control **performance vs. power usage** on Linux using the profiles provided by **power-profiles-daemon**.  
Useful mainly on **laptops** and systems with supported CPU/firmware power controls.

---

## 📌 What is `powerprofilesctl`?

`powerprofilesctl` is a command-line tool to manage system power profiles exposed by **power-profiles-daemon**.

It lets you switch between predefined modes that balance:
- ⚡ **Performance**
- 🔋 **Battery life / power consumption**
- 🧊 **Thermals** (indirectly, via lower power draw)

---

## 🎯 Available Power Profiles

Common profiles include:

- 🟢 **power-saver** → maximizes battery life
- 🔵 **balanced** → balance between performance and efficiency
- 🔴 **performance** → maximum system performance

⚠️ **Availability depends on your hardware and firmware support.**

---

## 🔍 Check the Current Power Profile

```bash
powerprofilesctl get
```

**What it does**
- Prints the currently active power profile

**After running**
- You’ll see the active profile name
- ✅ No system changes are made

**If you don’t use it**
- You won’t know which profile is currently active

---

## ⚙️ Set the Power Profile (Balanced)

```bash
powerprofilesctl set balanced
```

**What it does**
- Switches the system to the **balanced** profile
- Adjusts CPU/power behavior automatically

**After running**
- CPU scaling becomes more adaptive
- Power usage and performance are balanced
- ✅ Good default for daily use

**If you don’t run it**
- The system stays on the previously active profile  
  (could be **power-saver** with lower performance, or **performance** with higher power draw)

---

## ▶️ What Happens After Setting a Profile?

- Changes apply **immediately**
- ✅ **No reboot required**
- The profile persists until changed again (or overridden by the system)

---

## 🔍 List Available Profiles

```bash
powerprofilesctl list
```

Shows all profiles supported by your system.

---

## 🗑️ Reverting / Switching Profiles Anytime

```bash
powerprofilesctl set power-saver
powerprofilesctl set performance
```

---

## 🚫 When `powerprofilesctl` May Not Work

Common causes:
- `power-profiles-daemon` is **not installed** or **not running**
- **Unsupported hardware/firmware**
- Conflicts with other power managers (e.g., **TLP**)

---

## ⚠️ Important Notes

- Best suited for **laptops** and **mobile CPUs**
- Desktop systems may see **limited effect**
- Avoid running alongside other power tools unless you’ve configured them carefully

---

## ✅ Summary

| Command | Purpose |
|---|---|
| `powerprofilesctl get` | Show active power profile |
| `powerprofilesctl set balanced` | Set balanced power mode |
| `powerprofilesctl list` | Show supported profiles |
| `powerprofilesctl set power-saver` | Prioritize battery life |
| `powerprofilesctl set performance` | Prioritize maximum performance |

---

## 👉 Next: System Logs

- Move to **System log cmds**
- **[06.systemlogs](../06.systemlogs/README.MD)**
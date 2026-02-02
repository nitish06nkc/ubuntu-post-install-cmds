# 🛠️ System Update Basics

After installing Linux, these **3 commands** are the standard, safe workflow to keep your system updated:

1) ✅ **Update package lists**  
2) 🔎 **See what can be upgraded** *(optional but recommended)*  
3) ⬆️ **Install upgrades**

---

## 📝 Notes (read once)
- Run these commands **in the exact order shown**.
- If you use **PPAs / third‑party repos**, reviewing the upgrade list is **worth it**.
- After every Sudo cmd , a password is asked. Enter the password you set during the installation.
- `-y` = auto “yes” → convenient, but you may miss important prompts.
- After big upgrades, a **reboot** may be needed (kernel/libc updates).

---

## ⚡ Quick copy/paste (recommended order)

```bash
sudo apt update
apt list --upgradable
sudo apt upgrade
```

### 🧾 One-liner (WITH review)
```bash
sudo apt update && apt list --upgradable && sudo apt upgrade
```

### 🧾 One-liner (skip review)
```bash
sudo apt update && sudo apt upgrade
```

### 🤖 Non-interactive upgrade (auto “yes”)
```bash
sudo apt update && sudo apt -y upgrade
```

---

## 1) ✅ `sudo apt update`

### 🧠 Meaning of words (new ones)
- **sudo** → run command with administrator (**root**) privileges  
- **apt** → *Advanced Package Tool* (Ubuntu’s package manager)  
- **update** → refresh **package information** (not the packages themselves)

### 🔍 What this command does
- Downloads the latest **package lists** from configured repositories
- Checks whether newer versions exist for installed software
- **Does not install or upgrade anything**

### ✅ What happens after running it
- Your system now knows **which updates are available**
- This is typically **required before** running `apt upgrade`

### ⚠️ If you skip it
- Upgrades may be based on **outdated information**
- Updates can be missed
- Higher chance of dependency/version mismatch issues

---

## 2) 🔎 `apt list --upgradable`

### 🧠 Meaning of words (new ones)
- **list** → display package information  
- **--upgradable** → show only packages that have updates available

### 🔍 What this command does
- Shows a list of packages that **can be upgraded**
- **Does not change** the system

### ✅ What happens after running it
- You can **review updates** before installing them

### ℹ️ If you skip it
- You won’t see what’s pending
- The upgrade can still be safe on official repos, but you lose visibility

---

## 3) ⬆️ `sudo apt upgrade` or `sudo apt -y upgrade`

### 🧠 Meaning of words (new ones)
- **upgrade** → install available updates for already installed packages
- **-y** → automatically answer **“yes”** to prompts

### 🔍 What this command does
- Upgrades installed packages to their latest available versions
- Usually does **not** remove packages  
  *(for larger dependency changes you may need `full-upgrade`—separate topic)*

### ✅ What happens after running it
- System software is updated
- Security patches, bug fixes, and improvements are applied
- With `-y`, no user confirmation is required

### ⚠️ If you skip it
- You stay on older versions
- Security vulnerabilities may remain
- Fixes and stability/performance improvements are missed
---
## 👉 Next: System Cleanup

- Move to **System Cleanup Cmds**
- **[02.systemcleanup](../02.system_cleanup/README.MD)**

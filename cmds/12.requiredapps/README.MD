# 🧰 Basic Required Daily Apps Install (Ubuntu)

Essential applications for everyday Ubuntu desktop use — **media**, **office**, **GNOME extensions**, and **usability essentials**.

---

## 📌 Overview

After installing Ubuntu, some apps are almost universally needed for daily usage:

- 🎵 Music playback
- 🎬 Video/media playback
- 🧩 GNOME extensions (especially important on laptops)
- 📝 Documents & office work
- 🧑‍💻 A solid code editor (VS Code via official repo)

---

## 🎵 Music Player — Rhythmbox

**Install:**
```bash
sudo apt install rhythmbox
```

**Used for:**
- Playing local music
- Managing music libraries
- Basic podcast support

---

## 🎬 Media Player — VLC

**Install:**
```bash
sudo apt install vlc
```

**Why VLC:**
- Plays almost any audio/video format
- Independent of system codecs
- Reliable and lightweight

---

## 🧩 GNOME Extensions Manager

**Install:**
```bash
sudo apt install gnome-shell-extension-manager
```

This provides a **GUI** to safely install and manage GNOME Shell extensions.

---

## 🧠 MUST-HAVE GNOME EXTENSIONS (Highly Recommended)

After installing **Extension Manager**, open it and install the following:

### ✅ Touchpad Gestures (Laptop Users)

**Extension to install:**
- **X11 Gestures (Touchégg Integration)**

**📌 Why this matters**
- You already installed **Touchégg**
- This extension connects **Touchégg** with **GNOME**

**Enables:**
- **3-finger swipe** → switch workspaces
- **4-finger swipe** → window management

⚠️ Especially important for **X11 sessions** (common on many laptops).

---

### ✅ Clipboard History (**2M+ Downloads — MUST INSTALL**)

**Extension to install:**
- **Clipboard Indicator** *(by Tudmotu — from extensions.gnome.org)*

**📌 Why this extension is essential**
- GNOME has **no clipboard history** by default
- This is the most popular clipboard extension
- Used by **2M+ users worldwide**

**What it adds:**
- Clipboard history menu
- Multiple copied items
- Searchable clipboard entries
- Keyboard shortcuts
- Reliable, lightweight, battle-tested

➡️ **Recommendation:** Stick with **Clipboard Indicator (Tudmotu)** unless you have a specific reason to use another one.

---

## 📝 Office Suite — LibreOffice

**Install:**
```bash
sudo apt install libreoffice
```

**Provides:**
- **Writer** (Word replacement)
- **Calc** (Excel replacement)
- **Impress** (PowerPoint replacement)

Fully compatible with Microsoft Office formats.

---

## 🧑‍💻 Visual Studio Code (Official Microsoft Repository)

⚠️ VS Code should be installed via **Microsoft’s official repository**, not Ubuntu’s default repo.

### ✅ Install via Microsoft Repo (Recommended)

```bash
sudo apt install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo install -o root -g root -m 644 microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
sudo apt update
sudo apt install code
```

**Why this method:**
- Faster updates
- Official builds
- Better extension compatibility

---

## ❌ What This Section Does *NOT* Do

- No developer toolchains
- No heavy creative software
- No GNOME theming / ricing

✅ This section focuses on **daily usability first**.

---

## ✅ Recommended Installation Order

### 1) Install the core apps
```bash
sudo apt install rhythmbox
sudo apt install vlc
sudo apt install gnome-shell-extension-manager
sudo apt install libreoffice
```

### 2) Then install GNOME extensions (via Extension Manager)
- ✅ **X11 Gestures (Touchégg Integration)**
- ✅ **Clipboard Indicator (by Tudmotu)**

### 3) Install VS Code via Microsoft repo
Use the commands in the **VS Code** section above.

---

## 📌 Summary

| Component | Purpose |
|---|---|
| **Rhythmbox** | Music playback |
| **VLC** | Universal media player |
| **Extension Manager** | GNOME extension control |
| **Touchégg + X11 Gestures** | Laptop touchpad gestures |
| **Clipboard Indicator (Tudmotu)** | Clipboard history |
| **LibreOffice** | Office suite |
| **VS Code** | Code editor |

---
## 👉 Next: Cloudflare Warp

- Move to **Cloudflare Warp**
- **[13.cloudlfarewarp](../13.cloudlflarewarp/README.MD)**
# 🧰 Basic Required Daily Apps Install (Ubuntu)

Essential apps for everyday Ubuntu desktop use — **media**, **office**, **browsers**, **GNOME extensions**, and a **solid code editor**.

---

## 📌 Overview

After installing Ubuntu, these are the most common daily essentials:

- 🎵 **Music playback**
- 🎬 **Video/media playback**
- 🌐 **Web browsers** (Firefox / Brave)
- 🧩 **GNOME extensions** (extra useful on laptops)
- 📝 **Documents & office work**
- 🧑‍💻 **Code editor** (VS Code via Microsoft’s official repo)

This README includes **install** steps and **clean removal** steps for each item.

---

## 🧭 Table of Contents

- 🎵 Rhythmbox (Music)
- 🎬 VLC (Media)
- 🌐 Browsers: Firefox (APT) / Brave (Official repo)
- 🧩 GNOME Extension Manager
- 🧠 Must-have GNOME extensions
- 📝 LibreOffice
- 🧑‍💻 VS Code (Microsoft repo)
- ✅ Recommended install order
- 🧹 Full cleanup checklist
- 📌 Summary

---

## 🎵 Music Player — Rhythmbox

### ✅ Install
```bash
sudo apt install rhythmbox
```

**Used for**
- Playing local music
- Managing music libraries
- Basic podcast support

### ❌ Remove completely
```bash
sudo apt purge rhythmbox
sudo apt autoremove
sudo apt clean
```

---

## 🎬 Media Player — VLC

### ✅ Install
```bash
sudo apt install vlc
```

**Why VLC**
- Plays almost any audio/video format
- Works independently of many system codec issues
- Reliable + lightweight

### ❌ Remove completely
```bash
sudo apt purge vlc
sudo apt autoremove
sudo apt clean
```

---

## 🌐 Web Browsers

### 🦊 Firefox (APT version)

> Ubuntu may ship Firefox as a **Snap** by default. This installs the **APT** version.

#### ✅ Install
```bash
sudo apt install firefox
```

#### ❌ Remove completely
```bash
sudo apt purge firefox
sudo apt autoremove
sudo apt clean
```

**Optional user config cleanup**
```bash
rm -rf ~/.mozilla
```

---

### 🦁 Brave Browser (Official Repository) — Recommended

#### ✅ Install Brave
```bash
sudo apt install curl

sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg

sudo curl -fsSLo /etc/apt/sources.list.d/brave-browser-release.sources https://brave-browser-apt-release.s3.brave.com/brave-browser.sources

sudo apt update

sudo apt install brave-browser
```

**Why Brave**
- Privacy-focused
- Built-in ad & tracker blocking
- Chromium-based (Chrome extension support)

#### ❌ Remove Brave completely (including repo + key)
```bash
sudo apt purge brave-browser
sudo apt autoremove

sudo rm /etc/apt/sources.list.d/brave-browser-release.sources
sudo rm /usr/share/keyrings/brave-browser-archive-keyring.gpg

sudo apt update

```

**Optional user config cleanup**
```bash
rm -rf ~/.config/BraveSoftware
rm -rf ~/.cache/BraveSoftware
```

---

## 🧩 GNOME Extensions Manager

Provides a GUI to install and manage GNOME Shell extensions safely.

### ✅ Install
```bash
sudo apt install gnome-shell-extension-manager
```

### ❌ Remove completely
```bash
sudo apt purge gnome-shell-extension-manager
sudo apt autoremove
```

---

## 🧠 Must-have GNOME Extensions (Highly Recommended)

> Install these via **Extension Manager** (GUI).

### ✅ Touchpad Gestures (Laptop Users)
**Extension:** **X11 Gestures (Touchégg Integration)**

**Why it matters**
- Bridges Touchégg with GNOME
- Essential for **X11** sessions

**Enables**
- **3-finger swipe** → switch workspaces
- **4-finger swipe** → window management

---

### ✅ Clipboard History (2M+ downloads — MUST INSTALL)
**Extension:** **Clipboard Indicator** (by **Tudmotu**)

**Why it’s essential**
- GNOME has no clipboard history by default
- Widely used + trusted

**Adds**
- Clipboard history
- Searchable entries
- Keyboard shortcuts
- Lightweight & stable

---

## 📝 Office Suite — LibreOffice

### ✅ Install
```bash
sudo apt install libreoffice
```

**Provides**
- Writer
- Calc
- Impress  
…and strong compatibility with Microsoft Office formats.

### ❌ Remove completely
```bash
sudo apt purge libreoffice*
sudo apt autoremove
sudo apt clean
```

---

## 🧑‍💻 Visual Studio Code (Official Microsoft Repository)

⚠️ **Install only via Microsoft’s official repo.**

### ✅ Install
```bash
sudo apt install wget gpg

wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/microsoft.gpg > /dev/null

echo "deb [arch=amd64] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list

sudo apt update && sudo apt install code
```

### ❌ Remove VS Code completely (including repo + key)
```bash
sudo apt purge code
sudo apt autoremove
sudo rm /etc/apt/sources.list.d/vscode.list
sudo rm /etc/apt/trusted.gpg.d/microsoft.gpg
sudo apt update

```

**Optional user config cleanup**
```bash
rm -rf ~/.config/Code
rm -rf ~/.vscode
```

---

## ✅ Recommended Installation Order

### 1️⃣ Core apps
```bash
sudo apt install rhythmbox vlc libreoffice gnome-shell-extension-manager
```

### 2️⃣ Browsers
Pick one:
- 🦊 **Firefox (APT)**  
- 🦁 **Brave (official repo)**

### 3️⃣ GNOME extensions (GUI)
- **X11 Gestures (Touchégg Integration)**
- **Clipboard Indicator (Tudmotu)**

### 4️⃣ VS Code (Microsoft repo)

---

## 🧹 Full Cleanup Checklist (When needed)

```bash
sudo apt purge <package>
sudo apt autoremove
sudo apt clean

sudo rm /etc/apt/sources.list.d/<repo>.list
sudo rm /usr/share/keyrings/<key>.gpg
sudo rm /etc/apt/trusted.gpg.d/<key>.gpg

sudo apt update
```

---

## 📌 Summary

| Component | Purpose |
|---|---|
| Rhythmbox | Music playback |
| VLC | Universal media player |
| Firefox / Brave | Web browsing |
| Extension Manager | GNOME extensions |
| Touchégg + X11 Gestures | Laptop gestures |
| Clipboard Indicator | Clipboard history |
| LibreOffice | Office suite |
| VS Code | Code editor |

---

## 👉 Next: TLP

- Move to **TLP cmds**
- **[12.tlp](../13.tlp/README.MD)**




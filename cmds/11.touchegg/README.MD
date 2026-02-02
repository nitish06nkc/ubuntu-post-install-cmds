# 🖐️ Touchégg — Touchpad Gesture Support (Linux)

**Touchégg** is a background service that enables **multi-touch gestures** on touchpads (swipe, pinch, tap) and maps them to window/desktop actions.

Especially useful on laptops with modern multi-touch touchpads.

---

## 📌 Overview

Touchégg runs as a **daemon** and enables gesture detection **system-wide**. It can be used with desktop environments like **GNOME**, **KDE**, and **XFCE** (behavior may vary by DE).

---

## ➕ Add the Touchégg PPA (recommended)

```bash
sudo add-apt-repository ppa:touchegg/stable
```

### What this does
- Adds the official **Touchégg stable PPA**
- Makes newer versions available via **APT**

### Why this helps
- Ubuntu repos may ship **older versions**
- The PPA can provide **bug fixes** and improved gesture support

---

## 📥 Install Touchégg

```bash
sudo apt install touchegg
```

### What this does
- Installs the Touchégg service
- Registers it as a background daemon

### After installation
- Touchégg usually starts **automatically**
- No reboot is required

---

## ▶️ Check service status

```bash
systemctl status touchegg
```

### What to look for
You should see something like:

- **`Active: active (running)`**

---

## 🎯 What Touchégg is used for

Common examples (depends on your configuration/desktop):

- **Three-finger swipe** → switch workspaces
- **Four-finger swipe** → move windows
- **Pinch** → maximize / restore
- **Custom gesture mappings** (via configuration tools/files)

---

## ❌ What Touchégg is NOT

- Not a desktop environment replacement
- Not a keyboard shortcut manager
- Not for touchscreens
- Focused specifically on **touchpad gestures**

---

## 🚫 If Touchégg is not installed

- Gestures are limited or unavailable
- You may only have basic scrolling
- Advanced multi-touch features are missing

---

## ⚠️ Important notes

- Works best with **libinput**
- Requires a **multi-touch capable** touchpad
- Gesture behavior may depend on your desktop environment
- Can be customized using Touchégg config files or GUI tools

---

## 🗑️ Remove Touchégg

```bash
sudo apt remove touchegg
```

Remove the PPA:

```bash
sudo add-apt-repository --remove ppa:touchegg/stable
```

---

## ✅ Summary

| Step | Purpose |
|---|---|
| Add PPA | Get the latest stable Touchégg |
| Install | Enable touchpad gestures |
| Check status | Confirm the service is running |

---

## 📝 What’s next?

Now that we’ve covered most commands that can affect your PC (like **battery**, **RAM**, and **CPU** usage), we’ll move on to installing some **basic apps/software** that we use in daily life.

---

## 👉 Next: Required Apps

- Move to **Required Apps Cmds**
- **[12.requiredapps](../12.requiredapps/README.MD)**

# 🧹 Clean Up Your Linux System  
**Post‑Update & Upgrade Maintenance (Ubuntu)**


## 📌 Overview

After system updates/upgrades (and especially after uninstalling apps), Ubuntu may keep:

- **Unused dependency packages**
- **Downloaded package cache files** (`.deb`)

For safe, regular maintenance, these **two commands** are usually all you need.

---

## 1) 🔹 Remove Unused Dependencies — `autoremove`

### ✅ Command
```bash
sudo apt autoremove
```

### ✅ What this does
- Removes packages that were installed **automatically** and are **no longer required**
- Cleans up leftover dependencies from removed software
- Frees **disk space**

### ✅ What happens after execution
- **Orphaned packages** are removed
- System stays **lean** and easier to maintain

### ⚠️ If you skip it
- Unused dependencies **accumulate**
- Disk usage slowly **creeps up**

---

## 2) 🔹 Clear Package Cache — `clean`

### ✅ Command
```bash
sudo apt clean
```

### ✅ What this does
- Deletes **downloaded package cache files**
- Clears stored `.deb` packages from the local APT cache
- Reclaims **additional disk space**

### ✅ What happens after execution
- Cache is **fully cleared**
- No change to installed software

### ⚠️ If you skip it
- Old `.deb` files remain on disk
- Storage usage grows **unnecessarily** over time

---

## ✅ Recommended Usage (Copy/Paste)

```bash
sudo apt autoremove
sudo apt clean
```

**Tip:** Run this after big updates, or periodically to keep your system **clean, efficient, and lightweight**.

---

## 👉 Next: Preload Cmds

- Move to **Preload Cmds**
- **[03.preload](../03.preload/README.MD)**
# 🚀 Preload – Application Startup Optimizer

> **Improve App Launch Speed on Ubuntu**

---

## 📌 What is Preload?

**Preload** is a background service (daemon) that analyzes how you use applications over time and **preloads frequently used programs and libraries into RAM** before you launch them.

**Key Features:**
- 🎯 **Reduces application startup time**
- 📊 **Learns from your usage patterns**
- 🔄 **Works silently in the background**
- ⚡ **Becomes more effective over time**

---

## ✅ What Preload Is Good For

- ✨ **Faster launch** of frequently used applications
- 🖥️ **Improved responsiveness** on systems with:
  - 💾 HDDs (Hard Disk Drives)
  - 📀 Slower SATA SSDs
- 🛠️ **Lightweight optimization** with minimal user interaction

---

## ❌ What Preload Is NOT

| What It Doesn't Do | Why |
|-------------------|-----|
| 🚫 Speed up CPU/GPU performance | Only affects app loading |
| 🚫 Reduce boot time significantly | Works after boot |
| 🚫 Optimize disk writes | Read-only optimization |
| 🚫 Improve battery life | May increase RAM usage |

---

## 📥 Installation

### Install Preload

```bash
sudo apt install preload
```

**What happens during installation:**
- ✔️ Preload is installed as a system service
- ✔️ Automatically enabled and started
- ✔️ **No manual configuration required**

---

## ▶️ What Happens After Installation

1. 🔄 Preload starts running in the background
2. 👀 Monitors your application usage patterns
3. 💾 Frequently used binaries and libraries are cached in RAM
4. ⚡ App startup times improve gradually over days

> ⚠️ **Important:** Immediate speed gains are unlikely — Preload learns over time.

---

## 🔍 Verify Preload is Running

### Using systemctl

```bash
systemctl status preload
```

**Expected output:**
```
● preload.service
   Active: active (running)
```

### Using process check

```bash
ps aux | grep preload
```

---

## 📊 Resource Usage

| Resource | Impact |
|----------|--------|
| 🧠 **RAM** | Small amount (varies by usage) |
| ⚙️ **CPU** | Negligible |
| ✅ **Recommended** | Systems with 4GB+ RAM |

---

## 🚫 What If Preload Is NOT Installed?

- Applications load normally from disk each time
- ❌ No intelligent caching based on usage patterns
- 🐌 Startup times depend entirely on storage speed

---

## 🗑️ Uninstallation

### Remove Preload

```bash
sudo apt remove preload
```

### Complete removal (including config files)

```bash
sudo apt purge preload
```

**After removal:**
- ⛔ Preload stops running immediately
- 🧹 No background monitoring remains
- 🔙 System behavior returns to default

---

## ⚠️ Important Considerations

| Scenario | Recommendation |
|----------|----------------|
| 🚄 Fast NVMe SSDs | **Limited benefit** |
| 💾 Low RAM systems (<4GB) | **Not recommended** |
| 🖥️ HDD-based systems | **Highly recommended** |
| 📀 SATA SSD systems | **Moderate benefit** |

---

## 📋 Summary

| Feature | Status |
|---------|--------|
| 🔄 **Runs automatically** | ✅ Yes |
| 🧠 **Learns over time** | ✅ Yes |
| ⚙️ **Manual config needed** | ❌ No |
| 🗑️ **Safe to remove** | ✅ Yes |
| 💰 **Cost** | 🆓 Free |
| 📦 **Package name** | `preload` |

---

## 🎓 Pro Tips

- 💡 Give Preload at least **2-3 days** to learn your patterns
- 🔍 Monitor RAM usage if you have limited memory
- ⚡ Best results on **HDD-based systems**
- 🔄 Restart the service if needed: `sudo systemctl restart preload`

---

## 👉 Next: Zram Cmds

- Move to **Zram Cmds**
- **[04.zram](../04.zram/README.MD)**
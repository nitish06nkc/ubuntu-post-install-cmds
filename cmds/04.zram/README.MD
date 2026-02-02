# 🧠 ZRAM Compression (systemd-zram-generator)

**Improve memory efficiency** and **reduce swap latency** by using **compressed RAM** as swap.

---

## 📌 What is `systemd-zram-generator`?

`systemd-zram-generator` automatically creates **ZRAM-based swap** devices at boot via **systemd**.

✅ **ZRAM** stores swap pages in **compressed RAM instead of disk**, which typically means:
- **Much faster swapping** than disk swap
- **Less disk I/O** (useful for HDDs / slower SSDs)
- Better responsiveness under memory pressure

---

## 🎯 What It’s Good For

- ⚡ **Faster swap** compared to disk-based swap  
- 💾 **Reduced disk I/O** and wear  
- 🧩 **Better system responsiveness** when RAM is tight  

**Ideal for:**
- 🧳 Laptops
- 🧠 Low-RAM systems
- 🐢 Systems with HDDs or slower SSDs

---

## ❌ What It Is *Not*

- ❌ It does **not** increase physical RAM
- ❌ It does **not** replace the need for sufficient memory
- ❌ It does **not** directly improve CPU performance  
  (CPU is actually used a bit more due to compression)

---

## 📥 Install

```bash
sudo apt install systemd-zram-generator
```

**During installation:**
- ✅ The generator is installed
- ⏳ No swap is created immediately
- 🔁 ZRAM swap is configured **at next boot**

---

## ▶️ What Happens After Installation

After a reboot:
- systemd creates a **ZRAM device** (commonly `/dev/zram0`)
- the ZRAM device is used as **swap**
- swap data is stored **compressed in RAM**
- the system handles memory pressure more smoothly

⚠️ **Reboot required** for ZRAM to become active.

---

## 🔍 Verify ZRAM Is Working

### 1) Check swap devices
```bash
swapon --show
```

You should see something like:
- `/dev/zram0`

### 2) Check memory + swap usage
```bash
free -h
```

Look for a **zram-based** swap entry.

---

## 🧠 Resource Usage & Behavior

- Uses **compressed RAM** as swap
- Compression reduces the *effective* RAM consumed by swap pages
- ⚙️ Uses CPU for compression/decompression
- Usually **faster than disk-based swap**

---

## 🚫 If You Don’t Install It

- System uses **disk-based swap** (if configured)
- Slower swapping under memory pressure
- Increased disk I/O and latency

---

## 🗑️ Uninstall

Remove package:
```bash
sudo apt remove systemd-zram-generator
```

Remove package + config files:
```bash
sudo apt purge systemd-zram-generator
```

After removal:
- ZRAM swap is **no longer created** on boot
- Existing disk-based swap remains unchanged

---

## ⚠️ Important Notes

- 🔁 Requires reboot to take effect
- 📈 Slight CPU usage increase due to compression
- ✅ Generally safe for most systems
- 🤝 Works well **alongside disk swap** or **alone**

---

## ✅ Summary

| Feature | Behavior |
|---|---|
| Uses RAM as swap | ✅ Yes |
| Compression enabled | ✅ Yes |
| Requires reboot | ✅ Yes |
| Disk I/O reduced | ✅ Yes |
| Safe to remove | ✅ Yes |

---

## 👉 Next: Power Profiles

- Move to **Power Profile Cmds**
- **[05.powerprofile](../05.powerprofile/README.MD)**
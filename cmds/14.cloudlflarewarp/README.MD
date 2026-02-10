# 🔐 Cloudflare WARP (DNS + Secure Network Tunnel)

**Access restricted networks • Privacy • Safer Internet**


> ⚠️ **Important:** This Installation only works in **LTS versions**.
## 📌 Why Cloudflare WARP Is Needed

In many offices, colleges, hostels, and even home networks, administrators may:

- Block specific websites or services
- Apply **DNS-based** restrictions
- Monitor or filter internet traffic

Cloudflare WARP helps in such environments by:

- **Encrypting DNS queries**
- Preventing basic **DNS filtering**
- Making traffic harder to inspect or selectively block

It can also improve **privacy, security, and connection stability**, especially on public or restricted networks.

> ⚠️ **Important:** WARP helps against **DNS-level** and basic restrictions.  
> It does **not** bypass strict firewalls or authenticated networks.

---

## ✅ Installation & Setup (Step-by-step)

### 🔑 Step 1: Add Cloudflare GPG Key

```bash
curl -fsSL https://pkg.cloudflareclient.com/pubkey.gpg | sudo gpg --yes --dearmor --output /usr/share/keyrings/cloudflare-warp-archive-keyring.gpg
```

**Why this is required:**
- Verifies Cloudflare packages
- Prevents tampered or untrusted installs

---

### ➕ Step 2: Add Cloudflare Repository

```bash
echo "deb [signed-by=/usr/share/keyrings/cloudflare-warp-archive-keyring.gpg] https://pkg.cloudflareclient.com/ $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/cloudflare-client.list
```

**What this does:**
- Adds Cloudflare’s **official** package source
- Enables automatic updates via **APT**

---

### 📦 Step 3: Install Cloudflare WARP

```bash
sudo apt-get update
sudo apt-get install cloudflare-warp
```

After installation:
- `warp-cli` becomes available
- WARP is installed but **not active** yet

---

### 🧾 Step 4: Register Device (One-Time)

```bash
warp-cli registration new
```

**Why this is mandatory:**
- Registers your system with Cloudflare
- Generates a unique device identity
- Required before connecting

---

### 🔌 Step 5: Connect & Disconnect WARP

**Connect:**
```bash
warp-cli connect
```

- Enables encrypted DNS and secure tunnel
- Protection starts immediately

**Disconnect:**
```bash
warp-cli disconnect
```

- Restores normal network behavior

---

### 📊 Step 6: Check WARP Status

```bash
warp-cli status
```

Shows:
- Connection state
- Mode (connected / disconnected)
- Network status

---

### 🔁 Step 7: Always-On Mode (Recommended)

**Enable:**
```bash
warp-cli enable-always-on
```

- Automatically reconnects WARP
- Persists across reboots and network changes

**Disable:**
```bash
warp-cli disable-always-on
```

---

## 🎯 What Cloudflare WARP Is Good For

- Bypassing **DNS-based** blocks
- Safer browsing on **public Wi‑Fi**
- Preventing local network monitoring (basic/typical cases)
- Improving routing reliability

---

## ❌ What Cloudflare WARP Is NOT

- Not a full anonymity VPN
- Not a censorship bypass tool
- Not for geo‑unblocking content
- Not a Tor replacement

---

## 🗑️ Uninstall & Cleanup

```bash
sudo apt remove cloudflare-warp
sudo rm /etc/apt/sources.list.d/cloudflare-client.list
sudo rm /usr/share/keyrings/cloudflare-warp-archive-keyring.gpg
sudo apt autoremove
```

---

## 📚 All Commands (Future Reference)

```bash
# Add GPG key
curl -fsSL https://pkg.cloudflareclient.com/pubkey.gpg | sudo gpg --yes --dearmor --output /usr/share/keyrings/cloudflare-warp-archive-keyring.gpg

# Add repository
echo "deb [signed-by=/usr/share/keyrings/cloudflare-warp-archive-keyring.gpg] https://pkg.cloudflareclient.com/ $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/cloudflare-client.list

# Install
sudo apt-get update
sudo apt-get install cloudflare-warp

# Register
warp-cli registration new

# Connect / Disconnect
warp-cli connect
warp-cli disconnect

# Status
warp-cli status

# Always-on
warp-cli enable-always-on
warp-cli disable-always-on

# Remove
sudo apt remove cloudflare-warp
sudo apt autoremove
```


---

## ✅ Final Note

If you run all the commands above and complete the setup, your Ubuntu system should be **ready for long-term daily use** with fewer network/DNS-related issues.

If any command is outdated, incorrect, or no longer works, please **open a Pull Request** and mention what failed (Ubuntu version + error output).

If you have additional useful commands/improvements, feel free to **clone the repo** and open a **Pull Request** with your additions.



# 🙏 **Thanks**

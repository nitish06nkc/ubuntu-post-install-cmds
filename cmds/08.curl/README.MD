# 🌐 curl — Command-Line Data Transfer Tool

**curl** transfers data to/from servers using **URLs**. It supports multiple protocols (including **HTTP/HTTPS**, **FTP**, **SFTP**, and more) and is a core tool for **Linux**, **dev**, **ops**, and **automation** workflows.

---

## 📌 What is `curl`?

`curl` is used to:

- **Download files**
- **Call APIs**
- **Fetch scripts**
- **Test connectivity / inspect server responses**

> `curl` transfers **raw data** — it does **not** render pages like a browser.

---

## 📥 Install

```bash
sudo apt install curl
```

### What this does
- Installs the **curl** utility
- Makes the `curl` command available **system-wide**

### After installation
- You can fetch web content directly from the terminal
- Script-based installers that depend on `curl` start working
- API testing and quick debugging become easier

---

## ▶️ Quick start

Fetch a page:

```bash
curl https://example.com
```

Check version / supported protocols:

```bash
curl --version
```

---

## 🎯 Common uses (with examples)

### 1) Downloading files
Download and keep the remote filename (`-O`):

```bash
curl -O https://example.com/file.zip
```

### 2) Calling REST APIs
Simple GET request:

```bash
curl https://api.github.com
```

### 3) Installing software via scripts
Common pattern (fail fast, silent, follow redirects):

```bash
curl -fsSL https://example.com/install.sh | bash
```

> ⚠️ **Security tip:** Only pipe to `bash` if you **trust the source**. Consider reviewing first:
>
> ```bash
> curl -fsSL https://example.com/install.sh -o install.sh
> less install.sh
> bash install.sh
> ```

### 4) Debugging responses
Useful when troubleshooting network/server behavior (status codes, headers, etc.).

---

## ❌ What `curl` is NOT

- Not a **browser**
- Does not **render** web pages
- Not a full **download manager**
- Primarily for transferring **raw request/response data**

---

## 🚫 If `curl` is not installed

- Many install/setup guides will fail
- API testing from the terminal becomes difficult
- Script-based installers may not work
- Debugging network issues is harder
- Some tools assume `curl` is already present

---

## 🗑️ Uninstall

Remove package:

```bash
sudo apt remove curl
```

Remove package **and** configuration:

```bash
sudo apt purge curl
```

---

## ✅ Summary

| Feature | Behavior |
|---|---|
| Protocol support | Multiple |
| Script-friendly | Yes |
| Required by many tools | Yes |
| Safe to remove | Yes (but **not recommended**) |

---

## 👉 Next: Build Essential

- Move to **Build Essential Cmds**
- **[09.buildessential](../09.buildessential/README.MD)**
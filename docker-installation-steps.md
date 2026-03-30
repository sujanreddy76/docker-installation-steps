````md
# Docker Installation on Ubuntu

## 📌 Installation Steps

Go to the official Docker documentation:  
https://docs.docker.com/engine/install/ubuntu/

Search for: **Install using the apt repository**

Follow and execute commands under:

### 1. Set up Docker's apt repository

### 2. Install the Docker packages

---

## ✅ Docker Installation Complete

That's it — Docker will be installed successfully.

---

## ⚠️ Important Note (Permission Issue)

### 👉 Problem:

- Docker daemon runs as **root**
- Socket file: /var/run/docker.sock
```bash
/var/run/docker.sock
```
````

### 👉 Accessible only by:

* root
* docker group

---

## 🔧 Solution: Allow Non-root User Access

To allow another user (e.g., `siva`) to run Docker:

```bash
sudo usermod -aG docker siva
```

---

## 🔁 Apply Changes

```bash
su - siva
```

---

## 🔍 Verify

```bash
docker ps
```

✔ Should work without `sudo`

---

## 🧠 Why this works?

```text
siva → docker group → access docker.sock → talk to Docker daemon
```


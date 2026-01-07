# Ubuntu / WSL Complete Hackathon Development Setup

*January 4, 2026 • 3 min read*

## Ubuntu / WSL Complete Development Setup Guide

This document covers the complete setup of a development environment in Ubuntu (WSL), including Node.js (via NVM), npm, Python, and pip. It is based on the exact steps we followed and common issues we resolved.

---

## 1. Install Node.js inside WSL (Recommended)

### Update packages

```bash
sudo apt update
```

### Install Node.js (LTS)

```bash
sudo apt install -y nodejs npm
```

### Verify installation

```bash
node -v
npm -v
```

---

## 2. Installing Node.js 20 Using NVM (Best Practice)

We use **NVM (Node Version Manager)** because it allows easy switching between Node versions.

### Step 2.1: Install NVM

```bash
curl -fsSL https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

### Step 2.2: Reload Terminal

```bash
source ~/.bashrc
```

### Step 2.3: Verify NVM Installation

```bash
nvm --version
```

---

## 3. Install & Upgrade Node.js to Version 20

### Step 3.1: Install Node.js v20

```bash
nvm install 20
```

### Step 3.2: Use Node.js v20

```bash
nvm use 20
```

### Step 3.3: Set Node.js 20 as Default

```bash
nvm alias default 20
```

### Step 3.4: Verify Node & npm

```bash
node -v
npm -v
```

---

## 4. Installing Python, pip, and Virtual Environment

Ubuntu does not always come with Python and pip pre-installed.

### Step 4.1: Install Python & pip

```bash
sudo apt install -y python3 python3-pip python3-venv
```

### Step 4.2: Verify Python & pip

```bash
python3 --version
pip3 --version
```

### Step 4.3: Create virtual environment

```bash
python3 -m venv venv
```

### Step 4.4: Activate

```bash
source venv/bin/activate
```

When activated, you'll see `(venv)` at the start of your terminal prompt.

---

## 5. Enable `python` and `pip` Commands (Optional but Recommended)

By default, Ubuntu uses `python3` and `pip3`. To enable `python` and `pip`:

```bash
sudo apt install -y python-is-python3
```

### Verify

```bash
python --version
pip --version
```

---

## 6. Fixing Common Errors

### ❌ `command not found: node`

**Issue:** Node.js was not installed or NVM was not loaded

**Solution:**
```bash
source ~/.bashrc
nvm use 20
```

### ❌ `pip: command not found`

**Issue:** pip was not installed or only `pip3` exists

**Solution:**
```bash
sudo apt install python3-pip
sudo apt install python-is-python3
```

### ❌ `nvm: command not found`

**Issue:** NVM installation didn't update your shell profile

**Solution:**
```bash
# Add NVM to your bash profile manually
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.bashrc
echo '[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"' >> ~/.bashrc
source ~/.bashrc
```

---

## 7. Copy & Paste in Ubuntu Terminal

### Paste
- `Ctrl + Shift + V`
- Right-click → Paste

### Copy
- `Ctrl + Shift + C`

**Note:** In Windows Terminal (WSL), `Ctrl + V` also works for pasting.

---

## 8. Final Verification Checklist

Run these commands to confirm everything is set up correctly:

```bash
node -v
npm -v
nvm --version
python --version
pip --version
```

**If all commands return versions → ✅ Setup is complete!**

Expected output example:
```
v20.x.x
10.x.x
0.39.7
Python 3.12.x
pip 24.x.x
```

---

## 9. Recommended Tools

- **Windows Terminal** (Best for WSL)
- **VS Code + WSL Extension**
- **NVM** for Node version control
- **python-venv** for Python projects
- **Git** for version control

### Install Git (if not already installed)

```bash
sudo apt install git
git --version
```

### Configure Git

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

---

## 10. Quick Setup Script

If you want to run all commands at once, copy and paste this script:

```bash
#!/bin/bash

# Update system
sudo apt update

# Install Node.js
sudo apt install -y nodejs npm

# Install NVM
curl -fsSL https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

# Load NVM
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"

# Install Node 20
nvm install 20
nvm use 20
nvm alias default 20

# Install Python & pip
sudo apt install -y python3 python3-pip python3-venv python-is-python3

# Install Git
sudo apt install -y git

# Verify installations
echo "=== Verification ==="
node -v
npm -v
nvm --version
python --version
pip --version
git --version

echo "✅ Setup Complete!"
```

Save this as `setup.sh`, make it executable, and run:

```bash
chmod +x setup.sh
./setup.sh
```

---

## 11. Common Development Workflows

### Starting a Node.js Project

```bash
mkdir my-project
cd my-project
npm init -y
npm install express
```

### Starting a Python Project

```bash
mkdir my-python-project
cd my-python-project
python -m venv venv
source venv/bin/activate
pip install flask
```

### Starting a Next.js Project

```bash
npx create-next-app@latest my-nextjs-app
cd my-nextjs-app
npm run dev
```

### Starting a FastAPI Project

```bash
mkdir my-fastapi-app
cd my-fastapi-app
python -m venv venv
source venv/bin/activate
pip install fastapi uvicorn
```

---

## 12. Troubleshooting Tips

### NVM not working after restart

Add these lines to your `~/.bashrc`:

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

Then reload:
```bash
source ~/.bashrc
```

### Python packages not installing

Make sure you're in a virtual environment:

```bash
python -m venv venv
source venv/bin/activate
pip install package-name
```

### Permission errors with npm

Never use `sudo` with npm. If you get permission errors:

```bash
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
```

---

## ✅ Setup Completed Successfully

Your Ubuntu (WSL) environment is now fully ready for:

- ✅ Frontend (Next.js, React, Vue)
- ✅ Backend (FastAPI, Express, Node.js)
- ✅ Python development (Flask, Django, Data Science)
- ✅ npm & pip package management
- ✅ Git version control
- ✅ Hackathon-ready development environment

---

## 📚 Additional Resources

- [NVM Documentation](https://github.com/nvm-sh/nvm)
- [Node.js Official Docs](https://nodejs.org/docs/latest/api/)
- [Python Virtual Environments](https://docs.python.org/3/library/venv.html)
- [WSL Documentation](https://docs.microsoft.com/en-us/windows/wsl/)

---

**Happy Coding! 🚀**

---

*Last updated: January 4, 2026*

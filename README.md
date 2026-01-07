# Bash on Windows with WSL2 + Ubuntu

*January 3, 2026 • 3 min read*

## Complete Guide: Using Bash on Windows with WSL2 + Ubuntu (From Zero to Pro)

This guide explains how to set up a Linux Bash environment on Windows using WSL2 and Ubuntu, starting from zero and ending with a professional developer-ready setup. It also covers Python virtual environments for clean development.

---

## 1. What Is WSL?

**WSL (Windows Subsystem for Linux)** allows you to run a Linux environment directly on Windows without dual boot or virtual machines.

### Why WSL2?

- Real Linux kernel
- Native Bash shell
- Better performance
- Docker & AI-ready
- Industry standard for developers

---

## 2. Install WSL (1 Command)

Open **PowerShell** → **Run as Administrator**

Paste this command:

```bash
wsl --install
```

This will automatically:
- Enable WSL
- Install Ubuntu
- Set WSL 2

Wait a little → The PC will restart

### If Command Failed

If you see this error:

```
wsl --install
Downloading: Ubuntu
Installing: Ubuntu
WSL2 is not supported with your current machine configuration.
Please enable the "Virtual Machine Platform" optional component and ensure virtualization is enabled in the BIOS.
Enable "Virtual Machine Platform" by running: wsl.exe --install --no-distribution
For information please visit https://aka.ms/enablevirtualization
Error code: ...
```

Continue to the next step.

---

## 3. Enable Virtualization (BIOS)

### For HP Envy (Intel Core i7)

1. Shut down the laptop
2. Power on and immediately press **ESC**
3. Press **F10** to enter BIOS
4. Go to:
   ```
   System Configuration → Virtualization Technology
   ```
5. Set it to **Enabled**
6. Press **F10** → Save & Exit

✅ **Virtualization: Enabled**

---

## 4. Install WSL Core Components

Open **PowerShell as Administrator** and run:

```bash
wsl --install --no-distribution
```

**Restart your system** after this step.

---

## 5. Install Ubuntu on WSL

After restart, open **PowerShell (Admin)** and run:

```bash
wsl --install -d Ubuntu
```

Ubuntu will download and install automatically.

---

## 6. Ubuntu First-Time Setup

When Ubuntu opens:

- Create a **username**
- Create a **password** (input hidden)

You are now inside a Linux environment! 🎉

---

## 7. Verify Bash Installation

Run the following command inside Ubuntu:

```bash
bash --version
```

You should see output similar to:
```
GNU bash, version 5.x.x
```

---

## 8. Access Windows Files from Bash

Windows drives are mounted under `/mnt`:

```bash
cd /mnt/c
cd /mnt/c/Users/YourUsername/Desktop
```

This allows seamless Windows–Linux file sharing.

---

## 9. Basic Bash Commands (Must-Know)

These are the most important Bash commands every beginner should know when using Ubuntu on WSL.

### 1. `ls` – List Files and Folders

Shows all files and directories in the current location.

```bash
ls
ls -l      # detailed list
ls -a      # includes hidden files
```

### 2. `pwd` – Print Working Directory

Displays the full path of your current directory.

```bash
pwd
```

Example output:
```
/home/subhankaladi15
```

### 3. `cd` – Change Directory

Used to move between folders.

```bash
cd folder_name
```

Go back one level:
```bash
cd ..
```

Go to home directory:
```bash
cd ~
```

---

## 10. Beginner Practice Task

Try this mini exercise:

```bash
mkdir bash_practice
cd bash_practice
touch test.txt
echo "Bash is powerful" > test.txt
cat test.txt
pwd
ls
```

**Expected output:**
```
Bash is powerful
/home/yourusername/bash_practice
test.txt
```

---

## 🎯 What's Next?

Now that you have WSL2 + Ubuntu set up, you can:

- Install development tools (Git, Node.js, Python, etc.)
- Set up Python virtual environments
- Run Docker containers
- Start building projects in a real Linux environment

---

## 📚 Additional Resources

- [Official WSL Documentation](https://docs.microsoft.com/en-us/windows/wsl/)
- [Ubuntu on WSL](https://ubuntu.com/wsl)
- [Bash Scripting Guide](https://www.gnu.org/software/bash/manual/)

---

## 💡 Tips

- You can access Ubuntu by typing `wsl` or `ubuntu` in PowerShell
- Use `exit` to close the Ubuntu terminal
- Your Linux files are stored at: `\\wsl$\Ubuntu\home\yourusername`

---

**Happy Coding! 🚀**

---

*Last updated: January 3, 2026*

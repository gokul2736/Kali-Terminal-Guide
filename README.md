# Kali-Terminal-Guide
kali in windows-guide 


Don’t use WSL for low-level wireless attacks (monitor mode, packet injection), advanced hardware passthrough (USB Wi-Fi adapters), or kernel-module-level tools. For those, use a VM with USB passthrough (VirtualBox/VMware) or a live Kali USB / dual-boot.

🧠 Step-by-Step Guide to Install Kali Linux on Windows
1️⃣ Enable WSL and Virtualization

Run PowerShell as Administrator and execute:

wsl --install


This will automatically:

Enable WSL (Windows Subsystem for Linux)

Enable Virtual Machine Platform

Install Ubuntu by default (you can remove it later)

Install Windows Terminal

After it finishes, restart your computer.

2️⃣ Install Kali Linux

Once restarted, open Microsoft Store → search for “Kali Linux” → click Get → install it.

Or run this command directly in PowerShell:

wsl --install -d kali-linux


After installation, open Kali Linux from your Start menu — it will prompt you to:

Create a username

Set a password

You’ll then enter the full Kali shell.

3️⃣ Update & Upgrade Packages

Once inside Kali:

sudo apt update && sudo apt upgrade -y


Optional but recommended:

sudo apt install kali-linux-default -y


This installs all major Kali tools (Nmap, Metasploit, Burp Suite, etc.).

4️⃣ Set Kali as Your Default WSL Distro

Run in PowerShell:

wsl --setdefault kali-linux


Now, whenever you type wsl in the terminal, it will open Kali by default.

5️⃣ Use It Inside Windows Terminal (Highly Recommended)

If you don’t already have Windows Terminal:

winget install --id=Microsoft.WindowsTerminal -e


Then open it → click the dropdown arrow ▼ → you’ll see Kali Linux listed → click it.
You can also customize fonts, background, and add a hacker-style theme if you’d like.

6️⃣ (Optional) Install GUI Support

To run graphical Kali apps (like Burp, Wireshark, etc.):

sudo apt install kali-desktop-xfce -y
sudo apt install xrdp -y
sudo service xrdp start


Then connect via Remote Desktop (mstsc) using localhost:3389.

✅ You Now Have a Full Kali Linux on Windows

You can run:

nmap, hydra, sqlmap, msfconsole, burpsuite, aircrack-ng, etc.


Exactly as on a native Linux system.

# 🚀 Wi-Fi Security Checker (Linux)

<div align="center">

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![Linux](https://img.shields.io/badge/Platform-Linux-red?style=for-the-badge&logo=linux)
![Beginner Friendly](https://img.shields.io/badge/Level-Beginner-green?style=for-the-badge)
![Cyber Security](https://img.shields.io/badge/Category-CyberSecurity-black?style=for-the-badge)

### 📡 Beginner-Friendly Python Automation Project

Check your:
✅ Connected Wi-Fi  
✅ Signal Strength  
✅ Encryption Type  
✅ Basic Wi-Fi Security  

</div>

---

# 📖 About The Project

This project is a simple **Python automation tool** made for **Linux-based systems**.

The script uses Linux networking commands to:
- Detect connected Wi-Fi (SSID)
- Check signal strength
- Detect WPA2/WPA3 encryption
- Show basic Wi-Fi security status

This project is perfect for:
- Python beginners
- Cybersecurity students
- Linux learners
- Networking practice

---

# 🐍 Python Code

```python
import subprocess

print("=" * 50)
print("      Wi-Fi Security Checker")
print("=" * 50)

try:
    ssid = subprocess.check_output(
        "iwgetid -r", shell=True
    ).decode().strip()

    signal = subprocess.check_output(
        "iwconfig 2>/dev/null | grep 'Signal level'",
        shell=True
    ).decode()

    encryption = subprocess.check_output(
        "nmcli -t -f active,ssid,security dev wifi | egrep '^yes'",
        shell=True
    ).decode()

    print(f"\nConnected Wi-Fi : {ssid}")

    print("\nEncryption Details:")
    print(encryption)

    print("\nSignal Information:")
    print(signal)

    print("\nSecurity Status:")

    if "WPA2" in encryption:
        print("[+] WPA2 detected")
    elif "WPA3" in encryption:
        print("[+] WPA3 detected")
    else:
        print("[!] Weak or Unknown Encryption")

except Exception as e:
    print(f"Error: {e}")
```

---

# ⚙️ How It Works

The script uses Python's:

```python
import subprocess
```

module to run Linux terminal commands.

---

# 🔥 What is `subprocess`?

`subprocess` allows Python to:
- Run Linux commands
- Run Windows CMD commands
- Capture command output
- Automate terminal tasks

Example:

```python
subprocess.check_output("ls", shell=True)
```

Python runs:

```bash
ls
```

and captures the result.

---

# 🔍 What is `check_output()`?

```python
subprocess.check_output()
```

This function:
1. Executes a command
2. Captures the output
3. Returns the result to Python

Example:

```python
subprocess.check_output("whoami", shell=True)
```

---

# 🖥 Linux Commands Used

| Command | Purpose |
|---|---|
| `iwgetid -r` | Get connected Wi-Fi name |
| `iwconfig` | Get signal information |
| `nmcli` | Get Wi-Fi encryption details |

---

# 📦 Requirements

Install required packages:

```bash
sudo apt install wireless-tools network-manager
```

---

# ▶️ Run The Script

```bash
python3 wifi_checker.py
```

---

# 📌 Example Output

```text
==================================================
      Wi-Fi Security Checker
==================================================

Connected Wi-Fi : JioFiber

Encryption Details:
yes:JioFiber:WPA2

Signal Information:
Signal level=-40 dBm

Security Status:
[+] WPA2 detected
```

---

# 📚 Concepts Used

✅ Python Automation  
✅ subprocess Module  
✅ Linux Networking Commands  
✅ Exception Handling  
✅ Wi-Fi Enumeration  
✅ Basic Cybersecurity Scripting  

---

# 🚀 Upcoming Updates

Planned future updates:

- ✅ Windows Support
- ✅ Cross-Platform Support
- ✅ Automatic OS Detection
- ✅ Better Terminal UI
- ✅ Colored Output
- ✅ More Wi-Fi Details
- ✅ MAC Address Detection
- ✅ IP Address Detection

---

# 🌐 Future Cross-Platform Support

Upcoming versions will support:

| Operating System | Status |
|---|---|
| Linux | ✅ Current |
| Windows | 🔜 Upcoming |
| Both (Auto Detect) | 🔜 Upcoming |

using Python's:

```python
import platform
```

module.

---

# 🧠 What You Can Learn From This Project

This beginner project helps you learn:
- Python basics
- Automation scripting
- Linux commands
- Networking basics
- Cybersecurity fundamentals
- Exception handling
- subprocess module

---

# ⚠️ Disclaimer

This project is created only for:
- Educational purposes
- Learning automation
- Cybersecurity practice
- Networking practice

Do not misuse this tool.

---

# ⭐ Beginner Cybersecurity Project

If you are learning:
- Python
- Linux
- Networking
- Cybersecurity

then this is a great beginner project to practice automation scripting.

---

<div align="center">

## 💻 Happy Learning & Happy Hacking 🚀

</div>
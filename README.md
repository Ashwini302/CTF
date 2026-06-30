# CTF
# 🔐 Ashwini K CTF Machine

Custom Linux-based Capture The Flag (CTF) appliance developed for cybersecurity training, penetration testing practice, and vulnerability assessment exercises.

---

## 📌 Overview

This project presents a vulnerable Ubuntu Server environment designed to simulate realistic penetration testing scenarios.

Participants are expected to perform:

* Network Reconnaissance
* Service Enumeration
* Web Application Analysis
* Hidden Directory Discovery
* Credential Extraction
* Steganography Analysis
* SSH Authentication
* Privilege Escalation
* Flag Capture

The machine is intended for educational purposes and provides a complete end-to-end CTF experience.

---

# 🎯 Objectives

The objective of this project is to architect, configure, and deploy a custom Linux-based Capture The Flag machine capable of testing multiple cybersecurity concepts, including:

* Network Enumeration
* Web Security Assessment
* Hidden Content Discovery
* Source Code Analysis
* Credential Recovery
* Steganography
* Local Privilege Escalation
* Capture The Flag Methodology

---

# 🖥 Environment Specifications

| Component        | Configuration           |
| ---------------- | ----------------------- |
| Operating System | Ubuntu Server 24.04 LTS |
| Hypervisor       | VirtualBox / VMware     |
| RAM              | 2 GB                    |
| CPU              | 2 vCPUs                 |
| Storage          | 25 GB Dynamic Disk      |
| Graphics         | VMSVGA                  |
| Network Mode     | Host-Only Adapter       |
| Subnet           | 192.168.56.0/24         |

---

# 👥 User Accounts

| Username        | UID  | Shell     |
| --------------- | ---- | --------- |
| ashwini_sec     | 1001 | /bin/bash |
| dev_portal      | 1002 | /bin/bash |
| sys_maintenance | 1003 | /bin/bash |

---

# 🔥 Services and Firewall Configuration

Only essential services are exposed to participants.

### Allowed Services

| Port | Service |
| ---- | ------- |
| 22   | SSH     |
| 80   | HTTP    |

### UFW Rules

```bash
ufw --force reset

ufw default deny incoming
ufw default allow outgoing

ufw allow 22/tcp
ufw allow 80/tcp

ufw --force enable
```

---

# 🌐 Web Challenge Components

The target hosts a portfolio-style website containing embedded clues and hidden artifacts.

### Interesting Files

```text
robots.txt

/assets/css/main.css

/restricted_backup_node/
```

Participants are encouraged to inspect these resources during enumeration.

---

# 🕵️ Steganography Challenge

An image file contains embedded data that can be extracted during the challenge.

### File Location

```text
/home/ashwini_sec/Desktop/desktop_wallpaper.png
```

### Extraction Utility

```bash
steghide extract -sf desktop_wallpaper.png
```

---

# 🚩 Flags

### User Flag

```text
/home/ashwini_sec/user.txt
```

### Root Flag

```text
/root/root.txt
```

---

# ⚔ Suggested Walkthrough

## Step 1 — Reconnaissance

```bash
nmap -sC -sV <Target-IP>
```

---

## Step 2 — Enumeration

```bash
enum4linux <Target-IP>
```

Inspect:

* robots.txt
* HTML source code
* CSS files
* backup directories
* hidden assets

---

## Step 3 — Credential Discovery

Identify:

* usernames
* encoded strings
* passphrases
* hidden comments
* backup files

---

## Step 4 — Initial Access

```bash
ssh username@target-ip
```

---

## Step 5 — Steganography

```bash
steghide extract -sf desktop_wallpaper.png
```

---

## Step 6 — Privilege Escalation

Suggested enumeration:

```bash
sudo -l

find / -perm -4000 2>/dev/null

linpeas.sh
```

Retrieve the final administrative flag.

---

# 📥 Download

The complete virtual appliance, supporting files, and documentation can be downloaded using the link below.

> **Google Drive Link:**
> https://drive.google.com/file/d/1eCxLelweQ4qONnQtWA33TxjYALXHfwCh/view?usp=drive_link

Contents include:

* Virtual Machine Appliance
* Web Source Files
* Documentation Report
* Supporting Resources

---

# 📂 Repository Structure

```text
ashwini-k-ctf-appliance/

├── README.md

├── Documentation/
│   └── CTF_Development_Report.pdf

└── Google_Drive_Link.txt
```

---

# 🚀 Deployment

### VirtualBox

1. Download the appliance package.
2. Extract the archive.
3. Import the VM.
4. Configure networking as **Host-Only Adapter**.
5. Start the machine.

### VMware

1. Download the VM package.
2. Open the virtual machine.
3. Configure networking.
4. Boot the appliance.
5. Begin the challenge.

---

# 🎓 Learning Outcomes

This project demonstrates practical understanding of:

* Linux Administration
* Virtualization
* Web Security
* Enumeration Techniques
* Steganography
* Firewall Configuration
* SSH Services
* Privilege Escalation
* Offensive Security Methodologies
* CTF Machine Development

---

# 👨‍💻 Author

**Ashwini K**

Cybersecurity Enthusiast • CTF Developer

SRN: R25DE018

---

# ⚠ Disclaimer

This environment is intended strictly for educational purposes, laboratory exercises, and ethical security research.

Do not deploy intentionally vulnerable systems in production environments.

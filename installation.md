# Installation Guide

This document outlines the installation and setup process for the Help Desk Tier 1 emulation lab using EVE-NG Community Edition on a Windows 11 host with VMware Workstation.

## Host Environment

- **Host OS:** Windows 11 Pro  
- **Virtualization:** VMware Workstation  
- **EVE-NG version:** Community Edition  

---

## Step 1 — Download and Deploy EVE-NG

**[Setup]**  
- Download the EVE-NG Community OVA:  
  [https://www.eve-ng.net/index.php/download/](https://www.eve-ng.net/index.php/download/)  
- In VMware Workstation:  
  - Go to `File > Open`, select the OVA file.  
  - Import the VM and assign a name.  
  - Adjust VM resources:
    - CPU: 2 or more cores  
    - RAM: 4 to 8 GB  
    - Disk: Minimum 40 GB  
    - Network: Bridged (for direct LAN access)  
- Boot the virtual machine.

---

## Step 2 — Network Configuration

**[Setup]**  
- Log into the VM console:  
  - **Username:** `root`  
  - **Password:** `eve`  
- Identify the VM’s IP address:  
ip a

---

## Step 3 — Web GUI Access Issue: Nginx and Apache Conflict

**[Warning]**  
The web GUI did not load because Nginx was installed and occupied the required ports (80/443), causing a conflict with Apache2, which EVE-NG uses by default.

**[Resolution]**  
- Remove Nginx:  
apt remove nginx


- Ensure Apache2 is installed and running:  
apt install apache2
systemctl restart apache2

- Access the GUI:  
https://<EVE-NG-IP>


**[Success]**  
Web GUI displayed correctly.

---

## Step 4 — Web GUI Login Issue

**[Warning]**  
Initial login attempts failed after resolving the web server issue.

**[Attempts]**  
- Changed the root password:  
passwd

- Attempted to reset EVE-NG admin password via CLI (unsuccessful for GUI login)

**[Resolution]**  
- Consulted official documentation:  
[https://www.eve-ng.net/index.php/documentation/faq/](https://www.eve-ng.net/index.php/documentation/faq/)  
- Determined correct default credentials:  
admin / eve

- Logged into the web GUI successfully.

**[Success]**  
Login confirmed with default credentials.

---

## Step 5 — Uploading Lab Images

**[Setup]**  
- Downloaded images from official sources:
- [pfSense](https://www.pfsense.org/download/)
- [TinyCore Linux](http://tinycorelinux.net/)
- [Ubuntu Server](https://ubuntu.com/download/server)
- Uploaded images via WinSCP or `scp` to:
/opt/unetlab/addons/qemu/<image-folder>/


_(Folder names followed EVE-NG naming conventions, e.g., `vyos-1.3`)_
- Fixed permissions:
/opt/unetlab/wrappers/unl_wrapper -a fixpermissions

**[Success]**  
Uploaded images appeared in the node list in the EVE-NG web GUI.

---

## Notes

- EVE-NG deployed on VMware Workstation with bridged networking to provide LAN IP access.  
- Encountered and resolved web server conflict (Nginx vs. Apache2).  
- Default GUI login credentials: `admin / eve`  
- Initial images uploaded: pfSense, TinyCore Linux, Ubuntu Server.

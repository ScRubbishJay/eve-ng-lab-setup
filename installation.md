# Installation Guide for EVE-NG Community Edition on Windows 11 (VMware Workstation)

This document details the step-by-step installation and initial setup process for the EVE-NG Community Edition (CE) virtual machine on a Windows 11 host using VMware Workstation.

---

## Prerequisites

- Windows 11 Pro or higher  
- VMware Workstation installed  
- Stable internet connection for downloads  
- Minimum hardware requirements:  
  - CPU: 2+ cores  
  - RAM: 8 GB recommended  
  - Disk space: 40+ GB free

---

## Step 1 — Download EVE-NG CE OVA

- Go to [EVE-NG Downloads](https://www.eve-ng.net/index.php/download/)  
- Download the **Community Edition OVA** file.

---

## Step 2 — Import OVA into VMware Workstation

- Open VMware Workstation  
- Select `File > Open`  
- Browse to and select the downloaded OVA file  
- Follow prompts to import the VM  
- Name the VM (e.g., `EVE-NG-CE`)  
- Adjust VM settings:  
  - CPUs: 2 or more  
  - Memory: 8 GB recommended  
  - Network Adapter: Set to **Bridged** for LAN access  
- Finish the import process

---

## Step 3 — Power On and Initial Access

- Start the EVE-NG VM  
- Access the console window in VMware  
- Login with:  
  - **Username:** `root`  
  - **Password:** `eve`

---

## Step 4 — Identify EVE-NG IP Address

- At the root prompt, run:  
ip a


- Locate the IP address assigned to the bridged interface (likely `eth0` or similar)  
- Note this IP for web GUI access

---

## Step 5 — Web GUI Access Troubleshooting: Nginx vs Apache Conflict

- If the web GUI does not load at `https://<EVE-NG-IP>`, check for web server conflicts:  
- EVE-NG uses Apache2 by default  
- Nginx may be installed and occupy ports 80/443, causing conflicts

- To resolve:  
apt remove nginx
systemctl restart apache2


- After restarting Apache2, retry accessing the web GUI.

---

## Step 6 — Logging into the Web GUI

- Default web GUI credentials:  
- **Username:** `admin`  
- **Password:** `eve`

- If login fails:  
- Attempt to reset root password via console:  
  ```
  passwd
  ```
- Confirm you are using the `admin/eve` user for the GUI (not `root`).

---

## Step 7 — Next Steps After Login

- Once logged in, familiarize yourself with the interface  
- Proceed to upload images (see `image_upload.md`)  
- Create and run basic lab topologies

---

## Notes

- Ensure VM time is synchronized with host to avoid authentication issues  
- Run the following to fix permissions after uploading images:  
/opt/unetlab/wrappers/unl_wrapper -a fixpermissions


- Keep the VM updated with `apt update && apt upgrade` periodically.

---

## Summary

This guide covers the basics to get your EVE-NG environment running on Windows 11 with VMware Workstation

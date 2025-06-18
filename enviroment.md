# EVE-NG Lab Environment Setup (Shared for NOC + Help Desk)

This document covers full environment setup instructions for your EVE-NG labs in VMware Workstation, including installation, image preparation, network configuration, and troubleshooting. It serves as a single source of truth for building and maintaining your lab environment.

---

## 1. Prerequisites

- Windows 10 or 11 host machine
- VMware Workstation (or VMware Player)
- EVE-NG Community ISO (latest stable version)
- Internet access for downloads
- WinSCP (or another SFTP client)
- PuTTY (or another SSH client)

---

## 2. VMware Workstation: Create the EVE-NG VM

1. Open VMware Workstation and create a **New Virtual Machine**.
2. Select **Typical (recommended)**.
3. Choose **Installer disc image file (ISO)** and browse to your EVE-NG Community ISO.
4. Set guest OS type: **Linux > Ubuntu 64-bit**.
5. Name the VM (example: EVE-NG-LAB).
6. Set disk size: at least 20 GB (expandable if needed).
7. Finish the wizard and power on the VM.

---

## 3. EVE-NG Installation (Inside VM)

1. Follow the EVE-NG install prompts to complete setup.
2. When prompted, set passwords for `root` and the GUI admin.
3. Choose static IP or DHCP for EVE-NG.
4. After install completes, log in at the VM console:
   - Username: root
   - Password: the password you set

---

## 4. Network Configuration

- In VMware Workstation, set the VM’s network adapter:
  - **Bridged** (recommended for direct LAN access)
  - **NAT** (if you need to share host’s IP)

- Inside EVE-NG:
  - Verify IP address:
    ```
    ip a
    ```
  - Make sure the IP is reachable from your host.

- Access the GUI:
https://<EVE-NG-IP>

---

## 5. Importing Images

### Prepare your images
You will need to gather the following:
- pfSense (latest community ISO or QCOW2)
- TinyCore Linux (optional lightweight client)
- Windows 10 trial (or Ubuntu client if preferred)
- Zabbix appliance (or install on Ubuntu)
- Graylog appliance (or install on Ubuntu)
- OTRS (can install on Ubuntu or Docker)

### Upload the images
1. Open WinSCP and connect to EVE-NG:
Host: <EVE-NG-IP>
User: root
Password: <your password>
Protocol: SCP
2. Navigate to:
/opt/unetlab/addons/qemu/
4. Create a folder for each image (example: `pfsense-2.6.0`, `ubuntu-20.04`).
5. Upload the correct QCOW2 or image files into each folder.
6. After all uploads:
/opt/unetlab/wrappers/unl_wrapper -a fixpermissions

---

## 6. Adding Nodes in EVE-NG

1. In the web GUI, create a new lab.
2. Add nodes:
- Select the image name you uploaded.
- Set interfaces (default or custom as needed).
3. Connect nodes via virtual links.
4. Save the lab.

---

## 7. Common Troubleshooting

### Cannot access EVE-NG web GUI
- Check IP address: `ip a`
- Make sure the VM is on the right network mode (bridged/NAT)
- Check for host port conflicts (Apache2/Nginx running on host)
- Verify browser is using HTTPS and correct port

### Default login fails
- Double-check the password you set during install
- Reset root password at VM console:
passwd root


- Confirm you’re not using a changed password for initial setup login

### Images not showing in GUI
- Verify folder names match EVE-NG naming rules
- Confirm QCOW2 filenames are correct
- Make sure you ran `fixpermissions` after upload

### Nodes have no connectivity
- Verify interface assignments in node config
- Check virtual link connections in EVE-NG
- Confirm VM network (bridged/NAT) allows traffic
- Test host firewall for blocked traffic

---

## 8. Notes

- This setup is shared across all NOC and Help Desk labs.
- Snapshots of working environments are recommended for rollback.
- Document each lab’s topology and config as you build it.

---

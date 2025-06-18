# Image Upload and Management Guide for EVE-NG

This document explains how to add and manage virtual machine images in your EVE-NG Community Edition environment. Images are required to build lab topologies with various operating systems and network devices.

---

## Supported Image Types

- Virtual Machines (Linux distros like Ubuntu Server, TinyCore Linux, pfSense firewall, etc.)  
- Router and switch images (if applicable in future labs)  

---

## Step 1 — Prepare Images

- Download official or community-supported images in supported formats (QCOW2, VMDK, ISO)  
- Recommended images for Help Desk Tier 1 labs:  
  - Ubuntu Server (for server role)  
  - TinyCore Linux (lightweight client VM)  
  - pfSense (firewall/router VM)

---

## Step 2 — Upload Images to EVE-NG

You have two options:

### Option A — Using WinSCP (Windows)

1. Download and install [WinSCP](https://winscp.net)  
2. Connect to your EVE-NG VM using SCP protocol:  
   - Hostname: `<EVE-NG IP>`  
   - Username: `root`  
   - Password: `eve`  
3. Navigate to the image directory:  
/opt/unetlab/addons/qemu/
4. Upload the prepared image folder here (e.g., `ubuntu-server-20.04`)  
5. After upload, you may need to extract or rename images according to EVE-NG naming conventions.

---

### Option B — Using EVE-NG Web GUI

- Some images may be uploaded directly through the EVE-NG web interface (if enabled)  
- This method is less common for large images and advanced users prefer SCP.

---

## Step 3 — Fix Permissions

- After uploading or modifying images, run this command via SSH or console to fix permissions:  
/opt/unetlab/wrappers/unl_wrapper -a fixpermissions

---

## Step 4 — Validate Images

- Restart the EVE-NG VM or relevant services if necessary  
- Confirm images appear in the EVE-NG web GUI under “Add a Node” when building labs

---

## Tips

- Keep image names simple and consistent for easier management  
- Use official sources to avoid corrupted or incompatible images  
- Back up your `/opt/unetlab/addons/` directory regularly  

---

## Summary

Properly uploading and managing images in EVE-NG is critical to building functional labs. This guide pro

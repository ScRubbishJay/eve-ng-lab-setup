# EVE-NG Environment Setup and Configuration Tips

This document covers additional environment setup steps and tips after the base EVE-NG installation and image uploads.

---

## 1. Network Configuration

- Ensure the EVE-NG VM network adapter is set to **Bridged** mode for LAN access  
- Confirm the VM receives an IP address on your local network  
- Use this IP to access the web GUI and SSH if needed

---

## 2. Time Synchronization

- Time mismatch between host and VM can cause authentication or certificate issues  
- Sync time using:  
timedatectl set-ntp true


- Alternatively, enable VMware Tools (if installed) to sync time with host

---

## 3. User Management

- Default users:  
- CLI: `root` / `eve`  
- Web GUI: `admin` / `eve`  
- Change passwords immediately after first login using:  
passwd

- Consider adding additional users if multiple people will access the environment

---

## 4. Updating EVE-NG

- Regularly update the system to get security patches and bug fixes:  
apt update && apt upgrade -y

- Reboot the VM after major updates

---

## 5. Permissions and Ownership

- If you manually upload files or images via SCP, always fix permissions with:  
/opt/unetlab/wrappers/unl_wrapper -a fixpermissions


- This prevents issues when launching nodes or labs

---

## 6. Backup and Restore

- Backup important files regularly, especially:  
- `/opt/unetlab/labs/` (lab configurations)  
- `/opt/unetlab/addons/` (uploaded images)  
- Use standard Linux backup tools like `tar` or `rsync`

---

## 7. Common Troubleshooting Commands

- Check web server status:  
systemctl status apache2


- Restart services if needed:  
systemctl restart apache2


- Check network interfaces:  
ip a

- Check disk space:  
df -h


---

## Summary

This guide provides essential post-installation setup tips to maintain and operate your EVE-NG environment smoothly.

# Troubleshooting Common Issues in EVE-NG Setup

This document covers frequent problems encountered during installation and initial configuration of EVE-NG Community Edition and how to resolve them.

---

## 1. Web GUI Not Loading

**Symptom:** Cannot access `https://<EVE-NG-IP>` or get connection refused.

**Cause:** Port conflict between Apache2 and Nginx web servers.

**Solution:**  
- Check if Nginx is installed and running:  
systemctl status nginx

- If active, remove Nginx:  
apt remove nginx -y

- Restart Apache2:  
systemctl restart apache2

---

## 2. Web GUI Login Failure

**Symptom:** Default web credentials do not allow login.

**Clarification:**  
- According to official EVE-NG Community Edition documentation and support, the **default web GUI login** credentials are:  
  - **Username:** `admin`  
  - **Password:** `eve`  
- These credentials are different from the CLI `root` user credentials.

**Possible Causes:**  
- Using incorrect credentials (e.g., `root` username or other password).  
- Time synchronization issues affecting authentication.

**Resolution:**  
- Ensure you are using the correct web GUI credentials: `admin` / `eve`.  
- If you need to reset the web admin password, SSH into the VM and run:  

---

## 3. Permission Issues After Image Upload

**Symptom:** Uploaded images or nodes fail to start or give permission errors.

**Solution:**  
- Run:  
/opt/unetlab/wrappers/unl_wrapper -a fixpermissions


- Verify ownership and permissions of image folders.

---

## 4. Network Issues

**Symptom:** Cannot access EVE-NG VM from host or other machines.

**Check:**  
- VM network adapter set to **Bridged** mode.  
- Correct IP address assigned (use `ip a` to verify).  
- Firewall rules on host or network blocking traffic.

---

## 5. Disk Space Problems

**Symptom:** Labs fail to start or save changes.

**Check:**  
- Available disk space:  
df -h


- Clean up old snapshots or unused images.

---

## 6. VM Performance Issues

**Symptom:** Lab nodes run slowly or freeze.

**Recommendations:**  
- Allocate more CPU cores and RAM in VMware settings.  
- Close unnecessary applications on host machine.  
- Use lightweight images where possible (e.g., TinyCore Linux).

---

## Summary

This guide addresses common setup issues to help maintain a stable EVE-NG environment for your Help Des

# NOC Lab Installation Guide

## Purpose
This document describes the installation of the base environment to build and run NOC Tier 1 and Tier 2 labs using EVE-NG on VMware Workstation with the selected free/open-source tools.

## Prerequisites
- VMware Workstation installed on Windows 11 host  
- EVE-NG Community Edition VM deployed and running  
- Internet access for downloading VM images  
- Basic familiarity with VM management and Linux CLI  

## Installation Steps

1. **Deploy EVE-NG VM**  
   - Import the EVE-NG OVA file into VMware Workstation.  
   - Assign at least 4 CPUs, 8GB RAM, 100GB disk.  
   - Ensure bridged or NAT network is set for internet access.  

2. **Access EVE-NG Web UI**  
   - Open browser and navigate to EVE-NG IP address (e.g., https://[EVE-NG-IP])  
   - Login with default credentials (admin / eve) — verify with [EVE-NG official docs](https://www.eve-ng.net/documentation)  

3. **Prepare VM Images**  
   - Download required images:  
     - pfSense (Firewall / Router)  
     - Ubuntu Server (for Graylog, OTRS, general services)  
     - Zabbix (can be installed on Ubuntu VM)  
   - Upload images to EVE-NG via SCP or Web UI `/opt/unetlab/addons/qemu/` directory  
   - Convert images to compatible formats if needed (qcow2, etc.)  
   - Set proper permissions (chmod -R 755 on image folders)  

4. **Verify VM Images in EVE-NG**  
   - Create test lab topology and deploy VMs  
   - Power on VMs and verify boot success  

5. **Initial VM Configuration**  
   - pfSense: assign WAN/LAN interfaces, set DHCP or static IPs  
   - Ubuntu: install updates (`sudo apt update && sudo apt upgrade`)  
   - Install Graylog and OTRS on Ubuntu per their official guides  

6. **Set Up Networking and Monitoring**  
   - Configure pfSense firewall and routing rules  
   - Set up Zabbix server and agents on Ubuntu and other VMs  
   - Configure Graylog to collect syslog data from pfSense and other devices  
   - Configure OTRS for ticket management (optional but recommended)  

---

## Notes  
- Keep a snapshot of your EVE-NG VM before major changes for rollback.  
- Follow official docs for each tool for advanced configuration.  
- Refer to troubleshooting guide for common issues during setup.  

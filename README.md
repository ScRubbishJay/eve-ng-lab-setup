# EVE-NG Lab Setup for Help Desk and NOC Tier 1 & 2 Skills

## Overview

This repository contains detailed lab setups and configurations for practicing common Help Desk and Network Operations Center (NOC) Tier 1 and Tier 2 tasks using EVE-NG running on VMware Workstation.

The goal is to provide a realistic, hands-on environment to develop troubleshooting, configuration, and monitoring skills relevant to IT support and network operations roles.

---

## Repository Structure

- **helpdesk/**  
  Contains labs focused on common Help Desk Tier 1 & Tier 2 issues, primarily Windows and Ubuntu client/server troubleshooting.

- **noc/**  
  Contains labs for NOC Tier 1 & Tier 2 tasks, including network monitoring, firewall configuration, log management, and ticketing system emulation.

- **docs/**  
  General documentation related to environment setup, troubleshooting guides, and image installation.

---

## Lab Environment

- **Base Platform:**  
  EVE-NG Community or Professional Edition running inside VMware Workstation on Windows 11 host.

- **Help Desk Labs Tech Stack:**  
  - Windows 10 client (evaluation images)  
  - Windows Server (evaluation images)  
  - Ubuntu Server/Desktop (free, open source)

- **NOC Labs Tech Stack:**  
  - pfSense firewall/router  
  - Zabbix network monitoring server  
  - Graylog centralized log management  
  - OTRS ticketing system  
  - Ubuntu Server/Desktop (support VMs)

---

## Getting Started

### 1. Setup VMware Workstation and Import EVE-NG VM

Follow the installation guides in the respective folders to import and configure your EVE-NG VM, network settings, and access the EVE-NG web GUI.

### 2. Download and Prepare VM Images

Download evaluation ISOs for Windows and Windows Server, and official Ubuntu images. For NOC labs, download pfSense, Zabbix, Graylog, and OTRS images or prepare VMs accordingly.

### 3. Upload and Register Images in EVE-NG

Use SCP or WinSCP to upload images to EVE-NG and configure proper permissions.

### 4. Build Lab Topologies

Create lab projects in EVE-NG following the project outlines in `helpdesk/projects.md` and `noc/projects.md`.

### 5. Practice Troubleshooting

Use the troubleshooting guides for Help Desk and NOC labs in their respective folders to simulate and resolve common issues.

---

## Documentation

- `helpdesk/installation.md` — Help Desk environment installation and setup  
- `helpdesk/images.md` — Importing Help Desk VM images  
- `helpdesk/troubleshooting.md` — Help Desk troubleshooting workflows  
- `helpdesk/projects.md` — Help Desk lab projects outline  

- `noc/installation.md` — NOC environment installation and setup  
- `noc/images.md` — Importing NOC VM images  
- `noc/troubleshooting.md` — NOC troubleshooting workflows  
- `noc/projects.md` — NOC lab projects outline  

---

## Contributing

Feel free to submit issues or pull requests if you have suggestions or improvements.

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## Contact

For questions or support, reach out via GitHub Issues or contact [your email/contact info].





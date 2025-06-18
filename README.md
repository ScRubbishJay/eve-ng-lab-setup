# EVE-NG Lab Setup for Help Desk and NOC Simulation  
This repository documents the environment and lab projects for simulating Help Desk Tier 1 & 2 and NOC Tier 1 & 2 scenarios using EVE-NG on VMware Workstation. All components use free, open-source, or trial software.

---

## Tech Stack Used

| Component | Purpose | Tool |
|------------|---------|------|
| Firewall / Router | Routing, VPN, firewall | pfSense |
| Monitoring | Network/server monitoring | Zabbix (Ubuntu) |
| Syslog | Log aggregation | Graylog (Ubuntu) |
| Ticketing | Issue tracking | OTRS (Ubuntu) |
| User Client | End-user simulation | Windows 10 trial OR Ubuntu Desktop |
| Server | AD, file services | Windows Server eval (optional) |
| Utility | General servers | Ubuntu Server |

---

## Lab Categories & Projects

### Help Desk Tier 1 Projects
1️⃣ **Basic Network Connectivity**  
- Ping, tracert, nslookup usage  
- Resolve DNS misconfigurations  
- Fix gateway/DHCP issues  

2️⃣ **File Share Access & Permissions**  
- NTFS vs Share permission conflicts  
- Map drives, troubleshoot denied access  

3️⃣ **User Account Issues**  
- Password resets, unlock accounts  
- Group membership corrections  

4️⃣ **Printer Troubleshooting**  
- Clear queues  
- Restart spooler  
- Driver reinstall  

---

### Help Desk Tier 2 Projects
1️⃣ **Group Policy & Login Scripts**  
- Simulate GPO not applying  
- Troubleshoot with gpresult / rsop.msc  

2️⃣ **BitLocker Recovery**  
- Trigger recovery key prompt  
- Retrieve/apply recovery key  

3️⃣ **VPN/RDP Failures**  
- Simulate credential and port issues  
- Resolve pfSense VPN config  

4️⃣ **Application Crashes / Installs**  
- Simulate blocked installs  
- Analyze logs, resolve with reinstall  

---

### NOC Tier 1 Projects
1️⃣ **Zabbix Ping & Interface Monitoring**  
- Detect ping loss  
- Identify down interfaces  

2️⃣ **Basic Syslog Analysis**  
- Ingest pfSense logs to Graylog  
- Search for interface down/sys events  

3️⃣ **Simple Ticket Logging**  
- Enter tickets in OTRS  
- Assign/resolved basic alerts  

4️⃣ **VPN Tunnel Monitoring**  
- Alert on tunnel down  
- Verify pfSense status  

---

### NOC Tier 2 Projects
1️⃣ **Zabbix Custom Triggers**  
- CPU, RAM thresholds  
- Custom item monitoring  

2️⃣ **Complex Syslog Patterns**  
- Detect repeated failures / brute force  
- Alert on log patterns  

3️⃣ **Advanced Ticket Workflows**  
- Simulate escalation and ticket handoff  

4️⃣ **Multi-site Link Failure Handling**  
- Simulate routing failover  
- Verify Zabbix/Graylog alerting  

---

## Directory Structure

/eve-ng-lab-setup/
├── README.md
├── /helpdesk/
│ ├── tier1/
│ └── tier2/
├── /noc/
│ ├── tier1/
│ └── tier2/
└── /screenshots/


---

## How To Use This Repo

✅ Clone the repo  

git clone https://github.com/ScRubbishJay/eve-ng-lab-setup.git


✅ Follow instructions inside each project folder  

✅ Document: screenshots, configs, commands  

✅ Push updates  

git add .
git commit -m "Added lab results"
git push

---

## Notes  
- Windows 10 trial = 90-180 days  
- Windows Server eval = 180 days  
- Ubuntu Desktop = free alternative  
- All tools: open source / trial suitable for labs  





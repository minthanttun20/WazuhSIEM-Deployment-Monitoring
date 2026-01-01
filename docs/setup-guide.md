# Setup & Configuration Guide

## 1. Environment Topology

1. Manager: Ubuntu 24.04 (IP: 10.0.2.8)
2. Endpoint: Windows 10 (IP: 10.0.2.15)
3. Network: VirtualBox NAT Network

## 2. Installation

```
curl -sO https://packages.wazuh.com/4.9/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```
* After installation, must save User,Password and URL
----

## 3. Server start
1. Check verification status
```
sudo systemctl status wazuh-manager
```
2. To Start
```
sudo systemctl start wazuh-manager
```
4. To Stop
```
sudo systemctl stop wazuh-manager
```
6. To Restart
```
sudo systemctl restart wazuh-manager
```
7. This will show you a live scrolling list of everything the Wazuh server is doing.
```
sudo tail -f /var/ossec/logs/ossec.log
```

## Deploy a new agent
1. In the Wazuh dashboard, go to endpoint summary and click Deploy new agent.
2. Select your laptop's OS (e.g., Windows).
   Enter the VM's IP address.
   It will generate a single command. **Copy and paste** that command into your laptop's **PowerShell (Admin)**.
3. Verify: After a minute, your laptop will show as "Active" in the Wazuh dashboard.

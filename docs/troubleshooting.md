# Troubleshooting & Issue Resolution

During the deployment, I encountered and resolved several critical issues:

## 1. "Health Check 3000" / API Axios Error

Issue: The Wazuh Dashboard could not fetch the authorization token, resulting in a blank UI.

    Fix: Restarted the core services on the Ubuntu Manager to refresh the API connection: sudo systemctl restart wazuh-manager sudo systemctl restart wazuh-dashboard

## 2. FIM Alerts Not Triggering (Baseline Scan)

Issue: New files in C:\Wazuh-Test didn't show up immediately.

    Reason: Wazuh requires the initial "Baseline Scan" to finish before real-time alerts are sent.

    Resolution: Monitored ossec.log until the line syscheck: INFO: Ending syscheck scan appeared before testing.

## 3. Windows Firewall Blocks

Issue: Manager could not ping the Agent.

    Fix: Added an ICMPv4 allow rule in Windows Advanced Firewall to enable network visibility.

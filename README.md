# Wazuh SIEM Lab (Ubuntu)

## Overview
This project demonstrates the deployment and validation of a Security Information and Event Management (SIEM) solution using **Wazuh** on an Ubuntu Linux server. The lab focuses on log ingestion, security monitoring, and basic alert triage in a realistic environment.

## Environment
- Ubuntu Server (Virtual Machine)
- Wazuh all-in-one deployment (Manager, Indexer, Dashboard)
- VirtualBox with NAT networking and port forwarding
- SSH enabled for log generation and testing

## What I Did
- Deployed Wazuh using the official all-in-one installer
- Verified service health for the Wazuh manager, indexer, and dashboard
- Configured secure dashboard access from the host system
- Generated authentication-related security events through failed SSH login attempts
- Reviewed and analyzed alerts in the Wazuh dashboard

## Validation
To confirm the SIEM was functioning correctly, multiple failed SSH authentication attempts were generated on the server. These events were successfully ingested, parsed, and displayed as security alerts, confirming end-to-end visibility and detection.

## Alert Triage Example

**Alert:** SSH authentication failure / brute-force attempt  
**Severity:** Medium  

**Why it matters:**  
Repeated failed authentication attempts may indicate unauthorized access or credential guessing against the system.

**Initial triage steps:**  
- Review source IP address and frequency of attempts  
- Determine whether the activity is local, internal, or external  
- Check whether the targeted username exists on the system  

**Response:**  
In a production environment, repeated failures from an external source would be blocked or rate-limited and escalated if the activity continued.

## Skills Demonstrated
- SIEM deployment and validation
- Linux system administration
- Security event monitoring and alert analysis
- Basic incident triage and response reasoning
- Troubleshooting services and network access

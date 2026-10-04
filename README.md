# Mini-SOC-Lab

## Overview

This project is a hands-on SOC lab for learning security monitoring, log analysis, threat detection and incident response using the tools Wazuh, Sysmon, Windows and Linux

## Objectives

- Learn how SOC environments work
- Learn how to analyze security logs
- Monitor the endpoint activity in Windows
- Detect any suspicious behaviour
- Investigate the security alerts
- Perform basic threat hunting
- Map activity to MITRE ATT&CK
- Document incident investigations

## Planned Technologies
- Windows
- Linux
- Kali Linux
- Wazuh
- Sysmon
- MITRE ATT&CK
- GitHub

## Project Status

## Day 1 - Lab setup

## Host Machine
- Macbook with Apple silicon M1
- 16 GB RAM
- Oracle VirtualBox 7.2.4
- UTM

## Virtual Machines 
| Machine | Role | Platform | Status |
| SOC-KALI | Attacker | VirtualBox | Working✅|
| SOC-WAZUH | SIEM and Monitoring | UTM | Working✅|
| SOC-WINDOWS | Victim | VirtualBox | Planned⏳|

### SOC-WAZUH Configuration
- Operating System: Ubuntu 24.04 LTS
- Architecture: ARM64
- Virtualization: UTM
- Memory: 6GB
- CPU: 4 cores
- Storage 50GB

### Day 1 Objectives
- [x] VirtualBox installed
- [x] Github repo created
- [x] README created
- [x] Kali Linux VM created
- [x] Kali Linux tested
- [x] Ubuntu 24.04 ARM64 installed
- [x] Ubuntu networking tested
- [x] Ubuntu updated
- [ ] Windows VM - YET TO COMPLETE
- [ ] Lab network configuration - YET TO COMPLETE
- [ ] Wazuh installation - YET TO COMPLETE
- [ ] Sysmon installation - YET TO COMPLETE
- [ ] Windows endpoint connected to Wazuh - YET TO COMPLETE


## Day 2 - Wazuh Installation and Dashboard Setup

### Objective

The objective for day 2 was to install wazuh as the central security monitoring platform for my SOC lab, today my main goal was to successfully install and access the dashboard.

### What I did

- updated the Ubuntu environment
- Installed the tool curl into Ubuntu so that it could communicate with websites and servers
-  Downloaded the Wazuh installation assistant
-  Installed Wazuh using an all-in-one deployment including Wazuh Manager, Wazuh Indexer and Wazuh Dashboard
-  Configured the Wazuh Manager, Indexer and Dashboard
-  After Installation using the Web Address given to me by Wazuh I accessed the Wazuh Dashboard through Firefox
-  Encountered a certificate trust issues where Wazuh created its own certificate for its Dashboard
-  Successfully configured Firefox to trust the Wazuh Root Certificate Authority

### Troubleshooting: Wazuh Dashboard Certificate 
when I first attempted to access the Wazuh Dashboard, Firefox displayed the error:

'SEC_ERROR_UNKNOWN_ISSUER'

Firefox did not trust the certificate being used by the Wazuh Dashboard

I then decided to take a closer look at the certificate and later confirmed that the certificate was issued by Wazuh itself and was associated with the Wazuh dashboard.

I then located the Wazuh Root CA certificate:

'/etc/wazuh-dashboard/certs/root-ca.pem'

I then copied the certificate to my Ubuntu home directory and imported it into Firefox'

I selected:

**Trust this CA to identify websites**

After reloading the Wazuh Dashboard, Firefox trusted the certificate and the dashboard opened successfully.

### What I Learned 

This process of troubleshooting helped me understand how HTTPS certificates and Certificate Authorities work. I also gained experience in identifying certificate trust problems, investigating its cause and implementing a solution to fix the problem.

### Day 2 Status

- [x] Wazuh installed
- [x] wazuh Dashboard configured
- [x] Certificate issue investigated
- [x] Certificate trust issue resolved
- [x] Dashboard successfully accessed






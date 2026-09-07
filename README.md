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




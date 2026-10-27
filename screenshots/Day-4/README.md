Day 4 - Sysmon Integration and Event Verification

### Objective

The aim of day 4 was to install Sysmon on my Windows 11 endpoint, configure the Wazuh agent to collect its logs, and verify that the test command that I ran was received by Wazuh.

### What I Did

#### 1. Checked the Windows connection

I opened the Wazuh dashboard and confirmed that WIN-SOC-ENDPOINT showed as active. This showed me that the Wazuh agent on Windows was communicating successfully with the Wazuh server on ubuntu.

#### 2. Downloaded and installed Sysmon

I downloaded Sysmon64a.exe from Microsoft's official Sysinternals page as that is the version that needs to be downloaded for my Windows ARM64 Virtual machine and then I extracted it. I then in administrator PowerShell navigated to the extracted folder and installed Sysmon:

'''powershell .\Sysmon64a.exe -I'''



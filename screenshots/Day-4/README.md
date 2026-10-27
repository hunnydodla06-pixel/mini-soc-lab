Day 4 - Sysmon Integration and Event Verification

### Objective

The aim of day 4 was to install Sysmon on my Windows 11 endpoint, configure the Wazuh agent to collect its logs, and verify that the test command that I ran was received by Wazuh.

### What I Did

#### 1. Checked the Windows connection

I opened the Wazuh dashboard and confirmed that WIN-SOC-ENDPOINT showed as active. This showed me that the Wazuh agent on Windows was communicating successfully with the Wazuh server on ubuntu.

#### 2. Downloaded and installed Sysmon

I downloaded Sysmon64a.exe from Microsoft's official Sysinternals page as that is the version that needs to be downloaded for my Windows ARM64 Virtual machine and then I extracted it. I then in administrator PowerShell navigated to the extracted folder and installed Sysmon:

powershell .\Sysmon64a.exe -i

I also learned that folder paths containing spaces need quotation marks so PowerShell treats the whole path as one address.

#### 3. checked Sysmon was recording locally

I opened Event Viewer on my windows virtual machine to check that Sysmon was recording all the activity on Windows. I then found Event ID 1, which is a Sysmon entry that showed me that Sysmon was generating logs locally before I configured Wazuh to collect them.

#### 4. Backed up the Wazuh Configuration

Before I began editing the agent configuration, I created a backup so that the original configuration is preserved so it could be restored if needed.

#### 5. Configured Sysmon Log Collection

I edited the Wazuh agent configuration file, ossec.conf, to tell the agent where to find Sysmon's logs on Windows. This allowed the agent to collect the activity recorded by Sysmon and then send it to Wazuh server for further analysis. After saving the changes, I attempted to restart the agent so that the updated settings could load.

#### 6. Investigated the Wazuh Agent Issue

After I updated the configuration, I found that the Wazuh agent would not stay running. I checked the service status and reviewed the agent logs. I then looked for any error messages to help identify what was preventing the agent from running. I realized that the issue was a typo in the configuration file from when I edited it. I had accidentally typed "eventvhannel" instead of "event channel" which wazuh could not interpret correctly. I then corrected the spelling and saved the new file.

#### 7. Confirmed Agent was Working Again

I then started the Wazuh agent again and made sure that its service stayed running. I also checked the Wazuh dashboard, where WIN-SOC-ENDPOINT showed as Active. This confirmed that the agent was communicating with the server again.

#### 8. Ran a Test Command

I ran an 'echo' command that displayed the text MINI-SOC-DAY4-TEST.when I ran this command it started a process that Sysmon could record. The unique text made the activity very easy to find in Wazuh.

#### 9. Verified the Test Event in Wazuh

I searched for MINI-SOC-DAY4-TEST in Wazuh's Threat Hunting section and opened the matching event. I checked that it showed the command I ran and my Windows agent, WIN-SOC-ENDPOINT. I also found that the event came from Sysmon and had Event ID 1, meaning a program had started. This confirmed that Sysmon was recording activity on my Windows VM and that Wazuh was receiving those logs.










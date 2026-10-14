# Day 3 - Connecting Windows 11 to Wazuh

## Objective
The aim of Day 3 was to connect my Widows 11 virtual machine to the Wazuh server running on Ubuntu.
This allows Wazuh to monitor security activity on Windows.

## Lab setup 

| Component | Software |
|---|---|
| Wazuh Server | Ubuntu 24.04 ARM64 |
| Wazuh Version | 4.14.8 |
| Windows endpoint | Windows 11 ARM64 |
| Virtualization | UTM |
| Agent Name | WIN-SOC-ENDPOINT |
| Connection Status | Active |

## What I Did 

### 1. Checked Windows 11
I firstly started my windows 11 virtual machine and confirmed that it was running correctly and there were no obvious system errors present.

### 2. Tested Network Connectivity

I checked the IP addresses of my virtual machines and then used the 'ping' command to test whether the connection was successful between Windows and Ubuntu. 

The test was successful, which meant that both the virtual machines could communicate over the network.

### 3. Installed the Wazuh Agent

I downloaded and then installed the Wazuh Windows agent package compatible with my windows 11 endpoint. I configured the agent to communicate with the Wazuh Manager on Ubuntu and made the agents name **WIN-SOC-ENDPOINT**. This will allow the agent to collect configured endpoint information and send it back to the Wazuh server on ubuntu to be analyzed.

### 4. Troubleshooting - Agent initially Not Active 

After installing Wazuh I checked the Wazuh Dashboard and the Windows agent was not showing up as active.

To investigate, I:

- Rechecked network connectivity between Windows and Ubuntu.
- Reviewed the Wazuh agent logs for connection-related errors.
- Checked the Windows Wazuh agent service ('WazuhSvc') and confirmed that it was running.

After these checks, I checked the dashboard again and then confirmed that the agent was active. However I cannot confirm the initial cause of the initial connection issue.



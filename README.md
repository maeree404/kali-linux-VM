# Kali Server VM — Linux & SOC Foundations

## Project Overview
I built an isolated Kali Server virtual machine to practise Linux administration, network troubleshooting, and basic system-log investigation.

## Objectives
- Configure and boot a Linux virtual machine.
- Identify operating-system and kernel information.
- Inspect network interfaces, IP addresses, and routing.
- Test network connectivity and DNS resolution.
- Identify listening TCP/UDP ports.
- Review system logs and understand their relevance to security monitoring.

## Tools & Environment
- **Host OS:** Windows
- **Virtualisation:** Oracle VirtualBox
- **Guest OS:** Kali 2026.3
- **Allocated resources:** RAM- 2 GB, CPU cores- 2, virtual disk size- 25 GB
- **Networking:** NAT 

## Implementation
1. Created the virtual machine and configured its resources.
2. Installed Ubuntu Server and confirmed that it booted successfully.
3. Identified the operating system and kernel.
4. Inspected network interfaces and the routing table.
5. Tested DNS resolution and IP connectivity.
6. Checked listening ports and reviewed recent system logs.

## Validation 

| Test | Command | 

| OS identification | `cat /etc/os-release` `uname -a` `hostname` `id` `uptime`
| Running Processes |  `lsblk` `free -h` `df -h`
| Network interfaces & Routing | `ip addr` `ip route` `ping -c 4 1.1.1.1` `ping -c 4 kali.org` `ip -s link`
| DNS resolution | `getent hosts kali.org` 
| Listening ports | `ss -tuln` 
| System logs | `journalctl -n 30 --no-pager` 

## Security Considerations
- Used official software sources.
- Kept the VM's network configuration documented.
- Avoided exposing credentials or sensitive host-network information.

## Key Learnings

### 1. Linux System Identification
Learned how to identify the operating system, kernel version, current user, and system uptime using Linux commands. This information helps establish the environment during an investigation.

### 2. Network Configuration and Troubleshooting
Learned how to inspect network interfaces, IP addresses, routing tables, and DNS resolution using `ip addr`, `ip route`, and `getent hosts`. These commands help troubleshoot connectivity issues and understand a system's network configuration.

### 3. Processes and System Resources
Used `ps aux`, `top`, `free -h`, and `df -h` to inspect running processes, memory usage, and disk space. These checks provide a baseline for identifying unusual resource consumption.

### 4. Listening Ports and Services
Used `ss -tuln` to identify listening TCP and UDP sockets. Learned that a listening port is not automatically malicious; its purpose and expected exposure must be investigated.

### 5. System Logs and Event Investigation
Used `journalctl` to review system events and filter log entries. Learned that logs provide context for troubleshooting and security investigations, although available events depend on the services and logging configuration.

### 6. Virtualisation and Lab Isolation
Configured Kali Linux inside VirtualBox and explored its virtual hardware and networking settings. Learned how virtual machines provide a separate environment for security practice and why network configuration matters when isolating lab activity.

### 7. Relevance to SOC Analysis
Developed familiarity with foundational Linux commands used to establish system context, troubleshoot network issues, inspect processes, and review logs. These skills provide a foundation for future endpoint investigations and SIEM-based analysis.

## Evidence
See the `screenshots/` directory for configuration, command output, and validation evidence.

## Conclusion
This project establishes basic Linux and virtualisation skills. 

## CYBERSECURITY LAB  ENVIRONMENT SETUP

Creating a Kali Linux Lab for penetration testing and ethical hacking

![VirtualBox](https://img.shields.io/badge/VirtualBox-v7.2-blue)
![Kali Linux](https://img.shields.io/badge/Kali_Linux-v2026.2-blue)
![Networking](https://img.shields.io/badge/Network-10.0.0.0%2F24-blue)
![Penetration Testing](https://img.shields.io/badge/Penetration_Testing-Ethical_Hacking-green)
![Virtualization](https://img.shields.io/badge/Skill-Virtualization-blue)
![Linux](https://img.shields.io/badge/Skill-Linux-blue)
![GitHub](https://img.shields.io/badge/GitHub-Repository-black)
## project overview
This project involves building a basic cybersecurity practice environment using Oracle VirtualBox and Kali Linux. The setup provides a safe and controlled platform for learning and practicing cybersecurity and penetration-testing techniques.
Kali Linux is used as the main security workstation for performing activities such as network scanning, reconnaissance, and security testing. The virtual lab uses a private network configuration to keep the practice environment separated from the host network and to support the addition of other virtual machines for future testing.
### Key Benefits

<ul>
  <li>🖥️ <strong>VirtualBox + Kali Linux Setup</strong></li>
  <li>🔐 <strong>Safe Cybersecurity Practice</strong></li>
  <li>🌐 <strong>Network Scanning and Reconnaissance</strong></li>
  <li>🛡️ <strong>Penetration Testing Practice</strong></li>
  <li>📚 <strong>Learning Networking and Security Tools</strong></li>
  <li>🚀 <strong>Future Addition of Virtual Machines</strong></li>
</ul>

## Objectives
The main objectives of this project are to:

- Set up Oracle VirtualBox for the cybersecurity laboratory.
- Install and configure Kali Linux as a virtual security workstation.
- Create a controlled environment for cybersecurity practice.
- Configure and verify the required virtual network settings.
- Test the basic functionality and connectivity of the Kali Linux VM.
- Explore essential Kali Linux commands and security tools.
- Practice basic network discovery and reconnaissance in an authorized environment.
- Document the complete lab setup for future reference.
- Prepare the lab for future cybersecurity exercises and additional virtual machines.
  ## Tools used
  
| Tool | purpose|
|---|---|
|VirtualBox Manager|Created and configured the virtual machine|
|Kali Linux Terminal|Executed networking and system configuration commands|
|ifconfig / ip command|Checked and configured the network interface|
|ping|Tested connectivity between systems and gateway|
|ip route|Verified and configured the default gateway|
|NetworkManager|Managed network interface and connection settings|
|GitHub|Documented and stored the project configuration and procedures|
## Configuration Of Network

| Parameter | Value | Description |
|---|---|---|
| **NAT Network** | `NAT network` | Dedicated VirtualBox network for the lab |
| **IPv4 Subnet** | `10.0.0.0/24` | Private network range used by the lab |
| **NAT Gateway** | `10.0.0.1` | Gateway providing network access |
| **Kali Workstation IP** | `10.0.0.2` | Static address assigned to the Kali VM |
| **Interface** | `eth0` | Network interface used by Kali Linux |
| **Address Assignment** | Static | Manual IP configuration |
| **Subnet Mask** | `255.255.255.0` | Defines the `/24` network |
| **DNS Server** | `8.8.8.8` | Used for domain-name resolution |
## Steps to implement the kali linux lab
### step 1.Install 7-zip
To extract the kali Linux VM package install the 7-zip file.
### step 2.Install Virtual Box and Kali linux
virtual box was installed to run the Kali Linux in Virtual Machine.It was a hyperveisor.
## Screenshot
![Kali Linux]()
### step 3.VB NAT Network Configuration
A dedicated VB NAT Network was created with the configuration.

**Configuration:**

**Network Name: NAT Network**

**IPv4 Prefix:10.0.0.0/24**

**DHCP:Enabled**

**IPv6:Disabled**
## Screenshot
![NAT Network Settings](https://github.com/pavithrap99/Cyber-security-week-1-project-/blob/de90b9bec4169e425a9e1ab9bd72356278b28141/02_Nat%20network-settings.png)

### Step 4.IP Address Assignment
The Kali Linux network was configured with a static IP address
```bash
# Assign static IP address to eth0 interface
sudo ip addr add 10.0.0.2/24 dev eth0
#Activate the network interface
sudo ip link set eth0 up
```
### verification
```base
#confirm IP assignment
ip addr show eth0
```
### Result:IP address 10.0.0.2/24 confirmed on interface etho
## screenshot
![IP Address](https://github.com/pavithrap99/Cyber-security-week-1-project-/blob/d8ab08c06fd35020674169b03d50d3b0c1783910/03_IP%20address.png)

### Step5.Gateway and Internet Connectivity validation
ICMP echo request were used to validate connectivity to the configuration.
```bash
# Test Gateway connectivity
ping -c 4 10.0.0.1
```
```bash
# Test Internet connectivity
ping -c 4 8.8.8.8
```
**Result: Gateway responed successfully**

**Result:Internet connectivity confirmed**
## screenshot
![ping Test](https://github.com/pavithrap99/Cyber-security-week-1-project-/blob/55a0307255f5adfe774447a89e70d0c75d3cc190/04-ping-test.png)
## Verification & Testing

| Verification Item | Status | Verification Method | Outcome |
|---|---|---|---|
| Ethernet Interface Check | ✅ Passed | `ip addr show eth0` | Interface detected with 10.0.0.2/24 |
| IP Address Validation | ✅ Passed | `ip -4 addr show eth0` | Static IPv4 address verified |
| Routing Configuration | ✅ Passed | `ip route` | Default route through 10.0.0.1 confirmed |
| Local Gateway Test | ✅ Passed | `ping -c 4 10.0.0.1` | Successful replies received from gateway |
| Internet Connectivity Test | ✅ Passed | `ping -c 4 8.8.8.8` | External connectivity successfully verified |
| NAT Network Verification | ✅ Passed | VirtualBox Network Manager | NAT network configured and active |
| Network Interface Status | ✅ Passed | `ip link show eth0` | Ethernet interface confirmed operational |

## Problems Encountered & Solutions

Documenting the problems faced during the lab setup helps explain how the issues were identified and solved.

## Problem 1. Kali Linux Virtual Machine Import Issue

While setting up the Kali Linux virtual machine in VirtualBox, the downloaded Kali VM file was in a compressed format and could not be used directly.

## Solution:

1. Installed 7-Zip to extract the downloaded file.
2. Extracted the Kali Linux virtual-machine package.
3. Opened VirtualBox and selected Import Appliance.
4. Selected the extracted Kali VM file.
5. Completed the import process and started the virtual machine.
After these steps, Kali Linux was successfully imported and started in VirtualBox.

## Problem 2. Network Configuration Issue

During the network setup, the Kali Linux system did not initially have the required network configuration for the lab.

## Solution:

1. Configured the VirtualBox NAT Network.
2. Connected the Kali Linux VM to the NAT Network.
3. Checked the network interface using "ip addr".
4. Configured the required IP address.
5. Verified the default gateway using "ip route".
6. Tested the connection using the "ping" command.
After configuration, the Kali Linux VM successfully communicated with the gateway and Internet.

## Problem 3. Continuous Ping Command
While testing network connectivity, the ping command continued running and did not stop automatically.

## Solution:
The continuous ping was stopped by pressing:
"Ctrl + C"
The command then stopped and returned to the Kali Linux terminal.
## Security Considerations
⚠️ IMPORTANT: This laboratory is designed for educational purpose only.

|Consideration|Description|
|---|---|
|Network Isolation|NAT Network isolates VMs from host network|
|No DHCP |Static configuration reduces attack surface|
|Ethical Use|Testing only on systems you own or have explicit permission to test|
## Conclusion
The Cybersecurity Laboratory Environment was successfully established using Oracle VirtualBox and Kali Linux. All configuration objectives were met:

✅ Network Infrastructure: Dedicated CyberLab-NAT network created with proper subnet addressing

✅ System Configuration: Kali Linux configured with static IP addressing and default gateway

✅ Connectivity Validation: Gateway and Internet connectivity confirmed through ICMP testing

✅ Documentation: Complete configuration parameters and procedures documented

This laboratory environment provides a secure, isolated, and controlled platform for cybersecurity training, security testing, and research activities.
## Author

**Pavithra P**  
*Cybersecurity Student*

[GitHub](https://github.com/pavithrap99) | [LinkedIn](http://linkedin.com/in/pavithra-p-202131427/)


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
### step 2.Install Virtual Box
virtual box was installed to run the Kali Linux in Virtual Machine.It was a hyperveisor.
### step 3.VB NAT Network Configuration
A dedicated VB NAT Network was created with the configuration.

**Configuration:**

**Network Name: NAT Network**

**IPv4 Prefix:10.0.0.0/24**

**DHCP:Enabled**

**IPv6:Disabled**
## Screenshot
![Network Configuration](02_Nat_network-settings.png)
### Step 4.IP Address Assignment
The Kali Linux network was configured with a static IP address
```bash
# Assign static IP address to eth0 interface
sudo ip addr add 10.0.0.2/24 dev eth0
#Activate the network interface
sudo ip link set eth0 up
```
### verification
''' base
#confirm IP assignment
ip addr show eth0
'''
### Result:IP address 10.0.0.2/24 confirmed on interface etho
## screenshot


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

##Verification & Testing
Verification Item
Status
Verification Method
Outcome
Ethernet Interface Check
✅ Passed
ip addr show eth0
Interface detected with 10.0.0.2/24
IP Address Validation
✅ Passed
ip -4 addr show eth0
Static IPv4 address verified
Routing Configuration
✅ Passed
ip route
Default route through 10.0.0.1 verified
Local Gateway Test
✅ Passed
ping -c 4 10.0.0.1
Successful replies received from gateway
External Network Test
✅ Passed
ping -c 4 8.8.8.8
External connectivity successfully verified
NAT Network Verification
✅ Passed
VirtualBox → Network Manager
NatNetwork configured and active
Network Availability
✅ Passed
ip link show eth0
Ethernet interface confirmed operational




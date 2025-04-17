# Home Lab – Virtualized Cybersecurity Environment

##  Objective  
Designed a personal cybersecurity lab to simulate network environments, practice ethical hacking techniques, and understand network communications between machines.

##  Tools & Technologies  
- **Virtualization:** Oracle VirtualBox  
- **Operating Systems:** Windows 10, Kali Linux  
- **Networking:** NAT Network configuration for internal VM communication

##  Key Activities  
- Connected Windows 10 and Kali Linux virtual machines using NAT networking in a controlled lab setup.  
- Performed port scanning and service enumeration using tools like `nmap` and `netcat`.  
- Captured and analyzed network traffic using `Wireshark` to study TCP/IP behavior.  
- Executed basic attack simulations to understand vulnerability discovery and system response.  
- Practiced system hardening techniques and internal threat modeling.

##  Skills Gained  
- Virtual machine configuration and internal network setup  
- TCP/IP traffic analysis and network troubleshooting  
- Fundamental ethical hacking practices in a safe lab  
- Proficiency in Kali Linux tools (e.g., `nmap`, `netcat`, `whois`)  
- Foundational knowledge in system defense and basic offensive techniques

##  Steps

This repository demonstrates a home lab architecture where an Attacker VM (Kali Linux) and a Target VM (Windows 10) are connected using a NAT network inside Oracle VirtualBox. This setup is used to simulate attack scenarios and monitor network traffic during penetration testing.

## Reference 1: Network Diagram

The diagram below shows the architecture of the home lab. The Kali Linux VM (Attacker) and Windows 10 VM (Target) are connected through a NAT network. This allows the two VMs to communicate directly while keeping them isolated from the external internet. This internal network is ideal for performing attacks in a controlled environment.

![Ref1](https://github.com/user-attachments/assets/7cb7ab2a-0114-4195-9e58-2aeed6b98d98)


## Reference 2: NAT Network Configuration

The NAT Network is configured in Oracle VirtualBox under the "Network" settings. The configuration creates an internal subnet for the two VMs to communicate while preventing access to external networks.

- NAT Network Configuration Steps:
    1. Open Oracle VirtualBox.
    2. Navigate to the "Network" settings of the VM.
    3. Choose "Attached to: NAT Network" and configure the subnet.
    4. Ensure both VMs are connected to the same NAT network.

![Ref2](https://github.com/user-attachments/assets/a7b91845-fa76-41fd-adbe-eb113033ed25)


## Reference 3: Verifying Connectivity Between VMs

A ping test was performed from the Kali Linux VM to the Windows 10 VM to verify network connectivity. The test successfully confirmed that both VMs can communicate with each other over the NAT network.

- Command used on Kali Linux:
    ```
    ping 10.0.2.15
    ```
![Ref3](https://github.com/user-attachments/assets/1ca1a7f3-3bb0-4a48-9b35-4617f91e596c)


## Reference 4: Simulating Reconnaissance (Nmap Scan)

Nmap was used to perform a port scan on the Windows 10 VM from the Kali Linux VM. This simulates the reconnaissance phase of an attack, where the attacker identifies open ports and services running on the target.

- Nmap Command:
    ```
    nmap -A 10.0.2.4 -Pn
    ```

This scan results in a list of open ports, which can then be exploited in later stages of the attack.

![Ref4](https://github.com/user-attachments/assets/3136ebfb-8f08-44f3-be5e-6ecb94ab5969)


## Reference 5: Capturing Network Traffic (Wireshark)

Wireshark was used to capture the network traffic during the Nmap scan. The screenshot highlights the TCP SYN packets sent from the Kali Linux VM and the corresponding SYN-ACK responses from the Windows 10 VM.

This packet-level visualization helps understand the interactions between the attacker and target during a port scan.

![Ref5](https://github.com/user-attachments/assets/79b8b432-27aa-434a-a5ac-3b1a0a7bebe0)


---

> 📝 *This lab is a work-in-progress and will evolve with more advanced tools like Metasploit, Security Onion, and SIEM integrations in the future.*

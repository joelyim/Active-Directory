# Active Directory

## Objective

This project provides an educational platform to learn and apply Active Directory installation and configuration in a simulated environment. The project leverages tools like Splunk, Atomic Red Team, and Kali Linux to demonstrate and study data flow, security events, and attack techniques within a domain. This project aims to enhance proficiency in Active Directory, Splunk, and Windows Administration while highlighting the importance of network diagram creation and documentation.

### Skills Learned

- Installed and configured Active Directory on Windows Server, promoted servers to domain controllers, and created users/groups within Active Directory.
- Deployed Splunk on Ubuntu, configured Splunk Universal Forwarder and Sysmon on Windows to collect telemetry, and created indexes for data storage.
- Set up NAT networks in VirtualBox, configured static IP addresses, and verify network connectivity using CIDR notation.
- Conducted brute-force attacks using Kali Linux and Crowbar on RDP to test system security.
- Installed and utilized Atomic Red Team to simulate MITRE ATT&CK-based attacks, generate telemetry, and identify visibility gaps.

### Tools Used

- VirtualBox: Virtualization platform for creating and managing virtual machines.
- Splunk: SIEM tool for collecting and analyzing machine data and security logs.
- Sysmon: Windows tool for detailed system activity logging and monitoring.
- Kali Linux: Penetration testing OS used for ethical hacking and brute-force attacks.
- Atomic Red Team: Framework for simulating attacks based on MITRE ATT&CK techniques.
  
## Steps

*Ref 1: Logical Diagram*

<img src="https://github.com/user-attachments/assets/95ce8fd8-163f-4537-a2c6-25614ccead50" alt="Logical Diagram" width="300">
<br><br> <!-- Adds extra space between sections -->

*Ref 2: Virtual machines (VMs) configured in the project.*

<img src="https://github.com/user-attachments/assets/5a3a0493-d832-458c-973c-2eb3405555b2" alt="VMs" width="300">
<br><br> <!-- Adds extra space between sections -->

*Ref 3: Network setting configured as NAT Network, ensuring the virtual machines (VMs) are on the same network and have internet access.*

<img src="https://github.com/user-attachments/assets/d820308f-1df0-478d-bf40-567bdec98b03" alt="Nat Network" width="300">
<br><br> <!-- Adds extra space between sections -->

*Ref 4: Set up Static IP on Splunk Server*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/30966c24-9853-4700-aeaa-18515e72324e" alt="Splunk IP" width="300">
  <img src="https://github.com/user-attachments/assets/4e95611c-c6c7-407d-80f3-fba82a57bd29" alt="Splunk IP part 2" width="300">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 5: Install VirtualBox Guest Add-ons on Splunk VM.*
<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/6a79c61a-bffb-4474-a0d9-e7ca67521e3c" alt="Add on VirtualBox" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/d61a3378-0a14-4e8c-8128-deb233e1db31" alt="VirtualBox VM" width="300" height="200">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 6: Change Host Name to Target Machine.*
<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/37167de3-6bde-4f48-8f92-ce3803bd0971" alt="Rename Target Machine" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/683a7ed1-9ebc-4e20-ad75-6a060080697f" alt="Rename Target Machine Pt2" width="300" height="200">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 7: Change IPv4 Address on Target Machine to Avoid Conflict with Windows Server's VM Address.*
<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/0ba970f1-bccd-44c1-a710-5da770c24e5d" alt="Change IPv4 Address on Target Machine" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/a2094e4c-9a4b-4633-8e3a-d7a257b8ac49" alt="Change IPv4 Address Pt2" width="300" height="200">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 8: Install Splunk Universal Forwarder and Enter IP of Splunk Server on Receiving Indexer.*
<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/ab376990-7810-4be1-ae84-f657a64313e6" alt="Install Splunk Universal Forwarder" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/db09902b-75c8-4e0f-8e19-51cee0cf0532" alt="Enter IP on Splunk Universal Forwarder" width="300" height="200">
</div>



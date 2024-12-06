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

*Ref 4: Set up Static IP on Splunk Server.*

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

*Ref 6: Configure a Shared Directory on Ubuntu Splunk Server for Splunk Installer.*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/4384fbfe-0098-4cda-9666-e3843fe80204" alt="Shared Directory Configuration Step 1" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/bef1429b-f314-4a85-b0c9-198a53cede9f" alt="Shared Directory Configuration Step 2" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/ea0af069-33c2-4120-bb72-9c3f2234cdeb" alt="Shared Directory Configuration Step 3" width="300" height="200">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 7: Configure Splunk to Start Automatically at Boot Time (Enable BootStart).*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/8fd48a80-51c6-4f84-acbe-4489ff3a164f" alt="Enable BootStart Step 1" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/18ae7264-4414-4fa0-9679-3d113d79a777" alt="Enable BootStart Step 2" width="300" height="200">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 8: Change Host Name to Target Machine.*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/37167de3-6bde-4f48-8f92-ce3803bd0971" alt="Rename Target Machine" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/683a7ed1-9ebc-4e20-ad75-6a060080697f" alt="Rename Target Machine Pt2" width="300" height="200">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 9: Change IPv4 Address on Target Machine to Avoid Conflict with Windows Server's VM Address.*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/0ba970f1-bccd-44c1-a710-5da770c24e5d" alt="Change IPv4 Address on Target Machine" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/a2094e4c-9a4b-4633-8e3a-d7a257b8ac49" alt="Change IPv4 Address Pt2" width="300" height="200">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 10: Install Splunk Universal Forwarder and Enter IP of Splunk Server on Receiving Indexer.*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/ab376990-7810-4be1-ae84-f657a64313e6" alt="Install Splunk Universal Forwarder" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/db09902b-75c8-4e0f-8e19-51cee0cf0532" alt="Enter IP on Splunk Universal Forwarder" width="300" height="200">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 11: Download Sysmon and Sysmon Olaf Config on Target Machine.*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/4e3aa715-3c0d-4201-a905-1cd8e5733e20" alt="Download Sysmon on Target Machine" width="300" height="200">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 12: Install Sysmon Config through PowerShell.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/3dd7d39c-c622-4b73-89b5-efb5f7f5b6d4" alt="Installing Sysmon Config via PowerShell" width="300" height="200">
</div>
<br><br> <!-- Adds extra space between sections -->

*Ref 13: Add `inputs.conf` file in Splunk Universal Forwarder Local folder.*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/fe083202-4a6d-403e-8115-f7f052b569b3" alt="Adding Inputs.conf Part 1" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/2394b58c-b0c1-4817-b430-b58be00185b7" alt="Adding Inputs.conf Part 2" width="300" height="200">
</div>
<br><br>

*Ref 14: Add an index named `endpoint` in Splunk Enterprise.*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/ee045cea-7498-421c-8d35-e8bc70c4d1d9" alt="Creating Endpoint Index Part 1" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/c65baf91-68e8-4c97-aee4-528b5096511c" alt="Creating Endpoint Index Part 2" width="300" height="200">
</div>
<br><br>

*Ref 15: Configure Splunk to receive data on port 9997.*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/a0fdfe12-8b97-4d71-b01c-0101c0540f08" alt="Receiving Port Setup Part 1" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/2d9cfb86-ff3b-46e0-b831-595f9072bdcb" alt="Receiving Port Setup Part 2" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/67db15fd-0f67-4c96-8b6e-3e0cd49907a6" alt="Receiving Port Setup Part 3" width="300" height="200">
</div>
<br><br>

*Ref 16: Configure Splunk and Sysmon on the Windows Server.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/8a05a81f-7609-4fb2-93d2-fdda363b42a0" alt="Configuring Splunk and Sysmon" width="300" height="200">
</div>
<br><br>

*Ref 17: Set a static IP address for the Windows Server as shown in the Logical Diagram.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/5d14377c-1b1f-47bf-99c2-e08e76a89494" alt="Static IP for Windows Server" width="300" height="200">
</div>
<br><br>

*Ref 18: Add Active Directory Domain Services on the Windows Server.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/e5f9d128-953f-4742-87ea-05c60487b545" alt="Active Directory Domain Services Setup" width="300" height="200">
</div>
<br><br>

*Ref 19: Promote the server to a Domain Controller and create a root domain name.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/9bc4a888-f9be-4187-8e5a-c2ece0ce16b5" alt="Promoting to Domain Controller" width="300" height="200">
</div>
<br><br>

*Ref 20: Add users to the Active Directory.*

<div style="display: flex; gap: 20px;">
  <img src="https://github.com/user-attachments/assets/0ba5209a-3bc0-4fee-8df8-a293685440d6" alt="Adding Users Part 1" width="300" height="200">
  <img src="https://github.com/user-attachments/assets/466da1de-cf01-4b5f-ae86-34ecf980aef9" alt="Adding Users Part 2" width="300" height="200">
</div>
<br><br>

*Ref 21: Set a static IP address for Kali Linux.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/909ae9a3-4e96-4291-9560-4c6398a59271" alt="Static IP for Kali Linux" width="300" height="200">
</div>
<br><br>

*Ref 22: Enable RDP on the target machine for newly created users.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/f8150e7e-8c2b-4f57-b411-7878f6a0174a" alt="Enabling RDP on Target Machine" width="300" height="200">
</div>
<br><br>

*Ref 23: Execute a successful brute force attack on a newly created user (e.g., Jenny Smith).*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/80729574-77e7-42cd-8f64-d178ef5d3a9b" alt="Brute Force Example" width="300" height="200">
</div>
<br><br>

*Ref 24: Check EventCode for log events.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/ac1612fc-13b7-4201-954a-b82cc24b32fa" alt="EventCode Log Check" width="300" height="200">
</div>
<br><br>

*Ref 25: Install Atomic Red Team to identify security gaps.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/bebb8e63-7276-4afc-95e7-41a8f84b40c5" alt="Installing Atomic Red Team" width="300" height="200">
</div>
<br><br>

*Ref 26: Input technique ID and generate telemetry based on creating a local account.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/c7cf3336-9197-4ea7-9221-11c2176711e7" alt="Generating Telemetry with Technique ID" width="300" height="200">
</div>
<br><br>

*Ref 27: Check events for account name based on the technique ID.*

<div style="display: flex; justify-content: center;">
  <img src="https://github.com/user-attachments/assets/29f1a10b-ee2f-4e74-b124-487539b0b999" alt="Event Check Based on Technique ID" width="300" height="200">
</div>
<br><br>

















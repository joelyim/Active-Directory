# Active Directory Project Documentation

## Table of Contents
1. [Project Overview](#project-overview)
2. [Prerequisites](#prerequisites)
3. [Network Setup](#network-setup)
4. [Splunk Server Configuration](#splunk-server-configuration)
5. [Target Machine Configuration](#target-machine-configuration)
6. [Windows Server Configuration](#windows-server-configuration)
7. [Active Directory Setup](#active-directory-setup)
8. [Security Testing](#security-testing)
9. [Troubleshooting](#troubleshooting)
10. [Appendix](#appendix)

## Network Setup

### Configure NAT Network in VirtualBox

1. Open VirtualBox and navigate to File > Preferences > Network.
2. Click on the "+" icon to add a new NAT Network.
3. Configure the network with the following settings:
   - Network Name: AD_Lab_Network
   - Network CIDR: 10.0.2.0/24
   - Enable DHCP: Checked

![Nat Network](https://github.com/user-attachments/assets/d820308f-1df0-478d-bf40-567bdec98b03)

### Set Static IP for Splunk Server

1. Log into the Ubuntu Splunk server.
2. Edit the Netplan configuration file:
   ```bash
   sudo nano /etc/netplan/00-installer-config.yaml
   ```
3. Add the following configuration:
   ```yaml
   network:
     ethernets:
       enp0s3:
         dhcp4: no
         addresses: [10.0.2.10/24]
         gateway4: 10.0.2.1
         nameservers:
           addresses: [8.8.8.8, 8.8.4.4]
     version: 2
   ```
4. Apply the changes:
   ```bash
   sudo netplan apply
   ```
5. Verify the configuration:
   ```bash
   ip addr show
   ```

![Splunk IP](https://github.com/user-attachments/assets/30966c24-9853-4700-aeaa-18515e72324e)
![Splunk IP part 2](https://github.com/user-attachments/assets/4e95611c-c6c7-407d-80f3-fba82a57bd29)

### Verification Steps
1. Ping the gateway to ensure connectivity:
   ```bash
   ping 10.0.2.1
   ```
2. Ping an external site to verify internet connectivity:
   ```bash
   ping google.com
   ```

## Splunk Server Configuration

### Install VirtualBox Guest Additions

1. Insert the Guest Additions CD image by navigating to Devices > Insert Guest Additions CD image in the VirtualBox menu.
2. Mount the CD:
   ```bash
   sudo mount /dev/cdrom /mnt
   ```
3. Navigate to the mounted directory:
   ```bash
   cd /mnt
   ```
4. Run the installation script:
   ```bash
   sudo ./VBoxLinuxAdditions.run
   ```
5. Reboot the VM:
   ```bash
   sudo reboot
   ```

![Add on VirtualBox](https://github.com/user-attachments/assets/6a79c61a-bffb-4474-a0d9-e7ca67521e3c)
![VirtualBox VM](https://github.com/user-attachments/assets/d61a3378-0a14-4e8c-8128-deb233e1db31)

### Configure Shared Directory

1. Create a directory for the shared folder:
   ```bash
   sudo mkdir -p /mnt/splunk_installers
   ```
2. In VirtualBox settings for the VM, navigate to Shared Folders and add a new shared folder:
   - Folder Path: [Path on host machine]
   - Folder Name: splunk_installers
   - Auto-mount: Checked
   - Make Permanent: Checked
3. Mount the shared folder:
   ```bash
   sudo mount -t vboxsf splunk_installers /mnt/splunk_installers
   ```
4. Add the current user to the vboxsf group:
   ```bash
   sudo usermod -aG vboxsf $(whoami)
   ```

![Shared Directory Configuration Step 1](https://github.com/user-attachments/assets/4384fbfe-0098-4cda-9666-e3843fe80204)
![Shared Directory Configuration Step 2](https://github.com/user-attachments/assets/bef1429b-f314-4a85-b0c9-198a53cede9f)
![Shared Directory Configuration Step 3](https://github.com/user-attachments/assets/ea0af069-33c2-4120-bb72-9c3f2234cdeb)

### Install Splunk Enterprise

1. Navigate to the shared directory:
   ```bash
   cd /mnt/splunk_installers
   ```
2. Install Splunk using the .deb package:
   ```bash
   sudo dpkg -i splunk-*.deb
   ```
3. Configure Splunk to start automatically:
   ```bash
   sudo /opt/splunk/bin/splunk enable boot-start -user splunk
   ```
4. Start Splunk:
   ```bash
   sudo /opt/splunk/bin/splunk start
   ```
5. Follow the on-screen prompts to create an admin username and password.

![Enable BootStart Step 1](https://github.com/user-attachments/assets/8fd48a80-51c6-4f84-acbe-4489ff3a164f)
![Enable BootStart Step 2](https://github.com/user-attachments/assets/18ae7264-4414-4fa0-9679-3d113d79a777)

### Configure Splunk to Receive Data

1. Log into the Splunk web interface at http://10.0.2.10:8000
2. Navigate to Settings > Forwarding and receiving
3. Click on "Configure receiving"
4. Add a new receiving port:
   - Listen on this port: 9997
   - Click "Save"

![Receiving Port Setup Part 1](https://github.com/user-attachments/assets/a0fdfe12-8b97-4d71-b01c-0101c0540f08)
![Receiving Port Setup Part 2](https://github.com/user-attachments/assets/2d9cfb86-ff3b-46e0-b831-595f9072bdcb)
![Receiving Port Setup Part 3](https://github.com/user-attachments/assets/67db15fd-0f67-4c96-8b6e-3e0cd49907a6)

### Create Endpoint Index

1. In the Splunk web interface, navigate to Settings > Indexes
2. Click "New Index"
3. Configure the index:
   - Index Name: endpoint
   - Index Data Type: Events
   - Click "Save"

![Creating Endpoint Index Part 1](https://github.com/user-attachments/assets/ee045cea-7498-421c-8d35-e8bc70c4d1d9)
![Creating Endpoint Index Part 2](https://github.com/user-attachments/assets/c65baf91-68e8-4c97-aee4-528b5096511c)

### Troubleshooting Splunk Configuration
- If Splunk fails to start, check the logs in `/opt/splunk/var/log/splunk/`
- If data is not being received, verify firewall settings allow traffic on port 9997
- To verify the Splunk service is running:
  ```bash
  sudo systemctl status Splunkd
  ```

<p align="center">
<img width="320" height="320" alt="dns-logo-png_seeklogo-492112" src="https://github.com/user-attachments/assets/84efd039-9a26-4fe9-b4c7-05425794b97b" />
</p>

<h1>DNS Configuration and Setup</h1>

This lab demonstrates the installation and configuration of a basic DNS Server within a Windows Server environment.
The objective is to configure name resolution for a simulated internal network and test proper DNS functionality:
- Installing DNS Server
- Creating a Forward Lookup Zone
- Creating A Records
- Testing with nslookup
- Breaking DNS intentionally
- Fixing it

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- DNS Server Manager

<h2>Operating Systems Used </h2>

- Windows (Windows Server 2022 Datacenter Azure Edition)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Remote Desktop Connection

<h2>Installation Steps</h2>

1. Install DNS Role

On Windows Server:

Add Roles and Features
Install DNS Server
Open DNS Manager
mydomain.local
Screenshot:
DNS role installed
DNS Manager open

2. Create Forward Lookup Zone
Right-click Forward Lookup Zones
New Zone
Primary Zone
Name it: mydomain.local
Screenshot:
Zone creation wizard
Zone visible in DNS Manager

3. Create an A Record
Create a host record:
Name: fileserver
Screenshot:
A record created

This allows devices to resolve “fileserver.mydomain.local” to its IP address.

4. Test Name Resolution
Open Command Prompt:
nslookup fileserver.mydomain.local
ping fileserver.mydomain.local
Screenshot:
Successful resolution

5. Break DNS (This Makes It Better)

Delete the A record.
Run nslookup again.
It should fail.
Screenshot:
Failed lookup

Then recreate it and show it works again.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

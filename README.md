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

- Azure Virtual Machine, Virtual Box or VMWare
- Remote Desktop Connection
- Admin login

<h2>Install DNS Role</h2>
On Windows Server:

Add Roles and Features
- Install DNS Server
- Open DNS Manager
  - Server Manager 🡢 Tools 🡢 DNS
- mydomain.local

<p>
<img width="1901" height="1009" alt="DNSinstalled" src="https://github.com/user-attachments/assets/6cc314f5-5ad7-475c-a901-8b22d35a9964" />
</p>

<p><img width="1846" height="1030" alt="DNS Manager" src="https://github.com/user-attachments/assets/eac6c529-4235-447e-848a-605e784f75f3" />
</p>

<h2>Create Forward Lookup Zone</h2>

- Right-click Forward Lookup Zones
- New Zone
- Primary Zone
- Name it: mydomain.local
<p>
<img width="611" height="518" alt="zonewizard" src="https://github.com/user-attachments/assets/bc3ea1b3-7ab6-4912-b7ee-78559521392c" />
</p>

<p>
<img width="1180" height="311" alt="zonevisible" src="https://github.com/user-attachments/assets/2f383cbc-5310-457b-a013-7e7bfe49436b" />
</p>

<h2>Create an A Record</h2>

- Create a host record:
  - Right-click mydomain.local 🡢 New Host (A or AAAA)
- Name: fileserver
- IP:8.8.4.4

<p>
<img width="516" height="581" alt="fileservercreated" src="https://github.com/user-attachments/assets/68dc55ca-2a2b-46dd-92d4-853456ac63bf" />
</p>

DNS "A" record created.

This allows devices to resolve “fileserver.mydomain.local” to its IP address.

<h2>Test Name Resolution</h2>

- Open Command Prompt or Powershell:
- nslookup fileserver.mydomain.local
- ping fileserver.mydomain.local

<p>
<img width="1123" height="654" alt="powershellcmds" src="https://github.com/user-attachments/assets/01ee4422-a16f-4002-81e6-058daf1089fa" />
</p>

<h2>Break DNS</h2>

- Right click fileserver 🡢 Properties
- Change IP to 192.168.x.x
- Ping 192.168.x.x
- It should fail
  
<p>
<img width="1835" height="1024" alt="fileserverfail" src="https://github.com/user-attachments/assets/0aa594e8-f34c-4cf2-b6f3-fa9503ba5aa6" />
</p>

Important: If the ping is successful because it retrieves the same IP address of 8.8.4.4 the DNS cache needs to be flushed so it can be updated with the new IP of 192.168.x.x

<p>
<img width="1135" height="660" alt="flushdns" src="https://github.com/user-attachments/assets/3b6d4f7d-e89c-4990-a7bf-463d39fff4e7" />
</p>

- Right click fileserver 🡢 Properties
- Delete the A record.
- Run nslookup again
- It should fail
  
<p>
<img width="1842" height="1025" alt="fileserverfail2" src="https://github.com/user-attachments/assets/140fc6f9-841e-41c9-b8f0-4d59f2835570" />
</p>

Then recreate it and show it works again.

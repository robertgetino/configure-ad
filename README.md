<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com/watch?v=wuIE4p4io7Q)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Install Active Directory in Windows Server VM
- Step 2: Create a Domain Admin user within Active Directory
- Step 3: Attach Normal Account to Domain
- Step 4: Create Users with PowerShell and Setup Remote Desktop

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="[image](https://github.com/user-attachments/assets/58b49cf8-9595-4241-b3d4-22ea327d8a6d)
" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Step 1, I log into Microsoft Azure and create a virtual machine and name it dc-1, in this project. Next I log into the VM and install Active Directory Services and follow the respective prompts and allow permissions when necessary. Finally, as shown in the screenshot above, I promote to a domain controller by adding a forest and naming it as "mydomain.com", and restart the VM. I'll log in as the user "my-domain.com".
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Step 2, I went to the Active Directory Users and Computers, or ADUC, and created an OU (Organizational Unit) and named it "_EMPLOYEES". Next, I created another OU called "_ADMINS". Going back to the "_EMPLOYEES" OU, I created an employee name, "John Doe".
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

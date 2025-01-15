<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell
- PowerShell_ise

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Install Active Directory in Windows Server VM
- Step 2: Create a Domain Admin user within Active Directory
- Step 3: Create Users with PowerShell and Setup Remote Desktop

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://github.com/robertgetino/configure-ad/blob/b45fb1bdf3aa1dc3bddc2eef22617151279151ed/resourcegroup.png" height="45%" width="45%" alt="Disk Sanitization Steps"> <img src="https://github.com/robertgetino/configure-ad/blob/088019b90a9c546f832f055ed73f9a19ed83fc97/client1%26dc1vm.png" height="45%" width="45%" alt="Disk Sanitization Steps"> <img src="https://github.com/robertgetino/configure-ad/blob/5e0fc868a826348785338598ac6303efe8318e23/client1privateipaddress.png" height="45%" width="45%" alt="Disk Sanitization Steps"> <img src="https://github.com/robertgetino/configure-ad/blob/a90b9e33ae9d5dac59a5ba0b4744301851becbfc/dc1privateipaddress.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
I create a new resource group (Active-Directory-Labs) and virtual network in Microsoft Azure. I then create two new virtual machines within them and make sure they're all on the same subnet. The first virtual machine is running the Windows Server 2020 OS, which is the domain controller (dc-1) and I set the IP address to static instead of dynamic. The second virtual machine is running Windows 10 OS (client-1) and I also set the IP address to static. I attach it to the same virtual network as dc-1 and restart client-1.
</p>
<br />

<p>
<img src="https://github.com/robertgetino/configure-ad/blob/c892cae143c055992b3385f46dc684b15132b5e0/pingdc1.png" height="45%" width="45%" alt="Disk Sanitization Steps"/> <img src="https://github.com/robertgetino/configure-ad/blob/a6e26e973bd38094fd7c1be1384c2920930851f1/ipconfig%20%3Aall.png" height="45%" width="45%" alt="Disk Sanitization Steps"> <img src="https://i.imgur.com/DJmEXEB.png" height="45%" width="45%" alt="Disk Sanitization Steps"> <img src="https://i.imgur.com/DJmEXEB.png" height="45%" width="45%" alt="Disk Sanitization Steps"> <img src="https://i.imgur.com/DJmEXEB.png" height="45%" width="45%" alt="Disk Sanitization Steps"/>
</p>
<p>
I then log into client-1 and attempt to ping dc-1's IP address, to which I succeed. As another test, I run the command "ipconfig /all" to view the DNS settings of dc-1. Next, I log into dc-1 and install Active Directory Domain Services and promote it as a DC (domain controller). I setup a new forest and name it mydomain.com, then restart dc-1 and login as the new forest I just created. I then go to the folder, Active Directory Users and Computers (ADUC), create two Organizational Units (OU) "_EMPLOYEES" and "ADMINS".
</p>
<br />

<p>
<img src="https://github.com/robertgetino/configure-ad/blob/79be43d12a9e7049ecbd2f8b50ac4513e9858df0/PowerShell.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Step 3, I set up Remote Desktop and allow "all domain users" access to remote desktop. Next, I open PowerShell as an administrator and create a new file. In this file, I paste the contents of the script into it. Thirdly, I run the script and observe the accounts being created. Finally, I open ADUC (Active Directory Users and Computers) and observe the accounts in the proper OU (Organizational Unit).
</p>
<br />

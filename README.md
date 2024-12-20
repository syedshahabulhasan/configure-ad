<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Group Policy Management</h1>
This tutorial covers how to manage Group Policy in Active Directory, focusing on creating and configuring Group Policy Objects (GPOs) to control network settings and security policies.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1 - Install Active Directory
- Step 2 - Create a Domain Admin user within the domain 
- Step 3 - Join Client-1 to your domain (mydomain.com)

<h2>Setup and Configuration Procedures</h2>

Log in to the DC-1 server and proceed to install Active Directory Domain Services. Follow the prompts to complete the installation and configure the necessary settings.

<p>
<img src="https://i.imgur.com/2lPwtMA.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/cSM5mof.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/O7mtrmv.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/u6PhgYH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

Promote the server to a Domain Controller and set up a new forest with the domain name 'mydomain.com' (or any name you choose, just make sure to remember it).

<p>
<img src="https://i.imgur.com/lk5mi3h.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/NCmf6CC.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/oIdMlpT.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/BU0rvrB.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/GgWMCVI.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/jRNk1MW.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>

Restart the server and log back into DC-1 using the credentials: mydomain.com\labuser. After logging in, open the Active Directory Users and Computers (ADUC) console. In ADUC, create two Organizational Units (OUs): one called ‘_EMPLOYEES’ to organize user accounts for employees, and another called ‘_ADMINS’ to organize user accounts for administrative roles.

<p>
<img src="https://i.imgur.com/hx0Lwjn.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/92z7dg0.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/p2MOWjU.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

Create a new employee account in Active Directory named 'Jane Doe'. Use the username 'jane_admin' and set the password to 'Cyberlab123!' (the same password for the account).

<p>
<img src="https://i.imgur.com/Ws56CI9.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/JMIuSqQ.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>

Add the 'jane_admin' account to the 'Domain Admins' Security Group to grant administrative privileges. Once added, log out of the current session, close the connection to DC-1, and then log back in using the credentials 'mydomain.com\jane_admin'. From this point forward, use the 'jane_admin' account as your admin account.

<p>
<img src="https://i.imgur.com/dggKugf.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/XI4WaKe.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>

Join Client-1 to your domain (mydomain.com) by adding it to the domain through the system settings. In the Azure Portal, ensure that Client-1’s DNS settings are configured to use the Domain Controller’s private IP address (this step should already be completed). After verifying the DNS settings, restart Client-1 from the Azure Portal to apply the changes and ensure proper domain connectivity.


<p>
<img src="https://i.imgur.com/UtfZkJl.png" height="60%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/1uDbuxw.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

<img src="https://i.imgur.com/KACFOrl.png" height="40%" width="60%" alt="Disk Sanitization Steps"/>
</p>

Log in to Client-1 using the original local admin account (labuser). Once logged in, go to the system settings and join Client-1 to the domain (mydomain.com). After the domain join process is complete, the computer will automatically restart to apply the changes

<img src="https://i.imgur.com/sJ1rQhJ.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

<img src="https://i.imgur.com/NBRiXOZ.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>

<img src="https://i.imgur.com/W6p5GPn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>

Log in to the Domain Controller (DC-1) and open Active Directory Users and Computers (ADUC). Verify that Client-1 now appears in the list of computers within the domain. This confirms that the machine has successfully joined the domain and is visible in Active Directory

<img src="https://i.imgur.com/YUPRxSX.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>

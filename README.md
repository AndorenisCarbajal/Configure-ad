
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This Project outlines the implementation of on-premises Active Directory within Azure Virtual Machines. Using our Microsoft Azure VMs, we will log into Remote Desktop and install Active Directory in our virtual machine, which allows us to manage devices and provides a more effective way to control access to resources on a large scale—anything from Accounts, Passwords, Permissions, etc.
<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Install Active Directory
- Step 2: Create a Domain Admin user within the domain
- Step 3: Join Client-1 to your domain (mydomain.com)
- Step 4: Set up Remote Desktop for non-administrative users on Client-1
- Step 5: Create a bunch of additional users and attempt to log into client-1 with one of the users

<h2>Deployment and Configuration Steps</h2>

<p align="center">
Install Active Directory: <br/>  
<img width="450" alt="1 Installing Active Directoy on DC-1 vm" src="https://github.com/user-attachments/assets/f570b89c-00ca-47ff-9cd8-bf9e49fcd9e7" />
</p>
<p>
Log in to DC-1 and install Active Directory Domain Services. Promote as a DC: Set up a new forest as mydomain.com (can be anything, just remember what it is)
Restart and then log back into DC-1 as user: mydomain.com\labuser
</p>
<br />

<p align="center">
Employees & Admins Organizational units : <br/>
<img width="450" alt="2 Domain Admins created _EMPLOYEES, _ADMINS" src="https://github.com/user-attachments/assets/4f7a2c7a-17d5-4d6b-8e10-e391afd29b43" />
<p align="center">
Create a Domain Admin user within the domain: <br/>  
<img width="450" alt="3  security group Domain Admins" src="https://github.com/user-attachments/assets/4b5e2e86-52cc-443e-a86f-0435c2e83a10" />
</p>
<p>
In Active Directory Users and Computers, create an organizational unit called employees. And then create another organizational unit for Admins. Then, create a Domain Admin user within the domain. In this case, we used Jane Doe and added her to the security group "Domain Admins.</p> 
<br />

<p align="center">
Join Client-1 to your domain (mydomain.com): <br/>
<img width="450" alt="4  Client-1 added to clients on active directory on DC-1" src="https://github.com/user-attachments/assets/397f4c99-f87a-42f2-bf76-5c9714f1f351" />
</p>
<p>
Create a new Organizational unit named clients, and then drag client-1 into the OU. Log in to the domain controller, and you need to verify that client-1 shows up in Active Directory Users and Computers.
</p>
<br />

<p align="center">
Set up Remote Desktop for non-administrative users on Client-1: <br/>  
<img width="450" alt="5  allowing domain users to remote desktop" src="https://github.com/user-attachments/assets/f31843a9-48fb-4fc4-bb0e-86d2dc2e7513" />
</p>
<p>
Log into Client-1 as mydomain.com\user created
Open system properties
Click “Remote Desktop.”
Allow “domain users” access to the remote desktop
You can now log into Client-1 as a normal, non-administrative user.
</p>
<br/>

<h4>Create a bunch of additional users and attempt to log into client-1 with one of the users</h4>
<p align="center">
Observe the accounts created: <br/>
<img width="450" alt="6 observe the accounts being created" src="https://github.com/user-attachments/assets/55f5f4c8-894f-41fa-8353-0905060fab4c" />
<P>
You should log in to the user created and run PowerShell as an administrator. Create a file and paste the contents of the script into it, and then run the script and observe the accounts being created.
</P>
<p align="center">
Log in as client-1, the user created in my example Bag.Sato: <br/>
<img width="450" alt="7 Logged into Client-1 with one of the accounts" src="https://github.com/user-attachments/assets/53eeea59-193d-4d14-a49e-537d1b94b889" />
</p>
<p>
Once the accounts have been created, open ADUC and observe the accounts and attempt to log into client-1 with one of the accounts. You should have succeeded in logging in.
</p>
<br/>
</P>

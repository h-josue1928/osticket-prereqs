# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Install/ Enable Internet and Information Services (IIS) with CGI and common HTTP features
- Download and install PHP Manager for IIS
- Download and install the Rewrite Module
- Download PHP 7.3.8
- Download and install VC_redist.x86.exe
- Download and install MySQL 5.5.6
- Install osTicket v1.15.8
- Download and install HeidiSQL
- onfigured permissions and installed osTicket

<h2>Installation Steps</h2>
Step 1: Create a resource group in Azure
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 2: Create a Windows 10 Pro Virtual Machine (VM)

- Select the Resource group that was created
- VM name: VM-osTicket
- Select US East or US West region
- For Availability options, select 'No infrastructure redundancy required'
- For Security type select 'Standard'
- Image: Windows 10 Pro
- Size: 2 or 4 Virtual CPUs (vcpus)
- Choose your username and password
- Check the box for Licensing
- Click Review + Create

</p>
<br />

Step 2: Create a Windows 10 Pro Virtual Machine (VM)

- Select the Resource group that was created
- VM name: VM-osTicket
- Select US East or US West region
- For Availability options, select 'No infrastructure redundancy required'
- For Security type select 'Standard'
- Image: Windows 10 Pro
- Size: 2 or 4 Virtual CPUs (vcpus)
- Choose your username and password
- Check the box for Licensing
- Click Review + Create


Step 3: Open Remote Desktop Connection App

- Copy and paste the Public IP Address into the Remote Desktop Connection (Wait until the VM finished deploying)
- Click 'Connect'
- Log in with the credentials created during the virtual machine configuration process.
- Select 'Yes' to connect to you VM



Step 4: Install/Enable IIS in Windows with CGI and Common HTTP features

- Right click on the "start/windows" icon, click run, and enter "control"
- Click on 'Programs'
- Click the blue hyperlink that says 'Turn Windows features on or off"
- Select Internet Information Services (IIS) -> World Wide Web Services -> Application Development Features (click the plus sign to [X] CGI) -> Common HTTP Features (click the plus sign to [X] all.)
- Click 'Ok'



  Step 5: Open the Installation files page here -> (https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

- Download and isntall PHP Manager for IIS
- Download and install Rewrite Module
- Download and install PHP 7.3.8
- Download and install VC_redist.x86.exe.
- Download and install MySQL 5.5.62

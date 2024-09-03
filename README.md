# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

osTicket - Prerequisites and Installation
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


<img src="[image](https://github.com/user-attachments/assets/b0615d0a-9e34-4349-babc-b91a1e83d689)" alt="osTicket logo"/>



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


Step 6: Open IIS as an Admin

- Click start and type in IIS in the seach bar -> right click on IIS app and click 'Run as administrator'
- Register PHP from within the IIS app
- Click on PHP Manager
- Select blue hyperlink that says 'Register new PHP version'
- Click on PHP Manager -> Register new PHP version -> This PC -> PHP -> php-cgi -> open -> click 'Ok'
- Go back to the home page in the IIS app and click "Restart"


  Step 7: Download and install osTicket v1.15.8

- When the osTicket file has downloaded, open the osTicket file
- Once inside the folder, open another File Explorer (the yellow folder on the taskbar) and go to This PC -> Windows (C:) -> inetpub -> wwwroot
- Once inside the wwwroot folder, drag the "upload" folder within the "wwwroot" folder
- Right click the 'upload' witin the wwwroot folder and rename it "osTicket


Step 8: Go back to IIS app

- Click 'Restart'
- Go to Sites (left margin) -> Default Website -> osTicket ->  click "Browse *:80" (blue hyperlink on in the right margin)
- Webpage to osTicket should open


Step 9: Enable extentions

- Go back to IIS app -> Sites -> Default Website -> osTicket
- Double click on PHP Manager
- Click the blue hyperlink that says 'Enable or Disable an extension'
- Enable (right click each to enable): php_imap.dll, php_intl.dll, and php_opcache.dll
- Refresh osTicket webpage in order to review the enabled extentions

  Step 10: Rename ost-sampleconfig.php

- Go to the wwwroot folder in File Explorer
- Click on osTicket -> include-> scroll to find 'ost-sampleconfig.php' and rename it 'ost-config.php' (simply remove the word 'sample')
- Right click ost-config.php -> click Properties -> click Security (tab at the top) -> click Advanced -> click Disable inheritance -> click pop up hyperlink that says 'Remove all inherited permissions-> click Add -> Select Principle -> type 'Everyone' in the object name field -> click Ok -> click 'Full Control' -> click ok -> click Apply and then Ok


Step 11: Continue Setting up Osticket (click 'Continue' at the bottom

- Help Desk Name: Tammy Help Desk
- Email: tammy@helper.com (Receives email from customers)
- Name: Tammy
- Last name: Hooker
- Email address: tammy@gmail.com (can be any mail address)
- Username: tammyh
- Password: Choose your ownn
- Download and install HeidiSQL
- Open HeidiSQL will
- Click 'New' at the bottom left,
- Enter root password that was created when we downloaded MySQL
- Connect to the session
- Create a database called 'osTicket' in Heidi SQL -> right click where it says 'Unnamed' in bold -> Create New -> Database -> type 'osTicket' in the Name field
- Continue on to the Database Settings on the osTicket webpage:
  - MySQL Database: enter 'osTicket' (database we just created in HeidiSQL)
  - MySQL Username: root
  - MySQL Password: Password that was created when we downloaded MySQL
  - Click 'Install Now!'


Step 12: Clean up

- Go to Files Explorer
- Go to Windoows (C)-> inetpub -> wwwroot -> osTicket -> setup (right click and delete)
- Set Permissions to 'Read' only: Go to Windoows (C)-> inetpub -> wwwroot -> osTicket -> include -> ost-config.php -> right click and go to Properties -> Security -> Advanced -> Double click 'Everyone' -> deselect 'Full control' , 'Modify' , and 'Write' -> click 'Ok' and Apply
- Click on http://localhost/osTicket/scp under 'Your Staff Control Panel'
- Enter log in credentials
- Congrats, you have successfully logged into osTicket!

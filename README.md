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


![image](https://github.com/user-attachments/assets/c0fbf5e9-08c0-4563-af7d-088b35f0c516)







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

![image](https://github.com/user-attachments/assets/ab380386-7dc9-4f05-b695-c31df4d3343c)
![image](https://github.com/user-attachments/assets/1d722509-d976-48f2-8ddf-660f128f78cc)
![image](https://github.com/user-attachments/assets/1b15f4a4-e9e8-42a1-a716-0d307e8381e8)



Step 3: Open Remote Desktop Connection App

- Copy and paste the Public IP Address into the Remote Desktop Connection (Wait until the VM finished deploying)
- Click 'Connect'
- Log in with the credentials created during the virtual machine configuration process.
- Select 'Yes' to connect to you VM

![image](https://github.com/user-attachments/assets/c6945131-8cf5-4b32-9a0c-14f6f001df24)

![image](https://github.com/user-attachments/assets/51a29ce9-cb42-4ba7-bbde-9b9b428d7775)

![image](https://github.com/user-attachments/assets/491439eb-158f-49dc-bb27-7aabed4f3a11)



Step 4: Install/Enable IIS in Windows with CGI and Common HTTP features

- Right click on the "start/windows" icon, click run, and enter "control"
- Click on 'Programs'
- Click the blue hyperlink that says 'Turn Windows features on or off"
- Select Internet Information Services (IIS) -> World Wide Web Services -> Application Development Features (click the plus sign to [X] CGI) -> Common HTTP Features (click the plus sign to [X] all.)
- Click 'Ok'


![image](https://github.com/user-attachments/assets/6fb501ad-eb14-41c9-95e7-699db5f00329)





  Step 5: Open the Installation files page here -> (https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

- Download and isntall PHP Manager for IIS
- Download and install Rewrite Module
- Download and install PHP 7.3.8
- Download and install VC_redist.x86.exe.
- Download and install MySQL 5.5.62


![image](https://github.com/user-attachments/assets/bf771f7b-1c93-47fa-9477-4106358e217f)

Step 5.1 When PHP 7.3.8 is finished downloading, create a folder on Windows (C:) and name it 'PHP'-> right click the PHP 7.3.8 file -> Extract all -> Browse -> This PC -> Windows (C:) -> PHP -> Select Folder -> Extract

![image](https://github.com/user-attachments/assets/b4a54e57-57df-4f32-bcd8-f7fa0de8d38f)

Step 5.2 When downloading MySQL, choose 'Typical' as your set up type -> continue installation and set up credentials -> select 'Standard Configuration' -> select next -> choose your password (the username will automatically be 'root') -> Execute and finish

![image](https://github.com/user-attachments/assets/8579f270-94be-498a-967f-7e0f29678324)


Step 6: Open IIS as an Admin

- Click start and type in IIS in the seach bar -> right click on IIS app and click 'Run as administrator'
- Register PHP from within the IIS app
- Click on PHP Manager
- Select blue hyperlink that says 'Register new PHP version'
- Click on PHP Manager -> Register new PHP version -> This PC -> PHP -> php-cgi -> open -> click 'Ok'
- Go back to the home page in the IIS app and click "Restart"

![image](https://github.com/user-attachments/assets/62f7710c-f935-42c7-a6fa-d898e7c4353e)

![image](https://github.com/user-attachments/assets/ca4e63a2-0553-4e80-b880-958306572a0a)

![image](https://github.com/user-attachments/assets/57a01d13-7e7e-4fc1-8c35-33a75ba3d67d)



  Step 7: Download and install osTicket v1.15.8

- When the osTicket file has downloaded, open the osTicket file
- Once inside the folder, open another File Explorer (the yellow folder on the taskbar) and go to This PC -> Windows (C:) -> inetpub -> wwwroot
- Once inside the wwwroot folder, drag the "upload" folder within the "wwwroot" folder
- Right click the 'upload' witin the wwwroot folder and rename it "osTicket

![image](https://github.com/user-attachments/assets/1c43f281-89c0-4782-a935-d915e9fbbb19)


Step 8: Go back to IIS app

- Click 'Restart'
- Go to Sites (left margin) -> Default Website -> osTicket ->  click "Browse *:80" (blue hyperlink on in the right margin)
- Webpage to osTicket should open

![image](https://github.com/user-attachments/assets/f8565fcd-2706-4460-9702-7a13be725590)

![image](https://github.com/user-attachments/assets/0893942f-3206-48f9-a4a7-a52488aa02ad)



Step 9: Enable extentions

- Go back to IIS app -> Sites -> Default Website -> osTicket
- Double click on PHP Manager
- Click the blue hyperlink that says 'Enable or Disable an extension'
- Enable (right click each to enable): php_imap.dll, php_intl.dll, and php_opcache.dll
- Refresh osTicket webpage in order to review the enabled extentions

![image](https://github.com/user-attachments/assets/99f090fd-435f-4e82-a05e-20867f78a0d7)

![image](https://github.com/user-attachments/assets/5f284ebc-bf08-499f-b6eb-2dca5c515fb3)

![image](https://github.com/user-attachments/assets/8d42182a-9269-4d07-80a0-b0983b067cdb)

![image](https://github.com/user-attachments/assets/c2aab79e-d149-4a3b-af58-72856e862550)





  Step 10: Rename ost-sampleconfig.php

- Go to the wwwroot folder in File Explorer
- Click on osTicket -> include-> scroll to find 'ost-sampleconfig.php' and rename it 'ost-config.php' (simply remove the word 'sample')
- Right click ost-config.php -> click Properties -> click Security (tab at the top) -> click Advanced -> click Disable inheritance -> click pop up hyperlink that says 'Remove all inherited permissions-> click Add -> Select Principle -> type 'Everyone' in the object name field -> click Ok -> click 'Full Control' -> click ok -> click Apply and then Ok

![image](https://github.com/user-attachments/assets/c6f2552a-dbf8-4305-a59c-516b5efcd512)

Step 11: Continue Setting up Osticket (click 'Continue' at the bottom

- Help Desk Name: 
- Email: (Receives email from customers)
- Name: 
- Last name: 
- Email address: (can be any mail address)
- Username: t
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

 ![image](https://github.com/user-attachments/assets/e55685cd-91ce-4794-984a-61236ec2e306)

![image](https://github.com/user-attachments/assets/80626ecf-5093-4634-80a6-397d06878011)

![image](https://github.com/user-attachments/assets/41a36599-df2e-4d3b-a154-6349660e2f0c)

Step 12: Clean up

- Go to Files Explorer
- Go to Windoows (C)-> inetpub -> wwwroot -> osTicket -> setup (right click and delete)
- Set Permissions to 'Read' only: Go to Windoows (C)-> inetpub -> wwwroot -> osTicket -> include -> ost-config.php -> right click and go to Properties -> Security -> Advanced -> Double click 'Everyone' -> deselect 'Full control' , 'Modify' , and 'Write' -> click 'Ok' and Apply
- Click on http://localhost/osTicket/scp under 'Your Staff Control Panel'
- Enter log in credentials
- Congrats, you have successfully logged into osTicket!

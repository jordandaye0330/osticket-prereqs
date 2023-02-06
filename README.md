<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)


<h2>Installation Steps</h2>

<p>
<h2>Step 1: Enable IIS in Windows with CGI</h2>
<img src="https://i.imgur.com/ScXxzyL.png" height="80%" width="80%" alt="Enable IIS"/>
</p>
<p>
<h3>Step 1: Enable IIS in Windows with CGI</h3>

- Right click on the windows icon> choose "Run" 
- Open "Control Panel" 
- Click "Programs"
- Choose "Turn Windows Features on or Off"
- Scroll down to turn ON "Internet Information Services" by filling in the selection box.
- click the boxes to expand the following: "Internet Information Services"; "World Wide Web Services"; "Application Development Features"
- Click to check the box next to "CGI" to enable it
- Click "OK"
</p>
<br />
<hr>
<h2>Step 2: Access Prerequisite Installation Files</h2>

- Open Microsoft Edge from within the Remote Desktop to access the internet img#1
(On first time opening Edge, turn off any personalization or marketing options that pop up)

- From within Edge, Access the installation files for all prerequisite installations and osTicket Software installation by copying this file into the Edge browser: [Link to Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) 

</p>
<br /><hr>
<p>
<h2>Step 3: Install PHP Manager</h2>

- From the Installation files, Download and install PHP Manager for IIS (PHPMangerForLLS_V1.5.0msl)
(If you receive an error "this file type might be dangerous", click to "download anyway")
- After file has downloaded, choose "Open file"; click "next"; "I Agree"; "Next"; "Close"
</p>
<br /><hr>

<h2>Step 4: Install Rewrite Module</h2>

- From the Installation Files, Download and Install the "Rewrite Module" (rewrite_amd64_en-US.msl)
(If you receive an error "this file type might be dangerous", click to "download anyway")
- After file has downloaded, choose "Open file"; accept license agreement; Install; Finish
</p>
<br />
<hr>
<p>
<h2>Step 5: Create PHP Directory</h2>
<img src="https://i.imgur.com/hmXl0g8.png" height="80%" width="80%" alt="Enable IIS"/>
</p>
<p>
<h3>Step 5: Create PHP Directory</h3>

- Click on the "File Explorer" icon
- Choose "This PC"
- Type or Choose "C:"
- Right Click to choose to add a "New" "Folder"
- Name this folder "PHP"

</p>
<br /><hr>
<p>
<h2>Step 6: Install PHP7.3.8</h2>
<img src="https://i.imgur.com/LDIrYM7.png" height="80%" width="80%" alt="Enable IIS"/>
</p>
<p>
<h3>Step 6: Install PHP7.3.8</h3>

- From the Installation Files, download PHP7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) 
- Unzip contents into the new PHP folder  (C:\PHP)
  - Click to "Open File" from the downloads
  - "Extract All"
  - Select a destination, by typing "C:\PHP" to place it into the new C:\PHP folder.
  - "Select Folder"
  - "Extract"
</p>
<br />
<hr>
<p>
<h2>Step 7: Install VC_redist.x86.exe</h2>

- From the Installation Files, Download and install VC_redist.x86.exe.
- Click to "Open File" (If you receive an error "this file type might be dangerous", click to "download anyway")
- Click to agree to the license; "Install" and "Close"
</p>
<br />
<hr>
<p>
<h2>Step 8: Install MySQL</h2>

- From the Installation Files, Download and install MySQL5.5.62 (mysql-5.5.62-win32.msl)
- Click to "Open File"
- Accept the license
- Continue through the typical set up to finish installation and yes to launch wizard
- Modify Security Settings:(Choose your own password and write it down for future reference!)
-"Execute"; "Finish"

</p>
<br />
<hr>
<p>
<h2>Step 9: Register PHP</h2>
<img src="https://i.imgur.com/HIRzAGh.png" height="40%" width="40%" alt="Register new PHP"/> <img src="https://i.imgur.com/0YaCkqe.png" height="40%" width="40%" alt="Register new PHP"/>
</p>
<p>
<h3>Step 9: Register PHP</h3>

- Search for IIS Select IIS App, and choose to "Run as Administrator" 
- Select PHP Manager
- Click "Register new PHP Version"
- Enter the path to PHP executable file by entering: C:\PHP and clicking the box with 3 dots (...) then select the pathway- PHP-CGi, Click Open, and Ok
- Restart IIS by clicking the VM and then "Restart"

</p>
<br />
<hr>
<p>
<h2>Step 10: Install osTicket</h2>
<img src="https://i.imgur.com/MO9xJoA.png" height="80%" width="80%" alt="extract osticket"/> 
</p>
<p>
<h3>Step 10: Install osTicket</h3>

- From the Installation Files, Download and Install os Ticket v1.15.8
- Click "Open File" 
- Extract "upload" folder to C:\inetpub\wwwroot 
- Rename "upload" folder to "osTicket" 
- Open IIS and Restart again
</p>
<br />
<hr>

<p>
<h2>Step 11: Enable Extensions in IIS</h2>

- From IIS
- "Sites"
- "Default"
- "osTicket"
- "PHP Manager"
- "Enable or Disable an Extension"
- Enable the following: 
  - php_imap.dll
  - php_intl.dll
  - php_opcache.dll


</p>
<br />
<hr>
<p><h2>Step 12: Browse to osTicket</h2>
<img src="https://i.imgur.com/d72APDC.png" height="40%" width="40%" alt="extract osticket"/> <img src="https://i.imgur.com/0YaCkqe.png" height="40%" width="40%" alt="extract osticket"/> 
</p>
<p>
<h3>Step 12: Browse to osTicket</h3>

- From IIS, click "Sites"
- "Default Web Site"
- "osTicket"
- Click "Browse *:80" on the right.

Hopefully it was a success and you should see the osTicket image in the browser.


</p>
<br />
<hr>

<p>
<h2>Step 13: Rename ost-config.php and assign permissions</h2>
<img src="https://i.imgur.com/39JNgrH.png" height="80%" width="80%" alt="extract osticket"/> 
</p>
<p>
<h3>Step 13: Rename ost-config.php and assign permissions</h3>

- Navigate to c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- Right Click to Rename file to c:\inetpub\wwwroot\osTicket\include\ost-config.php

- Right click on the file name
- "Properties"
- "Security"
- "Advanced"
- "Disable Inheritance"
- "Remove all Inherited properties from this item"
- Click "Add"
- "Select a Principle" 
- Enter "Everyone" in the object name box
- Click "Check Names"
- "OK"; "Apply";choose "full control"; "ok"


</p>
<br />
<hr>

<p>
<h2>Step 14: Continue osTicket Installation</h2>

- In the Browser, click "Continue" to continue the setup of osTicket
- Enter Name and default email (receives email from customers)



</p>
<br />
<hr>
<p>
<h2>Step 15: Install HeidiSQL</h2>
<img src="https://i.imgur.com/jYtlgwN.png" height="40%" width="40%" alt="HeidiSQL"/> <img src="https://i.imgur.com/vmomahw.png" height="40%" width="40%" alt="HeidiSQL database"/></p>
<p>
<h3>Step 15: Install HeidiSQL</h3>

- From the Installation Files, download and install HeidiSQL
- Click to Open file
- Accept the license agreement and continue to finish installation 
- Within HeidiSQL, Create a new session by clicking on New
- Then assign the username and password: (root); 
- Connect to the session
- Create a database called "osTicket"

</p>
<br />
<hr>
<p>
<h2>Step 16: Finish Setting up osTicket in the Browser</h2>
<img src="https://i.imgur.com/VokWOji.png" height="80%" width="80%" alt="extract osticket"/> 
</p>
<p>
<h3>Step 16: Finish Setting up osTicket in the Browser</h3>

- Continue in the Browser to comlete the osTicket Set up process.
- Write down admin names, emails and passwords for reference
- MySQL database: osTicket
- mySqL Username: root
- MySqL Password: 
- Click "Install Now"

And hopefully your help desk installation is successful
</p>
<br />
<hr>
<p>
<h2>Step 17: Final File Clean Up</h2> 
</p>
<p>
- Delete C:\inetpub\wwwroot\osTicket\setup
- Set Permissions to "Read" only at c:\inetpub/wwwroot/osTicket/include/lost-config.php
</p>
<br />

<hr>


Login page: http://localhost/osTicket/scp/login.php
End User osTicket URL: http://localhost/osTicket/




<hr>


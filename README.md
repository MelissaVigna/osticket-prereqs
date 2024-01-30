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

- Enable Internet Information Services (ISS)
- Install Web Platform Installer
- Install MySequel & Set-Up Username & Password
- Install C++ Redistributable
- Configure Permissions & Install OS Ticket

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/GAufJol.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/KrcvrPL.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/mjHvBgE.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create Virtual Machine in Azure
Create a Resource Group
Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs

Install Software in Virtual Machine
Install/Enable IIS in Windows with CGI & Common HTTP Features
Install PHP Manager for IIS
Install the Rewrite Module

Create the directory C:\PHP
Download PHP 7.3.8 and unzip the contents into C:\PHP

Install VC_redist.x86.exe.
Install MySQL 5.5.62

Open IIS as an Admin
Register PHP from within IIS
Reload IIS (Open IIS, Stop and Start the server)

</p>
<br />

<p>
<img src="https://i.imgur.com/T3TefKK.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install osTicket v1.15.8
Download osTicket
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

</p>
<br />

<p>
<img src="https://i.imgur.com/qKyeItD.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install HeidiSQL
Open Heidi SQL
Create a new session, root/Password1
Connect to the session
Create a database called “osTicket”

Continue Setup In Browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click “Install Now!”

Clean up
•	Delete: C:\inetpub\wwwroot\osTicket\setup
•	Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>
<br />

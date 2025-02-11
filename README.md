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

- Virtual Machine (VM) inside Microsoft Azure 
- Remote Desktop Protocol (RDP) into VM


<h2>Installation Steps</h2>


<p>
</p>
<p>
Within the VM, download the zip file 'os.Ticket-Installation-Files.zip' and right click the application folder and click 'Extract All'.
</p>
<br />

<p>
<img src="https://i.imgur.com/BnnXW98.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install/Enable IIS in Windows with CGI:
  ->World Wide Web Services -> Application Development Features -> [X] CGI
</p>
<br />

<p>
<img src="https://i.imgur.com/GxAGkvx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the 'osTicket-Installation-Files' folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>
<br />


<p>
<img src="https://i.imgur.com/G4COIZf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the 'osTicket-Installation-Files' folder, install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>
<br />


<p>
<img src="https://i.imgur.com/sElk9lp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the directory C:\PHP
</p>
<br />


<p>
<img src="https://i.imgur.com/3qeuoou.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the "osTicket-Installation-Files" folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the "C:\PHP" folder
<br />


<p>
<img src="https://i.imgur.com/bKC3TLy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the "osTicket-Installation-Files" folder, install VC_redist.x86.exe
</p>
<br />


<p>
<img src="https://i.imgur.com/Ubr0Isq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the "osTicket-Installation-Files" folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  - Typical Setup ->
  - Launch Configuration Wizard (after install) ->
  - Standard Configuration ->
  - Username: root
  - Password: root
</p>
<br />

<p>
<img src="https://i.imgur.com/8fyhJ8c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS as an Admin and register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe) and reload IIS (Open IIS, Stop and Start the server)
</p>
<br />

<p>
<img src="https://i.imgur.com/RPENANl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install osTicket v1.15.8
    - From the "osTicket-Installation-Files" folder, unzip "osTicket-v1.15.8.zip" and copy the "unload" folder into the "c:\inetpub\wwwroot"
    - Within "c:\inetpub\wwwroot", Rename "upload" to "osTicket"; Reload IIS (Open IIS, Stop and Start the server)
</p>
<br />

<p>
<img src="https://i.imgur.com/su7IUzB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to sites -> Default -> osTicket; On the right, click "Browse *:80"
</p>
<br />

<p>
<img src="https://i.imgur.com/RAtt096.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Note that some extensions are not enabled.
Go back to IIS, sites -> Default -> osTicket.
Double-click PHP Manager.
Click “Enable or disable an extension”.
Enable: php_imap.dll,
Enable: php_intl.dll,
Enable: php_opcache.dll,
Refresh the osTicket site in your browser, observe the changes

<br />

<p>
<img src="https://i.imgur.com/eZ25qAB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/JppcaV4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Rename: ost-config.php.
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php.
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>
<br />

<p>
<img src="https://i.imgur.com/YzYckhC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

</p>
<br />

<p>
<img src="https://i.imgur.com/UDYoT6N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/EIhCG7p.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue Setting up osTicket in the browser (click Continue).
Name Helpdesk,
Default email (receives email from customers),
Admin User
</p>
<br />

<p>
<img src="https://i.imgur.com/vX8OhV8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the “osTicket-Installation-Files” folder, install HeidiSQL.
Open Heidi SQL,
Create a new session, root/root,
Connect to the session,
Create a database called “osTicket”

</p>
<br />

<p>
<img src="https://i.imgur.com/6gGBZ7O.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/sO1XQRL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/8OO3VWQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue Setting up osTicket in the browser:
MySQL Database: osTicket,
MySQL Username: root,
MySQL Password: root,
Click “Install Now!”

</p>
<br />

<p>
<img src="https://i.imgur.com/iTjtx3h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

</p>
<br />

<p>
<img src="https://i.imgur.com/I9DiUdk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>









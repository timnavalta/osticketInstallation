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

- Windows 11</b> (21H2)

<h2>List of Requirements</h2>

- ### osTicket-Installation-Files.zip (https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)

<h2>Installation Steps</h2>

<p>
<img src="https://imgur.com/YjtqYV0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/LDHEhFc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b> 1. Install / Enable IIS in Windows WITH CGI </b>
</p>
<br />

<p>
<img src="https://i.imgur.com/FscsK9z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<b> 2. From the “osTicket-Installation-Files” folder, Install the PHP Manager for IIS and Rewrite Module </b>
</p>
<br />

<p>
<img src="https://i.imgur.com/nxExZP5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<b> 3. Create the directory C:\PHP </b>

<b> 4. From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 into the “C:\PHP” folder </b>

<b> 5. Install VC_redist.x86.exe </b>
<p>
</p>

<p>
<img src="https://i.imgur.com/0pHFPjp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b> 6. Install MySQL 5.5.62 </b>
(Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> Enter a Username and Password)
</p>
<br />

<p>
<img src="https://i.imgur.com/sqgcOND.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<b> 7. Open IIS as an Admin and register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe) </b>
<p>
Reload IIS (Open IIS, Stop and Start the server)
</p>
<br />

<p>
<img src="https://i.imgur.com/D6Sf64v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b> 8. Install osTicket v1.15.8 </b>

From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”

Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
</p>
<br />

<p>
<img src="https://i.imgur.com/OqB6H5Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b> 9. Go to sites -> Default -> osTicket </b>
  
On the right, click “Browse *:80”
</p>
<br />

<p>
<img src="https://i.imgur.com/HbUTpxR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Note that some extensions are not enabled
<b> 10. Go back to IIS, sites -> Default -> osTicket </b>

Double-click PHP Manager

Click “Enable or disable an extension”

Enable: php_imap.dll

Enable: php_intl.dll

Enable: php_opcache.dll

Refresh the osTicket site in your browser, observe the changes
</p>
<br />

<p>
<img src="https://i.imgur.com/U1rZlvQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b> 11. Rename: ost-config.php </b>

From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<br />

<p>
<img src="https://i.imgur.com/sdpRTdg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b> 12. Assign Permissions: ost-config.php
Disable inheritance -> Remove All 
New Permissions -> Everyone -> All </b>

Continue Setting up osTicket in the browser (click Continue)

Name Helpdesk

Default email (receives email from customers)
</p>
<br />

<p>
<img src="https://i.imgur.com/uKPrmcM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the “osTicket-Installation-Files” folder, install HeidiSQL.
Open Heidi SQL
Create a new session, root/root
Connect to the session
Create a database called “osTicket”

Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”
</p>
<br />

<p>
<img src="https://i.imgur.com/cvERZTR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b> Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php </b>
</p>
<br />

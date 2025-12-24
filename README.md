<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. Click the link below to download the full installation package. <br />

- ### [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11</b> (21H2)

<h2>Installation Steps</h2>

<p>
<b> Enable IIS in Windows WITH CGI </b>

Click the box corresponding "Internet Information Services", then click the drop down box.
</p>
<p>
<img src="https://imgur.com/YjtqYV0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Under the "Application Development Features", select CGI then press OK.
<p>
<img src="https://i.imgur.com/LDHEhFc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />

<p>
<b> From the “osTicket-Installation-Files” folder, Install the PHP Manager for IIS and Rewrite Module </b>

Unzip the “osTicket-Installation-Files”, double-click and Install both the PHP Manager and Rewrite Module.
</p>
<p>
<img src="https://i.imgur.com/FscsK9z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<b> Create the directory C:\PHP </b>

Go to File explorer and click on "This PC" aand look for your C drive. Make a new folder and name it PHP.
</p>
<p>
<img src="https://i.imgur.com/nxExZP5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b> From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 into the “C:\PHP” folder </b>

<b> Install VC_redist.x86.exe </b>
<p>
</p>

<p>
<b> Install MySQL 5.5.62 </b>

Click the mysql-5.5.62. If asked to choose setup type, choose "Typical". Check "Launch the MySQL Instance Configuration Wizard before clicking Finish.

After the installation, the Configuration Wizard page should come out. Use the Standard Configuration then click next until it asks for a username and password.
Enter a username and password and finish the installation.
<img src="https://i.imgur.com/0pHFPjp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<p>
<b> Open IIS as an Admin and register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe) </b>

Open IIS as an Admin and click on PHP Manager, on the next page click "Register new PHP version", locate the PHP executable file and click open then click OK.
Reload IIS (Open IIS, Stop and Start the server)
<img src="https://i.imgur.com/sqgcOND.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<p>
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”

Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
<img src="https://i.imgur.com/D6Sf64v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b> Install osTicket v1.15.8 </b>

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
<b> 13.From the “osTicket-Installation-Files” folder, install HeidiSQL. </b>

Open Heidi SQL

Create a new session, root/root

Connect to the session

Create a database called “osTicket”

<b> 14. Continue Setting up osTicket in the browser </b>

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
<b> 15. Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php </b>
</p>
<br />

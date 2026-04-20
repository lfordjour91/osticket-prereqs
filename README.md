<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - osTicket Installation</h1>
Project shows the configuration of the osTicket system within a Virtual Machine running Windows 10. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure
- Knowledge of: Virtual Machines, Remote Deskto connections, and Web server configuration
- Download installation package for osTicket
- Stable Internet connection


<h2>Installation Steps</h2>

<p>

</p>
<p>
<b>STEP 1: Create Azure Virtual Machine</b>
<ul> 
<li>Go to Microsoft Azure</li>
<li>Navigate to Virtual Machines</li>
<li>Click Create → Azure Virtual Machine</li>
 <ul>
<li>Configuration:</li>
  <ul>
<li>Name: </li>
<li>Image: Windows 10</li>
<li>Size: 4 vCPUs</li>
<li>Username: </li>
<li>Password: </li>
  </ul>
 </ul> 
</ul>
</p>
<br />

<p>

</p>
<p>
 <b>STEP 2: Connect to Remote Desktop</b>
<ul> 
<li>After deployment, click Connect → RDP</li>
<li>Download the RDP file</li>
<li>Open it and log in with:</li>
 <ul>
<li>Username: labuser</li>
<li>Password: osTicketPassword1!</li>
 </ul>
</ul>
</p>
<br />

<p>

</p>
<p>
<b>STEP 3: Download Install Files</b>
<ul>
<li>Inside the VM, download:</li>
[osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)
<li>Extract it to your Desktop</li>
</p>
<br />

<p>
<img width="1779" height="549" alt="Screenshot 2026-04-13 at 3 13 34 PM" src="https://github.com/user-attachments/assets/5d7c95ff-cd12-4ab7-9417-06eba43dff50" />
</p>
<p>
<b>STEP 4: Install IIS with CGI</b>
 <ul>
<li>Open Control Panel → Programs → Turn Windows features on or off</li>
<li>Enable:</li>
  <ul>
<li>Internet Information Services (IIS)</li>
<li>Expand → World Wide Web Services</li>
<li>Expand → Application Development Features</li>
<li>✔️ Check CGI</li>
 </ul>
 </ul>
<br />

<p>
<img width="497" height="376" alt="Screenshot 2026-04-13 at 3 15 11 PM" src="https://github.com/user-attachments/assets/9982796d-ad8a-40b6-8d8e-e480935a698b" />
</p>
<p>
<b>STEP 5: Installed Required Files</b>
 <ul>
<li>From the installation folder:</li>
<li>Install:</li>
  <ul>
<li>PHP Manager for IIS</li>
<li>Rewrite Module</li>
 </ul>
 </ul>
</p>
<br />

<p>
<img width="1415" height="738" alt="Screenshot 2026-04-13 at 3 16 24 PM" src="https://github.com/user-attachments/assets/f06d6d3b-473b-44a8-a899-c5afac46b2c8" />
</p>
<p>
<b>STEP 6: Setup PHP</b>
 <ul>
<li>Create folder</li>
<li>Extract into C:\PHP</li>
 </ul>
</p>
<br />

<p>
<img width="745" height="164" alt="Screenshot 2026-04-13 at 3 19 01 PM" src="https://github.com/user-attachments/assets/3e72f870-5fff-4b64-9842-02c8de37fb53" />
</p>
<p>
<b>STEP 7: Install other components</b>
<ul>
 <li>Install:</li>
 <ul>
 <li>VC_redist.x86.exe</li>
<li> MySQL (mysql-5.5.62-win32.msi)</li>
 </ul>
<li>MySQL Setup:</li>
 <ul>
<li>Choose Typical Setup</li>
<li>Run Configuration Wizard:</li>
<li>Standard Configuration</li>
  <ul>
<li>Username: root</li>
 <li>Password: root</li>
  </ul>
 </ul>
</ul>
</ul>
</p>
<br />

<p>
<img width="385" height="483" alt="Screenshot 2026-04-13 at 3 20 10 PM" src="https://github.com/user-attachments/assets/da400eda-3eb1-4c6b-8feb-3b31d9c0a9dc" />
</p>
<p>
<b>STEP 8: Configure IIS & PHP</b>
Open IIS Manager (Run as Admin)
Go to:
PHP Manager
Click:
Register new PHP version
Select:
C:\PHP\php-cgi.exe
</p>
<br />

<p>
<img width="850" height="568" alt="Screenshot 2026-04-13 at 3 22 03 PM" src="https://github.com/user-attachments/assets/ca01f1d8-7cf0-4230-95cd-9598d5b044f2" />
</p>
<p>
<b>STEP 9: Restart IIS</b>
-In IIS:
 -Click Stop
 -Then Start
</p>
<br />

<p>
<img width="282" height="320" alt="Screenshot 2026-04-13 at 3 24 57 PM" src="https://github.com/user-attachments/assets/2f0a6613-87ff-4622-96c0-841ca2f7c762" />
</p>
<p>
<b>STEP 10: Install osTicket</b>
Extract:
osTicket-v1.15.8.zip
Copy the upload folder into:
C:\inetpub\wwwroot
Rename:
upload → osTicket
<br />

<p>
 <img width="624" height="375" alt="Screenshot 2026-04-13 at 3 25 33 PM" src="https://github.com/user-attachments/assets/e986baba-3ae4-4706-974d-d884a8aa533b" />
</p>
<p>
<b>STEP 11: Restart IIS Again</b>
Repeat:
Stop → Start IIS
</p>
<br />

<p>
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />
</p>
<p>
<b>STEP 12: Open osTicket in Browser</b>
In IIS:
Go to:
Sites → Default Web Site → osTicket
Click:
*Browse :80
</p>
<br />

<p>
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />
</p>
<p>
<b>STEP 13: Enable PHP Extensions</b>
Go back to IIS → osTicket
Open PHP Manager
Click:
Enable or disable extensions
Enable:
php_imap.dll
php_intl.dll
php_opcache.dll
Refresh browser
</p>
<br />

<p>
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />
</p>
<p>
<b>STEP 14: Configure osTicket File</b>
Navigate to:
C:\inetpub\wwwroot\osTicket\include\
Rename:
ost-sampleconfig.php → ost-config.php
</p>
<br />

<p>
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />
</p>
<p>
<b>STEP 15: Set Permissions</b>
Right-click ost-config.php
Go to Properties → Security
Disable inheritance
Remove all permissions
Add:
Everyone → Full Control
</p>
<br />

<p>
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />
</p>
<p>
<b>STEP 16: osTicket Setup (cont.)</b>
Fill out:
Helpdesk Name
Default Email
<br />

<p>
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />
</p>
<p>
<b>STEP 17: Setup Database</b>
Install and open HeidiSQL
Create new session:
Username: root
Password: root
Create database:
osTicket
</p>
<br />

<p>
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />
</p>
<p>
<b>STEP 18: Connect osTicket to Database</b>
Back in browser:
MySQL Database: osTicket
Username: root
Password: root
Click:
Install Now
</p>
<br />

<p>
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />
</p>
<p>
<b>STEP 19: Access osTicket</b>
Admin Login:
http://localhost/osTicket/scp/login.php
End User Portal:
http://localhost/osTicket/
</p>
<br />

<p>
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />
</p>
<p>
<b>RESULTS</b>
You now have a fully functional osTicket Help Desk System running on an Azure VM
</p>
<br />

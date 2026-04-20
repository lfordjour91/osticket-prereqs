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
<p>
<img width="1920" height="1080" alt="Artboard 1" src="https://github.com/user-attachments/assets/8d3bee4f-de8d-4d59-acdf-52820671604b" />
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
</ul>
</p>
<br />

<p>

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

</p>
<p>
<b>STEP 8: Configure IIS & PHP</b>
<ul>
<li>Open IIS Manager (Run as Admin)</li>
<li>Go to:</li>
 <ul>
<li>PHP Manager</li>
<li>Click:</li>
 </ul>
<li>Register new PHP version</li>
<li>Select:C:\PHP\php-cgi.exe</li>
</ul>
</p>
<br />

<p>

</p>
<p>
<b>STEP 9: Restart IIS</b>
<ul>
 <li>In IIS:</li>
 <ul>
 <li>Click Stop</li>
 <li>Then Start</li>
 </ul>
</ul>
</p>
<br />

<p>

</p>
<p>
<b>STEP 10: Install osTicket</b>
<ul>
 <li>Extract: osTicket-v1.15.8.zip</li>
 <li>Copy the upload folder into: C:\inetpub\wwwroot</li>
 <ul>
 <li>Rename:</li>
 <li>upload → osTicket</li>
 </ul>
</ul>
<br />

<p>

</p>
<p>
<b>STEP 11: Restart IIS Again</b>
 <ul>
<li>Repeat:</li>
<li>Stop → Start IIS</li>
 </ul>
</p>
<br />

<p>

</p>
<p>
<b>STEP 12: Open osTicket in Browser</b>
 <ul>
<li>In IIS:</li>
  <ul>
<li>Go to:</li>
   <ul>
<li>Sites → Default Web Site → osTicket</li>
<li>Click:</li>
<li>*Browse :80</li>
   </ul>
  </ul>
 </ul>
</p>
<br />

<p>
<
</p>
<p>
<b>STEP 13: Enable PHP Extensions</b>
<ul>
 <li>Go back to IIS → osTicket</li>
 <ul>
<li>Open PHP Manager</li>
<li>Click:</li>
<li>Enable or disable extensions</li>
<li>Enable:</li>
  <ul>
<li>php_imap.dll</li>
<li>php_intl.dll</li>
<li>php_opcache.dll</li>
  </ul>
<li>Refresh browser</li>
 </ul>
</ul>
</p>
<br />

<p>

</p>
<p>
<b>STEP 14: Configure osTicket File</b>
 <ul>
<li>Navigate to: C:\inetpub\wwwroot\osTicket\include\</li>
<li>Rename: ost-sampleconfig.php → ost-config.php</li>
 </ul>
</p>
<br />

<p>

</p>
<p>
<b>STEP 15: Set Permissions</b>
 <ul>
<li>Right-click ost-config.php</li>
<li>Go to Properties → Security</li>
  <ul>
<li>Disable inheritance</li>
<li>Remove all permissions</li>
<li>Add:</li>
   <ul>
<li>Everyone → Full Control</li>
   </ul>
  </ul>
 </ul>
</p>
<br />

<p>

</p>
<p>
<b>STEP 16: osTicket Setup (cont.)</b>
<ul>
 <li>Fill out:</li>
 <ul>
<li>Helpdesk Name</li>
<li>Default Email</li>
 </ul>
</ul>
<br />

<p>

</p>
<p>
<b>STEP 17: Setup Database</b>
<ul>
 <li>Install and open HeidiSQL</li>
 <ul>
<li>Create new session:</li>
  <ul>
<li>Username: root</li>
<li>Password: root</li>
  </ul>
<li>Create database:</li>
  <ul>
<li>osTicket</li>
  </ul>u
 </ul>
</ul>
</p>
<br />

<p>
</p>
<p>
<b>STEP 18: Connect osTicket to Database</b>
 <ul>
<li>Back in browser:</li>
  <ul>
<li>MySQL Database: osTicket</li>
<li>Username: root</li>
<li>Password: root</li>
  </ul>
<li>Click: <strong>Install Now</strong></li>
 </ul>
</p>
<br />

<p>

</p>
<p>
<b>STEP 19: Access osTicket</b>
 <ul>
<li>Admin Login:</li>
  <ul>
<li>http://localhost/osTicket/scp/login.php</li>
  </ul>
<li>End User Portal:</li>
  <ul>
<li>http://localhost/osTicket/</li>
  </ul>
 </ul>
</p>
<br />

<p>

</p>
<p>
<b>RESULTS</b>
You now have a fully functional osTicket Help Desk System running on an Azure VM
</p>
<br />

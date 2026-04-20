<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - osTicket Installation</h1>
Project shows the configuration of the osTicket system within a Virtual Machine running Windows 10. <br />



<h2>Environments and Technologies Used</h2>

- <a href="https://portal.azure.com/">Microsoft Azure (Virtual Machines/Compute)</a>
- Remote Desktop <Windows App)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)

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
<li>Click Create → Virtual Machine</li>
 <ul>
<li>Configuration:</li>
  <ul>
<li>Name: osTicket_VM</li>
<li>Image: Windows 10 (22H2) *if you don't see it, select "See All Images"</li>
<li>Size: 2-4 vCPUs</li>
<li>Username: labuser</li>
<li>Password: osTicketPassword1</li>
  </ul>
  <li>Click "Review + Create" → Click "Create"</li>
  <li>WAit for the Virtual Machine to be created and start running</li>
 </ul> 
</ul>
</p>
<p>
<img width="1920" height="1080" alt="Artboard 1" src="https://github.com/user-attachments/assets/8d3bee4f-de8d-4d59-acdf-52820671604b" />
</p>
<br />

<p>
 <b>STEP 2: Connect to Remote Desktop</b>
<ul> 
<li>Open Windows App Application, click "+" → Add PC</li>
<li>Copy the Public IP address for the Virtual Machine</li>
 <li>Paste the Public IP into Windows App</li>
<li>Open it and log in with:</li>
 <ul>
<li>Username: labuser</li>
<li>Password: osTicketPassword1!</li>
 </ul>
</ul>
</p>
<p>
<img width="1920" height="1080" alt="Artboard 2" src="https://github.com/user-attachments/assets/50d2f6a9-2ff4-4ecf-a7a8-f9bb10331762" />
</p>
<br />

<p>
<b>STEP 3: Download Install Files</b>
<ul>
<li>Inside the VM, download:</li>
<a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD">osTicket-Installation-Files.zip</a>
<li>Extract it to your Desktop</li>
</ul>
</p>
<p>

</p>
<br />

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
<p>
<img width="1920" height="1080" alt="Artboard 4" src="https://github.com/user-attachments/assets/8026854b-7339-47bf-9594-3d030ba3ef7f" />
</p>
<br />

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
<p>
<img width="1920" height="1080" alt="Artboard 5" src="https://github.com/user-attachments/assets/f83679c8-949f-45b2-b263-b83cb9086521" />
</p>
<br />


<p>
<b>STEP 6: Setup PHP</b>
<ul>
<li>Create folder</li>
 <ul>
  <li>Name the new folder "PHP"</li>
 </ul>
<li>Extract file "php-7.3.8-nts-Win32-VC15-x86" from osTicket Install folder into C:\PHP</li>
</ul>
</p>
<p>
<img width="1920" height="1080" alt="Artboard 6" src="https://github.com/user-attachments/assets/34e4bf78-5f93-4d23-aa17-d3348381d06b" />
</p>
<br />

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
<p>
<img width="1920" height="1080" alt="Artboard 7" src="https://github.com/user-attachments/assets/782cafee-6276-4eb8-b8f6-e0b65aa72851" />
</p>
<br />

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
<p>
<img width="1920" height="1080" alt="Artboard 8" src="https://github.com/user-attachments/assets/851e751d-86e4-450a-a476-e59b9fd8177e" />
</p>
<br />

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
<p>
<img width="1920" height="1080" alt="Artboard 9" src="https://github.com/user-attachments/assets/99e862c6-7ea0-4ed9-a5fa-f18df6484442" />
</p>
<br />

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
<p>
<img width="1920" height="1080" alt="Artboard 10" src="https://github.com/user-attachments/assets/97c9622a-f5bb-4650-ad2f-09e14dc1e666" />
</p>
<br />

<p>
<b>STEP 11: Restart IIS Again</b>
 <ul>
<li>Repeat:</li>
<li>Stop → Start IIS</li>
 </ul>
</p>
<p>
<img width="1920" height="1080" alt="Artboard 11" src="https://github.com/user-attachments/assets/5ce104ca-35b3-4d60-b0dc-966cfb28f1ef" />
</p>
<br />

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
<p>
<img width="1920" height="1080" alt="Artboard 12" src="https://github.com/user-attachments/assets/a8b0ea74-d7af-4b47-9618-1b7528e2a6e1" />
</p>
<br />

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
<p>
<img width="1920" height="1080" alt="Artboard 13" src="https://github.com/user-attachments/assets/7e41d9bd-6f24-4c35-aedb-659ceb0f0410" />
</p>
<br />

<p>
<b>STEP 14: Configure osTicket File</b>
 <ul>
<li>Navigate to: C:\inetpub\wwwroot\osTicket\include\</li>
<li>Rename: ost-sampleconfig.php → ost-config.php</li>
 </ul>
</p>
<p>
<img width="1920" height="1080" alt="Artboard 14" src="https://github.com/user-attachments/assets/32a4594f-4a4d-4037-8a11-998f7c25f5f7" />
</p>
<br />

<p>
<b>STEP 15: Set Permissions</b>
 <ul>
<li>Right-click ost-config.php</li>
<li>Go to Properties → Security → Advanced</li>
  <ul>
<li>Disable inheritance</li>
<li>Remove all permissions</li>
<li>Add:</li>
   <ul>
    <li>Click "Select A Principal"</li>
<li>Type "Everyone" → Press "Check Names" → Click "Add"</li>
    <li> Select "Full Control" → Press "Apply"</li>
   </ul>
  </ul>
 </ul>
</p>
<p>
<img width="1920" height="1080" alt="Artboard 15" src="https://github.com/user-attachments/assets/1c3c4a95-b765-4b28-85f4-0c4a5f4e904e" />
</p>
<br />

<p>
<b>STEP 16: osTicket Setup (cont.)</b>
<ul>
 <li>Fill out:</li>
 <ul>
<li>Helpdesk Name</li>
<li>Default Email</li>
  <li>Admin User</li>
 </ul>
 *Defualt Email & Admin Email must be different*
</ul>
<p>
<img width="1920" height="1080" alt="Artboard 16" src="https://github.com/user-attachments/assets/4059f9fe-4d5a-4696-8a25-4a99c1c02e2d" />
</p>
<br />

<p>
<b>STEP 17: Setup Database</b>
<ul>
 <li>Install and open HeidiSQL</li>
 <ul>
<li>Create new session:</li>
  <ul>
<li>Username: root</li>
<li>Password: root</li>
   <li>Click "Open"</li>
  </ul>
<li>Create database:</li>
  <ul>
<li>osTicket</li>
  </ul>
 </ul>
</ul>
</p>
<p>
<img width="1920" height="1080" alt="Artboard 17" src="https://github.com/user-attachments/assets/07461967-7c7d-4ab6-b894-182bc324b5b2" />
</p>
<br />

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
<p>
<img width="1920" height="1080" alt="Artboard 18" src="https://github.com/user-attachments/assets/b238b9a5-1942-474e-b4f8-8e883a3b4580" />

</p>
<br />

<p>
<b>STEP 19: Access osTicket</b>
 <ul>
<li>Admin Login:</li>
  <ul>
<li><a href="http://localhost/osTicket/scp/login.php">Admin Login</a></li>
  </ul>
<li>End User Portal:</li>
  <ul>
<li><a href="http://localhost/osTicket/">End User Portal</a></li>
  </ul>
 </ul>
</p>
<br />

<p>
<img width="1920" height="1080" alt="Artboard 19" src="https://github.com/user-attachments/assets/fd530dc2-ff5d-4866-9bc8-c6149afc865e" />

</p>
<p>
<b>RESULTS</b>
You now have a fully functional osTicket Help Desk System running on an Azure VM
</p>
<br />

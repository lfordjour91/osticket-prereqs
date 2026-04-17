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
<img width="1735" height="803" alt="Screenshot 2026-04-13 at 3 06 10 PM" src="https://github.com/user-attachments/assets/9c4b2e37-cba2-41a9-9bb1-71fcf1d31237" />
</p>
<p>
<b>STEP 1: Create Azure Virtual Machine</b>
 
-Go to Microsoft Azure
-Navigate to Virtual Machines
-Click Create → Azure Virtual Machine
Configuration:
-Name: 
-Image: Windows 10
-Size: 4 vCPUs
-Username: 
-Password: 
</p>
<br />

<p>
<img width="1250" height="633" alt="Screenshot 2026-04-13 at 3 09 32 PM" src="https://github.com/user-attachments/assets/014d4c61-ad94-4795-a2b4-68e08b0c0704" />
</p>
<p>
 <b>STEP 2: Connect to Remote Desktop</b>
 
-After deployment, click Connect → RDP
-Download the RDP file
-Open it and log in with:
-Username: labuser
-Password: osTicketPassword1!
</p>
<br />

<p>
<img width="340" height="292" alt="Screenshot 2026-04-13 at 3 10 46 PM" src="https://github.com/user-attachments/assets/e864adba-f60b-4e06-a4d2-7a0bfd5e347f" />
</p>
<p>
<b>STEP 3: Download Install Files</b>

-Inside the VM, download:
-osTicket-Installation-Files.zip
-Extract it to your Desktop
</p>
<br />

<p>
<img width="1779" height="549" alt="Screenshot 2026-04-13 at 3 13 34 PM" src="https://github.com/user-attachments/assets/5d7c95ff-cd12-4ab7-9417-06eba43dff50" />
</p>
<p>
<b>STEP 4: Install IIS with CGI</b>
 
-Open Control Panel → Programs → Turn Windows features on or off
Enable:
-Internet Information Services (IIS)
Expand → World Wide Web Services
Expand → Application Development Features
✔️ Check CGI
<br />

<p>
<img width="497" height="376" alt="Screenshot 2026-04-13 at 3 15 11 PM" src="https://github.com/user-attachments/assets/9982796d-ad8a-40b6-8d8e-e480935a698b" />
</p>
<p>
<b>STEP 5: Installed Required Files</b>
-From the installation folder:
Install:
-PHP Manager for IIS
-Rewrite Module
</p>
<br />

<p>
<img width="1415" height="738" alt="Screenshot 2026-04-13 at 3 16 24 PM" src="https://github.com/user-attachments/assets/f06d6d3b-473b-44a8-a899-c5afac46b2c8" />
</p>
<p>
<b>STEP 6: Setup PHP</b>
-Create folder
-Extract into C:\PHP
 
</p>
<br />

<p>
<img width="745" height="164" alt="Screenshot 2026-04-13 at 3 19 01 PM" src="https://github.com/user-attachments/assets/3e72f870-5fff-4b64-9842-02c8de37fb53" />
</p>
<p>
<b>STEP 7: Install other components</b>
-Install:
 -VC_redist.x86.exe
 -MySQL (mysql-5.5.62-win32.msi)
-MySQL Setup:
-Choose Typical Setup
-Run Configuration Wizard:
 -Standard Configuration
 -Username: root
 -Password: root
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
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />

</p>

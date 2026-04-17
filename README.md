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
Internet Information Services (IIS) was installed and enabled on the virtual machine. During setup, CGI was specifically enabled under World Wide Web Services → Application Development Features to support PHP processing.
</p>
<br />

<p>
<img width="1779" height="549" alt="Screenshot 2026-04-13 at 3 13 34 PM" src="https://github.com/user-attachments/assets/5d7c95ff-cd12-4ab7-9417-06eba43dff50" />
</p>
<p>
Required dependencies were installed, including PHP Manager for IIS, the IIS URL Rewrite Module, and the Visual C++ Redistributable package. A directory named C:\PHP was then created, and PHP 7.3.8 was extracted into this folder to prepare for integration with IIS.
</p>
<br />

<p>
<img width="497" height="376" alt="Screenshot 2026-04-13 at 3 15 11 PM" src="https://github.com/user-attachments/assets/9982796d-ad8a-40b6-8d8e-e480935a698b" />
</p>
<p>
MySQL 5.5 was installed using the typical setup configuration. The configuration wizard was launched after installation, and a standard configuration was selected with the root username and password set for database access.
</p>
<br />

<p>
<img width="1415" height="738" alt="Screenshot 2026-04-13 at 3 16 24 PM" src="https://github.com/user-attachments/assets/f06d6d3b-473b-44a8-a899-c5afac46b2c8" />
</p>
<p>
IIS was opened with administrative privileges, and PHP was registered using PHP Manager by pointing to the php-cgi.exe file located in the C:\PHP directory. IIS was then restarted to apply the configuration changes.
</p>
<br />

<p>
<img width="745" height="164" alt="Screenshot 2026-04-13 at 3 19 01 PM" src="https://github.com/user-attachments/assets/3e72f870-5fff-4b64-9842-02c8de37fb53" />
</p>
<p>
The osTicket installation files were extracted, and the upload folder was copied into the C:\inetpub\wwwroot directory. The folder was then renamed to osTicket, and IIS was restarted again to ensure the application was properly recognized.
</p>
<br />

<p>
<img width="385" height="483" alt="Screenshot 2026-04-13 at 3 20 10 PM" src="https://github.com/user-attachments/assets/da400eda-3eb1-4c6b-8feb-3b31d9c0a9dc" />
</p>
<p>
Within IIS, PHP Manager was used to enable required PHP extensions, including php_imap.dll, php_intl.dll, and php_opcache.dll. The osTicket site was refreshed in the browser to confirm that all required extensions were successfully enabled.
</p>
<br />

<p>
<img width="850" height="568" alt="Screenshot 2026-04-13 at 3 22 03 PM" src="https://github.com/user-attachments/assets/ca01f1d8-7cf0-4230-95cd-9598d5b044f2" />
</p>
<p>
The sample configuration file ost-sampleconfig.php was renamed to ost-config.php. File permissions were then modified by disabling inheritance and granting full control access to all users to allow osTicket to complete its setup.
</p>
<br />

<p>
<img width="282" height="320" alt="Screenshot 2026-04-13 at 3 24 57 PM" src="https://github.com/user-attachments/assets/2f0a6613-87ff-4622-96c0-841ca2f7c762" />
</p>
<p>
HeidiSQL was installed and used to connect to the MySQL server. A new database named osTicket was created to store the application’s data.
</p>
<br />

<p>
 <img width="624" height="375" alt="Screenshot 2026-04-13 at 3 25 33 PM" src="https://github.com/user-attachments/assets/e986baba-3ae4-4706-974d-d884a8aa533b" />
</p>
<p>
The osTicket setup was completed through a web browser by navigating to http://localhost/osTicket. The helpdesk name, default email, and database credentials were entered, and the installation was finalized by clicking “Install Now.”
</p>
<img width="813" height="637" alt="Screenshot 2026-04-13 at 11 19 22 AM" src="https://github.com/user-attachments/assets/ee46dc60-987e-48d3-9a0d-60cd0945445b" />

</p>

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
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
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
A Windows 10 virtual machine was created in Microsoft Azure with 4 vCPUs and configured with login credentials. The system was then accessed using Remote Desktop to begin the setup process.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The osTicket-Installation-Files.zip folder was downloaded onto the virtual machine and extracted onto the desktop. These files were used throughout the installation process to configure osTicket and its dependencies.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Internet Information Services (IIS) was installed and enabled on the virtual machine. During setup, CGI was specifically enabled under World Wide Web Services → Application Development Features to support PHP processing.
</p>
<br />

<p>
Required dependencies were installed, including PHP Manager for IIS, the IIS URL Rewrite Module, and the Visual C++ Redistributable package. A directory named C:\PHP was then created, and PHP 7.3.8 was extracted into this folder to prepare for integration with IIS.
</p>
<br />

<p>
MySQL 5.5 was installed using the typical setup configuration. The configuration wizard was launched after installation, and a standard configuration was selected with the root username and password set for database access.
</p>
<br />

<p>
IIS was opened with administrative privileges, and PHP was registered using PHP Manager by pointing to the php-cgi.exe file located in the C:\PHP directory. IIS was then restarted to apply the configuration changes.
</p>
<br />

<p>
The osTicket installation files were extracted, and the upload folder was copied into the C:\inetpub\wwwroot directory. The folder was then renamed to osTicket, and IIS was restarted again to ensure the application was properly recognized.
</p>
<br />

<p>
Within IIS, PHP Manager was used to enable required PHP extensions, including php_imap.dll, php_intl.dll, and php_opcache.dll. The osTicket site was refreshed in the browser to confirm that all required extensions were successfully enabled.
</p>
<br />

<p>
The sample configuration file ost-sampleconfig.php was renamed to ost-config.php. File permissions were then modified by disabling inheritance and granting full control access to all users to allow osTicket to complete its setup.
</p>
<br />

<p>
HeidiSQL was installed and used to connect to the MySQL server. A new database named osTicket was created to store the application’s data.
</p>
<br />

<p>
The osTicket setup was completed through a web browser by navigating to http://localhost/osTicket. The helpdesk name, default email, and database credentials were entered, and the installation was finalized by clicking “Install Now.”
</p>
</p>

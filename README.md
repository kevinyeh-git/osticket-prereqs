<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket within Azure VM - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure account with subscription
- Azure Virtual Machine with Windows 10, 4vCPUs
- Unzipped <a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD">osTicket Installation Files </a>
- Enable Internet Information Services (IIS)
- Install WebPlatform Installer
- Install MySQL
- Setup Username/Password
- Install C++ Redistributable
- Configure Permissions and install OSTicket

<h2>Installation Steps</h2>

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_5.png" height="70%" width="70%" alt="Enabling IIS and CGI"/>
</p>
<p>
From the Windows Search Bar, open Control Panel, navigate to "Programs", and open "Turn Windows features on or off". Within "Windows Features", check "Internet Information Services". Then, expand "World Wide Web Services" as well as "Application Development Features" and check "CGI". Then click "OK".
</p>
<br />

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_3.png" height="50%" width="50%" alt="PHP Manager Install"/>
</p>
<p>
Next we need to install "PHP Manager for IIS", this is essential for osTicket to work since osTicket runs off of PHP. From within the unzipped osTicket installation folder, run "PHPManagerForIIS_V1.5.0" and click "Next". Go through the installer, checking "I agree" and clicking "Next" until the installer is finished.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

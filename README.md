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
- Internet Information Services (IIS)
- WebPlatform Installer
- MySQL
- C++ Redistributable

<h2>Installation Steps</h2>

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_5.png" height="60%" width="60%" alt="Enabling IIS and CGI"/>
</p>
<p>
From the Windows Search Bar, open Control Panel, navigate to "Programs", and open "Turn Windows features on or off". Within "Windows Features", check "Internet Information Services". Then, expand "World Wide Web Services" as well as "Application Development Features" and check "CGI". Then click "OK".
</p>
<br />

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_3.png" height="50%" width="50%" alt="PHP Manager and rewrite and VC redist Install"/>
</p>
<p>
Next we need to install "PHP Manager for IIS", this is essential for osTicket to work since osTicket runs off of PHP. From within the unzipped osTicket installation folder, run "PHPManagerForIIS_V1.5.0" and click "Next". Go through the installer, checking "I agree" and clicking "Next" until the installer is finished. Do the same thing with the "rewrite_amd64_en-US" installer as well as the "VC_redist.x86" installer.
</p>
<br />

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, right click the zipped "php-7.3.8-nts-Win32-VC15-x86" file and select "Extract all". In the new window, select "Browse" and navigate to your Windows C: drive. Right click and create a new folder and name it "PHP". Select the newly created "PHP" folder and extract to that folder.
</p>
<br />

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_6.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now back in the unzipped osTicket installation folder, run the "mysql-5.5.62-win32" installer. This will install MySQL, a backend database that will store a majority of our data. In the installer, click "Next" and check any "I accept" boxes until we reach the "Choose Setup Type" section. We will select "Typical Setup" and then click "Install". Finally, click "Finish". A configuration window should appear.
</p>
<br />

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_7.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the configuration settings, select "Standard Configuration" and click "Next". Ignore the next page and click "Next" again. This next page is very important to not misstype. Input your chosen root password and retype the same password in the next box to confirm. Then click "Next", "Execute", and "Finish".
</p>
<br />

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_8.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open "Internet Information Services (IIS) Manager" as Administrator. Navigate to "PHP Manager" and select "Register new PHP version". Then click on the three dots to browse. Open our created "PHP" folder and select "php-cgi.exe". Next in the PHP Manager menu, select "Enable or disable an extension" and enable these three extensions: "php_imap.dll", "php_intl.dll", and "php_opcache.dll". To enable, just right click the extension and select "Enable".
</p>
<br />

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will now extract the second zipped file in our unzipped osTicket installation folder, "osTicket-v1.15.8". Click "Browse" and extract to this file address: C://Windows(C:)/inetpub/wwwroot. Then in the folder we just extracted to, "wwwroot", rename the folder named "upload" to "osTicket". Within this folder, open the folder named "include" and find the file named "ost-sampleconfig.php". Rename this file to "ost-config.php".
</p>
<br />

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_10.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next we must assign permissions to the file we just renamed. Right click the "ost-config.php" file and select properties. Navigate to the "Security" tab and select Advanced. Click "Disable inheritance" and then "Remove all inherited permissions from this object." Then, select "Add", then "Select a principal", and enter the object name "Everyone" and select "OK". Then check "Full Control" and hit "OK" and "Apply" to apply these new permissions
</p>
<br />

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_11.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Finally we will run the "HeidiSQL_12.3.0.6589_Setup" installer. HeidiSQL will be the connector between our SQL database and osTicket. Continue through the installer clicking "Next" and "Install" until finished. Select "Skip" in the new window. In the next new window, select "New" and then type in your previously selected root password into the password input box. Then select "Open". In the new window, create a new database by right clicking "Unnamed" and selecting "Create new" and then "Database". Name this database "osTicket".
</p>
<br />

<p>
<img src="https://github.com/kevinyeh-git/osticket-prereqs/blob/main/Screenshot_12.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next go to the local webpage and the osTicket installer should appear. Continue through until you reach the basic installation page. Fill out the System settings and Admin user information. Then in Database settings, name the MySQL Database "osTicket", the MySQL Username "root", and MySQL Password to your chosen password from before. Then Click "Install Now". If everything was correctly followed, osTicket should now be installed!
</p>
<br />

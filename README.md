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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- IIS
- PHP Manager
- URL Rewrite for IIS
- C++ Redistributable x86
- MySql
- HeidiSQL

<h2>Installation Steps</h2>

For this project, I created a virtual machine via Microsoft Azure using Windows 10 as the operating system. There are a handfull of requirements to install in order for osTicket to function properly.

<p>
<img src="https://i.imgur.com/mdu44fs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before we install osTicket, we must install and enable IIS in windows with CGI. We can achieve this by going to the windows search bar and type "Control Panel". Then we will go to Programs->Programs and Features->Turn Windows features on or off. We will find IIS and enable it, expand it, expand Application Development Features, and enable CGI. 

</p>
<br />
<p>
<img src="https://i.imgur.com/rkHcmpx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We must download the files in the image above and listed on the "prerequisites". We follow the instructions of each file to install the programs succesfully.
</p>
<br />

<p>
<img src="https://i.imgur.com/nuzTgBv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After installing MySQL, we will open IIS as an admin->Register PHP from within IIS. 
When doing anything with IIS, it is recommended that we click on restart so that we can see the changes.
</p>
<br />

<p>
<img src="https://i.imgur.com/oH3HGIg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once we install osTicket, we will have and osTicket zip folder in the downloads. We will click on this folder and see that there is an "upload" folder. We will drag this "upload" folder into C:\inetpub\wwwroot. Then we will rename the "upload" folder to "osTicket". 
</p>
<br />

<p>
<img src="https://i.imgur.com/cr7GiAU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will go back to IIS, click on the server, and restart again. We then will go to Sites->Defualt Web Site->osTicket and then click on Browse *:80 (http) on the right side of the directory. This will allow us to successfully access osTicket in the browser, but we will need to enable some features for improvements.
</p>
<br />

<p>
<img src="https://i.imgur.com/tdQvN9E.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To enable these feautres, we will go back to IIS and go to [our server]->Sites->Default Web Site->osTicket->PHP Manager->Enable or Disable and extension. We will enable: php_imap.dll, php_intl.dll, php_opcache.dll

</p>
<br />

<p>
<img src="https://i.imgur.com/gp4Ra40.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We are going to locate C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename it to C:\inetpub\wwwroot\osTicket\include\ost-config.php. We then will assign permissions to this file, First we will siable inheritence by right clicking on the file->properties->security->advanced->disable inheritance->remove all inherited permissions from this object. Then we will add permissions by going to select principle and type "everyone" under "Enter the object name to select". Check names, and then check the box that says "Full Control" click on "apply" and then "ok".

</p>
<br />

<p>
<img src="https://i.imgur.com/3rDmgsH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will continue to setting up osTicket by putting in the information that we are being asked. Before clicking "install now" we will go to HeidiSQL and create a new database called "osTicket". We will type the name of this database where it says "mySQL Database" on the browser.  We have successfully accessed osTicket, now we will delete C:\inetpub\wwwroot\osTicket\setup and then we will set permissions to "read" only on C:\inetpub\wwwroot\osTicket\include\ost-config.php.

</p>
<br />

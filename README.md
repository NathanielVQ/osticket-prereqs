<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. The project demonstrates deploying osTicket in a Microsoft Azure virtual machine environment while configuring IIS, PHP, MySQL, and database connectivity.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- osTicket
- MySQL
- HeidiSQL
- PHP
- PHP Manager

<h2>Operating Systems Used</h2>

- Windows 11 for Desktop
- Windows 10 Virtual Machine (22H2)

<h2>List of Prerequisites</h2>

- Azure Subscription
- Azure Virtual Machine
    - OS: Windows 10
    - vCPUs: 2
- Remote Desktop Connection
- osTicket Installation Files

<h2>Installation Steps</h2>

### Step 1: Create and Configure the Azure Virtual Machine

<p>
<img width="1837" height="846" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Logged into Microsoft Azure and created a Resource Group named "osTicket" to organize all resources related to the lab environment.
</p>
<br />

<p>
<img width="1873" height="924" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Created a Virtual Network named "ticket-vnet" inside the osTicket resource group. This virtual network allows the virtual machine and services to communicate properly within Azure.
</p>
<br />

<p>
<img width="1874" height="881" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Created a Windows 10 Virtual Machine named "ost-vm" inside the osTicket resource group. Selected the appropriate region and configured the virtual machine settings.
</p>
<br />

<p>
<img width="1142" height="542" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
For the operating system image, selected Windows 10 Enterprise 22H2 x64 Gen2. The virtual machine size selected was Standard D2s v3 with 2 vCPUs.
</p>
<br />

<p>
<img width="1870" height="879" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Configured the administrator login credentials for the virtual machine.

    - Username: labuser
    - Password: Password1

These credentials are only used for the lab environment.
</p>
<br />

<p>
<img width="1870" height="882" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Verified the correct Virtual Network was selected under the Networking tab before reviewing and creating the virtual machine deployment.
</p>

### Step 2: Connect to the Virtual Machine Using Remote Desktop

<p>
<img width="976" height="566" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Opened Remote Desktop Connection on the local computer and used the public IP address of the Azure virtual machine to connect remotely using the administrator credentials created during setup.
</p>
<br />

### Step 3: Download osTicket Installation Files

<p>
<img width="362" height="156" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="135" height="221" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Inside the virtual machine, downloaded the osTicket Installation Files package and extracted the folder contents onto the desktop for easier access during installation.
</p>
<br />

### Step 4: Install and Enable IIS with CGI

<p>
<img width="1118" height="628" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="1121" height="626" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="412" height="369" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Opened Control Panel and navigated to Programs -> Programs and Features -> Turn Windows Features On or Off.
</p>
<br />

<p>
<img width="1123" height="630" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="450" height="425" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Enabled Internet Information Services (IIS) and enabled CGI under World Wide Web Services -> Application Development Features. CGI support is required for PHP functionality within IIS.
</p>

<p>
<img width="918" height="947" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Verified IIS installation by entering the loopback address 127.0.0.1 into the web browser and confirming the IIS default page loaded successfully.
</p>
<br />

### Step 5: Install Required Components

<p>
<img width="1118" height="631" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Installed PHP Manager for IIS from the osTicket Installation Files folder. PHP Manager allows IIS to manage PHP configurations.
</p>
<br />

<p>
<img width="1122" height="631" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Installed the IIS URL Rewrite Module which is required for proper osTicket URL functionality.
</p>
<br />

<p>
<img width="1122" height="634" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Created a folder named PHP directly on the C drive at C:\PHP to store the PHP runtime files.
</p>
<br />

<p>
<img width="1033" height="737" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Extracted the PHP files into the C:\PHP directory from the osTicket installation package.
</p>
<br />

<p>
<img width="1129" height="638" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Installed the Microsoft Visual C++ Redistributable package required for PHP runtime dependencies.
</p>
<br />

<p>
<img width="1118" height="629" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Installed MySQL Server which will host the osTicket database and store all ticketing information and user data.
</p>
<br />

<p>
<img width="488" height="386" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="492" height="381" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Selected Typical Setup during the MySQL installation process and enabled the MySQL Configuration Wizard after installation completed.
</p>
<br />

<p>
<img width="494" height="375" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="494" height="376" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Selected Standard Configuration during MySQL setup and continued with the default configuration settings.
</p>
<br />

<p>
<img width="496" height="377" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="495" height="382" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Configured the MySQL root account credentials.

    - Username: root
    - Password: root

These credentials are only for the lab environment.
</p>
<br />

### Step 6: Configure IIS and PHP

<p>
<img width="1421" height="750" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Opened Internet Information Services (IIS) Manager as Administrator from the Windows search bar.
</p>
<br />

<p>
<img width="1420" height="751" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="1423" height="744" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Opened PHP Manager inside IIS and registered the PHP executable located at:

    C:\PHP\php-cgi.exe

This allows IIS to process PHP files properly.
</p>
<br />

<p>
<img width="1423" height="749" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="206" height="691" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Restarted IIS services to apply all PHP configuration changes to the web server.
</p>
<br />

### Step 7: Install osTicket

<p>
<img width="1121" height="627" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="1124" height="820" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Extracted the osTicket ZIP installation package and copied the upload folder into:

    C:\inetpub\wwwroot

The upload folder was renamed to osTicket.
</p>
<br />

<p>
<img width="1421" height="747" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="916" height="924" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Reloaded IIS and navigated to Sites -> Default Web Site -> osTicket -> Browse *:80 to launch the osTicket installer inside the browser.
</p>
<br />

<p>
<img width="1419" height="744" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="1419" height="749" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="497" height="255" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Enabled the required PHP extensions:
    
    - php_imap.dll
    - php_intl.dll
    - php_opcache.dll

These extensions are required for osTicket functionality.
</p>
<br />

<p>
<img width="1125" height="632" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Renamed:

    ost-sampleconfig.php

to:

    ost-config.php

inside the osTicket include directory.
</p>
<br />

<p>
<img width="915" height="595" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="912" height="589" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="766" height="517" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Modified file permissions for ost-config.php by disabling inheritance and assigning Everyone -> Full Control permissions so osTicket could update the configuration file during installation.
</p>
<br />

### Step 8: Configure HeidiSQL and Create Database

<p>
<img width="1122" height="629" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="778" height="606" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Installed HeidiSQL and launched the application to connect to the MySQL database server.
</p>
<br />

<p>
<img width="683" height="479" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Created a new database session using the MySQL root credentials configured earlier.
</p>
<br />

<p>
<img width="931" height="590" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Created a new database named "osTicket" which will store all help desk application data and ticketing information.
</p>
<br />

### Step 9: Complete osTicket Installation

<p>
<img width="816" height="910" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Completed the osTicket setup wizard by entering the Help Desk Name, Administrator account information, and Database configuration settings.
</p>
<br />

<p>
<img width="816" height="433" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Configured the database connection settings:

    - MySQL Database: osTicket
    - MySQL Username: root
    - MySQL Password: root

Clicked Install to finalize the deployment.
</p>
<br />

<p>
<img width="914" height="722" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="932" height="592" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
osTicket successfully installed and automatically created the required database tables inside MySQL.
</p>
<br />

### Step 10: Access osTicket

<p>
<img width="898" height="918" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
<img width="899" height="564" alt="image" src="YOUR-IMAGE-LINK-HERE"/>
</p>

<p>
Verified successful deployment by accessing both the Admin Panel and End User Portal.

    - Admin Login:
      http://localhost/osTicket/scp/login.php

    - End User Portal:
      http://localhost/osTicket/
</p>
<br />

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
<img width="2557" height="870" alt="image" src="https://github.com/user-attachments/assets/4e54ecde-369a-4614-a1a3-968f38d24add" />
</p>

<p>
Logged into Microsoft Azure and created a Resource Group named "osTicket" to organize all resources related to the lab environment.
</p>
<br />

<p>
<img width="2547" height="867" alt="image" src="https://github.com/user-attachments/assets/7689fd21-d49e-4862-a86a-c002d41cd7f6" />
</p>

<p>
Created a Virtual Network named "osTicket-vnet" inside the osTicket resource group. This virtual network allows the virtual machine and services to communicate properly within Azure.
</p>
<br />

<p>
<img width="1874" height="881" alt="image" src="https://github.com/user-attachments/assets/eb63a889-70ab-4c95-9fbd-92365ffe4529" />
</p>

<p>
Created a Windows 10 Virtual Machine named "ost-vm" inside the osTicket resource group. Selected the appropriate region and configured the virtual machine settings.
</p>
<br />

<p>
<img width="826" height="752" alt="image" src="https://github.com/user-attachments/assets/6e2ea18c-6acf-4961-b9e4-99bfaa756b3e" />
</p>

<p>
For the operating system image, select Windows 10 Enterprise 22H2 x64 Gen2. The virtual machine size selected was Standard D2s v3 with 2 vCPUs.
</p>
<br />

<p>
<img width="852" height="582" alt="image" src="https://github.com/user-attachments/assets/94c813bc-14a4-4311-80c1-de04fd175de6" />
</p>

<p>
Configured the administrator login credentials for the virtual machine.

    - Username: labuser
    - Password: Password1

These credentials are only used for the lab environment.
</p>
<br />

<p>
<img width="847" height="626" alt="image" src="https://github.com/user-attachments/assets/13a8c432-ab0c-47e3-9b1c-0717443086a5" />
</p>

<p>
Verified the correct Virtual Network was selected under the Networking tab before reviewing and creating the virtual machine.
</p>

### Step 2: Connect to the Virtual Machine Using Remote Desktop

<p>
<img width="982" height="602" alt="image" src="https://github.com/user-attachments/assets/dd4dca63-1a94-46b1-b9f4-bb5300003d08" />
</p>

<p>
Opened Remote Desktop Connection on the local computer and used the public IP address of the Azure virtual machine to connect remotely using the administrator credentials created during setup.
</p>
<br />

### Step 3: Download osTicket Installation Files

<p>
<img width="396" height="121" alt="image" src="https://github.com/user-attachments/assets/694bb585-fb3a-46b5-a4b6-11d8732c6f9e" />
<img width="967" height="421" alt="image" src="https://github.com/user-attachments/assets/1a046ccf-1710-451f-9aa9-a7831130f97c" />
</p>

<p>
Inside the virtual machine, I downloaded the osTicket Installation Files package and extracted its contents to the desktop for easier access during installation.
</p>
<br />

### Step 4: Install and Enable IIS with CGI

<p>
<img width="1022" height="567" alt="image" src="https://github.com/user-attachments/assets/0260a3ad-883d-4c61-985f-341cfceca842" />
<img width="1027" height="582" alt="image" src="https://github.com/user-attachments/assets/c05688af-077e-4d84-9eba-435746e801a2" />
</p>

<p>
Opened Control Panel and navigated to Programs -> Programs and Features -> Turn Windows Features On or Off.
</p>
<br />

<p>
<img width="500" height="337" alt="image" src="https://github.com/user-attachments/assets/4b2edd18-b061-42ee-aa67-dfde2f6aeeaf" />
<img width="381" height="332" alt="image" src="https://github.com/user-attachments/assets/40d82bbc-48ad-4459-bf61-65118a824415" />
</p>

<p>
Enabled Internet Information Services (IIS) and enabled CGI under World Wide Web Services -> Application Development Features. CGI support is required for PHP functionality within IIS.
</p>

<p>
<img width="792" height="620" alt="image" src="https://github.com/user-attachments/assets/df322961-1c89-4935-95c2-8a8fe0cafacc" />
</p>

<p>
Verified IIS installation by entering the loopback address 127.0.0.1 into the web browser and confirming the IIS default page loaded successfully.
</p>
<br />

### Step 5: Install Required Components

<p>
<img width="730" height="422" alt="image" src="https://github.com/user-attachments/assets/e7e40664-83f4-4519-bca0-9efd705e91a9" />
</p>

<p>
Installed "PHPManagerForIIS_V1.5.0" for IIS from the osTicket Installation Files folder. PHP Manager allows IIS to manage PHP configurations.
</p>
<br />

<p>
<img width="762" height="430" alt="image" src="https://github.com/user-attachments/assets/cebcfb31-4f5f-4a33-92a9-aa954d638c1e" />
</p>

<p>
Installed the IIS URL Rewrite Module, which is required for proper osTicket URL functionality.
</p>
<br />

<p>
<img width="611" height="582" alt="image" src="https://github.com/user-attachments/assets/aadb104f-1948-4ccc-a2b0-457ed2476581" />
</p>

<p>
Created a folder named PHP directly on the C drive at C:\PHP to store the PHP runtime files.
</p>
<br />

<p>
<img width="1072" height="476" alt="image" src="https://github.com/user-attachments/assets/7d40b620-225a-4f24-8a00-21acd8e9f452" />
</p>

<p>
Extracted the "php-7.3.8-nts-Win32-VC15-x86" files into the C:\PHP directory from the osTicket installation package.
</p>
<br />

<p>
<img width="450" height="582" alt="image" src="https://github.com/user-attachments/assets/113f8fe0-3c26-4998-940b-20226d3992d0" />
</p>

<p>
From the "osTicket-Installation-Files" folder, install "VC_redist.x86". This will satisfy the runtime dependencies necessary for PHP to function correctly within the IIS environment.
</p>
<br />

<p>
<img width="456" height="581" alt="image" src="https://github.com/user-attachments/assets/7db1fad8-1dac-4d5c-bccc-d0bd676bbbb9" />
</p>

<p>
Installed MySQL Server, which will host the osTicket database and store all ticketing information and user data.
</p>
<br />

<p>
<img width="456" height="352" alt="image" src="https://github.com/user-attachments/assets/cfde8ee2-9d71-48f4-b83c-224477f58e0e" />
<img width="447" height="347" alt="image" src="https://github.com/user-attachments/assets/46056953-b467-490e-8752-8da93a145c5c" />
</p>

<p>
Selected Typical Setup during the MySQL installation process and enabled the MySQL Configuration Wizard after installation completed.
</p>
<br />

<p>
<img width="460" height="341" alt="image" src="https://github.com/user-attachments/assets/390179e9-1d0d-4f1e-aa2c-5a096756c8e2" />
<img width="451" height="342" alt="image" src="https://github.com/user-attachments/assets/277c03f7-d3ac-4ea9-9c83-958017413306" />
</p>

<p>
Selected Standard Configuration during MySQL setup and continued with the default configuration settings.
</p>
<br />

<p>
<img width="451" height="346" alt="image" src="https://github.com/user-attachments/assets/d57ab494-6e6e-4134-ab68-fd2d88d07884" />
<img width="455" height="342" alt="image" src="https://github.com/user-attachments/assets/7b313a34-5c11-40cb-ab55-6b8b8ce1045e" />
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
<img width="720" height="382" alt="image" src="https://github.com/user-attachments/assets/0790c6e2-c487-46eb-b8f1-3b9cea4f34f6" />
</p>

<p>
Opened Internet Information Services (IIS) Manager as Administrator from the Windows search bar.
</p>
<br />

<p>
<img width="852" height="627" alt="image" src="https://github.com/user-attachments/assets/a0e38780-7435-4769-bea9-ac748d6bad01" />
<img width="852" height="642" alt="image" src="https://github.com/user-attachments/assets/9b273026-0201-491a-a0f5-07a8e256aefd" />
</p>

<p>
Opened PHP Manager inside IIS and registered the PHP executable located at:

    C:\PHP\php-cgi.exe

This allows IIS to process PHP files properly.
</p>
<br />

<p>
<img width="846" height="547" alt="image" src="https://github.com/user-attachments/assets/a67d36a2-0307-4d9c-a27a-f0b9d3ec8ff3" />
</p>

<p>
Restarted IIS services to apply all PHP configuration changes to the web server.
</p>
<br />

### Step 7: Install osTicket

<p>
<img width="1102" height="695" alt="image" src="https://github.com/user-attachments/assets/47495368-a9b4-43ad-83e8-f5024d6c6090" />
<img width="857" height="975" alt="image" src="https://github.com/user-attachments/assets/0e2badc2-8f7c-4f00-b0d7-c8e053da3562" />
<img width="690" height="582" alt="image" src="https://github.com/user-attachments/assets/a1958761-4e77-4376-a707-294cc4734867" />

</p>

<p>
Extracted the osTicket ZIP installation package and copied the upload folder into:

    C:\inetpub\wwwroot

The upload folder was renamed to osTicket.
</p>
<br />

<p>
<img width="852" height="517" alt="image" src="https://github.com/user-attachments/assets/db1138ac-fc23-4a40-9849-2bd701a6eaef" />
<img width="857" height="476" alt="image" src="https://github.com/user-attachments/assets/674027b7-d396-4e58-8a3a-e879daf0d967" />
<img width="752" height="672" alt="image" src="https://github.com/user-attachments/assets/2efeb7c5-6c7d-4453-a71c-29d7c7e944cd" />    
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

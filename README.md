# osTicket - Prerequisites and Installation

<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket Installation Lab</h1>

<p>
This project demonstrates the prerequisites, installation, and configuration process of the open-source help desk ticketing system <strong>osTicket</strong>. The lab was completed using a Windows virtual machine environment and includes the setup of IIS, PHP, MySQL, and osTicket.
</p>

---

<h2>Project Summary</h2>

<p>
This tutorial walks through the complete installation process of osTicket in a Windows environment. The project demonstrates how to prepare a server environment, install required dependencies, configure a MySQL database, and complete the web-based osTicket setup.
</p>

<h3>Languages Used</h3>

- PowerShell
- PHP

<h3>Environments Used</h3>

- Microsoft Azure (Virtual Machines)
- Windows 10 (21H2)
- Windows 11

<h3>Technologies / Applications Used</h3>

- osTicket
- Internet Information Services (IIS)
- MySQL
- PHP Manager
- HeidiSQL
- Remote Desktop

---

<h2>List of Prerequisites</h2>

- Microsoft Azure Account
- Windows Virtual Machine
- Remote Desktop Connection
- IIS Enabled
- osTicket Installation Files
- MySQL Database Server
- PHP Runtime

---

<h2>Installation Steps</h2>

<h3>Step 1: Prepare the Windows Environment</h3>

<p align="center">
  <img width="832" height="612" alt="iisstep1" src="https://github.com/user-attachments/assets/9525a6a6-2605-4a75-8055-2c070f5cc53c" />
</p>

<p>
The first step in the installation process is preparing the Windows environment. Internet Information Services (IIS) is enabled to allow the machine to host web applications. Additional dependencies such as PHP and MySQL are also installed to support osTicket functionality.
</p>

<br />

<h3>Step 2: Install osTicket Files</h3>

<p align="center">
  <img width="902" height="786" alt="Osinstall-packets" src="https://github.com/user-attachments/assets/dd1074df-3c19-4fad-af46-f8fac9f58374" />
</p>

<p>
The osTicket installation package is downloaded and extracted into the IIS web server directory. Configuration files are renamed, and the proper permissions are assigned so the installer can successfully access the required files during setup.
</p>

<br />

<h3>Step 3: Configure the MySQL Database</h3>

<p align="center">
  <img width="947" height="437" alt="mysql-setup" src="https://github.com/user-attachments/assets/98f1233d-25f2-4ae3-9aa5-8dad5de2f096" />
</p>

<p>
A MySQL database is created to store osTicket data. During installation, the database name, username, and password are entered into the osTicket setup wizard to establish the database connection.
</p>

<br />

<h3>Step 4: Complete the osTicket Installation</h3>

<p align="center">
  <img width="810" height="757" alt="osinstall-final" src="https://github.com/user-attachments/assets/811d9037-8c24-4a98-a4c4-088049ef5773" />
</p>

<p>
After entering the required system and database information, the osTicket installer finalizes the setup process. Once completed, the help desk portal becomes accessible through the browser, allowing administrators to manage users and support tickets.
</p>

<br />

---

<h2>Conclusion</h2>

<p>
This project successfully demonstrated the installation and configuration of osTicket using a Windows-based environment. The lab provided hands-on experience with web server configuration, database management, and help desk deployment technologies commonly used in IT support environments.
</p>

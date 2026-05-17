# osticket-prereqs
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
- Windows 11

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

<p>
<img width="832" height="612" alt="iisstep1" src="https://github.com/user-attachments/assets/9525a6a6-2605-4a75-8055-2c070f5cc53c" />
</p>
<p>
Before installing osTicket, the Windows machine must be prepared by enabling IIS and installing the required PHP and MySQL components. This creates the web server environment needed to host the ticketing system.
</p>
<br />

<p>
<img width="902" height="786" alt="Osinstall-packets" src="https://github.com/user-attachments/assets/dd1074df-3c19-4fad-af46-f8fac9f58374" />
</p>
<p>
The osTicket installation package is downloaded and extracted into the IIS web root directory. The required configuration files are renamed and permissions are adjusted so the installer can access them properly.
</p>
<br />

<p>
<img width="947" height="437" alt="mysql-3-png" src="https://github.com/user-attachments/assets/98f1233d-25f2-4ae3-9aa5-8dad5de2f096" />
</p>
<p>
A MySQL database is created for osTicket. During setup, the installer connects the application to the database using the server name, database name, username, and password.
</p>
<br />

<p>
<img width="810" height="757" alt="osinstall-4-" src="https://github.com/user-attachments/assets/811d9037-8c24-4a98-a4c4-088049ef5773" />
</p>
<p>
After entering the required system and database information, the osTicket installer finalizes the setup. The help desk portal becomes accessible through the browser, allowing ticket management and user administration.
</p>
<br />

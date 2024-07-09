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

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


<h2>Installation Steps</h2>


1.) The first thing you are going to want to do is create a virtual machine by going to https://portal.azure.com/. Setup your virtual machine with Windows 10 Pro, version 22H2. Note, you will want to create a virtual machine with atleast 2 vcpus and 16 gbs of memory.

2.) After creating your virtual machine, connect to it using the public IP address assigned to it. Use the Remote Desktop Connection app to establish the connection.



<img width="372" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/4962df1a-e2e2-41fd-8547-9310a1e31721">

<br/>

<p>
<img width="301" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/6e99fd57-046b-4083-b9f3-1092f399084e">
</p>



3.) After connecting to your virtual machine open up the link to the downloads on Microsoft edge and open the Control Panel. From there, navigate to Programs and select "Turn Windows features on or off."

<img width="592" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/b3993f00-453c-4769-a55e-f18b2539c45b">
<p>
<img width="542" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/0af696de-8614-42e4-bb7d-0ed675a17ece">
</p>

<p>
4.) You need to install and enable IIS in Windows, including CGI and Common HTTP Features.
Navigate to World Wide Web Services -> Application Development Features, and check [X] CGI and [X] Common HTTP Features.
</p>

<p>
<img width="127" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/b87077fc-492c-4ce3-982b-efad8876e9e6">
</p>

5.) To verify that IIS is installed and enabled, open a browser and navigate to 127.0.0.1. You should see a page that looks similar to this.
<p>
<img width="663" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/f39b95bf-7101-496c-ba95-95df168d955b">
</p>

<p>
6.) With IIS now enabled, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from the installation files. Follow the install wizard to complete the installation.
</p>

7.) Next, download and install the Rewrite Module (rewrite_amd64_en-US.msi) from the installation files.

8.) Then you'll download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the provided installation files. In the MySQL setup wizard, agree to the terms, choose a Typical installation, and proceed with the installation. Once installed, launch the Configuration Wizard. Opt for Standard Configuration and select Install As Windows Service, ensuring that Launch the MySQL Server automatically is checked. For credentials, use the username "root" and the password "Password1" for the sake of the tutorial.
<p>

<img width="206" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/9d938cf5-3f49-41db-9efe-fe6d4e03f1a2">


</p>

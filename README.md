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

9.) Now you will want to open IIS as a Administrator and register PHP from the PHP Manager by clicking on register new PHP version and navigating to the C-Drive, PHP folder, and selecting php-cgi. Make sure you restart the IIS after.

<p>
<img width="506" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/17624455-13d0-4ded-ab8c-91e80f104c6c">
</p>

<p>
  <img width="505" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/a50ee284-1692-4a8c-88a8-85e16e5e2804">

</p>

10.) Next you will want to download osTicket from the installation Files and drag the upload folder from within it to This PC -> C-Drive -> inetpub -> wwwroot. Then rename the upload folder to osTicket.

<p>
  <img width="680" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/208ce3cf-98ac-44a0-9e1f-056ffe98e600">

</p>

11.) Going back to IIS on the left side you will click on sites -> default -> osTicket and then "Browse .*80" on the right side. The following tab should open up in the browser.

<p>
  <img width="507" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/7dee97c4-d9bd-41e5-9ea8-7c198a4fc8af">
</p>

<p>
  <img width="397" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/df8fabdf-0179-4795-8689-673290579d13">

</p>

12.) Some of the extensions we need are not enabled so go back to IIS, sites -> Default -> osTicket. Double-click on the PHP manager -> enable or disable an extension and then enable php_imap.dll, php_intl.dll, and php_opcache.dll.

<img width="506" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/ccdf6321-22f5-41a9-84ca-d5267e00678c">

13.) Rename the file from C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php.

14.) Then right click on the ost-config.php and select properties -> security -> advanced -> disable inheritance -> remove all inherited permissions from this object. Then click on add -> select a principal -> add in everyone and click check names -> ok -> select full control -> apply. It should look like the screenshot below.

<p>
  <img width="145" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/55b32df4-0d28-45be-863f-e3fc5e8d6cc1">

</p>

15.) Next we will continue setting up osTicket in the browser by clicking continue. Create a name for the help desk, a default email, and create an admin user making sure that you remember all the information for later use.

<p>
  <img width="685" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/653c1b1c-bb6c-4904-8cae-2ad901639951">

</p>

16.) Now install HeidiSQL from the installation files and follow the installation wizard. Open heidiSQL, click on new enter the password you used to install MySQL, and hit open. Then right-click unnamed -> create new -> database -> name it osTicket -> ok.

<p>
  <img width="274" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/c91ad344-4940-4c98-a8e2-0f06b4671ef8">

</p>

<p>
  <img width="373" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/3a47630c-870f-492d-8158-26e8bb5d255e">

</p>

17.) Go back to the osTicket on the browser and go to the database setting. Put osTicket for the database name, root for the username, and your MySQL password. Then install osTicket on your VM.

<p>
  <img width="272" alt="image" src="https://github.com/JacobKnittle/osticket-prerequisites/assets/124555008/0637dba6-0277-41f1-8c52-4ddd14e303da">

</p>

18.) To clean up, we are going to delete C:\inetpub\wwwroot\osTicket\setup and set the permissions for C:\inetpub\wwwroot\osTicket\include\ost-config.php to "Read" only by right-clicking -> properties -> security -> everyone and make sure only read and read & execute are selected.

That concludes the initial setup and configuration of osTicket. If you want to continue to post-installation configuration you can click here https://github.com/JacobKnittle/osTicket-Post-Install-Config.

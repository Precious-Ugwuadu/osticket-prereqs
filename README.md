# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Set up and log into the virtual machine.
- Install the required software on IIS (Internet Information Services).
- Configure IIS to recognize PHP.
- Set up osTicket settings.
- Install osTicket and adjust permissions as needed.


<h2>Installation Steps</h2>

<p>
  
![image](https://github.com/user-attachments/assets/e7f2b3b0-0e4d-4530-9c9b-cc132be909c8) 

Firstly, I started by creating an Azure Virtual Machine with Windows 10, 4 vCPUs. 

![image](https://github.com/user-attachments/assets/1fd90667-60e2-4e43-b782-5953af95c2f2)


</p>
<p>
Once the VM was ready, I copied its public IP address and used Remote Desktop Connection to securely log in and manage the system.
</p>
<br />

<p>

</p>
<p> 

</p>
<br />
  
![image](https://github.com/user-attachments/assets/4353eef0-5574-43ec-9812-4da8d5a451a2)

Inside the virtual machine (named osticket-vm), I downloaded the file called osTicket-Installation-Files.zip and extracted its contents to my desktop. This will create a folder named osTicket-Installation-Files. The files inside this folder are needed to install osTicket and its required software components. 

osTicket runs on a web browser, so it requires a web browser and a database to be installed and configured.  

![image](https://github.com/user-attachments/assets/23784e29-466b-44ae-a85c-a34df6844d05)

Next, I  installed  IIS on Windows with CGI support by typing 127.0.0.1 in the web browser, and the above image opened up. This shows that the computer is now a web server, although it is not hosting anything.

![image](https://github.com/user-attachments/assets/4ed53d50-2594-4a2e-8fd7-250b15b495e1)

Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from the “osTicket-Installation-Files” folder. Because osTicket runs on PHP, I have to install it to make it work. This is a requirement.

How to:

Open the “osTicket-Installation-Files” folder > Double-click PHPManagerForIIS_V1.5.0.msi > follow the installation wizard to complete the setup.

![image](https://github.com/user-attachments/assets/210c95b5-2cf3-4a57-88fa-718ed4f26565)

From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

HOW TO:

- Navigate to the “osTicket-Installation-Files” folder on your system.

- Locate the file named rewrite_amd64_en-US.msi — this is the installer for the IIS URL Rewrite Module.

- Double-click the file to launch the installer.

- In the setup wizard, click Next, accept the license terms, and click Install.

- Once the installation is complete, click Finish.

- Restart IIS (using iisreset in Command Prompt) to apply the changes.

✅ The IIS Rewrite Module is now installed and ready to use.

Next, I created the directory C:\PHP. 

HOW TO:

- Open File Explorer.

- Go to Local Disk (C:).

- Right-click inside the window and select New > Folder.

- Name the folder PHP.


![image](https://github.com/user-attachments/assets/f02907d0-3482-42ad-9aa2-8a324c7b8e2d)

From the “osTicket-Installation-Files” folder, I installed VC_redist.x86.exe. 

To install VC_redist.x86.exe from the “osTicket-Installation-Files” folder:

Open the “osTicket-Installation-Files” folder > Locate VC_redist.x86.exe > Double-click the file to launch the installer > In the setup window, accept the license terms > Click Install and wait for the process to complete > Click Finish once installation is done.

✅ The Visual C++ Redistributable is now installed.

![image](https://github.com/user-attachments/assets/0412c45c-0100-4726-aea9-30cee39fbe07)

From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> Username: root -> Password: root (setting both user name and password as "root" is bad in real life, but i used it to keep things simple for this lab).

Next, I will  open IIS as an Administrator by clicking Start > typing IIS or Internet Information Services (IIS) Manager > Right-click it and select “Run as administrator.”

Next, I registered PHP in IIS. In IIS Manager > click on your server name in the left panel > Double-click PHP Manager > Click “Register new PHP version.”

Browse to and select:
makefile
Copy
Edit
C:\PHP\php-cgi.exe

Click OK to register PHP.

Next,  Reload IIS (Stop and Start the Server). In IIS Manager > right-click the server name (top level) > Click Stop, then right-click again and click Start.

✔️ PHP is now registered, and IIS has been reloaded.


![image](https://github.com/user-attachments/assets/3adce0b2-ebcc-4d39-90ec-f09839811b77)

Install osTicket v1.15.8
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

HOW TO:

✅ 1. Unzip the osTicket Files > Go to the “osTicket-Installation-Files” folder > Right-click osTicket-v1.15.8.zip and select Extract All > After extraction, open the extracted folder and locate the “upload” folder.

✅ 2. Copy the “upload” Folder to IIS Root > Navigate to C:\inetpub\wwwroot > Paste the “upload” folder there.

✅ 3. Rename the Folder > In C:\inetpub\wwwroot, right-click the “upload” folder > Select Rename, and change it to “osTicket”.

✔️ osTicket files are now ready under C:\inetpub\wwwroot\osTicket.

![image](https://github.com/user-attachments/assets/86e15da7-876e-4863-9d04-9f78cfbdb426)

![image](https://github.com/user-attachments/assets/3bfd24ae-2582-45bc-85a9-d47ca7d425cd)

Allowing everyone full control is not good, but for the sake of this lab, we can use it.

![image](https://github.com/user-attachments/assets/e557139f-fd95-41c7-8d93-3de2ae366930)

![image](https://github.com/user-attachments/assets/eac3a4a6-1a7f-46ce-9cd5-9c1fccc3e23a)

![image](https://github.com/user-attachments/assets/b9b62bc7-125f-4375-a548-e6217241a283)

![image](https://github.com/user-attachments/assets/942a6bd6-bcba-4f56-abff-b587d4e78f57)

![image](https://github.com/user-attachments/assets/145532f8-3841-4e25-9e7c-b50a9df43d9c)

This is where I can log in as an actual admin user 

![image](https://github.com/user-attachments/assets/c73777be-4c09-49f8-9586-a2f3d2dc8023)

This is my ticketing system
</p>
<p> 

</p>
<br />

<p>

</p>
<p>


  Lab Summary: Setting Up osTicket on an Azure VM

- Create a Windows 10 Virtual Machine on Azure named osticket-vm and log in using Remote Desktop.

- Download and unzip the osTicket-Installation-Files folder on the VM’s desktop — this contains everything needed for the setup.

- Install IIS with CGI, and enable required features like PHP Manager and Rewrite Module.

- Set up PHP and MySQL by creating a PHP folder, unzipping PHP 7.3.8 into it, and installing MySQL with username and password as root.

- Configure IIS to recognize PHP, restart IIS, and install osTicket by moving the upload folder to the web root and renaming it to osTicket.

- Enable required PHP extensions and rename the sample config file. Set the correct permissions on it.

- Finish setup in the browser by providing Helpdesk details and connecting to the MySQL database using HeidiSQL.

- Test osTicket by visiting the login and end-user URLs.

- Clean up by deleting the setup folder and restricting config file permissions.
  
</p>
<br />

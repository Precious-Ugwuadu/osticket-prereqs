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

![image](https://github.com/user-attachments/assets/1fd90667-60e2-4e43-b782-5953af95c2f2)


</p>
<p>
I created a virtual machine (VM) in the Microsoft Azure portal by setting it up with the needed options like name, size, and login details. Once the VM was ready, I copied its public IP address and used Remote Desktop Connection to securely log in and manage the system.
</p>
<br />

<p>

</p>
<p> 
Inside the virtual machine (named osticket-vm), I downloaded the file called osTicket-Installation-Files.zip and extracted its contents to my desktop. This will create a folder named osTicket-Installation-Files. The files inside this folder are needed to install osTicket and its required software components. 
</p>
<br />
  
![image](https://github.com/user-attachments/assets/4353eef0-5574-43ec-9812-4da8d5a451a2)

osTicket runs on a web browser so it requires a web browser and a database to be installed and configured.  

![image](https://github.com/user-attachments/assets/23784e29-466b-44ae-a85c-a34df6844d05)

I typed 127.0.0.1 in the web browser, and this opened up. This shows that the computer is now a web server, although it is not hosting anything.

![image](https://github.com/user-attachments/assets/4ed53d50-2594-4a2e-8fd7-250b15b495e1)

Because osTicket runs on PHP, I have to install it to make it work. This is a requirement.

![image](https://github.com/user-attachments/assets/210c95b5-2cf3-4a57-88fa-718ed4f26565)

![image](https://github.com/user-attachments/assets/f02907d0-3482-42ad-9aa2-8a324c7b8e2d)

![image](https://github.com/user-attachments/assets/0412c45c-0100-4726-aea9-30cee39fbe07)






</p>
<p> 
Inside 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

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

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

![image](https://github.com/user-attachments/assets/3adce0b2-ebcc-4d39-90ec-f09839811b77)

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

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket - Setup and Installation
This tutorial walks through how to setup and install the open source osTicket help desk ticketing system.<br />

# Environments and Technologies Used

- <a href="https://azure.microsoft.com/en-us"> Microsoft Azure (Virtual Machines/Compute)
- <a href="https://support.microsoft.com/en-us/windows/how-to-use-remote-desktop-5fe128d5-8fb1-7a23-3b8a-41e636865e8c"> Remote Desktop
- Internet Information Services (IIS)

# Operating System Used
- Windows 11 24h2 Pro

# Overview of Deployment and Phases
- Phase 1-25

  # Deployment and Phases

  ## Phase 1
  - Create an Azure VM machine within your Microsoft Azure portal
  <img width="800" height="800" alt="1" src="https://github.com/user-attachments/assets/bd2533b8-36a1-4ae1-9d38-7c9f326dd5d2" />

  ## Phase 2
  - Once created ensure the VM has Windows 11 and 4 vCPUS, and also make a new resource group as seen below
  <img width="800" height="800" alt="2" src="https://github.com/user-attachments/assets/1447b63c-162a-467e-80aa-d1062a7c633b" />

  ## Phase 3
  - Log In to the VM as seen below, make sure to use the public IPv4 address covered in black on the right of the photo
  - Also you will have to use the username and pass you created previously in phase 2 when trying to connect
  <img width="800" height="800" alt="3" src="https://github.com/user-attachments/assets/ae4c5cbe-8083-4d1f-8216-b62ed6bdd954" />

  ## Phase 4
  - Once your in copy and paste this link https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0 into your Microsoft Edge Browser and dowload the file and extract it all within your file explorer
  <img width="800" height="800" alt="phase 4" src="https://github.com/user-attachments/assets/5037054b-b48a-4b2f-8b01-eff9a851376a" />

  ## Phase 5
  - Now go to Control Panel> Programs and Features > Turn Windows Features on or off > Internet Information Services > World Wide Web Services > Application Development Featurs > [X] CGI > click ok and let it finish and exit
  <img width="800" height="800" alt="Screenshot 2025-09-22 175612" src="https://github.com/user-attachments/assets/ed3aa915-0116-4720-9f3b-bf3d09adaf34" />

  ## Phase 6
  - From the osTicket-Installation-Files folder install the PHP Manager for IIS and the Rewrite Module ( Not the Zips)
  <img width="800" height="800" alt="Phase 6" src="https://github.com/user-attachments/assets/68a9d830-876c-48c5-80b4-bd74fdf61c86" />

  ## Phase 7
  - Create the directory C:\PHP create a new folder> name it PHP within your C drive
  - From the osTicket-Installation-Files folder unzip PHP 7.3.8 into the C:\PHP folder
  <img width="800" height="800" alt="Screenshot 2025-09-22 180630" src="https://github.com/user-attachments/assets/7d1b649d-9c3f-447f-99d9-fc64143cd6f9" />

  ## Phase 8
  - From the osTicket-Installation-Files folder install VC_redist.x86.exe
  <img width="800" height="800" alt="Screenshot 2025-09-22 180749" src="https://github.com/user-attachments/assets/3ea4177c-1450-4806-914a-804a86b7b4ff" />

  ## Phase 9
  - (A) From osTicket-Installation-Files folder install MySQL 5.5.62 > Typical Setupp > Launch Config Wizard > Standard Config
  <img width="800" height="800" alt="Screenshot 2025-09-22 181031" src="https://github.com/user-attachments/assets/4132e173-12b7-4b5b-8450-85b996b86c4a" />
  - (B) In the Standard Config portion for your Username: root and Password: root use these two to easily remember what they are
  <img width="800" height="800" alt="Phase 9 (2)" src="https://github.com/user-attachments/assets/4690e8b7-3136-4327-a28f-5376ffb4c461" />

## Phase 10
- Open IIS as an Admin and register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
<img width="800" height="800" alt="Screenshot 2025-10-13 151013" src="https://github.com/user-attachments/assets/ad2feb6c-5fbd-4c99-9528-a623d1843f31" />

## Phase 11
- Within IIS reload it by opening IIS and stopping the server and then starting the server
<img width="800" height="800" alt="Screenshot 2025-10-13 151628" src="https://github.com/user-attachments/assets/8eb54a2a-2419-492c-a4c9-eac4a863f65f" />

## Phase 12
- Install osTicket v1.15.8 by going to to the "osTicket-Installation-Files" folder unzip the "osTicket-v1.15.8" zip and copy the "upload" folder into the "c:\inetpub\wwwroot" and rename it "osTicket"
<img width="800" height="800" alt="Screenshot 2025-10-13 151646" src="https://github.com/user-attachments/assets/8e27aee7-34c1-4352-82ad-99b4a3357b31" />

## Phase 13
- Reload IIS (Open IIS, Stop and Start the server
<img width="800" height="800" alt="Phase 11" src="https://github.com/user-attachments/assets/6b112a74-ec52-4388-be2a-0d8a9d7a543f" />

## Phase 14
- Go to Sites -> default -> osTicket and on the far right click "Browse *:80"
<img width="800" height="800" alt="Phase 14" src="https://github.com/user-attachments/assets/1bf23f50-3829-413f-a011-27575326175f" />

## Phase 15
- After pulling up osTicket you note that some extensions are not enabled within osTicket
<img width="800" height="800" alt="Screenshot 2025-10-13 151848" src="https://github.com/user-attachments/assets/c9bd0f9c-5c1b-4b08-8011-a958b6feb563" />

## Phase 16
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click "Enable or disable an extension "
- Enable: php_imap.dll, php_intl.dll, php_opcache.dll
<img width="800" height="800" alt="Screenshot 2025-10-13 151926" src="https://github.com/user-attachments/assets/c9a9d639-ce68-46d9-bd3c-0f2d55d3b7d7" />
<img width="800" height="800" alt="Screenshot 2025-10-13 152005" src="https://github.com/user-attachments/assets/f1187df4-3fb9-4575-8964-e53b22a27692" />

## Phase 17
- Refresh the osTicket site in your browser and observe the changes
<img width="800" height="800" alt="Screenshot 2025-10-13 152032" src="https://github.com/user-attachments/assets/466757cf-c26a-42e4-9ce9-945b435c594e" />

## Phase 18
- Rename C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php as shown below
<img width="800" height="800" alt="Phase 18" src="https://github.com/user-attachments/assets/66fe5abc-1b07-4bee-b5cd-87cfed5b9714" />

## Phase 19
- Assign permissions within ost-config.php -> disable Inheritance -> remove all -> new permissions -> everyone -> all like below
<img width="800" height="800" alt="Screenshot 2025-10-13 161413" src="https://github.com/user-attachments/assets/44426884-a441-4b5d-b500-97a3ad659f4d" />
<img width="800" height="800" alt="Screenshot 2025-10-13 161542" src="https://github.com/user-attachments/assets/9311b7f9-1623-4f14-9f8a-efc270d140b5" />

## Phase 20
- Continue to set up osTicket within the browser giving it a name and using a random email of your choice
<img width="800" height="800" alt="Phase 20" src="https://github.com/user-attachments/assets/c93e6e35-6ff9-4a9e-b6e9-7c2521fb186f" />

## Phase 21
- Now from the "osTicket-Installation-Files" folder install HeidiSQL
- Open HeidiSQL -> skip through and install -> create a new session user: root pass: root -> connnect to the session -> create a database called "osTicket"
<img width="800" height="800" alt="Phase 21" src="https://github.com/user-attachments/assets/2921a9e4-15aa-4798-86ef-f6c44908d917" />

## Phase 22 ( Last Phase )
- Continue setting up osTicket in the browser and filling everything in and at the bottom portion fill in as this
- MySQL Database: osTicket
  MySQL Username: root
  MySQL Passsword: root
- Click Install now 
<img width="800" height="800" alt="Phase 20" src="https://github.com/user-attachments/assets/62412c1b-9cb9-4909-a1ac-9a8f76c948c0" />

# Congratulations you have sucessfully installed osTicket and now have your very own ticketing system sandbox 
<img width="800" height="800" alt="Screenshot 2025-10-13 163510" src="https://github.com/user-attachments/assets/15fc00d6-3f86-49b1-9a08-186bff7ed4e0" />




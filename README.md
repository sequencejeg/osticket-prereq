<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Prerequisites</h2>

- [Creating Virtual Machines in the Cloud](https://github.com/sequencejeg/configure-vm)
- [osTicket Installation Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)(For reference purposes. Link to download zip file is below.)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machine)
- Windows App (macOS)
- Remote Desktop
- Internet Information Services (IIS)
- MySQL (HeidiSQL)
- osTicket

<h2> Operating Systems Used </h2>

- macOS Sequoia
- Windows 10</b> (21H2)

<h2>Installation Steps</h2>

<p> 
- Log into the VM with Remote Desktop
</p>
<br />

<img width="705" height="574" alt="Screenshot 2025-08-16 at 3 50 42 PM" src="https://github.com/user-attachments/assets/e39f6fce-b0f5-400c-a9a0-8770329e2ebc" />
<img width="1200" height="747" alt="Screenshot 2025-08-16 at 3 51 30 PM" src="https://github.com/user-attachments/assets/f8564b57-38ec-417a-8136-957240a3e29c" />
<br />

<p>
- Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
We will use the files in this folder to install osTicket and some of the dependencies.
</p>
<br />

<img width="1200" height="747" alt="Screenshot 2025-08-16 at 3 51 45 PM" src="https://github.com/user-attachments/assets/486bf9e5-d288-4d6e-af4b-a40cabd549a1" />
<img width="1200" height="747" alt="Screenshot 2025-08-16 at 3 52 23 PM" src="https://github.com/user-attachments/assets/f9fd5d5d-e0a9-4911-8aed-c88d27c0dccd" />
<br />

<p>
- Open the Windows Control Panel -> Programs -> Programs & Features -> Turn Windows features on or off
</p>
<br />

<img width="1200" height="747" alt="Screenshot 2025-08-16 at 3 54 31 PM" src="https://github.com/user-attachments/assets/756346ab-772a-4b34-8bf3-bc79080a49ca" />
<img width="899" height="472" alt="Screenshot 2025-08-16 at 3 54 50 PM" src="https://github.com/user-attachments/assets/d6829479-89a3-486a-b44d-3244f8b55452" />
<img width="899" height="472" alt="Screenshot 2025-08-16 at 3 55 06 PM" src="https://github.com/user-attachments/assets/388df7ab-1dec-49ad-896b-f61ad124e060" />
<img width="899" height="472" alt="Screenshot 2025-08-16 at 3 55 16 PM" src="https://github.com/user-attachments/assets/6ac96d31-15f5-4d07-8436-4eb116f19f56" />
<br />

<p>
- Install / Enable IIS in Windows WITH CGI. World Wide Web Services -> Application Development Features -> [X] CGI
</p>
<br />

<img width="347" height="299" alt="Screenshot 2025-08-16 at 3 56 19 PM" src="https://github.com/user-attachments/assets/41a1b62b-2c5a-4370-b5e7-bea50e16c30a" />
<img width="347" height="299" alt="Screenshot 2025-08-16 at 3 56 32 PM" src="https://github.com/user-attachments/assets/2d4c523d-8d8d-439e-9608-3a38f54643b5" />
<img width="550" height="399" alt="Screenshot 2025-08-16 at 3 57 12 PM" src="https://github.com/user-attachments/assets/52a3bc25-d7e5-4389-959c-ac55115d2e66" />
<img width="550" height="399" alt="Screenshot 2025-08-16 at 3 57 46 PM" src="https://github.com/user-attachments/assets/134c651f-65ff-45b5-bf65-f25debf4d503" />
<br />

<p>
- We can check if it worked by opening up our browser and typing in our loop back address "127.0.0.1". If it opens the page succesfully and you see "Internet Information Services", it means IIS has been installed correctly.
</p>
<br />

<img width="1205" height="720" alt="Screenshot 2025-08-16 at 3 58 00 PM" src="https://github.com/user-attachments/assets/2c063616-a5f3-42cd-8e73-164ac3482704" />
<br />

<p>
- From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>
<br />

<img width="1205" height="720" alt="Screenshot 2025-08-16 at 5 01 47 PM" src="https://github.com/user-attachments/assets/f53f7d68-5eeb-4102-b021-8141592453ac" />
<img width="1205" height="720" alt="Screenshot 2025-08-16 at 5 02 02 PM" src="https://github.com/user-attachments/assets/925d14e0-9aa7-48a9-af15-953644101751" />
<br />

<p>
- From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>
<br />

<img width="1205" height="720" alt="Screenshot 2025-08-16 at 5 02 54 PM" src="https://github.com/user-attachments/assets/dbdcc250-1e4e-4fe5-9a88-6e7615466c61" />
<img width="1205" height="720" alt="Screenshot 2025-08-16 at 5 03 04 PM" src="https://github.com/user-attachments/assets/60366a1b-02e8-4802-b531-b80faf2a2dee" />
<br />

<p>
- Create the directory C:\PHP 
</p>
<br />

<img width="1205" height="720" alt="Screenshot 2025-08-16 at 5 04 40 PM" src="https://github.com/user-attachments/assets/035d2ffc-1a78-46eb-a6d0-770dba73263c" />
<img width="1205" height="720" alt="Screenshot 2025-08-16 at 5 04 52 PM" src="https://github.com/user-attachments/assets/23d49fcb-d503-4bf5-a1d7-4125d3e8fd1f" />
<br />

<p>
- From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
</p>
<br />

<img width="922" height="500" alt="Screenshot 2025-08-16 at 5 05 59 PM" src="https://github.com/user-attachments/assets/5e5ebc61-c003-4b23-b88f-3de94e9a8237" />
<img width="488" height="370" alt="Screenshot 2025-08-16 at 5 06 33 PM" src="https://github.com/user-attachments/assets/8477db55-7b6d-4e0d-b964-33f8d4449120" />
<img width="592" height="378" alt="Screenshot 2025-08-16 at 5 07 01 PM" src="https://github.com/user-attachments/assets/7fabb5c5-f811-4ca0-bd20-e16fb91a0e5f" />
<img width="484" height="352" alt="Screenshot 2025-08-16 at 5 07 26 PM" src="https://github.com/user-attachments/assets/ae327240-2e35-4bb2-9216-d7f73be8da0b" />
<br />

<p>
- The files should have extracted succesfully inside the PHP folder in out C: drive
</p>
<br />

<img width="898" height="430" alt="Screenshot 2025-08-16 at 5 10 14 PM" src="https://github.com/user-attachments/assets/5fbc2c69-f3f4-4c60-ba8c-c4348349ceac" />
<br />

<p>
- From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
</p>
<br />

<img width="901" height="488" alt="Screenshot 2025-08-16 at 5 10 56 PM" src="https://github.com/user-attachments/assets/f2f7371f-1450-4610-9b85-61306ff1a350" />
<img width="901" height="488" alt="Screenshot 2025-08-16 at 5 11 07 PM" src="https://github.com/user-attachments/assets/534f566c-b13f-4f3e-a10e-603691034973" />
<br />

<p>
- From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi):
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Username: root
Password: root
</p>
<br />

<img width="901" height="488" alt="Screenshot 2025-08-16 at 5 11 56 PM" src="https://github.com/user-attachments/assets/3bcdaf51-e93a-47f3-9cdd-d15cccd03b14" />
<img width="901" height="488" alt="Screenshot 2025-08-16 at 5 12 25 PM" src="https://github.com/user-attachments/assets/9989e8bd-a6f4-4fe9-84a0-48c50c7b8d84" />
<img width="901" height="488" alt="Screenshot 2025-08-16 at 5 12 41 PM" src="https://github.com/user-attachments/assets/fbf2c477-2d98-44ca-8336-b55e54a32f65" />
<img width="901" height="488" alt="Screenshot 2025-08-16 at 5 13 01 PM" src="https://github.com/user-attachments/assets/baf0f663-3324-4146-8ee4-08237606d12f" />
<img width="901" height="488" alt="Screenshot 2025-08-16 at 5 13 15 PM" src="https://github.com/user-attachments/assets/27b71fad-16e9-40d9-82c0-eb3d1e86ed0e" />
<img width="901" height="488" alt="Screenshot 2025-08-16 at 5 13 29 PM" src="https://github.com/user-attachments/assets/0eedda7b-3499-41f6-8e10-33365a5ed3fe" />
<img width="901" height="488" alt="Screenshot 2025-08-16 at 5 13 43 PM" src="https://github.com/user-attachments/assets/c74f853c-dee0-4d75-afef-a4a694caaf85" />
<img width="901" height="488" alt="Screenshot 2025-08-16 at 5 14 04 PM" src="https://github.com/user-attachments/assets/aea45dfb-709f-4c56-aa22-3e11afb293a5" />
<br />

<p>
- Open IIS as an Admin
</p>
<br />

<img width="621" height="508" alt="Screenshot 2025-08-16 at 5 16 47 PM" src="https://github.com/user-attachments/assets/efc1d493-7779-4254-8c3e-5d079a0607b7" />
<br />

<p>
- Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
</p>
<br />

<img width="882" height="521" alt="Screenshot 2025-08-16 at 5 18 11 PM" src="https://github.com/user-attachments/assets/91ceb0d9-0c38-41b4-87b5-fe5d4ef1b946" />
<img width="882" height="521" alt="Screenshot 2025-08-16 at 5 18 26 PM" src="https://github.com/user-attachments/assets/a282c5e8-12ee-4903-8930-0b9e3aa822b1" />
<img width="882" height="521" alt="Screenshot 2025-08-16 at 5 18 41 PM" src="https://github.com/user-attachments/assets/6c17ec74-ac8a-4b8b-b2f8-01c5cbc9c59a" />
<br />

<p>
- Reload IIS (Open IIS, Stop and Start the server)
</p>
<br />

<img width="882" height="521" alt="Screenshot 2025-08-16 at 5 19 50 PM" src="https://github.com/user-attachments/assets/98103652-cd3c-44de-af85-f56067a3c245" />
<img width="695" height="326" alt="Screenshot 2025-08-16 at 5 20 08 PM" src="https://github.com/user-attachments/assets/2a2d7a1c-f28d-4d25-8de9-4a3e775dff72" />
<br />

<p>
- Install osTicket v1.15.8 From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
</p>
<br />

<img width="695" height="326" alt="Screenshot 2025-08-16 at 5 21 15 PM" src="https://github.com/user-attachments/assets/23c1fda1-0617-49e6-8d14-271f887a6f89" />
<img width="945" height="511" alt="Screenshot 2025-08-16 at 5 21 44 PM" src="https://github.com/user-attachments/assets/17a618f5-aca1-49a3-a9f9-3219284a451d" />
<img width="882" height="469" alt="Screenshot 2025-08-16 at 5 22 25 PM" src="https://github.com/user-attachments/assets/0a11df65-9621-41f3-81a0-8763d09f3021" />
<img width="1200" height="717" alt="Screenshot 2025-08-16 at 5 22 48 PM" src="https://github.com/user-attachments/assets/b31ecc1e-bc6c-4381-a060-dc6a13275d46" />
<img width="1200" height="717" alt="Screenshot 2025-08-16 at 5 22 57 PM" src="https://github.com/user-attachments/assets/f6781d72-2b26-4e97-8bbe-edb666305fb5" />
<img width="1200" height="717" alt="Screenshot 2025-08-16 at 5 23 14 PM" src="https://github.com/user-attachments/assets/484cb8b3-ab1b-4e45-97be-5e9aa61e313c" />
<br />

<p>
- Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
</p>
<br />

<img width="1200" height="717" alt="Screenshot 2025-08-16 at 5 23 23 PM" src="https://github.com/user-attachments/assets/71e675f5-fb33-43c9-85b1-492e77e64a1f" />
<img width="1200" height="717" alt="Screenshot 2025-08-16 at 5 23 36 PM" src="https://github.com/user-attachments/assets/9ec08e52-d0ff-484d-9494-ed9cd6e372cf" />
<br />

<p>
- Reload IIS (Open IIS, Stop and Start the server)
</p>
<br />

<img width="884" height="515" alt="Screenshot 2025-08-16 at 5 50 33 PM" src="https://github.com/user-attachments/assets/529bf402-5170-4b6e-8c36-156249ed0f42" />
<img width="884" height="515" alt="Screenshot 2025-08-16 at 5 50 48 PM" src="https://github.com/user-attachments/assets/f8918b1f-4e20-4de9-a97c-ec9c3f8ddd6d" />
<br />

<p>
- Go to sites -> Default -> osTicket
On the right, click “Browse *:80”
Note that some extensions are not enabled
</p>
<br />

<img width="884" height="515" alt="Screenshot 2025-08-16 at 5 52 19 PM" src="https://github.com/user-attachments/assets/466170a0-1ffe-476c-9f9e-73689a9f8e6f" />
<img width="725" height="293" alt="Screenshot 2025-08-16 at 5 52 43 PM" src="https://github.com/user-attachments/assets/4de1b596-71c8-4cd4-82c8-96b0458e921c" />
<img width="1202" height="716" alt="Screenshot 2025-08-16 at 5 53 01 PM" src="https://github.com/user-attachments/assets/d3ac3a57-47fd-4e3c-aec6-24e59125d42d" />
<br />

<p>
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
</p>
<br />

<img width="889" height="514" alt="Screenshot 2025-08-16 at 5 55 00 PM" src="https://github.com/user-attachments/assets/5c296728-2a3f-441d-af93-2eb18bf7b9c6" />
<br />

<p>
- Click “Enable or disable an extension”
</p>
<br />

<img width="889" height="514" alt="Screenshot 2025-08-16 at 5 55 53 PM" src="https://github.com/user-attachments/assets/84ff172d-0619-4570-b2cc-6dcb826dce37" />
<br />

<p>
- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll
</p>
<br />

<img width="889" height="514" alt="Screenshot 2025-08-16 at 5 56 36 PM" src="https://github.com/user-attachments/assets/b22a751a-99e7-4ddd-8ce4-15e82f6e8662" />
<br />

<p>
- Refresh the osTicket site in your browser, observe the changes
</p>
<br />

<img width="1205" height="719" alt="Screenshot 2025-08-16 at 5 57 46 PM" src="https://github.com/user-attachments/assets/238859fc-c875-4bd3-98a7-603764bab9f2" />
<br />

<p>
- Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<br />

<img width="904" height="474" alt="Screenshot 2025-08-16 at 5 58 54 PM" src="https://github.com/user-attachments/assets/4cd09e81-a0e6-4b1d-85cc-6bcd85df1ffd" />
<img width="904" height="474" alt="Screenshot 2025-08-16 at 5 59 01 PM" src="https://github.com/user-attachments/assets/3947ba9f-ad26-4509-99af-e9354634a8d0" />
<img width="904" height="474" alt="Screenshot 2025-08-16 at 5 59 08 PM" src="https://github.com/user-attachments/assets/cae0161d-8908-4f9a-a9cf-cfec1c226baa" />
<img width="904" height="474" alt="Screenshot 2025-08-16 at 5 59 40 PM" src="https://github.com/user-attachments/assets/686f9dd9-f149-43cd-ada6-8ac474374c22" />
<img width="904" height="474" alt="Screenshot 2025-08-16 at 6 00 05 PM" src="https://github.com/user-attachments/assets/c7fa0573-1331-479d-92d0-42c5cc132e8a" />
<img width="904" height="474" alt="Screenshot 2025-08-16 at 6 00 33 PM" src="https://github.com/user-attachments/assets/cc0ae242-fcfa-42d0-80bb-3ff83283e175" />
<br />

<p>
- Assign Permissions: ost-config.php
- Disable inheritance -> Remove All
- New Permissions -> Everyone -> All
</p>
<br />

<img width="904" height="474" alt="Screenshot 2025-08-16 at 6 02 28 PM" src="https://github.com/user-attachments/assets/af8671d7-17f1-4524-a60c-8753df8721ca" />
<img width="279" height="408" alt="Screenshot 2025-08-16 at 6 02 50 PM" src="https://github.com/user-attachments/assets/a19032fc-9b8e-4d4e-8fd5-6d1343ee8a90" />
<img width="612" height="410" alt="Screenshot 2025-08-16 at 6 03 06 PM" src="https://github.com/user-attachments/assets/1dbde4a6-5dd7-465a-9c7b-50b9aa898bae" />
<img width="612" height="410" alt="Screenshot 2025-08-16 at 6 03 22 PM" src="https://github.com/user-attachments/assets/7e78640b-c87a-400b-86d1-af2a8f3eb385" />
<img width="612" height="410" alt="Screenshot 2025-08-16 at 6 03 30 PM" src="https://github.com/user-attachments/assets/1b6bdab9-88f8-4e50-afa8-383404a92ca3" />
<img width="717" height="471" alt="Screenshot 2025-08-16 at 6 03 55 PM" src="https://github.com/user-attachments/assets/de12050c-65a5-4c4c-a622-23c9bb7080c1" />
<img width="619" height="414" alt="Screenshot 2025-08-16 at 6 04 13 PM" src="https://github.com/user-attachments/assets/2c9d7500-e172-4ff5-8790-4f1457aa984a" />
<br />

<p>
- Continue Setting up osTicket in the browser (click Continue)
- Name Helpdesk
- Default email (receives email from customers)
- For admin user, I used my name and email as reference
</p>
<br />

<img width="1200" height="722" alt="Screenshot 2025-08-16 at 6 06 04 PM" src="https://github.com/user-attachments/assets/04d30f13-73d6-4d89-95d6-c08228284cdd" />
<br />

<p>
  - From the “osTicket-Installation-Files” folder, install HeidiSQL.
- Open Heidi SQL
- Create a new session, root/root
- Connect to the session
- Create a database called “osTicket”
</p>
<br />

<img width="468" height="367" alt="Screenshot 2025-08-16 at 6 07 33 PM" src="https://github.com/user-attachments/assets/793275bd-de0f-48a7-bc1b-080df7e9b8c7" />
<img width="468" height="367" alt="Screenshot 2025-08-16 at 6 07 55 PM" src="https://github.com/user-attachments/assets/926680df-49db-4140-ae61-c1a6b4d053bf" />
<img width="588" height="461" alt="Screenshot 2025-08-16 at 6 08 39 PM" src="https://github.com/user-attachments/assets/9e879a83-6c9a-4c2c-ab50-97d8df209e14" />
<img width="588" height="461" alt="Screenshot 2025-08-16 at 6 08 56 PM" src="https://github.com/user-attachments/assets/1c4b3ab9-10ca-4594-80ef-0981dbe0d931" />
<img width="755" height="486" alt="Screenshot 2025-08-16 at 6 09 29 PM" src="https://github.com/user-attachments/assets/48dc977d-3c83-498f-89bd-025db9c0d19a" />
<img width="379" height="332" alt="Screenshot 2025-08-16 at 6 09 50 PM" src="https://github.com/user-attachments/assets/9ab54014-c2c6-4dd7-872b-7ff5d92d38b0" />
<br />

<p>
- Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”
</p>
<br />

<img width="1205" height="751" alt="Screenshot 2025-08-16 at 6 12 12 PM" src="https://github.com/user-attachments/assets/c2e32c61-fc29-41c8-a878-27c03594dada" />
<img width="584" height="326" alt="Screenshot 2025-08-16 at 6 12 29 PM" src="https://github.com/user-attachments/assets/0d411302-bfea-44fe-9ee0-b42045107b85" />
<img width="1200" height="723" alt="Screenshot 2025-08-16 at 6 12 42 PM" src="https://github.com/user-attachments/assets/2d1bb78e-98c3-4ce3-bfed-d249adcae611" />
<br />

<p>
- Congratulations, you have just installed osTicket with no errors!
- Browse to your help desk login page: http://localhost/osTicket/scp/login.php
- End Users osTicket URL:
http://localhost/osTicket/ 
<br />

<h3>Conclusion </h3>

<p> 
  In this tutorial we have demonstrated how to fully install our ticketing system, osTicket, and all of its neccessary and all of it's neccessary components.
</p>

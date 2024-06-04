This repository represents the full osTicket lab, if you would like to view it in sections it can be found on my github profile, divided into 3 sections.
https://github.com/ben-trainer 

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this lab, I install the ticketing system osTicket from the ground up using neccessary installation files. The lab is done in Windows 10 Pro 22H2 VM made on Microsoft Azure. I will outline the steps using pictures in this github repository. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

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

2.) With the public IP address we will now connect to the VM using Remote Desktop Connection on our Windows computer. We will use the search bar at the bottom of the screen and type in Remote Desktop Connection and select it to open. Now paste the VM’s public IP address and click connect to initialize our remote connection. Note: The VM may take a moment to start up
 
</p>
<br />

<p>
<img src="https://i.imgur.com/SBd2kxK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/0no6NJM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
3.) Once completed, we will click on the “More choices” option and “Use a different account.” Now log in using the credentials we made when setting up the VM and click “Ok”


<p>
<img src="https://i.imgur.com/d0GqyIh.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://i.imgur.com/3DaExaS.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
4.) To start we will need to enable Internet Information Services (IIS). To do this open the Control Panel -> Programs -> Turn Windows Features On or Off. 
We will then check Internet Information Services and expand it, expand World Wide Web Services, and Application Development Features. Check the CGI box. Now under Common HTTP Features check HTTP Redirection and WebDAV Publishing and click ok. Then IIS will be installed.


[X] CGI
[X] Common HTTP Features
  
<p>
<img src="https://i.imgur.com/kwYoh4V.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://i.imgur.com/wyBnhq6.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>


***NOTE*** Make sure all Common HTTP Features are checked.
 
 
5.) Next is to test the connectivity to the web server which can be done by opening a web browser and type 127.0.0.1 and it should look like this
  
<p>
<img src="https://imgur.com/eICujoq.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
  
  
6.) Now it’s time to make use of the installations, we will start with downloading and installing PHP Manager. Click Open File on the top right corner and install with default settings, agreeing to the License Agreement.
<p>
<img src="https://i.imgur.com/Qi3JgOy.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
7.) Now we are going to install rewrite_amd64_en-US.msi and open the file using the same method. We will agree to the license agreement and click finish
<p>
<img src="https://i.imgur.com/x5ptpWe.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
8.) After a successful installation of Rewrite Module we will open up file explorer, go to This Pc > Windows (C:) and create a folder named PHP which we will use to extract the contents of the PHP zip file which can be found in This PC > Downloads
<p>
<img src="https://i.imgur.com/WbGdbVO.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

9.) After created we will download and install the Redist executable (.exe)
  
  !! ATTENTION !!
If this appears, choose to “Keep” the file:
  
<p>
<img src="https://imgur.com/xZv1Yhw.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/YwBhqo0.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

10.) Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe. 
<p>
<img src="https://i.imgur.com/4RO41Qx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>


11.) Next step is to download and install php-7.3.8, right click it and extract all into the PHP folder we just created in the C drive.

Now download and install mysql-5.5.62, open the file, accept the agreement, do a typical install. Ensure “Launch the MySQL Instance Configuration Wizard” is checked and click finish. 
<p>
<img src="https://i.imgur.com/PdNVV4Q.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

Make sure to click standard configuration, install as windows service, and create a username and password for the root account. Next > Execute > Finish. This will install osTicket’s database to store data and tickets.
  
<p>
<img src="https://i.imgur.com/1lQnARR.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
11.) With that done we will go to the start menu and search for IIS, right click it and run as an administrator

Navigate to the PHP Manager button and double click to Register new PHP version. Path the install to the PHP folder we made within the C: drive, and click the PHP executable (.exe) and click ok

Give the server a quick restart and continue 


<p>
<img src="https://i.imgur.com/pjdn5c3.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://i.imgur.com/cMGFovJ.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
12.) Next download will be the osTicket zip file, open the file and drag the upload file into the C: > inetpub > wwwroot. Then rename upload to osTicket. Open IIS and give the server a restart.

  
<p>
<img src="https://i.imgur.com/UEpnaTM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
12.) Within IIS in the connections section open Sites > Default Web Site > osTicket and under Actions tab click Browse *:00 (http). This should take us to our osTicket homepage

  
<p>
<img src="https://i.imgur.com/TxSdyZl.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
13.) Now we should go under the osTicket folder in the connections tab of IIS and click PHP manager > Enable or Disable extension. Enable the following extensions: php_imap.dll, php_intl.dll, php_opcache.dll

<p>
<img src="https://i.imgur.com/HARG5Pb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
14.) Navigate to This PC > C: > inetpub > wwwroot > osTIcket > include. Rename “ost-sampleconfig.php” to ost-config.php

15.) Next is to change the permissions of ost-config.php. Right click it, Properties > Security > Advanced > Disable inheritance > Remove all inherited permissions from this object > Apply.

  
<p>
<img src="https://i.imgur.com/7z5HBoV.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
16.) Next add permissions > Select a principle > (type everyone into object name box) Check Names > Ok > Full control > Ok > Apply > Ok

17.) Now go to our browser > Continue. Now download and install HeidiSQL and run the executable and select the default configurations and finish.

18.) Inside HeidiSQL click new, and enter the credentials and right click unnamed to create a new database

<p>
<img src="https://i.imgur.com/OjnEH7k.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
19.) All that’s left is to clean up. Go to C: > inetpub > wwwroot > include ost-config.php > Properties > Security > Advanced > Everyone > Edit. Only have Read & execute and read enabled. Apply. 
<p>
<img src="https://i.imgur.com/dITLQKY.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
20.) With that done we have completed the prequisites and installation for osTicket!

<img src="https://i.imgur.com/pN5jDKa.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>

<p>

<h1>osTicket - Post-Install Configurations</h1>
In this second section of the osTicket lab I will demonstrate the necessary changes I make to configure osTicket so it can be used as a proper ticketing system. This is done by settings the roles and permissions for who can view and create a ticket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- osTicket 

<h2>Operating Systems Used </h2>

- Windows 10 Pro</b> (22H2)


<h2>Configuration Steps</h2>

With our osTicket database set up we will now begin our Post-Install configuration. Starting with roles and creating a supreme admin role. We will click the link named "http://localhost/osTicket/scp" and will navigate over to the admin panel on the top right and select Agents > Roles > Create New Role. Name it some kind of admin account > Permissions, check all boxes for full permissions.
<p>
<img src="https://i.imgur.com/wyWPnLg.png" height="80%" width="80%" alt="Configuration Steps"/>
<img src="https://i.imgur.com/FvTp4cr.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>
Now create a department. Navigate to Agents > Departments > Add a new Department. Name the department and add a new department.

</p>
<br />

<p>
<img src="https://i.imgur.com/wpEGDxa.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>
Next is to create some teams, go to Agents > Teams > Add New Team. Name level II support. We will now allow anyone to create tickets. Admin Panel > Settings > Users. Ensure “Require registration and login to create tickets” is unchecked.

</p>
<br />

<p>
<img src="https://i.imgur.com/X0gfpmt.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>
Now we will create our agents who submit tickets. Go to Admin Panel > Agents > Add New Agent. Name one John Doe and Jane Doe. Setting up a username and password for both of them.
</p>
<br />

<p>
<img src="https://i.imgur.com/UnYyh3B.png" height="80%" width="80%" alt="Configuration Steps"/>
<img src="https://i.imgur.com/9I00e4Q.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>
Next is creating our customers. Swap to the Agent Panel > Users > Add User. Create 2 sample users. 
</p>
<br />

<p>
<img src="https://i.imgur.com/qZi2Nns.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>
We will now create 3 SLAs. Swap back to the Admin Panel > Manage > SLA. We should look to get a result like this. Setting up 3 severities for tickets. In this case, SEV-A, B, and C have been created to categorize tickets that need to be resolved within 1 hour, 4 hours, and 8 hours respectively. This is what the result should look like. Service Level Agreements (SLAs) will have to be made in order to categorize tickets according to their level of impact. 

</p>
<br />

<p>
<img src="https://i.imgur.com/EmSnEcf.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>
</p>
<br />
Lastly we will now set up help topics, Manage > Help Topics. Create “Business Critical Outage”, “Equipment Request”, “Personal Computer Issues”, and “Password Reset." Help Topics need to be created to help users select an appropriate category that describes their problem so that Agents get an idea of what problem is described in the ticket.


<p>
<img src="https://i.imgur.com/N8X5Rwo.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

<h2>osTicket Configurations are Complete </h2>

Now that the configurations have been set in place, I can now utilize osTicket as a proper ticketing system. I can create tickets and be able to traige them as if I were in a real environment.
With the configurations, roles, departments, and permissions set, I can now utilize osTicket as a ticketing system properly. Similar to a real environment I am able to create, categorize, assign, answer, and resolve tickets.

<h1>Resolving Tickets in osTicket</h1>
In this lab I go through the lifecycle of a ticket from the intake to resolution within the open-source help desk ticketing system osTicket. We will be creating and managing our own tickets for the purpose of demonstration. <br />

<h2>Lifecycle Stages</h2>
Now we will begin with our ticketing life cycle. First we must create our tickets which can be done by visiting the “localhost/osTicket/index” on our web browser. Select open ticket and fill out the request.
<p>
<img src="https://i.imgur.com/HC8kKV0.png" height="80%" width="80%" alt="Ticket Steps"/>

Once we have created our sample tickets they will appear in our tickets tab within our admin panel. Here I created a variety of tickets which need to be categorized based on priority and assign them to the correct professional.

<img src="https://i.imgur.com/GDQ6vLa.png" height="80%" width="80%" alt="Ticket Steps"/>
</p>
<p>
Jane Doe (me) worked the ticket and assigned it to the System Administrator department, also setting the SLA level, and adjusted the Priority Level. The customers are also able to select the Help Topic to help the IT professionals categorize tickets better.

</p>
<br />

<p>
<img src="https://i.imgur.com/gtw5Nok.png" height="80%" width="80%" alt="Ticket Steps"/>

This is what the ticket looks like on the System Administrator’s side, logged in as Benjamin Bravo.
  
<img src="https://i.imgur.com/cACxLCP.png" height="80%" width="80%" alt="Ticket Steps"/>
</p>
<p>
Here I resolve the issue, closing the ticket, and you can see the updated ticket here.

</p>
<br />

<p>
<img src="https://i.imgur.com/j29yfjo.png" height="80%" width="80%" alt="Ticket Steps"/>

Jane Doe (me) was able to work the ticket and assign it to herself, resolving the issue promptly.

<img src="https://i.imgur.com/H0vCre3.png" height="80%" width="80%" alt="Ticket Steps"/>

Jane Doe (me) reached out to John with a warm hand off. Now John Doe (me) received the ticket directly into his ticket queue. Where John Doe (me) was able to resolve it promptly.

<img src="https://i.imgur.com/Tfk912Y.png" height="80%" width="80%" alt="Ticket Steps"/>

The tickets have all been worked and here is the result from my view on the Agent Panel.

<img src="https://i.imgur.com/0t58zTx.png" height="80%" width="80%" alt="Ticket Steps"/>
</p>
<p>


</p>
<br />

<h2>Lessons Learned</h2>

I learned of the use of SLAs in help desk positions, which can change the priority of a ticket, outside of its own categorized priority to uphold a specific company’s quotas. Building out a database like this from scratch helped me understand how valuable documentation is within a helpdesk environment regarding departments and who to assign tickets to. Ensuring concise clear communication between each other.

Strong communication is critical while resolving tickets, being clear and concise go a long way for you coworkers and customers. Tickets are coming in with very different or similar issues and should be assigned to the appropriate person or team. Jane was able to manage and resolve a ticket on her own quickly without the need to have John resolve it, lightening the load on John. This also shows the importance of documentation as the ticket was able to be resolved and another agent wouldn't accidentally work a ticket that is already done. The documentation can also be later used to fix the problem in the future, ensuring smoother operations within the company.

</p>
<p>


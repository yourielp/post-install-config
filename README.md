<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
Hey there! This is a guide on how to configure osTicket, an open-source help desk ticketing system, after the installation process.<br />

<b>Note:</b> To follow along with this guide, make sure you have completed the prerequisites and installation steps described in my previous demonstration, "Prerequisites and Installation".  The video will guide you visually through the steps involved and then further on there are some notes and screenshots provided to provide highlights of some or all of the material.

<h2>Video Demonstration</h2>

- ### [How To Configure osTicket, post-installation](https://drive.google.com/file/d/1dFvXN6I8EnOFGr2uQspMP-gzzkNG1OoA/view?usp=sharing)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- [osTicket Documentation](https://docs.osticket.com/en/latest/index.html)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)


<h2>Post-Install Configuration Objectives</h2>
Create and Configure Roles
Create and Configure Departments & Teams
Create and Configure Agents (workers) & Users (clients)
Configure SLA (Service Level Agreements)
Configure Help Desk Topics
<h2>Configuration Steps</h2>
<h3>&#9312; Prerequisites and Installation</h3>
This demonstration assumes a virtual machine is established with the prerequisite files installed for working osTicket. </br>
Credentials and configurations that will be used in this demonstration can be found in "Prerequisites and Installation". </br>

<hr>
<h3>&#9313; Admin Panel - Roles, Departments, Teams, & Agents</h3>
On the web browser (Microsoft Edge), go to the Help Desk Login Page and sign into your osTicket Help Desk credentials (this example uses username ostuser / ostuser@email.com).
Help Desk Login Page -- http://localhost/osTicket/scp/login.php

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/73954501-a231-4363-9236-ffadcfb671b3)
![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/b2ff7ff8-8b74-47da-b81f-1dc0797268e4)

Currently at the Agent Panel, click on "Admin Panel" at the top-right of the page.

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/49ba8841-ef98-4276-98a2-a0422e10cfb0)


Click on the "Agents" tab > "Roles" > "Add New Role".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/e6846ce0-afec-4d48-8b2d-663a08a8657b)


"Roles are the permissions granted to Agents per Department that they have access to."

In the Definition tab, type any Role name of your choice (this example uses Supreme Admin).
This role will be given all permissions.
Then, click on the Permissions tab.

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/822bd216-c592-424d-85c5-709d56cc0313)


In the Permissions tab, under the Tickets category, checkmark ALL boxes.
Go through both Tasks and Knowledgebase categories and checkmark ALL boxes as well.
Once done, click "Add Role".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/e894b3a2-4a3a-4fbb-a3cb-572ddb0cd3f2)

Now we've created a Supreme Admin role with all permissions granted. Next, we'll create a Department.

Currently in the Agents tab, click on the "Departments" category.
Click "Add New Department".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/f577a57b-0c17-44c3-9fb7-c632d84674cc)

Create a Department name of your choice (this example uses System Administrators).
Skip everything else for now and click "Create Dept".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/cdceb898-1360-4d89-b4fa-b15a2d069a7e)

Next, we'll move onto creating a Team. <br>
"Teams allow you to pull Agents from different Departments and organize them to handle a specific issue or user via a Help Topic or Ticket Filter."

Currently in the Agents tab, click on the "Teams" category.

Click "Add New Team".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/8c47d00b-25bb-4bb0-b0a2-4a229f91bb2a)


Create a Team name of your choice (this example uses Level II Support).
Click "Create Team".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/c9a6881f-c53b-4db1-82fd-4928f126b4c2)


Currently in the Agents tab, click "Agents" category.

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/caac7681-50de-4377-944a-544192184204)


Create the required credentials for this user that are in bold:
First Name (this example uses Jane).
Last Name (this example uses Doe).
Email Address (this example uses jane.doe@osTicket.com).
Username (this example uses jane.doe).
Click "Set Password" and a windows prompt will appear:
Uncheck "Send the agent a password reset email".
Create a password for this user.
Uncheck "Require password change at next login".
Click "Set".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/08747335-6630-4bc8-b279-085ccc9f876a)


Click on the "Access" tab:
Assign this user the Department that we created (this example uses System Administrators).
Assign this user the Role that we created (this example uses Supreme Admin).
Under Extended Access, assign this user the "Support" department with the "Supreme Admin" role.
Click "Save Changes".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/7ab53742-2268-44ec-a655-2426d8fc1d84)


Click on the "Teams" tab:
Assign this user the Team that we created (this example uses Level II Support).
Once done, click "Create".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/c8a715ae-2f97-4667-aa56-c8890ff14069)


Create another Agent following the steps, however assign it to a different Role and Department.</br>
This example creates Agent "John Doe" | Department: "Level I Support" | Role: "View only | Extended Access: Support".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/7575d375-1878-45e1-b27b-5251d54daf5a)


<hr>
<h3>&#9314; Agent Panel - Creating Users</h3>
Click on "Agent Panel" on the top-right of the page.

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/b0d3ad56-2a52-451b-b1a8-8f5a2661a97c)

Click on the "Users" tab.
Click on "Add User".
Create an Email Address and Full Name for this user (this example uses karen@osticket.com / Karen Karen).
Click "Add User".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/a3bc0447-ac41-4a32-b211-21d00dc61324)

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/2560cbf6-8863-4798-99c4-65a865c2f94d)


Create another user of your choice (this example uses ken@osticket.com / Ken Ken)

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/d0ee8458-14f2-49d3-9a64-f4f25ca82218)


<hr>
<h3>&#9315; Admin Panel - Configuring SLA</h3>
"SLA Plans or Service Level Agreements, are unlimited in osTicket. The purpose of the SLA Plan is to provide a length of time in which the help desk Administrator expects tickets to be closed."

Return to the "Admin Panel".
Navigate to "Manage" tab > "SLA".
Click "Add New SLA Plan".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/c7e65cb3-0bac-486b-bc9e-54a1055609fa)


Create the following plans:
SEV-A

Grace Period: 1 hour (Amount, in hours, before tickets with this SLA will become overdue if not closed in allotted time.)
Schedule: 24/7 (Accounted for all days of the week, even on non-business days)
SEV-B

Grace Period: 4 hours
Schedule: 24/7
SEV-C

Grace Period: 8 hours
Schedule: Monday - Friday 8am - 5pm with U.S. Holidays
Click "Add Plan" for each.

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/b83a83d6-2330-4e83-99ae-57a39b487253)

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/64008205-55d2-4609-8249-04f937458f17)


<hr>
<h3>&#9316; Configure Help Topics</h3>
Help Topics will help streamline your end-user’s help desk experience to ensure proper assignment and prompt response to the ticket.

Currently in the Admin Panel, navigate to "Manage" tab > "Help Topics".
Click "Add New Help Topic".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/a5cbf5d4-735b-48e0-b5ca-9d82b99925b0)


Create Help Topics with the following names:
Business Critical Outage
Personal Computer Issues
Equipment Request
Password Reset
"Internal Notes" can be written down for personal use, but not necessary.
After that, click "Add Topic".

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/59aaf9fe-4492-433b-b1f7-fb012213f561)

![image](https://github.com/JasonDelahoussaye/post-install-config/assets/106440235/7cdfb439-7df5-4d16-9e88-5ab6a5d5d23a)


<hr>
<h1><p align=center>All Done</p></h1

<h2><p align=center>Next Demonstration:<br><a href="https://github.com/JasonDelahoussaye/ticket-lifecycle">Ticket Lifecycle Examples</a></p></h2>

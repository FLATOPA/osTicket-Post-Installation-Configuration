<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Configure osTicket, post-installation](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

Post-Install Configuration Objectives

Familiarity with the UI of osTicket
Creating and Configuring Roles
Creation of Tickets
Creating Agents and Users
Setting up Service Level Agreements (SLA Plans) in ticketing system
Configuring Help Topics

Configuration Setups

Configuring Roles, Departments, & Teams

Note: There are two panels when navigating osTicket; Agent Panel and Admin Panel, you'll know which panel you are on if the opposite panel is displayed on the top right of the UI next to your user login name
In this example, the user "josh" is on the Agent Panel
https://user-images.githubusercontent.com/147654000/275617322-6abb22de-3ec5-47a9-8efd-46caf9d1622f.png

Roles grant certain permisions to Agents in an Department they are assigned to
In the Admin Panel, go to the Agents tab and click on Roles, then click on Add New Role
Note: osTickets creates four Roles (All Access, Expanded Access, Limited Access, and View Only) by default.
https://user-images.githubusercontent.com/147654000/275618068-6347ce31-f5f1-4078-b738-dc70dd037df6.png

Name the new Role Supreme Admin, and click on the Permissions tab; in this tab you can assign specific permissions to this role. For our "Supreme Admin" Role, we will check every box under the Tickets, Tasks, and Knowledgebase tabs. Click on Add Role to finish and create the role.
https://user-images.githubusercontent.com/147654000/275619574-306c368f-76fb-4b25-869b-d1a1f430ed76.png

Departments are needed to route and resolve tickets based on their importance or instructions
Still on the Agents tab, click on Departments and click on Add New Department
Note: Much like Roles, osTicket also creates two Departments (Maintenance and Support) by default
https://user-images.githubusercontent.com/147654000/275623256-2a449d47-9632-47ee-9606-65512e292a2e.png

Name the Department System Administrators (we'll leave everything else by default for now), then click on Create Dept to create Department
https://user-images.githubusercontent.com/147654000/275623955-700f78be-2640-4f34-85d6-0ab8ff6ae994.png

Teams allow us to organize Agents from different Departments in osTicket to handle specific issues and supersede Agents and their Departments' parameter rules
In the Agents tab, click on Teams and click on Add New Team
Note: Just like previous set ups, osTicket creates a Team (Level I Support) by default
https://user-images.githubusercontent.com/147654000/275627287-5ede2f9c-91d5-4f9b-8199-99e8f0696e5c.png

Name the Team Level II Support then click on Create Team to create the Team
https://user-images.githubusercontent.com/147654000/275627989-b9aa5ab2-2c41-4666-a4f2-6a0f3ff88bc1.png

Allowing anyone to create Tickets

In the Admin Panel, head to the Settings tab and click on Users, make sure Registration Required is unchecked. This will allow us to create tickets anonymously
https://user-images.githubusercontent.com/147654000/275632110-97c51388-324a-42e0-a808-067de164c4b6.png

Adding Agents and Users

Agents (or Workers) are given the access to the help desk in osTicket to respond, resolve, and update the status of tickets
In the Admin Panel, head to the Agents tab and click on Add New Agent
https://user-images.githubusercontent.com/147654000/275634356-d66757f0-54d1-458f-8a2d-4f1890b2da1d.png

For this tutorial, we will be creating two new Agents Jane and John, it is advise to have a notepad ready to catalog login information as you enter their credentials, but we will set their user names as [name].doe and both of their passwords as Password1 for convenience (which is our admin password from the installation tutorial)
Fill in the Agent's basic info and set the Agent's email address as [name].doe@osticket.com and click on Set Password

https://user-images.githubusercontent.com/147654000/275637100-06fbd1ca-9d97-4f4f-b866-9b304dbdeb57.png

Set the Agent's password to Password1 and unchecked the boxes to prevent the Agent for our example from needing to reset password or change password after login
https://user-images.githubusercontent.com/147654000/275637305-51953148-bddc-476c-9368-4b62f4bf3d42.png

OPTIONAL: Head to the Teams tab to assign the Agent to a Team
Users (or Customers) are creators and owners of tickets and by using osTicket they are able to track the status of their tickets
In the Agent Panel, go to the Users tab and click on Add User
https://user-images.githubusercontent.com/147654000/275639725-f08ec067-3a66-420e-bfaf-6a3003512bcb.png

For this tutorial, we will be creating two new Users Ken and Karen and setting up usernames, emails, and passwords similar to our Agents.
https://user-images.githubusercontent.com/147654000/275642305-8eadff14-b483-4781-9679-80b252a092c4.png

Adding SLA Plans

Service Level Agreements or SLA Plans provide a length of time for the ticket Administrator when the ticket is expected be CLOSED. They can also be designated to specific Departments or Help Topics
In the Admin Panel, go to the Manage tab and drop down to SLA then click on Add New SLA Plan
https://user-images.githubusercontent.com/147654000/275645978-1ebc6fe9-aa95-4e52-9fd9-1ecd7724d3b9.png

osTicket by default has the SLA Plan Default SLA. We will be creating three SLA Plans each with their own length of time for different kinds of importance of the ticket, from highest priority to lowest priority:
SEV-A with 1 hour Grace Period, 24/7 Schedule, suitable for tickets that are business critical
SEV-B with 4 hour Grace Period, 24/7 Schedule, suitable for tickets affecting employees such as troubleshooting or PC problems
SEV-C with 8 hour Grace Period, business hours Schedule, suitable for tickets requesting new equipment
Example of creating SEV-A SLA Plan, click on Add Plan to create the SLA Plan
https://user-images.githubusercontent.com/147654000/275648256-ee7d6fbb-f67a-4055-aa9b-b9fd77d48de1.png

Configuring Help Topics

Help Topics are helpful to streamline the ticket entry experience for the user by helping them specify their ticket info and also determine what Department the ticket should go to
In the Admin Panel, go to the Manage tab and click on Add New Help Topic
Note: osTicket creates four Help Topics (Feedback, General Inquiry, Report a Problem, and Report a Problem / Access Issue) by default
https://user-images.githubusercontent.com/147654000/275650851-27299450-a705-462c-a7d0-6fcdac6f5a59.png

We will create four different Help Topics based on the potential serverity a ticket could have, from highest to lowest priority:
Business Critical Outage
Personal Computer Issues
Equipment Request
Password Reset
Example of entering credentials for the Help Topic "Equipment Request," click on Add Topic to create the Help Topic
https://user-images.githubusercontent.com/147654000/275652143-97777c9e-516c-4831-891b-9d65e9613ed0.png

Further Reading and Manual

This concludes to basics of osTicket configuration, but further information and research on the features of osTicket can be found in the official online doccumentation here

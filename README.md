<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/> </p>

<h1>osTicket - Post-Installation Configuration </h1>
This guide outlines the steps to configure the osTicket system after installation, focusing on setting up agents, users, permissions, teams, departments, SLAs, and help topics. This configuration creates a system where end users can submit tickets, agents can work on them, and admins can manage everything behind the scenes, ensuring proper ticket routing, access control, organization, and flow of requests. 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- osTicket

<h2>Prerequisite</h2>

- [osTicket - Prerequisites and Installation](https://github.com/nikocapp56/osticket-prereqs)

<h2>Configuration Steps</h2>

<h3>0️⃣ Overview of osTicket Post-Installation </h3>

Admin/Analyst Login URL: http://localhost/osTicket/scp/login.php 

End User Ticket Submission URL: http://localhost/osTicket

- Admin Panel: Used for configuration and system management (accessible only by admins)
<img width="700" alt="1" src="https://github.com/user-attachments/assets/41821a43-fbc9-417d-990a-49bc5f0f8f29" />
</p>

- Agent Panel: Used by helpdesk staff/agents to manage and respond to tickets
<img width="700" alt="2" src="https://github.com/user-attachments/assets/330cbf08-6858-4718-a227-f75c54ba0d3c" />
</p>

- Configure Roles: Create roles to manage permissions.
- Set Up Departments: Create departments to control ticket visibility.
- Create Teams: Built cross-department teams to group agents from multiple departments.
- Allow Unregistered Users to Submit Tickets: Modify user settings to allow end users to create tickets without prior registration.
- Add Agents: Add workers to handle tickets.
- Add End Users: Add test users to simulate ticket creation.
- Configure SLA Policies: Set different SLA levels with varying grace periods and schedules.
- Set Up Help Topics: Create topics for better ticket categorization.

<h3> 1️⃣ Configure Roles </h3>

Roles are used to determine an agent's permissions. 

Admin Panel -> Agents -> Roles -> Add New Role

<img width="800" alt="3" src="https://github.com/user-attachments/assets/2e8afeed-01de-4ddb-8e53-f394d151e7d9" />

Create a Supreme Admin that will be given full permissions. (Not all agents will have unlimited access.)

<img width="444" alt="4" src="https://github.com/user-attachments/assets/14e122f8-6bbb-4330-8026-be6752c00124" />
<img width="560" alt="5" src="https://github.com/user-attachments/assets/9df7c037-5092-43bf-a978-459067fa2eae" />
<img width="600" alt="6" src="https://github.com/user-attachments/assets/63bad364-42a9-45e7-ac7b-eb868dd17597" />
<img width="800" alt="7" src="https://github.com/user-attachments/assets/a09d5333-4bb8-4046-b3e3-8adf8716665a" />

<h3> 2️⃣ Configure Departments </h3>

Each Agent is assigned to a specific department depending on their assigned role within the helpdesk. Diferent departments are set up to ensure that tickets are only visible to the apprpriate teams (e.g., Help Desk, System Admins, Networking).

Admin Panel -> Agents -> Departments -> Add New Department

<img width="800" alt="8" src="https://github.com/user-attachments/assets/a09026e7-3194-46c4-87e7-8f3673799e75" />

Create a System Admins department. This is where the Supreme Admins will be designated. 

<img width="800" alt="9" src="https://github.com/user-attachments/assets/d565f038-5e4e-4b13-a5ca-86c45407b3e6" />

<img width="800" alt="10" src="https://github.com/user-attachments/assets/fa3b70cd-6e17-49b5-8805-9c9a5709b325" />

Delete the Maintenance Department so that the tickets do not get routed there.

<img width="800" alt="10 5" src="https://github.com/user-attachments/assets/f9ebd7b2-1fec-45ff-b131-6d4bb3bf0ecc" />

<h3> 3️⃣ Configure Teams </h3>

Teams allow collaboration between agents from different departments who will work together on specific types of issues.

Admin Panel -> Agents -> Teams -> Add New Team

<img width="800"  alt="11" src="https://github.com/user-attachments/assets/37a8e42f-51d4-4b4e-b2b1-9d924b63aa77" />

Create an Online Banking Team. 

<img width="800" alt="12" src="https://github.com/user-attachments/assets/3de24fc0-8542-49d4-88f4-d0e57bd1b242" />
<img width="800" alt="13" src="https://github.com/user-attachments/assets/49ce82ce-1b56-478a-a817-162709f98653" />

<h3> 4️⃣ Modify User Registration Settings </h3>

Allow end users to create tickets without having to sign up first. This option is usually unchecked by default, but this is where you can choose to or not to require registration and login to create tickets.

Admin Panel -> Settings -> Users -> Settings

<img width="800" alt="14" src="https://github.com/user-attachments/assets/489f27bc-f274-4a4a-885d-566c83cbc4ea" />

<h3> 5️⃣ Add Agents </h3>

Agents are the employees of the helpdesk that actually work on solving tickets. They are assigned primary departments and given a primary role for tickets sent to their department. They can be given access to other departments other than their own and can also have different roles depending on which department they are in.

Admin Panel -> Agents -> Add New Agent

<img width="800" alt="15" src="https://github.com/user-attachments/assets/7b5d2709-a7c3-44bd-ae19-a00e91bc9f74" />

Create 2 Agents:

- Jane Doe
  - Username: jane
  - Password: Password1
  - Department: System Admins
  - Role: Supreme Admin
  - Team: Online Banking

<img width="800" alt="16" src="https://github.com/user-attachments/assets/ad38d0fc-6a01-4b53-a0f2-ddef92525981" />
<img width="800" alt="21" src="https://github.com/user-attachments/assets/b08be484-87b9-44af-8f47-87c03c0cd8f3" />
<img width="800" alt="17" src="https://github.com/user-attachments/assets/8fcd0efd-a52b-4491-9f31-59fbcd8a5dc2" />
<img width="800" alt="18" src="https://github.com/user-attachments/assets/bb4dc3bc-c1d8-4b3c-a6c3-724688e87fa9" />

- John Doe
  - Username: john
  - Password: Password1
  - Department: Support
  - Role: Expanded Access

<img width="800" alt="19" src="https://github.com/user-attachments/assets/1a0b68b2-7f60-4990-8301-e49351fe1aad" />
<img width="800" alt="21" src="https://github.com/user-attachments/assets/df23a86f-5653-4c82-beba-1899ff0650a4" />
<img width="800" alt="20" src="https://github.com/user-attachments/assets/6b687c13-bda7-4f43-b12b-a92f89ec7659" />
</p>
<img width="800" alt="21 5" src="https://github.com/user-attachments/assets/a3082375-5c34-4a05-bb18-088066606138" />

<h3> 6️⃣ Add Users (End Users / Customers) </h3>

Agent Panel -> Users -> Add User

<img width="800" alt="22" src="https://github.com/user-attachments/assets/06369645-1449-407c-8642-7d7cb96c1b9f" />

Create 2 Users that will be used to create trouble tickets for testing:
- Karen
- Ken

<img width="800" alt="23" src="https://github.com/user-attachments/assets/40b499d9-b5b0-4330-b33f-e3a7a056ca4a" />

<h3> 7️⃣ Configure SLA Plans </h3>

SLA Plans provide a length of time in which the help desk is expected to take to solve a specific ticket. Each SLA has a schedule and within that schedule there is a grace period that gives time to respond before the SLA timer kicks back in after a new update on the ticket.

Admin Panel -> Manage -> SLA -> Add New SLA Plan

<img width="800" alt="24" src="https://github.com/user-attachments/assets/f93ec25f-453b-4460-bc25-8dd097deaff0" />

Create 3 SLA Plans:

- Sev-A (Critical problem)
  - Grace Period: 1 hour
  - Schedule: 24/7
 
<img width="800" alt="25" src="https://github.com/user-attachments/assets/791ec1ca-475c-463b-91dd-6b188f099449" />

- Sev-B (High problem)
  - Grace Period: 4 hours
  - Schedule: 24/7
 
<img width="800" alt="26" src="https://github.com/user-attachments/assets/9dc37644-0f1b-4e9d-b652-31b7f4fabdfb" />

- Sev-C (Medium or low problem)
  - Grace Period: 8 hours
  - Schedule: Business Hours
 
<img width="800" alt="27" src="https://github.com/user-attachments/assets/16cfc556-dd5b-45b2-bd53-5224420e7a20" />
</p>
<img width="800" alt="28" src="https://github.com/user-attachments/assets/bb499854-9e30-4475-ad81-97de2e59b00b" />

<h3> 8️⃣ Configure Help Topics </h3>

Help topics help users categorize their tickets.

Admin Panel -> Manage -> Help Topics -> Add New Help Topic

<img width="800" alt="29" src="https://github.com/user-attachments/assets/fcb36cf5-e17b-4cd0-a875-52e2f81a7959" />
</p>
Create 5 Help Topics:

- Business Critical Outage
<img width="800" alt="30" src="https://github.com/user-attachments/assets/49267b15-ea06-41d6-b763-25d432448fd2" />

- Personal Computer Issues
<img width="800" alt="31" src="https://github.com/user-attachments/assets/f8ede3c1-c4f3-4609-b73e-31dad54280b6" />

- Equipment Request
<img width="800" alt="32" src="https://github.com/user-attachments/assets/fc93ac36-52f9-4fb7-ba25-5b4776cc792c" />

- Password Reset
<img width="800" alt="33" src="https://github.com/user-attachments/assets/ccaeb315-8c53-4361-9e7c-290cf5bc3ee1" />

- Other
<img width="800" alt="34" src="https://github.com/user-attachments/assets/fad3aaf6-ae53-4765-968b-4146ece8c907" />

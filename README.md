<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/> </p>

<h1>osTicket - Post-Installation Configuration </h1>
This guide outlines the steps to configure the osTicket system after installation, focusing on setting up agents, users, permissions, teams, departments, SLAs, and help topics. This configuration ensures proper ticket routing and access control within your support environment.

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

- Acknowledge Admin Panel vs Agent Panel
  - Admin Panel: Used for configuration and system management (accessible only by admins).

<img width="700" alt="1" src="https://github.com/user-attachments/assets/41821a43-fbc9-417d-990a-49bc5f0f8f29" />
</p>

  - Agent Panel: Used by helpdesk staff/agents to manage and respond to tickets.
<img width="700" alt="2" src="https://github.com/user-attachments/assets/330cbf08-6858-4718-a227-f75c54ba0d3c" />

- Configure Roles - Create roles to manage permissions.
- Set Up Departments - Create departments to control ticket visibility.
- Create Teams - Built cross-department teams to group agents from multiple departments.
- Allow Unregistered Users to Submit Tickets - Modify user settings to allow end users to create tickets without prior registration.
- Add Agents - Add workers to handle tickets.
- Add End Users (Customers) - Added test users to simulate ticket creation.
- Configure SLA Policies - Set different SLA levels with varying grace periods and schedules.
- Set Up Help Topics - Created topics for better ticket categorization.

<h3> 1️⃣ Configure Roles (Permissions Grouping) </h3>

Admin Panel -> Agents -> Roles -> Add New Role

<img width="572" alt="3" src="https://github.com/user-attachments/assets/2e8afeed-01de-4ddb-8e53-f394d151e7d9" />

Create a Supreme Admin that will be given full permissions. Roles are used to determine an agent's permissions so not all agents will have unlimited access. 

<img width="444" alt="4" src="https://github.com/user-attachments/assets/14e122f8-6bbb-4330-8026-be6752c00124" />
<img width="560" alt="5" src="https://github.com/user-attachments/assets/9df7c037-5092-43bf-a978-459067fa2eae" />
<img width="600" alt="6" src="https://github.com/user-attachments/assets/63bad364-42a9-45e7-ac7b-eb868dd17597" />
<img width="800" alt="7" src="https://github.com/user-attachments/assets/a09d5333-4bb8-4046-b3e3-8adf8716665a" />

<h3> 2️⃣ Configure Departments (Ticket Visibility) </h3>
Admin Panel -> Agents -> Departments -> Add New Department

<img width="700" alt="8" src="https://github.com/user-attachments/assets/a09026e7-3194-46c4-87e7-8f3673799e75" />

Create a System Admins department. This is where the Supreme Admins will be designated. Each Agent is assigned to a specific department depending on their assigned role within the helpdesk. 

<img width="800" alt="9" src="https://github.com/user-attachments/assets/d565f038-5e4e-4b13-a5ca-86c45407b3e6" />

Diferent departments are there so that tickets are only visible to the right departments (e.g., Help Desk, System Admins, Networking).

<img width="800" alt="10" src="https://github.com/user-attachments/assets/fa3b70cd-6e17-49b5-8805-9c9a5709b325" />

<h3> 3️⃣ Configure Teams (Cross-Department Agent Groups) </h3>
Admin Panel -> Agents -> Teams -> Add New Team

<img width="800"  alt="11" src="https://github.com/user-attachments/assets/37a8e42f-51d4-4b4e-b2b1-9d924b63aa77" />

Create an Online Banking Team. Teams allow collaboration between agents from different departments who will work together on specific types of issues.

<img width="800" alt="12" src="https://github.com/user-attachments/assets/3de24fc0-8542-49d4-88f4-d0e57bd1b242" />
<img width="800" alt="13" src="https://github.com/user-attachments/assets/49ce82ce-1b56-478a-a817-162709f98653" />

<h3> 4️⃣ Modify User Registration Settings </h3>

Admin Panel -> Settings -> Users -> Settings

Allow end users to create tickets without having to sign up first. This option is usually unchecked by default, but this is where you can choose to or not to require registration and login to create tickets.

<img width="800" alt="14" src="https://github.com/user-attachments/assets/489f27bc-f274-4a4a-885d-566c83cbc4ea" />

👩‍💼 5. Add Agents (Internal Help Desk Workers)
Location: Admin Panel -> Agents -> Add New

Agents Created:

Jane (Department: SysAdmins)

John (Department: Support)

👨‍👩‍👧‍👦 6. Add Users (End Users / Customers)
Location: Agent Panel -> Users -> Add New

Users Created:

Karen

Ken

⏱ 7. Configure SLA Plans
Location: Admin Panel -> Manage -> SLA

SLAs Created:

Sev-A: 1-hour grace period (24/7 support)

Sev-B: 4-hour grace period (24/7 support)

Sev-C: 8-hour grace period (business hours only)

❓ 8. Configure Help Topics
Location: Admin Panel -> Manage -> Help Topics

Topics Created:

Business Critical Outage

Personal Computer Issues

Equipment Request

Password Reset

Other

 Setup PHP </h3>



<h3> 5️⃣ Install additional prerequisites within osTicket installation Files </h3>



<h3> 6️⃣ Configure PHP in IIS </h3>



<h3> 7️⃣ Install osTicket </h3>



<h3> 8️⃣ Enable required PHP extensions </h3>



<h3> 9️⃣ Configure osTicket </h3>



<h3> 🔟 Setup the database </h3>



<h3> 1️⃣1️⃣ Finalize and cleanup </h3>



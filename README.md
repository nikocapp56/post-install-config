<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/> </p>

<h1>osTicket - Post-Installation Configuration </h1>
This guide outlines the steps to configure the osTicket system after installation, focusing on setting up agents, users, permissions, teams, departments, SLAs, and help topics. This configuration ensures proper ticket routing and access control within your support environment.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Prerequisites</h2>
Before starting, ensure the following environment is in place:

  - Azure Resource Group (example: osTicketRG)
  - Azure Virtual Machine (example: osticketVM)
    - Operating System: Windows 10 Pro, version 22H2 - x64 Gen2
    - Size: 4 vCPUs
  - Remote Desktop Access enabled (for connecting to the VM)
  - [osTicket Installation Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<h2>Installation Steps</h2>

<h3>0️⃣ Overview of osTicket Installation </h3>

- Enable Internet Information Services
- Install Web Platform Installer
- Install MySQL and Set Up Useranme and Password
- Install C++ Redistributable
- Congure Permissions and Install osTicket

🔐 Login URLs
Admin/Analyst Login Page:
http://localhost/osTicket/scp/login.php

End User Ticket Submission Page:
http://localhost/osTicket

🔄 Admin Panel vs Agent Panel
Admin Panel: Used for configuration and system management (accessible only by admins).

Agent Panel: Used by helpdesk staff/agents to manage and respond to tickets.

🧩 Configuration Steps
🔐 1. Configure Roles (Permissions Grouping)
Location: Admin Panel -> Agents -> Roles

Role Created: Supreme Admin
Used to assign full privileges to trusted agents.

🏢 2. Configure Departments (Ticket Visibility)
Location: Admin Panel -> Agents -> Departments

Department Example: SysAdmins
Helps control visibility of tickets among different teams (e.g., Help Desk, SysAdmins, Networking).

👥 3. Configure Teams (Cross-Department Agent Groups)
Location: Admin Panel -> Agents -> Teams

Team Created: Online Banking
Allows collaboration between agents from different departments.

⚙️ 4. Modify User Registration Settings
Location: Admin Panel -> Settings -> User Settings

Setting Changed:

✅ Require registration and login to create tickets

❌ Uncheck "Allow unregistered users to create tickets"

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
<h3>1️⃣ Install/Enable Internet Information Services (IIS) with CGI </h3>



<h3> 2️⃣ Install PHP Manager for IIS </h3>



<h3> 3️⃣ Install IIS Rewrite Module </h3>



<h3> 4️⃣ Setup PHP </h3>



<h3> 5️⃣ Install additional prerequisites within osTicket installation Files </h3>



<h3> 6️⃣ Configure PHP in IIS </h3>



<h3> 7️⃣ Install osTicket </h3>



<h3> 8️⃣ Enable required PHP extensions </h3>



<h3> 9️⃣ Configure osTicket </h3>



<h3> 🔟 Setup the database </h3>



<h3> 1️⃣1️⃣ Finalize and cleanup </h3>



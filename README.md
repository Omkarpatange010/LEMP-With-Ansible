# LEMP Stack Automation with Ansible

This repository contains an **Ansible playbook** to automate the installation and configuration of a **LEMP stack** (Linux, NGINX, MariaDB, PHP) on a target server, and deploy a custom HTML landing page.

---

## 📌 Overview

This playbook performs the following tasks:

- Installs **NGINX**, **MariaDB**, **PHP**, and **PHP-FPM**
- Starts and enables the installed services
- Deploys a custom landing page (`index.html`) with a polished layout
- Ensures a repeatable and automated setup

Perfect for consistent infrastructure provisioning using **Infrastructure as Code (IaC)** with Ansible!

---

## 🗂️ Repository Structure

Lemp/ <br>
├── inventory.ini <br>
├── lemp-target.yml <br>
└── README.md <br>

yaml
Copy code

- **inventory.ini**: Defines the target hosts
- **lemp-target.yml**: Main Ansible playbook
- **README.md**: Documentation

---

## 🧠 Prerequisites

Before running the playbook, ensure you have:

- Ansible installed on your control machine  
- SSH key access configured to your target server(s)  
- A valid `inventory.ini` file listing your target servers

Example inventory:


[targetservers]
your-server-ip ansible_user=ec2-user
🚀 Running the Playbook
1. Check Syntax
Always validate the playbook before executing:

bash
Copy code
ansible-playbook lemp-target.yml -i inventory.ini --syntax-check
2. Run the Playbook
Deploy the stack:

bash
Copy code
ansible-playbook lemp-target.yml -i inventory.ini
📄 What Gets Installed
Component	Purpose
Linux	Base Operating System
NGINX	Web Server
MariaDB	Database Server
PHP	Server-side scripting language
PHP-FPM	Processes PHP for NGINX

🖼️ Custom Landing Page
The playbook deploys a custom HTML page at:

swift
Copy code
/usr/share/nginx/html/index.html
This page visually confirms that the stack is installed and running successfully.

🛠️ Customization
You can update the landing page content by editing the HTML in the playbook under the Deploy custom HTML page task.

You can also add roles or expand tasks to include:

SSL certificate installation

Virtual host configuration

MariaDB secure setup

💬 Contributions
Feel free to fork this project and enhance automation, add roles, or modularize for reuse in production environments.


# mini-project5-ansible-roles
# Ansible Roles Project

This repository contains multiple **Ansible roles** to automate the installation and configuration of common DevOps tools and services.  
Each role follows the standard Ansible Galaxy structure and can be reused or extended for different environments.

---

## 📂 Project Structure
```bash
.
├── docker/       # Role for Docker Engine
├── jdk/          # Role for Java JDK 21
├── jenkins/      # Role for Jenkins
├── maven/        # Role for Maven
├── memcached/    # Role for Memcached
├── mysql/        # Role for MySQL
├── nginx/        # Role for Nginx
├── rabbitmq/     # Role for RabbitMQ
└── tomcat/       # Role for Tomcat
Each role contains:

tasks/ – Main automation logic

defaults/ – Default variables

vars/ – Additional variables

handlers/ – Handlers for services

templates/ – Config templates

files/ – Static files

🚀 Available Roles

Docker – Installs Docker Engine

MySQL – Installs MySQL, sets username and password

Nginx – Installs and starts Nginx web server

Memcached – Installs and starts Memcached

RabbitMQ – Installs and starts RabbitMQ

Jenkins – Installs and starts Jenkins

JDK – Installs Java JDK 21

Maven – Installs Apache Maven

Tomcat – Installs and configures Apache Tomcat


📝 Usage
1. Setup Prerequisites

Install required dependencies:

sudo apt update -y
sudo apt install python3 -y
sudo apt install ansible -y

2. Inventory Setup

Put your private IP in the inventory file.

Store your SSH private key in key.pem.

Example inventory:

[myservers]
192.168.1.10 ansible_user=ubuntu ansible_ssh_private_key_file=./key.pem

3. Create Roles

You can create new roles using:

ansible-galaxy init my_role

4. Test SSH Connection

Verify SSH connectivity before running playbooks:

ansible all -m ping -i inventory

5. Dry Run

Run the playbook in check mode:

ansible-playbook playbook.yml --check -i inventory

6. Execute Playbook

Finally, apply the playbook:

ansible-playbook playbook.yml -i inventory

📌 Notes

Always test roles in check mode first.

Ensure key.pem has proper permissions:

chmod 400 key.pem


Roles are modular and can be used independently.

Designed for Ubuntu/Debian-based systems.

📖 References

Ansible Documentation

Personal implementation of standard Ansible Galaxy role structure

Learned concepts from multiple DevOps projects and course notes

meta/ – Role metadata

tests/ – Inventory & sample test playbook

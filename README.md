# Jenkins + Ansible Web Server Automation

This project demonstrates **CI/CD automation** using **Jenkins + Ansible** to configure a web server on an EC2 instance.

When code is pushed to this repository:
- Jenkins runs automatically using a **Jenkinsfile**
- Ansible executes playbooks to install and configure a **Apache Web Server**
- A sample webpage is deployed to `/var/www/html/`

This provides a **fully automated pipeline** from code commit → server configuration → web deployment.

---

## 🚀 Architecture Workflow


---

## 🛠️ Tools & Technologies

- **Jenkins**
- **Ansible**
- **Apache2**
- **Ubuntu EC2**
- **Git/GitHub**
- **SSH Keys**
- **YAML Playbooks**

---

## 📂 Project Structure

├── inventory/
│ └── hosts.ini # Target server details
│
├── playbooks/
│ └── webserver.yaml # Ansible playbook for Apache setup
│
└── Jenkinsfile # Pipeline script

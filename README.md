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

---

## 🧰 Jenkins Pipeline

The Jenkins pipeline is defined in the `Jenkinsfile`:

### 🔹 Pipeline Stages
1. **Checkout Source Code**
2. **Install Dependencies (Optional)**
3. **Run Ansible Playbook**
4. **Deploy Web Content**
5. **Post-build Notification (Optional)**

---

## 🟢 Ansible Playbook (Example)

Below is a basic version of `webserver.yaml` for reference:

```yaml
---
- name: Deploy simple website on both servers
  hosts: webservers
  become: yes

  tasks:
    - name: Install Apache
      yum:
        name: httpd
        state: present

    - name: Start and enable Apache service
      service:
        name: httpd
        state: started
        enabled: yes

    - name: Create index.html
      copy:
        dest: /var/www/html/index.html
        content: |
          <html>
          <head><title>Welcome</title></head>
          <body>
            <h1>🚀 Welcome to Ansible Automated Web Server!</h1>
            <p>Deployed automatically using Ansible.</p>
          </body>
          </html>

🔐 Inventory File (hosts.ini)

Example:

[webservers]
your_server_ip ansible_user=ubuntu ansible_ssh_private_key_file=/path/key.pem

```
```
▶ How to Run
Step-1 — Configure Jenkins

Install plugins:

Ansible

Pipeline

SSH Agent

Configure Global Key

Create Pipeline Job

Use GitHub URL of this repo

Step-2 — Run Job

Trigger job manually or with Git push

Jenkins will execute Ansible playbook
```
```
http://<server-ip>
Deployed with Jenkins + Ansible
```



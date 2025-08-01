# ansible-windfly
 🛰️ WildFly Application Deployment using Ansible on AWS EC2

This project automates the deployment of a **Java application on WildFly (formerly JBoss)** using **Ansible**. The automation includes provisioning an EC2 instance, installing WildFly, configuring the server, and deploying a `.war` file.

---

## 📁 Project Structure

wildfly-ansible-project/
├── group_vars/
│ └── all # Global variables (AWS credentials, EC2 config, etc.)
├── roles/
│ ├── wildfly/
│ │ ├── tasks/
│ │ │ └── main.yml # Installation & configuration tasks
│ │ ├── templates/
│ │ │ ├── standalone.xml.j2 # WildFly configuration template
│ │ │ └── iptables-save.j2 # Firewall rules
│ │ ├── files/
│ │ │ └── wildfly-app.war # Java WAR file to be deployed
│ │ └── handlers/
│ │ └── main.yml # Service restart triggers
├── hosts # Ansible inventory (localhost or dynamic EC2)
├── site.yml # Master playbook
└── README.md

yaml
Copy
Edit

---

## 🚀 Features

- ✅ Automates EC2 instance provisioning
- ✅ Installs WildFly 26+ and required dependencies
- ✅ Configures firewall rules
- ✅ Deploys a `.war` Java application
- ✅ Uses templated `standalone.xml` for clean customization

---

## 🔧 Requirements

- Python 3
- Ansible 2.10+
- AWS credentials with EC2 permissions
- SSH key pair for EC2 access
- A `.war` file (Java Web App)

---

## 🔐 Security

> **Do not store AWS credentials in plaintext.**
Use **Ansible Vault** or environment variables to encrypt or inject secrets securely.

```bash
ansible-vault encrypt group_vars/all
📦 Usage
1️⃣ Clone the Repo
bash
Copy
Edit
git clone https://github.com/yourusername/wildfly-ansible-project.git
cd wildfly-ansible-project
2️⃣ Edit Variables
Edit group_vars/all:

yaml
Copy
Edit
aws_access_key: "YOUR_ACCESS_KEY"
aws_secret_key: "YOUR_SECRET_KEY"
ec2_image: ami-xxxxxx
ec2_region: ap-south-1
ec2_keypair: my-key
3️⃣ Run Playbook
bash
Copy
Edit
ansible-playbook -i hosts site.yml
✅ Output
EC2 instance launched

WildFly installed and configured

Your Java application deployed at:

php-template
Copy
Edit
http://<EC2_PUBLIC_IP>:8080/<app-name>
🧠 Author
Mrutyunjay Masanta
DevOps & Cloud Engineer
📧 mrutyunjaymasanta@gmail.com
🌐 LinkedIn

🛡 License
This project is licensed under the MIT License.

yaml
Copy
Edit

---

Let me know if you'd like to:

- Add badges (CI, Terraform, Ansible Galaxy, etc.)
- Include Ansible Vault integration instructions
- Turn this into a real CI/CD pipeline using Jenkins or GitHub Actions

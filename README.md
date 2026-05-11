## Setup Architecture 

![jenkins-ha](https://user-images.githubusercontent.com/106984297/226690774-66731923-a2cd-45cc-b387-c959e5b713c1.png)

# 🚀 Jenkins High Availability Setup on AWS

This project demonstrates a production-style Jenkins High Availability (HA) setup on AWS using Infrastructure as Code (IaC) and automation tools like Terraform, Ansible, and Packer.

The goal of this project is to automate the provisioning and configuration of Jenkins controller and agent infrastructure in a scalable and reusable way.

---

# 📌 Project Overview

This setup includes:

- Jenkins Controller
- Jenkins Agent Nodes
- AWS Infrastructure Provisioning
- Automated Configuration Management
- Custom AMI Creation
- Infrastructure as Code (IaC)

---

# 🛠️ Technologies Used

- AWS EC2
- Jenkins
- Terraform
- Ansible
- Packer
- Linux
- Git & GitHub

---

# 🏗️ Architecture

```text
Developer → GitHub → Jenkins Controller → Jenkins Agents → AWS Infrastructure
```

## 📂 Project Structure
01-jenkins-setup/
│
├── ansible/
│   ├── playbooks
│   └── configuration files
│
├── terraform/
│   ├── EC2 setup
│   ├── Security Groups
│   └── Infrastructure code
│
├── jenkins-controller.pkr.hcl
├── jenkins-agent.pkr.hcl
│
└── README.md

## 🚀 Setup Instructions
# 1️⃣ Clone Repository
```
git clone https://github.com/Suraj2429/jenkins-ha-setup-aws.git
cd jenkins-ha-setup-aws
```

# 2️⃣ Install Required Tools
Make sure the following tools are installed:
- Terraform
- Ansible
- Packer
- AWS CLI

Verify installation:
```
terraform -version
ansible --version
packer --version
aws --version
```

# 3️⃣ Configure AWS CLI
```
aws configure
```

Provide:

AWS Access Key
AWS Secret Key
Region

# 4️⃣ Build AMIs using Packer
packer build jenkins-controller.pkr.hcl
packer build jenkins-agent.pkr.hcl


# 5️⃣ Deploy Infrastructure using Terraform
```
cd terraform

terraform init
terraform plan
terraform apply

```

# 6️⃣ Configure Servers using Ansible
```
cd ../ansible
ansible-playbook main.yml
```


# 🌐 Access Jenkins

After deployment:

http://<EC2-PUBLIC-IP>:8080

# Ansible-Jenkins
## A project to demo a CICD pipeline build, test and deploy with Ansible, Jenkins, and Docker
markdown

# CI/CD Pipeline with Jenkins, Ansible, and Docker


[![Jenkins](https://img.shields.io/badge/Jenkins-Docker-blue?logo=jenkins)](https://www.jenkins.io/)

[![Ansible](https://img.shields.io/badge/Ansible-2.17+-green?logo=ansible)](https://www.ansible.com/)

[![Docker](https://img.shields.io/badge/Docker-24.0+-blue?logo=docker)](https://www.docker.com/)


Automate deployments using Jenkins for CI/CD, Ansible for configuration management, and Docker for containerization.


---


## 📋 Overview

This project automates the deployment of a web application using:

- **Jenkins** to trigger builds and manage pipelines.

- **Ansible** to provision infrastructure and manage Docker containers.

- **Docker** to containerize the application for consistent environments.


![Architecture Diagram](https://via.placeholder.com/800x400.png?text=Jenkins+%E2%86%92+Ansible+%E2%86%92+Docker) <!-- Replace with your diagram -->


---


## ✨ Features

- **Automated Builds**: Jenkins triggers builds on Git commits.

- **Container Management**: Ansible playbooks handle Docker image/container lifecycle.

- **Idempotent Deployments**: Playbooks ensure consistent server states.

- **Self-Healing**: Failed deployments roll back automatically.


---


## 🛠️ Prerequisites

- Jenkins server (v2.4+)

- Ansible (v2.17+) on the Jenkins host

- Docker (v24.0+) on target servers

- SSH access to EC2 instances


---


## 🚀 Quick Start


### 1. Clone the Repository

```bash

git clone https://github.com/<your-username>/ansible-jenkins.git

cd ansible-jenkins

2. Configure Jenkins

    Install required plugins:
        Ansible
        Docker Pipeline
    Create a Freestyle Project with these build steps:

    bash

scp -r $WORKSPACE/* root@<YOUR-EC2-IP>:~/project/

    ansible-playbook /var/lib/jenkins/playbooks/deployment.yaml

3. Deploy with Ansible

bash

ansible-playbook playbooks/deployment.yaml

📂 Project Structure

.

├── playbooks/

│   └── deployment.yaml     # Main Ansible playbook

├── Dockerfile              # Docker image definition

└── README.md

🔧 Troubleshooting

Error: "pull access denied for spering"

yaml

# In playbooks/deployment.yaml

- name: Stopping the container

  docker_container:

    name: spering-container

    image: spering:latest

    state: stopped

    pull: no  # Add this line

  ignore_errors: yes

Common Fixes

    Ensure Docker is running on target hosts:

    bash

sudo systemctl status docker

Validate Ansible connectivity:

bash

    ansible all -m ping

🤝 Contributing

    Fork the repository
    Create a feature branch:

    bash

git checkout -b feature/your-feature

Commit changes:

bash

    git commit -m "feat: add container health checks"

    Push and open a Pull Request.

📄 License

MIT License. See LICENSE for details.
📧 Contact

For issues or questions, open a GitHub Issue.

Email Summarization
Overview
This project aims to address the challenge of managing extensive email communication within the software production lifecycle by integrating advanced email summarization capabilities. By employing Python, Jenkins, Docker, and Ansible, we establish a robust ML-Ops pipeline that automates build, deployment, and infrastructure management processes. This integration streamlines communication and optimizes software development workflows, reducing the overhead associated with manual email review. Docker ensures consistency and portability across environments, while Ansible automates infrastructure tasks, promoting improved quality and maintainability. Ultimately, our solution enhances software engineering practices, facilitating better knowledge retention and decision-making.

Authors
Keshav Agarwal (MT2023114)
Email: Keshav.Agarwal@iiitb.ac.in
Swarnim Kukreti (MT2023029)
Email: Swarnim.Kukreti@iiitb.ac.in
Problem Statement
Our project addresses the challenge of effectively managing extensive email communication within the software production lifecycle by integrating advanced email summarization capabilities. By employing Python, Jenkins, Docker, and Ansible, we establish a robust ML-Ops pipeline that automates build, deployment, and infrastructure management processes. This integration not only streamlines communication but also optimizes software development workflows, reducing the overhead associated with manual email review. Docker ensures consistency and portability across environments, while Ansible automates infrastructure tasks, promoting improved quality and maintainability. Ultimately, our solution enhances software engineering practices, facilitating better knowledge retention and decision-making.

Technologies and Tools
Required Imports
Flask: A lightweight web framework for Python.
Flask-SQLAlchemy: An extension for Flask that adds support for SQLAlchemy, a SQL toolkit, and ORM library.
mysql-connector-python: A MySQL database connector for Python.
Transformers: A library developed by Hugging Face for natural language processing (NLP).
python-dotenv: A library for managing environment variables.
torch (PyTorch): An open-source machine learning library developed by Facebook's AI Research lab.
Continuous Integration and Continuous Deployment (CI/CD)
CI/CD are software development practices designed to automate the building, testing, and deployment of code changes. The primary goal is to streamline the development process and minimize errors by continuously integrating new code and running automated tests to ensure stability and functionality.

Git Version Control
Git is a distributed version control system (VCS) used for software development and version control tasks. It is designed to handle projects of all sizes with speed and efficiency.

Jenkins
Jenkins is an open-source automation server used for continuous integration and continuous delivery (CI/CD). It automates the building, testing, and deployment of code changes.

Docker
Docker is an open-source platform that allows developers to create, deploy, and run applications in isolated containers. These containers are lightweight, portable, and self-sufficient, simplifying the development, testing, and deployment of applications across various environments.

Ansible
Ansible is an open-source automation tool used for automating various IT tasks. It uses a YAML-based syntax to describe the desired state of a system or environment and then executes tasks to ensure that the system meets that state.

Kubernetes
Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications.

Installation and Setup
Jenkins Installation Steps
Install Java:

sudo apt install default-jdk
Add the Jenkins Repository Key:

wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
Add the Jenkins repository to your system:

sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
Install Jenkins:

sudo apt install jenkins
Start the Jenkins service:

sudo systemctl start jenkins
Docker Setup
Dockerfile example:
FROM python:3.8
RUN apt-get update && apt-get install -y default-mysql-client
WORKDIR /app
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
COPY wait-for-db.sh /app/
RUN chmod +x wait-for-db.sh
CMD ["./wait-for-db.sh", "db", "3306", "python", "run.py"]
Ansible Setup
Update the package index:

sudo apt update
Install the Ansible package:

sudo apt install ansible
Verify the installation:

ansible --version
Ansible Playbook
Example playbook file:

- name: Deploy Kubernetes cluster
  hosts: localhost
  become: false
  tasks:
    - name: Apply Kubernetes resources
      command: kubectl apply -f ../k8s/
Example inventory file:

localhost ansible_user=keshav ansible_ssh_pass=8989 ansible_ssh_common_args='-o StrictHost

# 🚀 CI/CD Pipeline using Jenkins, Docker & AWS

## 📌 Project Overview

This project demonstrates an end-to-end **CI/CD pipeline** that automates the build and deployment of a Python Flask application using Jenkins, Docker, and AWS EC2.

Whenever code is pushed to GitHub, Jenkins automatically builds a Docker image and deploys the application on an EC2 instance.

---

## 🧠 Architecture

Developer → GitHub → Jenkins → Docker Build → Container → AWS EC2 → Browser

---

## 🛠️ Tech Stack

* Jenkins (CI/CD Automation)
* Docker (Containerization)
* Git & GitHub (Version Control)
* AWS EC2 (Deployment)
* Python (Flask)

---

## 📁 Project Structure

devops-project/
│── app.py
│── requirements.txt
│── Dockerfile
│── Jenkinsfile

---

## ⚙️ Setup Instructions

### 1️⃣ Clone Repository

```bash
git clone https://github.com/Shalini-abc/devops-project-1.git
cd devops-project-1
```

---

### 2️⃣ Build Docker Image

```bash
docker build -t devops-app .
```

---

### 3️⃣ Run Docker Container

```bash
docker run -d -p 5000:5000 --name devops-container devops-app
```

---

### 4️⃣ Access Application

Open browser:
http://<EC2-PUBLIC-IP>:5000

---

## 🔄 CI/CD Pipeline Flow

1. Developer pushes code to GitHub
2. Webhook triggers Jenkins automatically
3. Jenkins executes pipeline stages:

   * Build Docker image
   * Stop existing container
   * Deploy new container
4. Updated application is available on EC2

---

## 📄 Jenkins Pipeline (Jenkinsfile)

```groovy
pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop devops-container || true'
                sh 'docker rm devops-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name devops-container devops-app'
            }
        }
    }
}
```

---

## 🌐 Features

* Automated CI/CD pipeline using Jenkins
* Docker-based containerized deployment
* Webhook integration for auto build trigger
* Deployment on AWS EC2
* Zero manual intervention after setup

---

## 📸 Output

Access the application:
http://<EC2-IP>:5000

Output:
Hello DevOps! 🚀

---

## 🚀 Future Improvements

* Push Docker image to Docker Hub
* Add test stage in Jenkins pipeline
* Deploy using Kubernetes
* Add monitoring using Prometheus & Grafana

---

## 👩‍💻 Author

Shalini S
GitHub: https://github.com/Shalini-abc

---

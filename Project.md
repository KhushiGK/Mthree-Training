

## 🔍 Problem Statement

A modern banking institution needs a robust, secure, and scalable system to manage various banking operations such as customer onboarding, account management, transactions (deposit, withdrawal, transfer), user authentication, and support ticketing. The system must also maintain historical records for auditing and regulatory compliance.

The goal is to design and implement a comprehensive **Banking System** that enables seamless interaction between customers, staff, and banking services, while ensuring data integrity, traceability, and ease of management.

---

Team Contribution:
- Backend - Vishnu, Chaitanya
- Frontend - Sindhuja, Himaansh
- Dockerfile - Hema
- Kubernetes - Khushi, Himaansh
- Jenkins - Sandeep, Vishnu
- Prometheus & Grafana - Sindhuja, Sandeep

## 📈 ER Diagram

The system is modeled with 36 tables in total:
- **20 application tables** for customer, account, transactions, etc.
- **6 Celery-related tables** for background task processing.
- **10 Django internal tables** for admin, auth, sessions, etc.

![Schema 1](https://github.com/user-attachments/assets/9fc32c38-d287-471c-935d-54032c100d9b)

---

## ⚙️ Functionalities

### 1. **Customer Management**
- Register new customers with personal details.
- Store and manage customer addresses.
- Link users with customer accounts.

### 2. **User Management**
- User login and logout functionalities.
- Role-based access control (e.g., staff or non-staff).
- Maintain login/logout logs.

### 3. **Account Management**
- Create new accounts linked to a customer.
- Maintain different account types (savings, checking, etc.).
- Enable account editing and updates.
- Store deleted account information for auditing.

### 4. **Branch Management**
- Manage branch details including name and location.
- Link accounts to specific branches.

### 5. **Transaction Management**
- Record all types of transactions (deposits, withdrawals, transfers).
- Maintain logs with timestamps for each transaction.
- Track balances for each account.

### 6. **Deposit & Withdrawals**
- Allow deposits to an account.
- Allow withdrawals from an account.
- Each operation links to a transaction ID for traceability.

### 7. **Funds Transfer**
- Transfer funds from one account to another (transferout & transferin).
- Store details like sender/receiver account numbers, amount, and timestamp.

### 8. **Support Ticket System**
- Allow users to raise tickets for issues.
- Admin/staff can update and resolve tickets.
- Maintain ticket status and resolution messages.

### 9. **Interest Table Management**
- Store and manage interest rates for different account types.
- Update rates as required.

### 10. **Announcements**
- Post announcements for users/customers (e.g., system updates, new features).
- Include title, message, creation, and update timestamps.

### 11. **Audit Logs and History**
- Maintain logs for deleted accounts.
- Track login/logout events.
- Store past balances and account edits.

---

## 🏗️ System Architecture

The architecture of the Banking System is designed to be modular and scalable, composed of multiple interacting layers and services:

### **1. Frontend Layer**
- Built using **ReactJS**
- Communicates with the backend through REST APIs
- Responsible for user interaction and UI rendering

### **2. Backend Layer**
- Developed with **Django (Python)**
- Handles business logic and database operations
- Includes API endpoints, authentication, and transaction processing

### **3. Celery Workers**
- Used for background processing (e.g., sending emails, logs)
- Task queue powered by **Redis**

### **4. Database Layer**
- **SQLite** stores structured banking data
- Tables include customer, account, transaction, logs, etc.

### **5. Monitoring & Observability**
- **Prometheus** scrapes metrics from Django and Redis
- **Grafana** visualizes real-time data and system health

### **6. CI/CD Pipeline**
- **Jenkins** automates build, test, and deployment
- Integrated with GitHub and DockerHub

### **7. Containerization & Orchestration**
- **Docker** used to containerize each service (frontend, backend, workers)
- **Kubernetes** orchestrates services and manages deployments, networking, scaling

<img width="611" alt="image" src="https://github.com/user-attachments/assets/e3c2321e-6d3f-42a9-adfc-0a8ee3f279b3" />

---
##💡 Why This Project?

In today's digital-first world, banking systems require high performance, security, and scalability. Traditional banking software often lacks real-time responsiveness, modularity, and integration with modern DevOps practices. This project aims to bridge that gap by providing a robust solution using modern technologies like Django, React, Docker, and Kubernetes.

By implementing this system, we address real-world challenges such as:
- Efficient customer onboarding and user management.
- Secure transaction processing and logging.
- Scalable infrastructure deployment.
- Real-time monitoring and alerting.

It reflects how modern banking infrastructures can evolve to stay competitive while remaining user-centric and reliable.

---

## 🌟 Advantages of the Banking System Project

### ✅ Scalable Microservices Architecture
- Designed for scalability using Docker and Kubernetes.
- Enables horizontal scaling and load distribution.

### 🔐 Enhanced Security
- Role-based access control for users and staff.
- Centralized audit logs and authentication mechanisms.

### 🧠 Intelligent Background Processing
- Integrated Celery with Redis for asynchronous task handling (e.g., email notifications, ticket alerts).

### 📊 Comprehensive Monitoring
- Prometheus and Grafana dashboards enable real-time tracking of performance and metrics.

### 🔄 Continuous Integration & Delivery
- Jenkins pipeline ensures seamless updates and deployment.
- Supports agile development workflows.

### 📱 Responsive Frontend
- Built with ReactJS for a user-friendly interface.
- Smooth interaction across desktop and mobile browsers.

### 🧩 Modular Design
- Clear separation of concerns (frontend, backend, worker services).
- Easy to maintain, test, and upgrade.

---



## 🚀 Step-by-Step Deployment Guide

This section previously included terminal commands for deploying the application using Docker and Kubernetes. For clarity and simplicity, we are presenting a high-level overview of the deployment steps:

### Deployment Flow Overview

1. **Docker Image Preparation**
   - Login to DockerHub
   - Build and tag the Docker image
   - Push the image to DockerHub repository

2. **Run the Application Locally with Docker**
   - Run the backend (Django) and frontend (React) containers
   - Ensure services are accessible via browser (localhost ports)

3. **Kubernetes Cluster Setup with Minikube**
   - Start/reset Minikube cluster
   - Deploy Kubernetes manifests (YAML files)
   - Expose services and verify pods

4. **Monitoring Stack Installation**
   - Create a dedicated monitoring namespace
   - Deploy Redis Exporter
   - Deploy Prometheus and Grafana
   - Port-forward services for local access

5. **Access Services via Browser**
   - Access NodePort, Prometheus, and Grafana UIs

---
## Grafana Dashboard
![IMG-20250407-WA0033](https://github.com/user-attachments/assets/a33a0247-92ce-4064-bd81-56140e956162)<br><br>

![IMG-20250407-WA0032](https://github.com/user-attachments/assets/a04a3d0c-981e-448a-a3eb-22f80b63a22c)<br><br>

![IMG-20250407-WA0031](https://github.com/user-attachments/assets/0bf02d08-d1e8-46cf-bafd-4721dcb7e92e)<br><br>
![IMG-20250407-WA0030](https://github.com/user-attachments/assets/88198a28-9fe3-4759-bec3-4fe10a68c63c)<br><br>
![IMG-20250407-WA0034](https://github.com/user-attachments/assets/2454c2e7-8deb-409e-b935-3787a9753e53)<br><br>
![IMG-20250407-WA0037](https://github.com/user-attachments/assets/e6472861-da04-4425-83d5-2148793cf29c)<br><br>
![IMG-20250407-WA0036](https://github.com/user-attachments/assets/4d5ed877-6116-4ce4-9951-12a1af5c6aeb)<br><br>
![IMG-20250407-WA0035](https://github.com/user-attachments/assets/ee8b0db4-4dac-46bb-bb86-5c25ca6b4d97)<br><br>
![IMG-20250407-WA0038](https://github.com/user-attachments/assets/d7587e74-3f96-4488-a1a9-9e2425446dda)<br><br>
![IMG-20250407-WA0039](https://github.com/user-attachments/assets/7e4103f3-a516-4706-8f59-6bf5dd83e886)<br><br>

## 🔧 Site Reliability Engineering (SRE) Tools Used
- **Docker**: Containerization of app components.
- **Kubernetes**: Cluster orchestration for scaling and reliability.
- **Jenkins**: CI/CD automation.
- **Prometheus**: Metrics collection.
- **Grafana**: Dashboard visualization of metrics.

---

![WhatsApp Image 2025-04-07 at 12 24 46_4eb113be](https://github.com/user-attachments/assets/25814cf5-0eb0-48be-999e-fef73cf8eeb8)


## ✅ Conclusion
This comprehensive Banking System enables secure, scalable financial operations and includes monitoring capabilities for high reliability. The architecture supports modern DevOps and SRE practices, ensuring production-readiness and observability.

*Next: Add Kubernetes architecture diagram once the image is shared.*

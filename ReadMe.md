# 🛠️ FreeScout Docker Deployment

A containerized, self-hosted help desk application built with Docker Compose using the [tiredofit/freescout](https://hub.docker.com/r/tiredofit/freescout) image. This project demonstrates a real-world containerization and deployment scenario suitable for DevOps labs, self-hosting, or preparing for Azure cloud infrastructure roles.

---

## 📦 Project Overview

This repository sets up a complete FreeScout instance using Docker Compose, following best practices for:

- **Secure configuration using environment variables**
- **Data persistence with Docker volumes**
- **Testing locally before production**
- **Scalability for future container hosting (e.g. Azure Container Apps)**

This project supports hands-on learning in containerization, volume mounting, environment configuration, and self-hosting fundamentals — all while deploying a functional help desk app.

---

## 🧰 Tech Stack

- **Docker + Docker Compose**
- **FreeScout** (via `tiredofit/freescout` image)
- **MariaDB** (as the backend database)
- **.env file** for sensitive configuration values
- *(Optional)* GitHub for version control and portability

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

git clone https://github.com/smiths0521/freescout-docker.git
cd freescout-docker
### 2. Create a `.env` File

Create a `.env` file in the root directory (next to `docker-compose.yml`) and add your secure environment variables:
env
DB_NAME=freescout
DB_USER=freescoutuser
DB_PASS=strongpassword
DB_ROOT_PASS=rootpassword

> 🛡️ Use strong passwords — this file should **not be committed to GitHub**. It’s in `.gitignore` by default.

---

### 3. Start the Containers

docker compose up -d

FreeScout will now begin its setup and be available at:
**[http://localhost:80](http://localhost:80)** (or your configured port)

📌 If you're running on Linux and need root privileges:

sudo docker compose up -d

---

### 4. Stop the Environment

docker compose down

This will stop all containers but keep your persistent data safe.

---

## 📁 Project Structure

freescout-docker/
├── docker-compose.yml

├── .env             # Your secure config (excluded from Git)

└── README.md

---

## ✅ What This Project Covers

* ✅ Container orchestration using `docker-compose`
* ✅ Environment-based configuration
* ✅ Freescout + MariaDB integration
* ✅ Secure secrets management (via `.env`)
* ✅ Volume persistence for database and uploaded files
* ✅ Debugging container startup logs

---

## 🔒 Security Notes

* Passwords and sensitive variables are passed via `.env` — **never commit this file.**
* Ensure your firewall or reverse proxy protects this if exposed to the internet.
* When production-ready, consider HTTPS (via reverse proxy like Nginx + Let's Encrypt) and database hardening.

---

## 🌐 Future Enhancements (Optional)

* Add Nginx reverse proxy with HTTPS
* Deploy to Azure Container Apps or Azure VM
* Configure SMTP and mail routing
* CI/CD pipeline for GitHub integration

---

## 🤝 Acknowledgments

* [FreeScout](https://freescout.net/) – the lightweight helpdesk solution
* [tiredofit/freescout](https://hub.docker.com/r/tiredofit/freescout) – container maintainer
* Microsoft Learn – reference for Docker container lesson structure

---

## 🧑‍💻 Built For:

Those learning container deployment, DevOps tooling, or preparing for cloud-native roles using Azure, Docker, and GitHub.


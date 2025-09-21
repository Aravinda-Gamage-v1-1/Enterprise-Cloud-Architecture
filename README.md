# Cloud-Enabled Deployment with AWS & GCP

This project demonstrates a **cloud-enabled, microservices-based deployment architecture** using **Spring Boot**, **React**, **Docker**, and cloud platforms (**AWS** & **GCP**).

It provides an end-to-end example of how to **develop, containerize, and deploy** backend services and a frontend application with both **cloud-managed** and **self-hosted databases**.

---

## Author  

| Name               | Student ID      | Email                            | GitHub                                                    |
|--------------------|-----------------|----------------------------------|-----------------------------------------------------------|
| Ashen Sumudu Aravinda | 2301682016   | aravindagamage1998@gmail.com     | [GitHub Profile](https://github.com/Aravinda-Gamage-v1-1) |

---

## Repository Structure

The repository contains the following modules:

* **course-service** → Spring Boot + MySQL - cloud deployment scaffolding for AWS & GCP
* **student-service** → Spring Boot + MongoDB
* **media-service** → Spring Boot + Local file storage (extensible to S3/MinIO)
* **frontend-app** → React + TypeScript

---

## Backend Services

### 1. Course Service

* **Entity:** `Course(id, name, duration)`
* **REST Endpoints:**

  * `GET /courses`
  * `GET /courses/{id}`
  * `POST /courses`
  * `DELETE /courses/{id}`
* **Default Port:** `8081`
* Requires **MySQL** configuration

---

### 2. Student Service

* **Document:** `Student(registrationNumber, fullName, address, contact, email)`
* **REST Endpoints:**

  * `GET /students`
  * `GET /students/{id}`
  * `POST /students`
  * `DELETE /students/{id}`
* **Default Port:** `8082`
* Requires **MongoDB** configuration

---

### 3. Media Service

* **Resource:** File storage
* **REST Endpoints:**

  * `POST /files` (upload via multipart/form-data)
  * `GET /files` (list all files)
  * `GET /files/{id}` (retrieve file)
  * `DELETE /files/{id}` (remove file)
* **Default Port:** `8083`
* Uses local storage at `./data/media` (configurable via `MEDIA_STORAGE_DIR`)

---

## Frontend Application

* **Stack:** React, TypeScript, Material UI, Axios, Vite
* **Features:** Courses, Students, Media management
* **Scripts:**

  ```bash
  npm run dev       # Start development server
  npm run build     # Build production-ready bundle
  npm run preview   # Preview build output
  ```

---

## Development Environment

### Build Instructions

* **Backend Services:**

  ```bash
  mvn -q -e -DskipTests package
  ```
* **Frontend Application:**

  ```bash
  cd frontend-app
  npm install
  npm run dev
  ```

### Local Database Setup (Docker)

**Start MySQL**

```bash
docker run -d --name mysql \
  -v mysql-data:/var/lib/mysql \
  -e MYSQL_ROOT_PASSWORD=mysql \
  -p 15000:3306 mysql:lts
```

**Start MongoDB**

```bash
docker run -d --name mongo \
  -v mongo-data:/data/db \
  -e MONGO_INITDB_ROOT_USERNAME=root \
  -e MONGO_INITDB_ROOT_PASSWORD=mongo \
  -p 16000:27017 mongo:latest
```

> Data is persisted via Docker volumes: `mysql-data`, `mongo-data`

---

## Deployment

The system can be deployed across **AWS** and **Google Cloud Platform (GCP)**.

* **Containerized with Docker** for portability
* **Cloud-managed databases** or **self-hosted instances** supported
* Configurable for:

  * AWS EC2 + RDS + S3
  * GCP Compute Engine + Cloud SQL + Cloud Storage

*(Deployment configurations and infrastructure-as-code templates are included in the project repository.)*

---

## Technology Stack

* **Backend:** Spring Boot, Maven
* **Frontend:** React, TypeScript, Vite, Material UI
* **Databases:** MySQL, MongoDB
* **DevOps:** Docker
* **Cloud:** AWS, GCP

---

## Demo

🎥 [Watch the Demo](https://drive.google.com/file/d/18fw68TR0NWvbqgsSHC48fQCzT8tNx_00/view?usp=share_link)

---

## Clone the Project

```bash
git clone https://github.com/Aravinda-Gamage-v1-1/Enterprise-Cloud-Architecture.git
```

---

## License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

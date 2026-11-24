# Serverless Task Manager REST API (AWS)

**Developed by:** Sameer Kumar  
**Course:** B.Tech in Computer Science & Engineering (IIMT College of Engineering, AKTU)  

---

## 📋 Project Overview

This project implements a **fully serverless, cloud-native REST API** for task and to-do management. Built using **AWS Lambda** for event-driven compute, **Amazon API Gateway** for HTTP routing, and **Amazon DynamoDB** as a NoSQL database, the system eliminates server provisioning and maintenance overhead while offering automatic scalability.

The API supports complete **CRUD operations** (Create, Read, Update, Delete) with status-based filtering and is accessible via any standard HTTP client such as Postman, cURL, or a web frontend.

---

## 🏗️ System Architecture

```text
┌──────────┐     ┌───────────────┐     ┌──────────┐     ┌──────────────┐
│  Client  │────▶│  API Gateway  │────▶│  Lambda  │────▶│  DynamoDB    │
│ (curl/   │◀────│  (REST API)   │◀────│ Function │◀────│  (TaskTable) │
│  Postman)│     └───────────────┘     └──────────┘     └──────────────┘
└──────────┘                                │
                                            ▼
                                     ┌──────────────┐
                                     │  CloudWatch  │
                                     │   (Logs)     │
                                     └──────────────┘
                                     ```

---

## 🚀 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/tasks` | Retrieve all tasks (supports optional `?status=` query filter) |
| `GET` | `/tasks/{id}` | Retrieve a specific task by its unique ID |
| `POST` | `/tasks` | Create a new task item |
| `PUT` | `/tasks/{id}` | Update an existing task's details or status |
| `DELETE` | `/tasks/{id}` | Remove a task from the database |

---

## 🛠️ AWS Services & Tech Stack

* **Compute:** AWS Lambda
* **API Management:** Amazon API Gateway (REST API)
* **Database:** Amazon DynamoDB (`TaskTable`)
* **Monitoring & Logging:** Amazon CloudWatch
* **Security:** AWS IAM (Least-privilege execution role)
# Go Uptime Monitor

A lightweight uptime monitoring application built using **Go**, **Docker**, **AWS ECS Fargate**, and **Terraform**. This application monitors the uptime of various services and exposes endpoints for health, status, and monitoring control.

> 🔗 **Hosted URL**: [`monitor.modulynx.in`](http://monitor.modulynx.in)

> ⚠️ Note: The service may not always be running due to infrastructure cost optimizations. Please refer to the deployment instructions to set it up on your own AWS environment.

---

## 🧠 Features

- Written in **Go** for performance and concurrency
- API endpoints:
  - `GET /health` – Health check for the server
  - `GET /monitored` – View all currently monitored URLs
  - `POST /monitor` – Add a new URL to monitor uptime
- Built as a **Docker container** and deployed via **ECS Fargate**
- Infrastructure managed via **Terraform**

---

## 🏗️ Architecture

- **Frontend**: Exposed via **Application Load Balancer** (ALB)
- **Backend**: Go HTTP server hosted in ECS Fargate containers
- **Logging**: Integrated with **AWS CloudWatch Logs**
- **Networking**: VPC with public subnets and security groups
- **Domain**: `monitor.modulynx.in` pointing to the ALB via **GoDaddy DNS + ACM certificate**

---

## 🛠️ Tech Stack

| Tool        | Purpose                      |
|-------------|------------------------------|
| Go          | Application logic            |
| Docker      | Containerization             |
| AWS ECS     | Container orchestration      |
| Fargate     | Serverless compute engine    |
| Terraform   | Infrastructure as Code (IaC) |
| ACM         | HTTPS Certificate management |
| CloudWatch  | Logs                         |
| Route 53    | DNS management (optional)    |

---

## 🚀 Getting Started

You can deploy this project to your own AWS account using the [infrastructure code](https://github.com/your-username/go-uptime-monitor-infra) and [application source](https://github.com/your-username/go-uptime-monitor-app). Follow the steps in the `infra/README.md` for provisioning resources using Terraform.

---

## 📁 Project Structure

This project is split into two repositories:

1. **Infrastructure (Terraform)** – [`go-uptime-monitor-infra`](https://github.com/your-username/go-uptime-monitor-infra)
2. **Application (Go + Docker)** – [`go-uptime-monitor-app`](https://github.com/your-username/go-uptime-monitor-app)

---

## 📬 API Endpoints

| Method | Endpoint                    | Description              |
|--------|-----------------------------|--------------------------|
| GET    | `/health`                   | Server health check      |
| GET    | `/monitored`                | List monitored URLs      |
| POST   | `/monitor`                  | Add new URL to monitor   |

---

## 📦 Deployment Notes

- **Domain**: Managed via GoDaddy with a CNAME pointing to ALB
- **Certificate**: Issued via ACM (Amazon Certificate Manager)
- **Public Access**: Ensure security group allows traffic on ports 80/443/8080 as needed

---

## 📌 To Do (Upcoming)

- Add persistent storage (e.g., RDS or DynamoDB)
- CI/CD pipeline for auto-deployment
- Alerts and notifications

---

## 🧾 License

This project is open-source and available under the [MIT License](LICENSE).
# 🏥 Patient Management System – Java Microservices Project

A comprehensive **Java-based Microservices Project** built from scratch, demonstrating enterprise-grade architecture, scalable service communication, event-driven design using Kafka, and infrastructure-as-code using AWS CDK + LocalStack.

---

## 📚 Project Structure

This project follows a **microservices architecture** and includes the following services:

- **Patient Service** – Manages patient CRUD operations.
- **Billing Service** – Handles billing logic via gRPC.
- **Analytics Service** – Consumes patient events from Kafka.
- **Auth Service** – JWT-based authentication service.
- **API Gateway** – Central entry point with routing and security.

---

## 🚀 Technology Stack

| Area            | Tech Stack                                                                 |
|-----------------|----------------------------------------------------------------------------|
| Language        | Java 17                                                                     |
| Framework       | Spring Boot                                                                 |
| API Gateway     | Spring Cloud Gateway                                                        |
| Auth            | Spring Security + JWT                                                       |
| Inter-service   | REST, gRPC                                                                  |
| Async Messaging | Apache Kafka                                                                |
| Databases       | PostgreSQL (via AWS RDS CDK)                                                |
| IaC             | AWS CDK (in Java)                                                           |
| Local AWS Mock  | LocalStack                                                                  |
| Containers      | Docker                                                                      |
| Service Registry| AWS CloudMap via ECS                                                        |
| Monitoring      | AWS CloudWatch Logs                                                         |

---

## 📂 Modules / Services

### 1. **Patient Service**
- CRUD operations for patients.
- Sends patient events to Kafka.
- Calls Billing Service via gRPC.

### 2. **Billing Service**
- Exposes gRPC server.
- Handles billing logic invoked during patient creation.

### 3. **Analytics Service**
- Kafka consumer that listens to patient events.
- Prints or stores analytics data.

### 4. **Auth Service**
- JWT-based login & token validation.
- Stores user data in PostgreSQL.

### 5. **API Gateway**
- Routes all API requests to appropriate services.
- Handles JWT validation using Auth Service.

---

## 🛠️ Development Flow

Below is a high-level breakdown of the project and what was built:

### 🔧 Development Setup
- Java, Maven, Docker, Spring Boot dev tools, etc.

### 📐 Architecture Design
- Monorepo structure.
- Microservices communication via REST, gRPC, Kafka.

### 📦 Service Development
- Controllers, DTOs, Validation, Services, Repositories.
- Unit and integration testing for endpoints.

### 🐘 Databases
- PostgreSQL setup per service.
- Data seeding via SQL or Spring `data.sql`.

### 🐳 Dockerization
- Dockerfiles for each service.
- Docker Compose setup for local development (optional).

### 📡 gRPC
- Proto files for patient ↔ billing.
- Client and server implementation using Spring Boot gRPC.

### 📨 Kafka
- Patient events produced after creation.
- Consumed by Analytics Service.

### 🔐 Authentication
- Auth Service with JWT generation and validation.
- Token validation integrated with API Gateway filter.

### 🌐 API Gateway
- Routes requests to services.
- Applies JWT security filters.

---

## ☁️ Infrastructure as Code (AWS CDK)

### 📦 Stack Components
- VPC
- RDS for each service
- Health checks
- MSK (Kafka) Cluster
- ECS Fargate cluster + services
- CloudMap for service discovery
- Application Load Balancer for API Gateway

### 🧪 Local Deployment
Deployed using **LocalStack**, simulating AWS locally.

---

## 🧪 Testing

- Unit testing with JUnit & Mockito.
- Integration tests for:
  - Auth login & protected routes
  - Patient service CRUD
  - Token validation scenarios

---

## 🧑‍💻 How to Run (Local)

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/patient-management-system.git
   cd patient-management-system

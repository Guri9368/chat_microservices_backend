<h1 align="center">🔗 ChatSync – Real-Time Microservices Chat App</h1>

<p align="center">
  A production-ready <b>real-time chat platform</b> built with <b>Microservices</b>, 
  <b>MERN stack</b>, <b>RabbitMQ</b>, <b>Docker</b>, and <b>AWS EC2</b>, designed for scalability, performance, and learning.
</p>

<p align="center">
  🔥 <i>Built for interviews, devops practice, and advanced backend systems</i> 🔥
</p>

---

## 🚀 Features Overview

- ⚙️ **Microservices Architecture**: Modular services for User, Chat, and Mail — enabling independent scalability and faster deployments.
- 🔒 **Authentication Service**:
  - JWT-based Auth
  - OTP-based Email Verification (via RabbitMQ)
  - Redis-backed Session Management
- 💬 **Chat Service**:
  - Real-time messaging with Socket.IO
  - Typing indicators, delivery statuses, presence tracking
  - Media sharing via Cloudinary
- 📬 **Mail Service**:
  - Email OTPs and notifications via RabbitMQ queues
- 🗃️ **Queueing with RabbitMQ**:
  - Decoupled inter-service communication
  - High reliability, retry logic
- ⚡ **API Gateway**:
  - Centralized entry point with route proxying and load distribution
- 🐳 **Dockerized Infrastructure**:
  - Fully containerized with Docker & Docker Compose
- ☁️ **AWS EC2 Deployment**:
  - Hosted on Ubuntu with Nginx & PM2 for process management
- 🧩 **Ready for Scaling**:
  - Easily extendable to Kubernetes, Prometheus/Grafana monitoring, etc.

---

## 🧱 System Architecture

markdown
Copy
Edit
                    ┌───────────────────┐
                    │     Frontend      │
                    └────────┬──────────┘
                             │
                    ┌────────▼──────────┐
                    │   API Gateway     │
                    └────────┬──────────┘
         ┌───────────────────┴────────────────────┐
         │                                        │
  ┌──────▼───────┐                        ┌───────▼───────┐
  │ Auth Service │                        │ Chat Service  │
  └──────┬───────┘                        └──────┬────────┘
         │                                        │
   ┌─────▼──────┐                          ┌──────▼──────┐
   │  RabbitMQ  │◄─────────────────────────┤  Mail Service│
   └────────────┘                          └──────────────┘
         │
   ┌─────▼──────┐
   │  MongoDB   │
   └────────────┘
markdown
Copy
Edit

---

## 🧑‍💻 Tech Stack (🔥 Highlighted)

| Layer             | Tech Stack                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Frontend**      | `Next.js` • `Tailwind CSS` • `TypeScript` (UI currently basic; extensible) |
| **Backend**       | `Node.js` • `Express.js` • `Socket.IO`                                     |
| **Database**      | `MongoDB` + `Mongoose`                                                     |
| **Communication** | `RabbitMQ` (via `amqplib`)                                                 |
| **Storage**       | `Cloudinary` for media uploads                                             |
| **Session Mgmt**  | `Redis`                                                                    |
| **Deployment**    | `Docker` • `Docker Compose` • `AWS EC2` • `PM2`                            |
| **Monitoring**    | `RabbitMQ Management UI` (Dashboard)                                       |

---

## 📁 Folder Structure

chat-app-microservices/
├── api-gateway/ # Handles routing and load balancing
├── auth-service/ # Login, Register, JWT, OTP via RabbitMQ
├── chat-service/ # WebSockets, message DB, status updates
├── mail-service/ # Email service consuming from RabbitMQ
├── frontend/ # Next.js UI (optional enhancement)
├── docker-compose.yml # Unified service orchestration

yaml
Copy
Edit

---

## ⚙️ Setup & Installation

### 🔐 Prerequisites

- Node.js v18+
- Docker & Docker Compose
- MongoDB
- RabbitMQ
- Git

### 🧰 Clone the Repository

```bash
git clone https://github.com/yourusername/chat-app-microservices.git
cd chat-app-microservices
▶️ Start Services with Docker
bash
Copy
Edit
docker-compose up --build
🐇 Visit RabbitMQ UI at http://localhost:15672 (default: guest/guest)

🔗 Local Service URLs
Service	URL
API Gateway	http://localhost:5000
Auth Service	http://localhost:5001
Chat Service	http://localhost:5002
RabbitMQ UI	http://localhost:15672
WebSocket	ws://localhost:8900

🔌 API Endpoints
Auth
http
Copy
Edit
POST   /api/v1/register       # User registration
POST   /api/v1/login          # Login with JWT
Chat
http
Copy
Edit
POST   /api/v1/chat           # Send or initiate chat
GET    /api/v1/chats/:id      # Get all messages by chat ID
🌐 Deployment on AWS EC2
SSH into EC2:

bash
Copy
Edit
ssh -i your-key.pem ubuntu@your-ec2-ip
Clone & setup .env files for each service

Start containers:

bash
Copy
Edit
docker-compose up --build -d
Open these ports in EC2 security group:

5000, 5001, 5002, 8900, 15672, 80

📈 Future Enhancements
🔍 OAuth 2.0 / Google Login

🧠 AI Assistant via Ollama + RAG (like Expensio project)

☁️ S3 Integration for file/image uploads

📲 Mobile App (React Native)

📊 Prometheus + Grafana dashboard

🧩 Kubernetes deployment on GCP/AWS EKS

🕵️‍♂️ WebSocket room authorization & reconnection logic

🔐 Rate limiting & email verification on critical actions

🎯 Why Dockerize RabbitMQ?
🛠️ Portability: Easy to boot on any system

⚙️ Isolation: No local RabbitMQ config conflicts

🚀 Quick Setup: docker-compose up spins up everything

🔄 Reliability: Clean restart, version control, resource-limited

🧠 Learning Outcomes
✅ Hands-on experience with Microservices and async event communication

🐳 Docker orchestration with PM2 + RabbitMQ

☁️ Real-world deployment on AWS EC2 with robust process monitoring

🎓 Great resume-ready project for backend/system design interviews

🙋‍♂️ Author
Gurmeet Singh Rathour
🎓 Final Year @ MNNIT Allahabad
💼 Passionate about DevOps, System Design & Cloud-Native Systems
📧 gurigurmeet1234567@gmail.com
🔗 LinkedIn

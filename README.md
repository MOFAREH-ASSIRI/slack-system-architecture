# slack-system-architecture
A Slack-like system project with architecture and CI
# Slack-Like Messaging System

## Architecture Overview

The system is a Slack-like messaging platform built using a microservices architecture. It consists of independently deployable services communicating via REST APIs and message queues. The architecture supports scalability, maintainability, and real-time communication.

### Key Components:

- **Frontend**: React-based SPA for user interface.
- **API Gateway**: Routes requests to backend services.
- **Auth Service**: Handles login, registration, and JWT token creation.
- **User Service**: Manages user profile and settings.
- **Channel Service**: Manages public and private channels.
- **Message Service**: Sends, stores, and retrieves chat messages.
- **Notification Service**: Delivers push or real-time alerts.
- **Database**: Each service owns its own DB (PostgreSQL).
- **Message Broker**: Kafka or RabbitMQ for events between services.
- **Object Storage**: For attachments (e.g., AWS S3).


## Architecture Components (Detailed)

### 1. Frontend
- A single-page application (SPA) built with React (or any modern frontend framework).
- Handles user interface, chat views, channel switching, and real-time message updates via WebSocket.

### 2. API Gateway
- A reverse proxy that routes requests to backend services (Auth, Users, Channels, Messages).
- Can enforce authentication, rate-limiting, and logging.
- Example: Kong, NGINX, or a custom Node.js/Express gateway.

### 3. Authentication Service
- Handles user registration, login, and logout.
- Issues JWT (JSON Web Tokens) for secure communication.
- Verifies token validity before allowing access to other services.

### 4. User Service
- Stores and manages user profiles (username, avatar, bio).
- Supports search, settings update, and account status.

### 5. Channel Service
- Manages public and private channels.
- Handles channel creation, joining, leaving, and listing members.

### 6. Message Service
- Handles sending, storing, retrieving messages (including attachments).
- Writes messages to a database.
- Publishes events to notify other users (via broker or WebSocket).

### 7. Notification Service
- Sends real-time updates using WebSocket or Firebase.
- Can support push notifications, sound alerts, and unread message counters.

### 8. Database(s)
- Each microservice owns its own database (PostgreSQL or MongoDB).
- Ensures data isolation and microservice independence.

### 9. Message Broker
- Handles event communication between services (e.g., new message, user joined).
- Tools: Kafka, RabbitMQ, or Redis Pub/Sub.

### 10. Object Storage
- Used to store user-uploaded images, videos, or files.
- Tools: Amazon S3, MinIO, or Google Cloud Storage.

### 11. Monitoring and Logging
- Logs service activity and errors (ELK: Elasticsearch, Logstash, Kibana).
- Monitors health, uptime, and metrics using Prometheus and Grafana.

---

## 🧠 Architecture Diagram

This is the system architecture diagram generated using D2:

![Architecture Diagram](d2.png)

The `architecture.d2` source file is included for editing or reuse.

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

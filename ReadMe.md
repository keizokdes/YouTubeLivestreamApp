# YouTube Livestream Tracking Service

> YouTube Livestream has full of user engagement information while no one has access to this kind of data other than the livestream channel owner. This application detects specified channels' livestream session automatically, monitor the engagement such as comments, user donation, and the listeners, and provide an analysis regarding the interactions and listener donations per channel or livestream session in real time.

## Quick Snaps


## System Architecture
### Overview

This document outlines the high-level and detailed system architecture of the YouTube Livestream Tracking Service.

### Business & Technical Requirements

- Monitor and track YouTube livestream comments and donations in real time
- *Support 100+ concurrent streams with sub-200ms API response time
- Maintain high availability and fault tolerance
- Provide analytics dashboard and developer-friendly API

### Architecture Diagrams

- System Overview  
  ![System Overview](docs/diagrams/system-overview.png)

- Sequence Diagram  
  ![Data Flow](docs/diagrams/sequence-overview.png)

- Database Schema\
  ![Database Schema](docs/diagrams/database-schema.png)


### Components

| Component         | Technology         | Description |
|------------------|--------------------|-------------|
| Server-side API        | Flask              | REST API, request validation, routing |
| Async Processing  | Celery + RabbitMQ  | Background processing for comments & donations |
| Database          | PostgreSQL         | Normalized data storage |
| Frontend          | React Native       | Mobile interface |
| Infra             | Docker, AWS EC2    | Containerized deployment |


## Engineering Decisions

### Backend Stack

- **Flask** over FastAPI for flexibility
- **Celery + RabbitMQ** for async task handling
- **PostgreSQL** with normalized schema

### Infra & Tooling

- Dockerized for portability
- GitHub Actions for CI/CD
- Nginx + HTTPS (in production)

### Security (future feature)

- Rate limiting
- Input validation
- Webhook verification

### Performance (future feature)

- Indexing strategy in PostgreSQL
- Connection pooling
- Caching (future: Redis)
  
## Measured Results

## How to reproduce

> requires: .env for __frontend__/ and __backend__/


```bash
git clone https://github.com/Keizo410/YouTubeLivestreamApp.git
# for backend 
cd YouTubeLivestreamApp/backend
docker-compose up -d
# for frontend use web option 
cd ../frontend
npm install 
npm start 
``` 

## My contribution and limitations

## 📁 Documentation Overview

- [System Architecture](docs/ARCHITECTURE.md)
- [API Documentation](docs/API_DOCUMENTATION.md)
- [Development Setup](docs/DEVELOPMENT.md)
- [Testing Strategy](docs/TESTING.md)
- [Technical Decisions](docs/TECHNICAL_DECISIONS.md)
- [Contributing Guidelines](CONTRIBUTING.md)




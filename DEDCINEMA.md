# DedCinema 🎬

A production-ready cinema ticket booking platform built with microservices architecture.

## Architecture

The system consists of multiple microservices communicating via gRPC:

- **Gateway Service** — API Gateway, REST endpoints, auth middleware
- **Auth Service** — JWT, OTP (email/SMS), Telegram verification, role-based access
- **Movie Service** — Film catalog, categories, Redis caching
- **Screening Service** — Sessions management, scheduling
- **Theater Service** — Theaters, halls, seats management
- **Booking Service** — Seat reservation, ticket generation, QR codes
- **Payment Service** — Stripe integration, webhooks, payment lifecycle
- **Media Service** — File uploads to S3 (written in Go)
- **Notification Service** — Email/SMS notifications via RabbitMQ

## Tech Stack

### Backend
- **Runtime:** Node.js + TypeScript
- **Framework:** NestJS
- **Communication:** gRPC (protobuf contracts)
- **Message Queue:** RabbitMQ

### Databases
- **PostgreSQL** — structured data (auth, payments, theaters, bookings)
- **MongoDB** — screenings 
- **Redis** — caching, sessions, queues (BullMQ)

### Infrastructure
- **Containerization:** Docker + Docker Compose
- **Media Service:** Go
- **Payments:** Stripe (Checkout Sessions, Webhooks)
- **Storage:** S3

### Observability
- **Tracing:** Jaeger + OpenTelemetry
- **Metrics:** Prometheus + Grafana
- **Logs:** Loki + Promtail
- **Exporters:** postgres-exporter, redis-exporter, rabbitmq-exporter, node-exporter

## Getting Started

```bash
# Start infrastructure
docker compose up -d

# Install dependencies (per service)
yarn install

# Run migrations
yarn prisma migrate dev  # PostgreSQL services
yarn run migrate:up      # Custom migration runner

# Start service
yarn start:dev
```

## API Documentation

Swagger UI available at `http://localhost:4000/docs`

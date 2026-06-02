# DedStream 🎥

A full-stack live streaming platform built with NestJS and Next.js — inspired by Twitch/YouTube Live. Supports real-time video streaming, chat, OTP authentication, Telegram verification, and Stripe payments.

## Features

- 🔐 **Auth** — JWT sessions, OTP via email/SMS, Telegram verification, 2FA with QR codes
- 🎬 **Streaming** — Real-time video via LiveKit (WebRTC)
- 💬 **Chat** — GraphQL Subscriptions for live chat
- 💳 **Payments** — Stripe Checkout integration
- 📁 **Media** — Image upload and processing (Sharp + AWS S3)
- 🌐 **i18n** — Multi-language support via next-intl
- 📧 **Notifications** — Transactional emails with React Email + Nodemailer

## Tech Stack

### Backend
- **Runtime:** Node.js + TypeScript
- **Framework:** NestJS
- **API:** GraphQL (Apollo Server v5)
- **ORM:** Prisma (PostgreSQL adapter)
- **Auth:** JWT, express-session, OTP (otpauth), Telegram (nestjs-telegraf)
- **Streaming:** LiveKit Server SDK
- **Payments:** Stripe
- **Storage:** AWS S3 + Sharp (image processing)
- **Email:** Nodemailer + React Email templates
- **Cache/Sessions:** Redis (ioredis, connect-redis)
- **Scheduling:** @nestjs/schedule

### Frontend
- **Framework:** Next.js 16 (App Router)
- **Language:** TypeScript
- **Styling:** Tailwind CSS v4 + shadcn/ui + Radix UI
- **State Management:** Zustand
- **Forms:** React Hook Form + Zod
- **API Client:** Apollo Client + GraphQL Codegen
- **Streaming:** LiveKit Components React
- **Payments:** Stripe Checkout (redirect flow)
- **i18n:** next-intl
- **DnD:** @hello-pangea/dnd

### Database
- **PostgreSQL** — users, streams, payments, sessions
- **Redis** — caching, session store

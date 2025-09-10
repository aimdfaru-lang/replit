# Nuvra AI - AI API Platform

## Overview

Nuvra AI is a comprehensive AI API platform that provides unified access to 300+ AI models through a single API endpoint. The application serves as an API gateway and management platform, allowing users to interact with various AI models (GPT-5, Claude, Gemini, DeepSeek, etc.) through a standardized interface. It features a modern web dashboard for API key management, usage analytics, billing, and an interactive playground for testing AI models.

The platform is built as a full-stack TypeScript application with Express.js backend and React frontend, targeting developers and businesses who need reliable AI model access with enterprise-grade features like authentication, usage tracking, and billing integration.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript and Vite for fast development and building
- **UI Library**: Shadcn/ui components built on Radix UI primitives for consistent, accessible design
- **Styling**: Tailwind CSS with CSS variables for theming and dark mode support
- **State Management**: TanStack Query (React Query) for server state management and caching
- **Routing**: Wouter for lightweight client-side routing
- **Forms**: React Hook Form with Zod validation for type-safe form handling

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ESM modules for modern JavaScript features
- **Authentication**: Replit OAuth integration with session-based authentication
- **Database ORM**: Drizzle ORM with PostgreSQL for type-safe database operations
- **API Proxy**: Custom AI model proxy system that translates between different AI provider APIs

### Database Design
- **Primary Database**: PostgreSQL with Neon serverless hosting
- **Schema Management**: Drizzle Kit for migrations and schema management
- **Key Tables**:
  - `users`: User profiles and subscription information
  - `api_keys`: User-generated API keys with hashing and usage tracking
  - `usage`: Detailed request logging and cost tracking per model
  - `billing_history`: Payment and subscription tracking
  - `sessions`: Secure session storage for authentication

### AI Model Integration
- **Model Proxy System**: Unified interface that maps Nuvra model names to actual provider models
- **Supported Providers**: OpenAI, Anthropic, Google (Gemini), DeepSeek with extensible architecture
- **Cost Tracking**: Per-request token usage and cost calculation with configurable pricing
- **Request Validation**: Zod schemas for input validation and type safety

### Authentication & Authorization
- **OAuth Provider**: Replit OAuth with OIDC (OpenID Connect) integration
- **Session Management**: PostgreSQL-backed sessions with configurable TTL
- **API Authentication**: Bearer token authentication for API endpoints
- **Security**: Secure cookie handling, CORS configuration, and request validation

### Payment Integration
- **Payment Processor**: Stripe integration for subscription management and billing
- **Subscription Plans**: Multiple tiers (Developer, Startup, Production, Scale, Enterprise)
- **Usage-Based Billing**: Pay-per-use model with detailed cost tracking
- **Billing Dashboard**: Real-time usage analytics and payment history

## External Dependencies

### Core Infrastructure
- **Database**: Neon PostgreSQL serverless database for scalable data storage
- **Authentication**: Replit OAuth service for user authentication and authorization
- **Payment Processing**: Stripe for subscription management, payment processing, and billing
- **Session Storage**: PostgreSQL-based session storage with connect-pg-simple

### AI Model Providers
- **OpenAI**: GPT models, embeddings, and completions API
- **Anthropic**: Claude models for advanced reasoning and longer contexts
- **Google AI**: Gemini models for multimodal AI capabilities
- **DeepSeek**: Cost-effective AI models with competitive performance

### Development & Monitoring
- **Build Tool**: Vite for fast development server and optimized production builds
- **Runtime Error Handling**: Replit error overlay plugin for development debugging
- **Code Quality**: TypeScript strict mode with comprehensive type checking
- **Development Server**: Express with Vite middleware integration for full-stack development

### UI & Design System
- **Component Library**: Radix UI primitives for accessible, unstyled components
- **Design Tokens**: Shadcn/ui design system with customizable theming
- **Icons**: Lucide React for consistent iconography
- **Fonts**: Google Fonts (Inter, JetBrains Mono) for typography
- **Animation**: CSS transitions and Tailwind utilities for smooth interactions
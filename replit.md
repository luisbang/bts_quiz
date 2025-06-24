# BTS Personality Quiz Application

## Overview

This is a full-stack web application that determines which BTS member matches a user's personality through an interactive quiz. The application features a colorful, modern interface with BTS-themed styling and provides detailed personality insights based on quiz responses.

## System Architecture

The application follows a monorepo structure with clear separation between frontend and backend:

- **Frontend**: React-based SPA built with Vite
- **Backend**: Express.js REST API server
- **Database**: PostgreSQL with Drizzle ORM
- **Deployment**: Replit with autoscale deployment target

### Directory Structure
```
├── client/          # React frontend application
├── server/          # Express.js backend API
├── shared/          # Shared types and schemas
├── migrations/      # Database migration files
└── components.json  # shadcn/ui configuration
```

## Key Components

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite with custom configuration
- **Routing**: Wouter (lightweight React router)
- **State Management**: TanStack Query for server state
- **UI Library**: shadcn/ui components with Radix UI primitives
- **Styling**: Tailwind CSS with custom BTS-themed color palette
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database ORM**: Drizzle ORM with PostgreSQL
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **API Style**: RESTful endpoints
- **Validation**: Zod schemas for request/response validation
- **Session Storage**: connect-pg-simple for PostgreSQL session storage

### Database Schema
The application uses three main tables:
- `quiz_questions`: Stores quiz questions with multiple choice options
- `bts_member_profiles`: Contains detailed BTS member information and traits
- `quiz_results`: Tracks user quiz completions and results

## Data Flow

1. **Quiz Flow**: User starts quiz → Questions fetched from API → User answers stored → Result calculated → Personality match displayed
2. **Result Calculation**: Answers are aggregated by member preference → Most frequent member becomes the result
3. **Session Management**: Each quiz session gets a unique ID for result tracking

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: Serverless PostgreSQL connection
- **drizzle-orm**: Type-safe database operations
- **@tanstack/react-query**: Server state management
- **wouter**: Lightweight routing for React
- **@radix-ui/***: Accessible UI component primitives
- **tailwindcss**: Utility-first CSS framework

### Development Dependencies
- **vite**: Fast build tool and dev server
- **tsx**: TypeScript execution for development
- **esbuild**: Fast JavaScript/TypeScript bundler for production

## Deployment Strategy

The application is configured for Replit deployment with:
- **Development**: `npm run dev` - runs both frontend and backend in development mode
- **Build**: `npm run build` - creates production builds for both client and server
- **Production**: `npm run start` - serves the production application
- **Database**: Uses environment variable `DATABASE_URL` for PostgreSQL connection
- **Port Configuration**: Server runs on port 5000, mapped to external port 80

### Environment Setup
- Node.js 20 runtime
- PostgreSQL 16 module enabled
- Nix package manager for system dependencies

## Changelog
- June 24, 2025. Initial setup

## User Preferences

Preferred communication style: Simple, everyday language.
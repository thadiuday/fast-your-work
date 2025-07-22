# Find Your Work - Mobile Application

## Overview

This is a full-stack mobile application built for connecting workers with job opportunities. The application features a React frontend with TypeScript, an Express.js backend, and uses PostgreSQL with Drizzle ORM for data management. The app is designed as a mobile-first experience with features like visual search, real-time messaging, and job matching.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with shadcn/ui component library
- **State Management**: TanStack React Query for server state
- **Routing**: Wouter for client-side routing
- **Build Tool**: Vite for development and production builds
- **Mobile-First Design**: Responsive design optimized for mobile devices

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Runtime**: Node.js with ESM modules
- **Database ORM**: Drizzle ORM for type-safe database operations
- **API Design**: RESTful API endpoints
- **Session Management**: PostgreSQL-based session storage

### Data Storage
- **Database**: PostgreSQL (configured for Neon serverless)
- **ORM**: Drizzle ORM with Zod validation
- **Migrations**: Drizzle Kit for schema management
- **Connection**: Serverless-compatible with connection pooling

## Key Components

### Database Schema
The application manages five main entities:
- **Users**: Authentication and user management
- **Workers**: Worker profiles with skills, ratings, and availability
- **Jobs**: Job postings created by recruiters
- **Job Applications**: Connections between workers and jobs
- **Messages**: Real-time communication system

### Frontend Components
- **Layout Components**: Header navigation and bottom tab navigation
- **Interactive Components**: Visual search, live chat, filter bars
- **Data Components**: Worker cards, job cards, message interfaces
- **UI Components**: Comprehensive shadcn/ui component library

### Backend Services
- **Storage Layer**: Abstracted storage interface with in-memory implementation
- **Route Handlers**: RESTful endpoints for all entities
- **Validation**: Zod schemas for request/response validation
- **Development Tools**: Hot reload and error overlay for development

## Data Flow

1. **Client Requests**: React components use TanStack React Query to make API calls
2. **API Layer**: Express routes handle requests and validate data using Zod schemas
3. **Storage Layer**: Storage interface abstracts database operations
4. **Database**: Drizzle ORM manages PostgreSQL operations with type safety
5. **Response Flow**: JSON responses flow back through the query client to React components

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: PostgreSQL serverless driver
- **@tanstack/react-query**: Server state management
- **@radix-ui/***: Accessible UI primitives
- **drizzle-orm**: Type-safe ORM
- **wouter**: Lightweight routing

### Development Tools
- **Vite**: Fast build tool and development server
- **@replit/vite-plugin-***: Replit-specific development enhancements
- **TypeScript**: Type safety across the stack
- **Tailwind CSS**: Utility-first styling

### UI and UX
- **shadcn/ui**: Modern component library
- **class-variance-authority**: Component variant management
- **lucide-react**: Icon library
- **date-fns**: Date manipulation utilities

## Deployment Strategy

### Development
- Uses Vite dev server with HMR
- Express server runs on Node.js with tsx for TypeScript execution
- Development-specific plugins for error handling and debugging

### Production
- Frontend: Vite builds to static assets
- Backend: esbuild bundles Express server for Node.js
- Database: Drizzle migrations handle schema updates
- Environment: Configured for serverless deployment (Replit/cloud platforms)

### Build Process
1. `npm run build`: Builds both frontend (Vite) and backend (esbuild)
2. `npm run start`: Runs production server serving static assets and API
3. `npm run db:push`: Applies database schema changes via Drizzle

The application is architected for modern serverless deployment while maintaining full-stack type safety and excellent developer experience.
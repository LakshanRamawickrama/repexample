# MedScript - Medical Prescription Management System

## Overview

MedScript is a full-stack web application that connects patients with pharmacies through a secure prescription upload and quotation system. The platform allows patients to upload prescription images and receive competitive quotes from multiple pharmacies, streamlining the medication procurement process.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: TailwindCSS with shadcn/ui component library
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query for server state management
- **Form Handling**: React Hook Form with Zod validation
- **Build Tool**: Vite with custom configuration for development and production

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Runtime**: Node.js with ESM modules
- **Session Management**: Express sessions with PostgreSQL store
- **File Upload**: Multer for prescription image handling
- **Authentication**: Session-based authentication with bcrypt password hashing

### Database Architecture
- **Database**: PostgreSQL (via Neon serverless)
- **ORM**: Drizzle ORM with type-safe queries
- **Migration**: Drizzle Kit for schema management
- **Connection**: Connection pooling with @neondatabase/serverless

## Key Components

### User Management
- **User Types**: Patients and Pharmacies with role-based access control
- **Authentication**: Session-based auth with secure password hashing
- **Authorization**: Route-level protection with role-specific access

### Prescription System
- **Upload**: Multi-image prescription upload with file validation
- **Storage**: Images stored in local filesystem with metadata in database
- **Status Tracking**: Prescription lifecycle management (uploaded → quoted → accepted/rejected)

### Quotation System
- **Quote Creation**: Pharmacies can create detailed quotes with itemized drug lists
- **Price Calculation**: Automatic total calculation with unit price × quantity
- **Status Management**: Quote acceptance/rejection workflow

### Real-time Features
- **Query Invalidation**: Automatic data refreshing on state changes
- **Optimistic Updates**: Immediate UI feedback with rollback on errors
- **Toast Notifications**: User feedback for actions and errors

## Data Flow

1. **Patient Registration**: User creates account with patient role
2. **Prescription Upload**: Patient uploads prescription images with delivery details
3. **Pharmacy Discovery**: Available prescriptions displayed to pharmacy users
4. **Quote Creation**: Pharmacies create detailed quotes with itemized pricing
5. **Quote Review**: Patients review and accept/reject quotes
6. **Order Processing**: Accepted quotes trigger order fulfillment workflow

## External Dependencies

### UI/UX Dependencies
- **Radix UI**: Accessible component primitives for complex UI components
- **Lucide React**: Icon library for consistent iconography
- **Class Variance Authority**: Utility for managing component variants
- **TailwindCSS**: Utility-first CSS framework for rapid styling

### Backend Dependencies
- **bcrypt**: Secure password hashing
- **multer**: File upload middleware
- **connect-pg-simple**: PostgreSQL session store
- **ws**: WebSocket support for Neon database connections

### Development Dependencies
- **tsx**: TypeScript execution for development
- **esbuild**: Fast JavaScript bundler for production builds
- **@replit/vite-plugin-runtime-error-modal**: Development error handling

## Deployment Strategy

### Development Environment
- **Hot Reload**: Vite dev server with HMR support
- **Error Handling**: Runtime error overlay for debugging
- **Database**: Neon serverless PostgreSQL with connection pooling

### Production Build
- **Frontend**: Vite production build with asset optimization
- **Backend**: esbuild bundling with external package references
- **Static Assets**: Served via Express static middleware
- **Environment**: NODE_ENV-based configuration switching

### Database Management
- **Schema**: Defined in shared/schema.ts with Drizzle ORM
- **Migrations**: Generated and managed via drizzle-kit
- **Connection**: Environment-based DATABASE_URL configuration

## Changelog
- July 01, 2025. Initial setup

## User Preferences

Preferred communication style: Simple, everyday language.
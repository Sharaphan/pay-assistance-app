# Pay Assistance Application

## Overview

This is a full-stack web application built for pay calculation assistance, designed to help users track their work hours, calculate earnings, and manage tax deductions. The application follows a monorepo structure with separate client and server directories, using modern web technologies for both frontend and backend development.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Build Tool**: Vite for development and production builds
- **UI Library**: Radix UI primitives with shadcn/ui components
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **State Management**: TanStack Query for server state and local React state for UI state
- **Routing**: Wouter for client-side routing
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Session Management**: PostgreSQL-backed sessions with connect-pg-simple
- **API Design**: RESTful API with structured error handling

### Development Setup
- **Development Server**: Vite dev server with HMR for frontend, tsx for backend hot reloading
- **Build Process**: Vite for frontend bundling, esbuild for backend compilation
- **Type Safety**: Shared TypeScript schemas between client and server

## Key Components

### Database Schema
The application uses four main database tables:
- **users**: User authentication and profile data
- **pay_weeks**: Weekly pay period records with calculated totals
- **work_days**: Individual work day entries with hours and earnings
- **tax_settings**: User-specific tax calculation settings

### API Endpoints
- `GET/POST /api/pay-weeks`: Manage pay week records
- `GET/POST/PUT/DELETE /api/work-days`: Handle individual work day entries
- `GET/POST/PUT /api/tax-settings`: Tax configuration management

### Core Features
- **Pay Calculation Engine**: Complex wage calculation with overtime, public holidays, and shift allowances
- **Tax Estimation**: Australian tax system calculations with TFN and ABN modes
- **Work Schedule Management**: Daily time tracking with break calculations
- **Default Schedule Templates**: Quick setup for recurring work patterns

## Data Flow

1. **User Input**: Time entries, hourly rates, and schedule settings through React forms
2. **Client Validation**: Zod schemas validate data before API calls
3. **API Processing**: Express routes handle CRUD operations with database transactions
4. **Database Storage**: Drizzle ORM manages PostgreSQL interactions
5. **Real-time Updates**: TanStack Query provides optimistic updates and cache management
6. **Tax Calculations**: Server-side calculations for accurate tax estimations

## External Dependencies

### Frontend Dependencies
- **UI Components**: Extensive Radix UI component library for accessible primitives
- **Date Management**: date-fns for date calculations and formatting
- **Form Validation**: @hookform/resolvers with Zod for type-safe form handling
- **Styling**: Tailwind CSS with class-variance-authority for component variants

### Backend Dependencies
- **Database**: @neondatabase/serverless for PostgreSQL connectivity
- **ORM**: drizzle-orm with drizzle-zod for schema validation
- **Session Storage**: connect-pg-simple for PostgreSQL session management
- **Development**: tsx for TypeScript execution and hot reloading

### Build Dependencies
- **Bundling**: Vite with React plugin for frontend, esbuild for backend
- **Development Tools**: Replit-specific plugins for development environment integration
- **Type Checking**: TypeScript compiler with strict mode enabled

## Deployment Strategy

### Development Environment
- **Frontend**: Vite dev server with HMR on port 5173
- **Backend**: Express server with tsx hot reloading
- **Database**: Neon Database connection via environment variables

### Production Build
- **Frontend**: Vite builds static assets to `dist/public`
- **Backend**: esbuild compiles TypeScript to `dist/index.js`
- **Static Serving**: Express serves built frontend assets in production

### Environment Configuration
- **Database**: PostgreSQL connection string via `DATABASE_URL`
- **Session**: Secure session configuration for production
- **CORS**: Configured for cross-origin requests in development

## Changelog

```
Changelog:
- July 05, 2025. Initial setup
- January 05, 2025. Completed full-featured daily salary calculator:
  * Orange/blue color scheme implemented
  * Casual loading (25%) option added
  * Customizable default schedule with times, breaks, allowances, afternoon shift
  * Enhanced sharing: WhatsApp, Line, Gmail, SMS options
  * Daily tax estimation based on annual projection
  * Complete daily work tracking (Mon-Fri)
  * Records saving and viewing functionality
  * ABN contractor mode (no tax)
  * All calculations working correctly
- January 05, 2025. Final Phase - App Store Ready:
  * Updated color scheme to match user requirements (blue header, orange accents)
  * Extended work tracking to full 7 days (Mon-Sun) for weekend overtime
  * Added individual day work/no-work toggle switches
  * Weekend days default to non-working status
  * Refined Default Schedule Modal with weekend work options
  * Removed ABN contractor mode (simplified interface)
  * Fixed all calculation accuracy issues
  * Ready for APK conversion and mobile app deployment
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
User wants to share this app publicly to help others with salary calculations.
Ready for mobile app conversion and Google Play Store release.
```

## Mobile App Conversion Status

```
Ready for APK Generation:
- Web application fully functional and tested
- UI optimized for mobile interfaces
- All core features implemented and working
- Color scheme finalized (blue header, orange accents)
- Complete 7-day work tracking system
- Individual day work/no-work controls
- Australian tax calculation system integrated
- Casual loading and overtime calculations accurate

Next Steps for Mobile Deployment:
1. Convert to APK using Capacitor framework (already configured)
2. Test on Android devices
3. Prepare Google Play Store listing
4. Deploy for public use

Technology Stack for Mobile:
- Capacitor for native mobile wrapper
- React/TypeScript web app as core
- Responsive design for mobile screens
- Offline capability through local storage
```
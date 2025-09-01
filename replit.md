# Overview

Kush Klicker is a cannabis-themed incremental clicker game built as a full-stack web application. Players click to earn "KUSH" currency, purchase upgrades to increase their earning power, unlock achievements, and compete on leaderboards. The game features a modern web interface with mobile-responsive design, real-time gameplay mechanics, social features like referrals, and comprehensive Solana wallet integration.

**✅ PRODUCTION READY STATUS**: The game is fully deployed and working through Telegram with 50 achievements, 18 upgrades, rich UI animations, and portable database architecture designed for multi-agent development.

**🎮 Latest Enhancements (Current Session)**: 
- ✅ Deployed for Telegram access and confirmed working
- ✅ Created comprehensive 50-achievement system with diverse goals
- ✅ Expanded upgrade system to 18 upgrades across multiple categories
- ✅ Implemented rich UI animations throughout the app (floating buttons, click effects, achievement unlocks)
- ✅ Made database portable and agent-friendly with auto-seeding data
- ✅ Updated comprehensive documentation for multi-agent handoffs

# User Preferences

Preferred communication style: Simple, everyday language.
Development approach: Focus on completing tasks fully before moving to next items.
Documentation priority: Always update technical docs for future agent handoffs.

# System Architecture

## Frontend Architecture
The client uses **React 18** with **TypeScript** for the user interface, styled with **Tailwind CSS** and **shadcn/ui** components for a consistent design system. The application follows a single-page application (SPA) pattern with client-side routing using **Wouter**. State management is handled through **TanStack Query** for server state and React hooks for local state.

The frontend is organized into:
- **Pages**: Main game view and error pages
- **Components**: Reusable UI components organized by feature (game, navigation, upgrades, achievements, etc.)
- **Hooks**: Custom React hooks for game state management and UI utilities
- **Lib**: Utility functions for game calculations, formatting, and API communication

## Backend Architecture
The server uses **Express.js** with **TypeScript** running in ESM mode. It provides a RESTful API for game operations including player management, upgrade purchases, and leaderboard queries. The architecture supports both development and production environments with Vite integration for hot module replacement during development.

Routes are organized around core game entities:
- Player operations (CRUD, stats updates)
- Upgrade system (purchase tracking, cost calculations)
- Achievement system (progress tracking, unlocking)
- Leaderboard functionality

## Data Storage Solutions
The application uses **Drizzle ORM** with **PostgreSQL** for persistent data storage. The database schema includes tables for players, upgrades, achievements, and their relationships. For development and testing, an in-memory storage implementation is provided as a fallback.

Database schema includes:
- **Players**: Core user data, game stats, Solana wallet integration with network preferences
- **Upgrades**: Purchasable improvements with scaling costs
- **Player Upgrades**: Purchase tracking and quantities
- **Achievements**: Goal-based rewards system
- **Player Achievements**: Progress tracking per user

### Solana Integration Schema
- **walletAddress**: Solana wallet public key for user accounts
- **solanaNetwork**: Network preference (mainnet/devnet) with environment-based defaults
- **walletSyncEnabled**: Toggle for automatic progress synchronization
- **lastWalletSync**: Timestamp tracking for sync operations

## Authentication and Authorization
Currently implements a basic session-based system using localStorage for player identification. Players are created with auto-generated usernames and persist across browser sessions. The architecture supports future expansion to include proper authentication, wallet connections, and social login systems.

## External Dependencies

### Database Services
- **Neon Database**: PostgreSQL hosting via @neondatabase/serverless
- **Drizzle**: Type-safe ORM with automatic migrations

### Blockchain Integration
- **Solana Web3.js**: Core Solana blockchain integration
- **Solana Wallet Adapters**: Multi-wallet connection support
- **Network Switching**: Live mainnet and devnet environment support
- **Wallet Sync**: Automatic progress synchronization with connected wallets

### UI Framework
- **React**: Component-based UI with hooks
- **Tailwind CSS**: Utility-first CSS framework
- **shadcn/ui**: Pre-built accessible components using Radix UI primitives
- **Radix UI**: Headless component primitives for complex interactions

### Development Tools
- **Vite**: Fast build tool and development server
- **TypeScript**: Type safety across frontend and backend
- **ESBuild**: Production bundling for server code

### Game Features
- **TanStack Query**: Server state management and caching
- **Wouter**: Lightweight client-side routing
- **React Hook Form**: Form handling with validation
- **Zod**: Runtime type validation and schema parsing

### Styling and Icons
- **Font Awesome**: Icon library for game elements
- **Google Fonts**: Typography (Inter, DM Sans, Fira Code, Geist Mono)
- **CSS Variables**: Theme system for dark mode support

### Production Infrastructure
- **Replit**: Hosting platform with integrated development environment
- **Connect-pg-simple**: PostgreSQL session storage for Express
- **Date-fns**: Date manipulation and formatting utilities
# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

AIlergy Chef is a health-aware meal planning app that helps users plan meals based on their dietary restrictions and health profiles.

**Tech Stack:** Next.js 14 (App Router) + TypeScript + Prisma/PostgreSQL (Supabase) + NextAuth.js v5 + Tailwind CSS + shadcn/ui

**External Integrations:**
- Anthropic Claude API - AI-powered meal suggestions
- Spoonacular API - Recipe and nutrition data
- Google Maps API - Store location services

**Database Schema:** users, health_profiles, recipes, meal_plans, meal_plan_entries, grocery_lists, grocery_items, saved_recipes

## Build & Development Commands

```bash
npm run dev      # Start development server on localhost:3000
npm run build    # Production build
npm run start    # Start production server
npm run lint     # Run ESLint
```

### Testing

```bash
npx vitest              # Run unit tests
npx vitest run          # Run tests once (CI mode)
npx vitest <file>       # Run single test file

npx playwright test              # Run e2e tests
npx playwright test <file>       # Run single e2e test
npx playwright test --ui         # Run with UI mode
```

### Database (Prisma)

```bash
npx prisma generate      # Generate Prisma client
npx prisma db push       # Push schema to database
npx prisma migrate dev   # Create and apply migration
npx prisma studio        # Open database GUI
```

## Architecture

**Key directories:**
- `src/app/` - App Router pages and layouts (file-based routing)
- `src/components/` - React components (create as needed)
- `src/lib/` - Utilities, database client, auth config (create as needed)

**Import alias:** `@/*` maps to `./src/*`

## Development Guidelines

**Component Strategy:** Use Server Components by default. Only use Client Components (`"use client"`) when you need interactivity, browser APIs, or React hooks.

**Validation:** Use Zod for all input validation (API routes, form data, environment variables).

**Styling:** Tailwind CSS + shadcn/ui components. CSS variables for theming (`--background`, `--foreground`). Utility functions: `clsx`, `tailwind-merge`, `class-variance-authority`.

**Icons:** `lucide-react`

**Fonts:** Geist Sans and Geist Mono via `next/font/local`.

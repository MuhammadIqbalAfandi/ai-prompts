# 🧭 Full Stack Reference (Separated)

This document defines the standard full stack architecture for projects with separated backend and frontend.
Use this as the default unless there is a strong reason to deviate.

---

## 🎯 Objective

Provide a consistent, scalable, and maintainable full stack architecture with clear separation between backend and frontend.

---

## 🧱 Tech Stack

### Backend

- Runtime: Bun
- Framework: ElysiaJS
- Database: PostgreSQL
- ORM: Drizzle ORM

### Frontend

- Framework: React Router v7 (framework mode)
- UI: Shadcn UI + Tailwind CSS
- Form Handling: React Hook Form + Zod (use only when needed)
- State Management: Zustand (use only when needed)

---

## 📌 Principles

- Prefer simplicity over complexity
- Avoid over-engineering
- Use only necessary libraries
- Follow convention over configuration
- Keep code readable and maintainable
- Maintain clear separation between backend and frontend

---

## 🗂 Folder Structure (Recommended)

### Backend

```md
src/
├── routes/ # API routes (ElysiaJS)
├── lib/ # utilities, db, helpers
├── schemas/ # drizzle schemas
├── services/ # business logic layer
├── middleware/ # custom middleware
└── types/ # type definitions
```

### Frontend

```md
src/
├── routes/ # route modules (React Router framework mode)
├── components/ # reusable UI components
├── features/ # domain-based modules
├── hooks/ # custom hooks
├── lib/ # utilities, helpers
├── store/ # zustand state (if needed)
├── schemas/ # zod schemas (if needed)
├── services/ # API client layer
└── styles/ # global styles
```

---

## 📛 Naming Conventions

- Components: `PascalCase.tsx`
- Hooks: `useSomething.ts`
- Files: `kebab-case.ts`
- Variables/functions: `camelCase`
- Route files: follow respective framework conventions
- API endpoints: RESTful or GraphQL conventions

---

## ⚙️ Usage Rules

### Backend

- Use ElysiaJS for routing and middleware
- Place Drizzle schema in `lib/db/schema.ts`
- Keep business logic in `services/`
- Use middleware for authentication and validation
- Follow RESTful API design

### Frontend

- Use Zustand only for global/shared state
- Use React Hook Form + Zod only for complex forms
- Keep components small and composable
- Separate business logic into `features/`
- Keep route logic inside `routes/`, not in components
- Use API client in `services/` for backend communication

---

## 🗄 Database Guidelines

- Use PostgreSQL as primary database
- Use Drizzle ORM for type-safe queries
- Keep schema explicit and versioned
- Prefer simple relations over complex joins
- Run migrations through Drizzle

---

## 🔌 Data Fetching Strategy

### Backend

- Use ElysiaJS routes for API endpoints
- Handle data fetching and mutations in route handlers
- Use Drizzle for database operations

### Frontend

- Use loaders/actions (React Router) for server interaction
- Keep data fetching close to routes
- Avoid fetching directly inside UI components when possible
- Use API client for backend communication

---

## 🚫 Anti-Patterns

- Do not introduce unnecessary abstraction
- Do not use global state for local UI state
- Do not mix unrelated logic in one component
- Do not bypass ORM without clear reason
- Do not place business logic in UI components
- Do not tightly couple backend and frontend logic
- Do not expose database details in API responses

---

## 🧪 Output Guidelines (for AI usage)

- Use clear and structured Markdown
- Provide file structure when relevant
- Include code examples when necessary
- Keep explanations concise and actionable
- Specify backend/frontend context when relevant

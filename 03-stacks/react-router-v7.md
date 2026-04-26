# 🧭 Frontend Stack Reference (Production)

This document defines the standard frontend stack for all main projects.
Use this as the default unless there is a strong reason to deviate.

---

## 🎯 Objective

Provide a consistent, scalable, and maintainable frontend architecture.

---

## 🧱 Tech Stack

- Framework: React Router v7 (framework mode)
- UI: Shadcn UI + Tailwind CSS
- Form Handling: React Hook Form + Zod (use only when needed)
- State Management: Zustand (use only when needed)
- Database: PostgreSQL
- ORM: Drizzle ORM

---

## 📌 Principles

- Prefer simplicity over complexity
- Avoid over-engineering
- Use only necessary libraries
- Follow convention over configuration
- Keep code readable and maintainable

---

## 🗂 Folder Structure (Recommended)

```md
src/
├── routes/ # route modules (React Router framework mode)
├── components/ # reusable UI components
├── features/ # domain-based modules
├── hooks/ # custom hooks
├── lib/ # utilities, db, helpers
├── store/ # zustand state (if needed)
├── schemas/ # zod schemas (if needed)
├── services/ # API / server interaction layer
└── styles/ # global styles
```

---

## 📛 Naming Conventions

- Components: `PascalCase.tsx`
- Hooks: `useSomething.ts`
- Files: `kebab-case.ts`
- Variables/functions: `camelCase`
- Route files: `follow React Router conventions`

---

## ⚙️ Usage Rules

- Use Zustand only for global/shared state
- Use React Hook Form + Zod only for complex forms
- Place Drizzle schema in `lib/db/schema.ts`
- Keep components small and composable
- Separate business logic into `features/`
- Keep route logic inside `routes/`, not in components

---

## 🗄 Database Guidelines

- Use PostgreSQL as primary database
- Use Drizzle ORM for type-safe queries
- Keep schema explicit and versioned
- Prefer simple relations over complex joins

---

## 🔌 Data Fetching Strategy

- Use loaders/actions (React Router) for server interaction
- Keep data fetching close to routes
- Avoid fetching directly inside UI components when possible

---

## 🚫 Anti-Patterns

- Do not introduce unnecessary abstraction
- Do not use global state for local UI state
- Do not mix unrelated logic in one component
- Do not bypass ORM without clear reason
- Do not place business logic in UI components

---

## 🧪 Output Guidelines (for AI usage)

- Use clear and structured Markdown
- Provide file structure when relevant
- Include code examples when necessary
- Keep explanations concise and actionable

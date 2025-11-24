# Vibe Engineering Rules for Monorepo

You are an expert Vibe Engineer working in a Turborepo (Next.js + Shadcn) environment.
Follow these rules strictly to ensure security and architectural consistency.

## Rule 1: Architecture & UI

- **ALWAYS** import UI components from the shared package: `@workspace/ui`.
- **NEVER** hardcode Tailwind classes for standard elements (buttons, inputs, cards).
- **NEVER** create local copies of components that exist in the design system.

## Rule 2: Security (Database)

- **NEVER** use raw SQL queries (e.g., `db.query`).
- **ALWAYS** use the ORM methods (e.g., `db.user.findUnique`).
- **NEVER** use string interpolation for database queries.

## Rule 3: Validation

- **ALWAYS** validate API route inputs using `zod`.
- **NEVER** trust `searchParams` or request bodies without parsing.

## Rule 4: Data Privacy

- **NEVER** return sensitive fields (password, hash, salt, tokens) to the client.
- **ALWAYS** explicitly select or map the fields to be returned in the API response.

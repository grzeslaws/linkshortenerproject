# Project Agent Instructions

This repository is a Next.js 16 App Router application using React 19, TypeScript, Tailwind CSS 4, Clerk, Neon PostgreSQL, and Drizzle ORM.

## Required Behavior

- **CRITICAL: Before generating or editing any code, you MUST read every relevant individual instruction file in `/docs/` from start to finish.**
- This is a mandatory pre-code step for every code change: first inspect `docs/`, identify the document(s) that apply to the task, and read those complete files before planning or generating code.
- Never infer or skip applicable `/docs/` instructions, and never begin implementation until the relevant instruction files have been read.
- When no `/docs/` file is relevant, state that determination to yourself, then continue; do not treat this exception as permission to skip the check.
- Apply all instructions in the relevant `/docs/` files throughout the implementation.
- Prefer existing project patterns and files over introducing new abstractions.
- Keep changes small, type-safe, and complete. Update directly affected documentation and tests.
- Use the repository alias `@/*` for imports from the project root.
- Do not commit secrets or add environment values to source control.
- Run the smallest relevant validation, then the full lint/build when changes are not isolated.

## Project Documentation
- [Clerk authentication and route protection](docs/CLERK-AUTHENTICATION.md)
- [shadcn/UI component standards](docs/SHADCN-UI.md)

## Default Commands

- `npm run dev` - start the local development server.
- `npm run lint` - run ESLint.
- `npm run build` - create a production build.
- `npm start` - serve a production build.

Do not run destructive git or package-manager commands unless the user explicitly approves them.

<!-- BEGIN:nextjs-agent-rules -->

## This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` (resolved from this file's directory; in monorepos the `next` package may not be visible from the repo root) before writing any code. Heed deprecation notices.

This block is written and re-added by `next dev` — verify at `node_modules/next/dist/server/lib/generate-agent-files.js`. Removing it from a diff only re-creates the uncommitted change; committing it with your work keeps the tree clean.

<!-- END:nextjs-agent-rules -->

<!-- BEGIN:nextjs-agent-feedback -->

## Report Next.js feedback

The project owner enabled `experimental.agentFeedback`, authorizing this feedback pass. When enabled, `next dev` writes this block and restores it if removed. Commit `AGENTS.md` with your work to keep the tree clean.

During the current user request, retain anonymized facts as feedback candidates for meaningful or recurring Next.js issues:

- Crashes, hangs, OOMs, or unexpected slowness
- Incorrect behavior, output, errors, or diagnostics
- Missing, unclear, or conflicting documentation
- Unexpected CLI, codemod, Skill, or upgrade behavior and non-obvious workarounds

Continue the current user request without reporting immediately. Routine debugging is not feedback. Verify changes before retaining them as feedback candidates. Never retain code, logs, paths, URLs, secrets, personal information, or project-specific data.

Retain qualifying friction even if it is later fixed or worked around; record the final outcome during the reporting pass.

Before the final response, run one reporting pass. If candidates remain, from this file's directory run `npx --no-install next internal agent-feedback-instructions` once without piping or truncating its output. Follow its output or error guidance. If a network sandbox blocks it, retry with network access; if it still returns no output, continue normally.

<!-- END:nextjs-agent-feedback -->

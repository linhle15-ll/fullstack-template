

Recommended set up of a project
```
fullstack-template/
├── .github/
│   └── workflows/
│       ├── client.yml
│       ├── server.yml
│       └── docker.yml
│
├── .husky/
│   └── pre-commit
│
├── .prettierrc
├── .prettierignore
├── pnpm-workspace.yaml
│
├── client/
├── server/
└── docker-compose.yml
```

Root:
`pnpm init` - Create `pnpm-lock.yaml`
`pnpm install`
`pnpm exec husky init`

Code quality check (install at root):
Lint, Husky, Prettier:
`pnpm add -Dw prettier prettier-plugin-tailwindcss husky lint-staged`
`-D` stands for development dependency (only needed in development)
`-w` flags tell pnpm to install them in the workspace root

Client:
Install pnpm: `npm install -g pnpm`

Create Next.js app: `pnpm create next-app@latest .` (remember `.` so it does not create another folder for the project inside client folder)
Click yes for all suggested set up

Run `pnpm approve-builds` to pick which dependencies should be allowed to run scripts.

Installation:

- prettier: `pnpm add -D prettier prettier-plugin-tailwindcss`
- axips: `pnpm add axios`
- tanstack/ react-query: `pnpm add @tanstack/react-query`
- React hook form: `pnpm add react-hook-form` (pending)
- Zod: `pnpm add zod` (pending)
- Hookform Resolver: `pnpm add @hookform/resolvers` (pending)
- Manage dark mode/ light mode: `pnpm add next-themes` (pending, for now set all to light mode)
- Lucide React: `pnpm add lucide-react`
- clsx with Tailwind (enable TailwindSS + condition): `pnpm add clsx tailwind-merge`
- Toast notification: `pnpm add sonner`
- Initialize ShadCN (UI Components): `pnpm dlx shadcn@latest init`


## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.




use `pnmp` to install, NOT using `npm` or `yarn`

Create new branch:
- For feature: `feature/<feature_name>
- For bug fix: `bugfix/<bugfix_feature>
- For refactor: `refactor`

client and server are set up with separate config file (for example: not having the same typescript set up for both client and server)


.env to client and server, and copy the environment key from example.env file in each of client and server to .env
The key's value can be found at: [Github Gist]


This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Code Quality Check
Before making commit:
- Run `pnpm lint` to fix lint. 
- Run `pnpm lint-staged`
- Run `pnpm prettier --write .` to format the project
or `pnpm prettier --write client` to format only the client

Commit is not approved if lint and prettier check is not passed.


# Server:
```
cd server
pnpm init

pnpm add express cors cookie-parser dotenv

pnpm add -D typescript
pnpm add -D @types/node @types/express
pnpm add -D eslint
pnpm add -D tsx // watch files for change, watch Typescript closely (better than Nodemon)
```

morgan logs every incoming HTTP request, which is extremely useful during development and debugging.

Development dependencies
```
pnpm add -D typescript tsx
pnpm add -D @types/node
pnpm add -D @types/express
pnpm add -D @types/cors
pnpm add -D @types/morgan
pnpm add -D @types/cookie-parser
```
The `@types` packages provide type definitions (useful for file written in JavaScript in a TypeScript project).

Initalize Typescript
```
npx tsc --init
```

# Checklist
Template (current set-up in this repo):
- [x] Root:
- [x] Client:
- [x] Server:
- [] Testing: Unit test + Vitest
- [] Github Actions: install, lint, format, build
- [] Docker: DockerFiles, `docker-compose.yml`

Backend features:
- [] Third-party authentication (e.g., Clerk or Auth0)
- [] REST APIs
- [] Validation
- [] Database

Production:
- [] Deployment workflows
- [] Monitoring and logging
- [] Environment-specific Docker Compose overrides (optional)

# hangout-pnpm-mono

## What's inside?

<!-- tree -I "node_modules|dist|.pnpm|build" .  -->
```c
.
├── README.md
├── package.json
│
│   // package-based monorepo structure
├── pnpm-lock.yaml
├── pnpm-workspace.yaml
│
│   // standalone applications folder
├── apps
│   └── my-remix-app
│       ├── README.md
│       ├── app
│       │   └── *.tsx
│       ├── package.json // "name": "my-remix-app"
│       ├── tsconfig.json
│       └── vite.config.ts
│
│   // dependent libraries folder
└── packages
    └── shared-ui
        ├── *.tsx
        ├── package.json // "name": "shared-ui"
        └── tsconfig.json
```

## How to run it

Install all packages

```bash
pnpm install
```

Build dependent library

```bash
pnpm --filter shared-ui build
```

Run application

```bash
pnpm --filter my-remix-app dev
```

Build all packages

```bash
pnpm run -r build
```

## Reference

[Setup a Monorepo with PNPM workspaces and speed it up with Nx!](https://dev.to/nx/setup-a-monorepo-with-pnpm-workspaces-and-speed-it-up-with-nx-1eem)

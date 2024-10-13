# hangout-pnpm-mono

[![package-based monorepo](https://img.shields.io/static/v1?label=Nx%20setup&message=package-based%20monorepo&color=orange)](https://nx.dev/concepts/integrated-vs-package-based#package-based-repos)

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
# pnpm --filter shared-ui build
npx nx build shared-ui
```

Run application

```bash
# pnpm --filter my-remix-app dev
npx nx dev my-remix-app
```

Build all packages

```bash
# pnpm run --recursive build
npx nx run-many --target=build
```

Visualize Project Graph

```bash
pnpm dlx nx graph
```

## Reference

[Setup a Monorepo with PNPM workspaces and speed it up with Nx!](https://dev.to/nx/setup-a-monorepo-with-pnpm-workspaces-and-speed-it-up-with-nx-1eem)

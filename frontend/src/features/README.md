# Features Directory

This directory contains feature-based modules. Each feature should be self-contained with its own components, hooks, and logic.

## Structure Example

```
features/
├── auth/
│   ├── components/
│   ├── hooks/
│   ├── services/
│   └── index.ts
└── dashboard/
    ├── components/
    ├── hooks/
    └── index.ts
```

## Guidelines

- Each feature should export its public API through an index.ts file
- Keep feature-specific logic isolated within the feature directory
- Share common utilities through the top-level utils directory

# Why This Directory Exists

This empty `pages/` directory is a placeholder to prevent conflicts between Next.js build system and our Feature Sliced Design (FSD) architecture.

## The Problem

Next.js treats any directory named `pages` as a potential Pages Router directory. When both `app/` (App Router) and `pages/` directories exist in the project root, Next.js throws a build error:

```
Error: > `pages` and `app` directories should be under the same folder
```

However, in our FSD architecture, we have component pages stored in `src/pages/` (the FSD Pages layer), which contains reusable page components that are imported by Next.js routes in the `app/` directory.

## The Solution

This empty `pages/` directory in the root acts as a placeholder that satisfies Next.js's directory structure requirements while allowing us to:

1. Use Next.js App Router (`app/` directory) for routing
2. Maintain FSD architecture with `src/pages/` for page components
3. Avoid build conflicts between the two systems

## Important Notes

- This directory should remain **empty** (except for this README)
- Do not add any Next.js route files here - use `app/` for routing
- Page components belong in `src/pages/` following FSD conventions
- The actual routing is handled by `app/` directory with imports from `src/pages/`

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is `@iwf-web/tsconfig`, a TypeScript configuration package for IWF projects. It provides reusable, strict TypeScript compiler configurations optimized for React + Vite development.

## Commands

```bash
pnpm install    # Install dependencies
```

No build step required - the package exports JSON configuration files directly.

## Architecture

```
react-strict/
└── tsconfig.json   # Main exported configuration
```

The `react-strict/tsconfig.json` extends three base configurations:
- `@tsconfig/recommended` - Recommended TypeScript settings
- `@tsconfig/vite-react` - Vite + React optimizations
- `@tsconfig/strictest` - Strictest type checking rules

It then relaxes specific settings for practical development (see the file for details).

## Package Manager

This project uses **pnpm** exclusively. The exact version is pinned in `package.json` under `packageManager`.

## Release Process

Releases are published to npm automatically via GitHub Actions when a GitHub release is created. The workflow runs `pnpm publish --provenance --access public`.

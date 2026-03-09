# IWF TypeScript Config

Standard TypeScript configurations for IWF projects, optimized for React development with Vite.

[![License](https://img.shields.io/github/license/iwf-web/tsconfig)][license]
[![Version](https://img.shields.io/npm/v/@iwf-web/tsconfig?label=latest%20release)][npm]
[![Downloads](https://img.shields.io/npm/dt/@iwf-web/tsconfig)][npm]

## Configurations

This package provides the following TypeScript configurations:

| Configuration | Description |
|---------------|-------------|
| `react-strict` | Strict TypeScript settings for React + Vite projects |

## Getting Started

### Prerequisites

- Node.js 18 or higher
- pnpm, npm, or yarn

### Installation

```bash
pnpm add -D @iwf-web/tsconfig
```

Or with npm:

```bash
npm install -D @iwf-web/tsconfig
```

### pnpm Configuration

When using pnpm, you need to hoist the base tsconfig packages so TypeScript can resolve them. Add the following to your `pnpm-workspace.yaml`:

```yaml
publicHoistPattern:
  - "@tsconfig/*"
```

Or in your `.npmrc`:

```ini
public-hoist-pattern[]=@tsconfig/*
```

### Usage

Extend the configuration in your `tsconfig.json`:

```json
{
  "extends": "@iwf-web/tsconfig/react-strict/tsconfig.json",
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  },
  "include": ["src"]
}
```

## Configuration Details

### react-strict

This configuration extends three base configurations for comprehensive TypeScript support:

- [`@tsconfig/recommended`](https://www.npmjs.com/package/@tsconfig/recommended) - Recommended TypeScript settings
- [`@tsconfig/vite-react`](https://www.npmjs.com/package/@tsconfig/vite-react) - Optimized settings for Vite + React
- [`@tsconfig/strictest`](https://www.npmjs.com/package/@tsconfig/strictest) - Strictest type checking rules

#### Customizations

The following settings are relaxed from the strictest defaults for practical development:

| Setting | Value | Reason |
|---------|-------|--------|
| `erasableSyntaxOnly` | `false` | Allows enums, namespaces, and classes |
| `noPropertyAccessFromIndexSignature` | `false` | Allows dot notation for index signatures |
| `noImplicitAny` | `false` | Permits implicit `any` types where inference fails |
| `exactOptionalPropertyTypes` | `false` | Allows `undefined` assignment to optional properties |

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

This project uses [Conventional Commits](https://www.conventionalcommits.org/) for automated releases and changelog generation.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For available versions, see the [tags on this repository][gh-tags].

## Authors

All authors can be found in the [AUTHORS.md](AUTHORS.md) file.

Contributors can be found in the [CONTRIBUTORS.md](CONTRIBUTORS.md) file.

See also the full list of [contributors][gh-contributors] who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.txt](LICENSE.txt) file for details.

## Acknowledgments

A list of used libraries and code with their licenses can be found in the [ACKNOWLEDGMENTS.md](ACKNOWLEDGMENTS.md) file.

[license]: https://github.com/iwf-web/tsconfig/blob/main/LICENSE.txt
[npm]: https://www.npmjs.com/package/@iwf-web/tsconfig
[gh-tags]: https://github.com/iwf-web/tsconfig/tags
[gh-contributors]: https://github.com/iwf-web/tsconfig/contributors

# TypeScript 7 + typescript-eslint Workaround

This branch demonstrates a temporary workaround for using the TypeScript 7 compiler while keeping ESLint functional with `typescript-eslint@8.63.0`.

It does not add real TypeScript 7 support to `typescript-eslint`. Instead:

- `typescript` stays on `6.0.3` so `typescript-eslint` sees a supported peer dependency.
- `typescript-7` is installed as an npm alias for `typescript@7.0.2`.
- `npm run lint` uses the supported TypeScript 6 peer.
- `npm run tsc7` runs the TypeScript 7 compiler via the alias.

## Versions

- Node.js: `24`
- npm: `11`
- ESLint: `10.6.0`
- TypeScript for ESLint: `6.0.3`
- TypeScript compiler alias: `7.0.2`
- typescript-eslint: `8.63.0`

## Commands

```sh
npm ci
npm run versions
npm run lint
npm run tsc7
```

The included GitHub Actions workflow validates the workaround.

# TypeScript 7 + typescript-eslint 8.73.0 Reproduction

This repository reproduces two related failures after upgrading TypeScript to `7.0.2` while using `typescript-eslint@8.73.0`.

## Versions

- Node.js: `24`
- npm: `11`
- ESLint: `10.15.0`
- TypeScript: `7.0.2`
- typescript-eslint: `8.73.0`

## Reproduction

```sh
npm ci
```

Expected result: dependency installation succeeds.

Actual result: `npm ci` fails because `typescript-eslint@8.73.0` declares a peer dependency on `typescript >=4.8.4 <6.1.0`.

```sh
npm install --force
npm run lint
```

Expected result: ESLint either succeeds or reports a clear unsupported TypeScript version error.

Actual result: ESLint exits with an explicit error that typescript-eslint does not support TS 7.0 (see [typescript-eslint#10940](https://github.com/typescript-eslint/typescript-eslint/issues/10940)).

The included GitHub Actions workflow runs both cases as separate jobs so maintainers can see both failure modes.

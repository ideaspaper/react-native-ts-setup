# React Native with TypeScript Setup

## Development Environment

[Source](https://reactnative.dev/docs/environment-setup)

## Initializing Project

```
npx react-native init <ProjectName> --template react-native-template-typescript
cd <ProjectName>
git init
```

## ESLint

ESLint is a tool for identifying and reporting on patterns found in ECMAScript/JavaScript code.

*Already included in project initialization.*

**References**

- [npm - eslint](https://www.npmjs.com/package/eslint)

## Prettier

Prettier is an opinionated code formatter. It enforces a consistent style by parsing your code and re-printing it with its own rules that take the maximum line length into account, wrapping code when necessary.

*Already included in project initialization.*

`package.json`

```json
...
  "scripts": {
    ...
    "tidy": "prettier '*/**/*.{js,ts,tsx,json,md,html}' --write"
  },
...
```

**References**

- [npm - prettier](https://www.npmjs.com/package/prettier)

## ESLint vs Prettier

[Source](https://blog.logrocket.com/using-prettier-eslint-automate-formatting-fixing-javascript/#managing-eslint-rules-avoid-conflict-prettier)

## Husky

Husky is a package that allows custom scripts to be ran against your Git repository. These scripts trigger actions in response to specific events, so they can help you automate your development lifecycle.

```
npm i -D husky
npm pkg set scripts.prepare="husky install"
npm run prepare
npx husky add .husky/pre-commit "npm run tidy && npm run lint && npm run test -- --watchAll=false --passWithNoTests"
```

`.husky/pre-commit`

```sh
#!/usr/bin/env sh
. "$(dirname -- "$0")/_/husky.sh"

npm run tidy && npm run lint && npm run test -- --watchAll=false --passWithNoTests
```

**References**

- [npm - husky](https://www.npmjs.com/package/husky)
- [git - Customizing Git - Git Hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)
- [Altlassian - Git Hooks](https://www.atlassian.com/git/tutorials/git-hooks)

# Monorepo with Lerna

### Intro

Here I'm using Lerna mainly to facilitate running scripts in all apps at once and integrating with Husky for git hooks.
In this case I've built a monorepo considerings that all apps/packages have independent versions and following the scructure
of VTEX apps, meaning that each app will have its own **CHANGELOG**.

### Main advantages

With this approach I was able to concentrate all eslint/prettier configs on the root `package.json` and I'm able
to run batch actions on all apps, actions like: run all tests, format all files, etc.

To test this out you should first run `yarn` on the root of this folder and after `lerna bootstrap`, which will install
the deps in all apps, the ones located inside the `/react` folder.

### Features

- `yarn lint`: will do type checking and eslint check in all files.
- `yarn test`: will run all the tests.
- `locales:lint`: will verify some intl messages are missing or not using the **@vtex/intl-equalizer**.
- `locales:fix`: fix the order of the intl messags.

##### Commit Hoooks

- **pre-commit**: Run eslint and prettier on the staged files and also verify for missing locale messages.
- **pre-push**: Fix the intl message order and run all the tests.

### Next steps

- Integrate with yarn workspaces.

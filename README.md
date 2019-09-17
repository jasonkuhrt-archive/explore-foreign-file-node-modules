# Exploration of Forign File Retention in node_modules

## On Package Add

#### `yarn`

Yarn wipes all foreign content becuase packages are rebuilt. This behaviour falls under an [open yarn issue](https://github.com/yarnpkg/yarn/issues/4703). Age of the issue suggests low priority.

1. Run `yarn run setup:yarn` to ensure clean slate
1. Observe state change by running `yarn run check` (foreign content)
1. Run `yarn add fp-ts`
1. Observe state by running `yarn run check` (no foreign content)

#### `npm`

NPM retains the forign file in existing package.

1. Run `npm run setup:npm` to ensure clean slate
1. Observe state change by running `npm run check` (foreign content)
1. Run `npm install fp-ts`
1. Observe state by running `npm run check` (foreign file only)

## On Package Upgrade

#### `yarn`

Yarn wipes all foreign content becuase packages are rebuilt. This behaviour falls under an [open yarn issue](https://github.com/yarnpkg/yarn/issues/4703). Age of the issue suggests low priority.

1. Run `yarn run setup:yarn` to ensure clean slate
1. Observe state change by running `yarn run check` (foreign content)
1. Run `yarn install fp-ts@2.0.4`
1. Observe outdated package state by running `yarn outdated`
1. Run `yarn upgrade`
1. Observe state by running `yarn run check` (foreign content)

#### `npm`

NPM retains the forign file in existing package.

1. Run `npm run setup:npm` to ensure clean slate
1. Observe state change by running `npm run check` (foreign content)
1. Run `npm install fp-ts@2.0.4`
1. Observe outdated package state by running `npm outdated`
1. Run `npm upgrade`
1. Observe state by running `npm run check` (foreign content)

## On No-Op Upgrade

#### `yarn`

Yarn wipes all foreign content becuase packages are rebuilt. This behaviour falls under an [open yarn issue](https://github.com/yarnpkg/yarn/issues/4703). Age of the issue suggests low priority.

1. Run `yarn run setup:yarn` to ensure clean slate
1. Observe state change by running `yarn run check` (foreign content)
1. Run `yarn upgrade`
1. Observe state by running `yarn run check` (no forign content)

#### `npm`

NPM retains all foreign content.

1. Run `npm run setup:npm` to ensure clean slate
1. Observe state change by running `npm run check` (foreign content)
1. Run `npm upgrade`
1. Observe state by running `npm run check` (foreign content)

## On Prune

#### `yarn`

Yarn retains all foreign content.

1. Run `yarn run setup:yarn` to ensure clean slate
1. Observe state change by running `yarn run check` (foreign content)
1. Run `yarn install`
1. Observe state change by running `yarn run check` (foreign content)

#### `npm`

NPM retains the foreign file in existing package.

1. Run `npm run setup:npm` to ensure clean slate
1. Observe state change by running `npm run check` (foreign content)
1. Run `npm prune`
1. Observe state change by running `npm run check` (foreign file only)

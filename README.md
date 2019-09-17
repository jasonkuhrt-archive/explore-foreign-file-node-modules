# Exploration of Forign File Retention in node_modules

## On Package Install

#### `yarn`

Yarn wipes all foreign content becuase packages are rebuilt.

1. Run `yarn run setup:yarn` to ensure clean slate
1. Observe state change by running `yarn run check` (foreign content)
1. Run `yarn add axios`
1. Observe state by running `yarn run check` (no forign content)

#### `npm`

NPM retains the forign file in existing package.

1. Run `npm run setup:npm` to ensure clean slate
1. Observe state change by running `npm run check` (foreign content)
1. Run `npm install axios`
1. Observe state by running `npm run check` (forign file only)

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

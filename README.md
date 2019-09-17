# Node Dependency Pruning Exploration

## On Package Install

#### `yarn`

1. Run `yarn run clean` to ensure clean slate
1. Run `yarn install`
1. Observe state by running `yarn run check` (no forign content)
1. Run `yarn run setup`
1. Observe state change by running `yarn run check` (foreign content)
1. Run `yarn add expect`
1. Observe state by running `yarn run check` (no forign content)

#### `npm`

1. Run `npm run clean` to ensure clean slate
1. Run `npm install`
1. Observe state by running `npm run check` (no forign content)
1. Run `npm run setup`
1. Observe state change by running `npm run check` (foreign content)
1. Run `npm install expect`
1. Observe state by running `npm run check` (no forign content)

## On Prune

#### `yarn`

1. Run `yarn run clean` to ensure clean slate
1. Run `yarn install`
1. Observe state by running `yarn run check` (no forign content)
1. Run `yarn run setup`
1. Observe state change by running `yarn run check` (foreign content)
1. Run `yarn install`
1. Observe state change by running `yarn run check` (foreign content)

#### `npm`

1. Run `npm run clean` to ensure clean slate
1. Run `npm install`
1. Observe state by running `npm run check` (no forign content)
1. Run `npm run setup`
1. Observe state change by running `npm run check` (foreign content)
1. Run `npm prune`
1. Observe state change by running `npm run check` (foreign file only)

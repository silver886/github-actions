# Centralized GitHub Actions

## Actions

### `checkout`

Checkout repository.

### `create-pull-request`

Create a new branch with current date and a pull request.

#### Inputs

- `body`: (Optional) Body of pull request.
- `assignees`: (Optional) Assignees of pull request.
- `reviewers`: (Optional) Reviewers of pull request.

### `setup/nodejs`

Setup Node.js 18.

### `setup/pnpm`

Setup pnpm 7 and clean install dependencies.

### `time`

Get current time.

#### Outputs

- `date`: Current date.
- `time`: Current time.
- `rfc3339`: Current date and time in RFC3339 format.

## Workflows

### `create-release`

Create release.

### `release-npm`

Release npm package.

#### Inputs

- `test`: (Optional) Unit test.

#### Secrets

- `NPM`: NPM token.

# Centralized GitHub Actions

## Actions

### `checkout`

Checkout repository.

### `create/pull-request`

Create a new branch with current date and a pull request.

#### Inputs

- `token`: GITHUB_TOKEN or a `repo` scoped Personal Access Token (PAT). [^4]
- `body`: The body of the pull request. [^4]
- `assignees`: A comma or newline separated list of assignees (GitHub usernames). [^4]
- `reviewers`: A comma or newline separated list of reviewers (GitHub usernames) to request a review from. [^4]

[^4]: https://github.com/peter-evans/create-pull-request/blob/main/action.yml

### `create/release`

#### Inputs

- `name`: Gives the release a custom name. Defaults to tag name. [^2]
- `files`: Newline-delimited list of path globs for asset files to upload. [^2]
- `body_path`: Path to load note-worthy description of changes in release from. [^2]

[^2]: https://github.com/softprops/action-gh-release/blob/master/action.yml

### `create/token`

#### Inputs

- `app-id`: GitHub App ID. [^3]
- `private-key`: GitHub App private key. [^3]
- `owner`: The owner of the GitHub App installation (defaults to current repository owner). [^3]
- `repositories`: Comma or newline-separated list of repositories to install the GitHub App on (defaults to current repository if owner is unset). [^3]
- `skip-token-revoke`: If truthy, the token will not be revoked when the current job is complete. [^3]
- `github-api-url`: he URL of the GitHub REST API. [^3]

#### Outputs

- `token`: GitHub installation access token. [^3]
- `installation-id`: GitHub App installation ID. [^3]
- `app-slug`: GitHub App slug. [^3]

[^3]: https://github.com/actions/create-github-app-token/blob/main/action.yml

### `setup/nodejs`

Setup Node.js 18.

#### Inputs

- `scope`: Optional scope for authenticating against scoped registries. Will fall back to the repository owner when using the GitHub Packages registry (https://npm.pkg.github.com/). [^1]
- `registry-url`: Optional registry to set up for auth. Will set the registry in a project level .npmrc and .yarnrc file, and set up auth to read in from env.NODE_AUTH_TOKEN. [^1]

[^1]: https://github.com/actions/setup-node/blob/main/action.yml

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

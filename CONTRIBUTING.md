# Contributing to SmallPict

Thanks for taking the time to contribute! This guide applies to every repository in the smallPict organization unless the repository has its own `CONTRIBUTING.md`.

## Before you start

- **Bugs:** search the existing issues first, then open a new one with the bug report form.
- **Features:** open a feature request first so we can agree on the approach before you write code.
- **Security issues:** do not open an issue. Follow [SECURITY.md](SECURITY.md).

## API contract

All SDKs follow the OpenAPI spec in [smallpict-sdk](https://github.com/smallPict/smallpict-sdk). A change to an endpoint, request parameter or response field starts with a change to that spec, then the SDKs follow.

## Pull requests

1. Fork the repository and create a branch from `main`.
2. Keep the change focused: one fix or feature per pull request.
3. Add or update tests, and run the repository's test and lint commands.
4. Update the README or docs when behavior changes, and add an entry to `CHANGELOG.md` under **Unreleased**.
5. Use [Conventional Commits](https://www.conventionalcommits.org/) for commit messages, for example `fix(client): retry on 429` or `feat(options): add maxDimension`.
6. Open the pull request and fill in the template.

## Releases

Maintainers release by pushing a `vX.Y.Z` tag. The release workflow publishes the package to its registry, so version files do not need to be bumped by hand in a pull request.

## Code of conduct

By taking part you agree to follow our [Code of Conduct](CODE_OF_CONDUCT.md).

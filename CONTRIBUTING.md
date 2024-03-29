# Contributing

Anyone providing assistance to the future of this project is considered a contributor. If you wish to play a part in this project, then thank you! This document outlines some of the ways to help.

## Sponsor

_Role: non-code contributors._

Give back to the software that's important to you by investing in their developers. Sponsorships in the USA are tax deductible. Shabad OS is a 501(c)(3) non-profit.

## Issue

_Role: non-code contributors with a GitHub account._

There are many ways to contribute, beyond writing code or programming, by: asking questions, reporting bugs, and suggesting features. To do so, please log a [new issue](https://github.com/shabados/gurmukhiutils/issues/new).

## Triage

_Role: contributors managing issues and pull requests_

This is a pretty flexible way to help out. Triage can help code contributors and maintainers prioritize work. Some examples:

- Label/tag issues
- Respond to new issues/comments
- Request more details
- Verify bug reports (aka reproduce the problem)
- Edit issue titles/descriptions

## Pull Request

_Role: contributors wishing to change the project source code_

**Requirements:**

- [Python](https://www.python.org/) (see version in `pyproject.toml`)
- [Poetry](https://python-poetry.org/)

**Workflow:**

- Fork this repository
- Create a branch from `main`
- Make any changes
- Submit a pull request

Note: Before creating new branches, ensuring that the forked `main` is up to date with the upstream/original `main` will ease workflow.

**Development:**

- Install project dependencies with `poetry install`.
- Automatically format/lint when committing by enabling pre-commit hooks with `poetry run autohooks activate --mode poetry`.
- Run tests with `poetry run pytest`.

Note: Select the Python Interpreter in VS Code to access dev dependencies.

Note: VS Code's SCM (source control manager) does not respect the virtual environment created by Poetry (see [vscode-python#10165](https://github.com/microsoft/vscode-python/issues/10165)). To use pre-commit, you'd have to run something like `poetry run git commit -m "feat: add your message here"`

Note: If you don't enable pre-commit hooks, please manually run the related commands in the `[tool.autohooks]` section of `pyproject.toml` before submitting each and every PR.

## PR Merge

_Role: project authors/maintainers_

- Pull requests should be squashed or rebased.
- Commit messages on `main` branch should generally conform to [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/).

**Types**

Some _types_ correlate with incrementing major, minor, and patch versions in [Semantic Versioning](https://semver.org/). These _types_ should only be used for code changes in the `gurmukhiutils` folder. (This folder is considered the project's API.)

- `BREAK` increments major. To be used when making incompatible changes to the API.
- `feat` increments minor. To be used when adding backwards-compatible functionality to the API.
- `fix` increments patch. To be used when making backwards-compatible bugfixes to the API. Do not use this type when fixing something outside the `gurmukhiutils` folder.

All other _types_ are ignored by the version bump workflow. These types are typically used outside the API folder, but may change API source code without actually affecting anything for the end user. Valid non-versioning (non-API related) _types_ include: `build`, `chore`, `ci`, `docs`, `perf`, `refactor`, `revert`, `style`, and `test`.

## Release

_Role: project authors/maintainers_

See [actions](https://github.com/shabados/gurmukhiutils/actions) for incrementing the version and publishing.

**Version Increment/Bump**

- This workflow bumps/increments the version via a Pull Request.
- The PR will list all the commit history from after the last release.
- The PR must be merged prior to publishing.

Note: Leave the override field blank for automatic versioning.

**Publish**

- This workflow will publish to PyPI and create a GitHub release.

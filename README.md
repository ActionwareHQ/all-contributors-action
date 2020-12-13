<p align="center">
  <img src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/240/apple/271/busts-in-silhouette_1f465.png" width="120" alt="@all-contributors action">
  <h3 align="center">All contributors action</h3>
  <p align="center">GitHub Action reacting on comments and pushing new <a href="https://allcontributors.org/">@all-contributors</a> contributors directly to the repo</p>
  <p align="center">
    <img alt="Build status" src="https://github.com/ActionwareHQ/all-contributors-action/workflows/CI/badge.svg">
    <a href="/package.json"><img alt="Software License" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square"></a>
    <img alt="All contributors" src="https://img.shields.io/badge/all_contributors-1-orange.svg?style=flat-square">
  </p>
</p>

## What does it do?

On comments like:

```
@all-contributors please add @octocat for design
```

It will automatically update **@all-contributors** list and push changes to the default branch.

## Why is it better than @all-contributors-bot?

- 🤖 It's as reliable as GitHub Actions
- 💪 It's frictionless - it will automatically push changes to the default branch. Forget PRs (and their conflicts)
- 🧹 It's tidier - it supports `.all-contributorsrc` placed in `.github` directory

## Usage

**.github/workflows/all-contributors.yml**:

```yml
name: all-contributors

on:
  issue_comment:
    types: [created]

jobs:
  all-contributors:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v1

      - uses: ActionwareHQ/all-contributors-action@action
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Any issue comment like:

```
@all-contributors please add @octocat for code, design
```

Will trigger the action. We support few different forms of comments, check out our
[test](https://github.com/ActionwareHQ/all-contributors-action/blob/master/test/all-contributors/parseComment.test.ts)
for more.

## License

Kris Kaczor MIT

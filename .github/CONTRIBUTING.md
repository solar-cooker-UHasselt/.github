# Contributing

How changes reach `main` in every solar-cooker-UHasselt repo. A repo's own README adds
what is specific to it, such as its check command.

1. Work on a branch and open a pull request to `main`.
2. CI must pass. For a board, `just check` runs the same ERC and DRC locally.
3. A code owner, listed in the repo's `.github/CODEOWNERS`, approves it. `main` accepts
   no force pushes.

Commits follow [Conventional Commits](https://www.conventionalcommits.org), one change
per commit. Each repo's types, scopes and check are in its
`.agents/commit_conventions.md`.

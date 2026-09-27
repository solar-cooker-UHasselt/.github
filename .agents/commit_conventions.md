# Commit conventions

This repo's commit rules. The shared procedure is the `propose-commit` skill, which
reads this file first and follows it where the two differ.

## Check

Every commit leaves the repo consistent: each image in `profile/README.md` exists.

```bash
grep -oE 'src="[^"]+"' profile/README.md | cut -d'"' -f2 | sed 's#^#profile/#' | xargs ls >/dev/null
```

A change to `renovate-config.json` passes Renovate's validator:

```bash
npx --yes --package renovate -- renovate-config-validator renovate-config.json
```

## Types

Choose by the change's *nature*, not by copying past messages.

| Type    | When to use                                             |
| ------- | ------------------------------------------------------- |
| `docs`  | Text or images on the org profile page, the default     |
| `fix`   | A broken link or image on the profile page              |
| `style` | Formatting / whitespace only, no content change         |
| `chore` | Repo maintenance, and the shared Renovate settings      |

## Scope

Optional. `profile` for anything under `profile/`, `renovate` for
`renovate-config.json`. Leave the scope out otherwise.

## Rules

- `profile/README.md` is what GitHub shows on the organisation page. Paths in it
  resolve relative to `profile/`, so images are `assets/<file>`.
- `renovate-config.json` holds the Renovate settings every repo extends, with
  `local>solar-cooker-UHasselt/.github:renovate-config` in its `renovate.json`. A
  change here reaches every repo that uses Renovate on its next run.
- Breaking changes: never marked. The repo has no releases.

## Well-formed examples

```
docs(profile): add the version 2 testing station renders
fix(profile): point the logo at the png in assets
chore: add commit conventions and ignore tmp/
```

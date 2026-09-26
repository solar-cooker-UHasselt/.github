# Commit conventions

This repo's commit rules. The shared procedure is the `propose-commit` skill, which
reads this file first and follows it where the two differ.

## Check

Every commit leaves the repo consistent: each image in `profile/README.md` exists.

```bash
grep -oE 'src="[^"]+"' profile/README.md | cut -d'"' -f2 | sed 's#^#profile/#' | xargs ls >/dev/null
```

## Types

Choose by the change's *nature*, not by copying past messages.

| Type    | When to use                                             |
| ------- | ------------------------------------------------------- |
| `docs`  | Text or images on the org profile page, the default     |
| `fix`   | A broken link or image on the profile page              |
| `style` | Formatting / whitespace only, no content change         |
| `chore` | Repo maintenance with no visible change on the org page |

## Scope

Optional. `profile` for anything under `profile/`. Leave the scope out otherwise.

## Rules

- `profile/README.md` is what GitHub shows on the organisation page. Paths in it
  resolve relative to `profile/`, so images are `assets/<file>`.
- Breaking changes: never marked. The repo has no releases, and nothing outside it
  links to its files.

## Well-formed examples

```
docs(profile): add the version 2 testing station renders
fix(profile): point the logo at the png in assets
chore: add commit conventions and ignore tmp/
```

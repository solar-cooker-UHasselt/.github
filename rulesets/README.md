# Rulesets and teams

A record of the org's branch protection and teams, as GitHub's own JSON (2026-10-24).
GitHub holds the live settings: after a change there, fetch the files again.

```bash
# Rulesets: list the ids, then fetch one without its repo-specific fields
gh api repos/solar-cooker-UHasselt/<repo>/rulesets --jq '.[] | "\(.id) \(.name)"'
gh api repos/solar-cooker-UHasselt/<repo>/rulesets/<id> \
  --jq 'del(.id, .node_id, .source, .source_type, .created_at, .updated_at, ._links, .current_user_can_bypass)'

# Teams: settings and repos per team
gh api orgs/solar-cooker-UHasselt/teams/<team>
gh api orgs/solar-cooker-UHasselt/teams/<team>/repos --jq '.[] | "\(.name) \(.role_name)"'
```

| File | What it sets |
| ---- | ------------ |
| `main_history.json` | Ruleset `main-history`: no force push and no deleting `main`, for everyone |
| `main_review.json` | Ruleset `main-review`: a pull request needs one approval from a code owner (the `maintainers` team, named in each repo's `.github/CODEOWNERS`). Org owners and repo admins bypass it |
| `main_review_board.json` | The same, plus a green `kicad-ci / ERC, DRC and outputs`, for the board repos |
| `teams.json` | The org's base permission, and each team with its repos. Members are managed on GitHub and not listed |

## A new repo

Needs `gh` logged in as an org owner. Replace `<repo>` with the repo's name.

1. Add `.github/CODEOWNERS` to it, copied from any repo here, and push.
2. Give `maintainers` write access, so it can approve:

   ```bash
   gh api -X PUT orgs/solar-cooker-UHasselt/teams/maintainers/repos/solar-cooker-UHasselt/<repo> -f permission=push
   ```

3. Add the two rulesets: in the repo, Settings > Rules > Rulesets > New ruleset >
   Import a ruleset, once with `main_history.json` and once with `main_review.json`. A
   board repo takes `main_review_board.json` instead of `main_review.json`.

4. Give the team that works in it access, as in `teams.json`: the same call as in step 2
   with that team's name, `permission=push` for write or `pull` for read. Then add the
   repo to `teams.json`.

A private repo cannot get rulesets on the free plan, only team access.

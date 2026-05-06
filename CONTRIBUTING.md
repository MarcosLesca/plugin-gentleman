# Contributing to Plugin Gentleman

Thanks for helping improve **Plugin Gentleman** — an OpenCode TUI plugin that brings Mustachi and the Gentleman theme into the terminal.

This repo follows an **issue-first workflow** inspired by `gentle-ai` and `engram`: start with a clear issue, get maintainer approval, then open a focused PR.

---

## Contribution Workflow

```text
Open Issue → Get status:approved → Open PR → Add one type:* label → Review & Merge
```

### Step 1: Open an Issue

Use the right template:

- **Bug Report** — broken behavior, crashes, rendering regressions, install/update problems.
- **Feature Request** — new options, visual improvements, detection behavior, or developer workflow improvements.

Blank issues are disabled. Fill in the required fields so maintainers can triage quickly.

### Step 2: Wait for Approval

A maintainer reviews the issue and adds `status:approved` when it is ready for implementation.

Do **not** open a PR until the issue is approved. Maintainers may close PRs that are not linked to an approved issue.

### Step 3: Open a Pull Request

Once the issue is approved:

1. Fork the repo and create a branch from `main`.
2. Keep the change focused on one logical outcome.
3. Verify the plugin locally using the checklist below.
4. Open a PR with the template and link the issue using `Closes #N`, `Fixes #N`, or `Resolves #N`.
5. Add exactly one `type:*` label to the PR.

---

## Development Setup

### Prerequisites

- Node.js and npm
- OpenCode CLI available on your `PATH`
- Git

### Install Dependencies

```bash
npm install
```

### Local Testing with `npm link`

```bash
npm link
```

Then add the linked plugin to `~/.config/opencode/opencode.json`:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "plugin": ["plugin-gentleman"]
}
```

Restart OpenCode after each change you want to inspect.

### Local Testing with a Tarball

```bash
npm pack
opencode plugin ./plugin-gentleman-<version>.tgz --global
```

If your OpenCode version does not accept a tarball path, use the published package flow instead.

---

## Verification Checklist

There is no build step. OpenCode transpiles TSX at runtime.

Before opening a PR, run the checks that match your change:

| Check | Command | When to run |
|-------|---------|-------------|
| Type check | `npx tsc --noEmit` | TypeScript, TSX, config, runtime helper changes |
| Package smoke check | `npm pack` | Packaging, exports, files list, install/update changes |
| Local cache smoke check | `./mini-local-check.sh` | TUI behavior, OpenCode cache, package-slot verification |
| Manual runtime check | Restart OpenCode | Any visual, theme, animation, detection, or sidebar change |

Manual runtime checks should confirm:

- [ ] Mustachi renders in the sidebar.
- [ ] The home logo/theme still loads as expected.
- [ ] Animations respect the `animations` setting.
- [ ] Personality phrases respect the `personality_enabled` setting.
- [ ] OS/provider/metrics display still behaves correctly when touched.
- [ ] No obvious TUI layout regression appears in OpenCode.

> This repository currently has no automated test runner, linter, formatter, or build script. Do not invent commands in PRs; document exactly what you ran.

---

## Label System

### PR Type Labels

Every PR should have exactly one type label.

| Label | Use for |
|-------|---------|
| `type:bug` | Bug fixes |
| `type:feature` | New behavior or user-facing enhancements |
| `type:docs` | Documentation-only changes |
| `type:refactor` | Code restructuring with no behavior change |
| `type:chore` | Maintenance, dependencies, packaging, tooling |
| `type:breaking-change` | Changes that break existing behavior or configuration |

### Issue Status Labels

| Label | Meaning |
|-------|---------|
| `status:needs-review` | Newly opened, awaiting maintainer triage |
| `status:approved` | Accepted and ready for implementation |
| `status:in-progress` | Someone is actively working on it |
| `status:blocked` | Waiting on another decision, dependency, or upstream behavior |
| `status:wontfix` | Out of scope or intentionally not planned |

### Priority and Effort Labels

Maintainers may also use:

- `priority:high`, `priority:medium`, `priority:low`
- `effort:small`, `effort:medium`, `effort:large`

---

## Commit Convention

Use [Conventional Commits](https://www.conventionalcommits.org/):

```text
<type>(<optional-scope>): <short description>

[optional body]

[optional footer]
```

Allowed types: `feat`, `fix`, `docs`, `refactor`, `chore`, `style`, `perf`, `test`, `build`, `ci`, `revert`.

Examples:

```text
feat(sidebar): add calmer busy-state expression
fix(config): preserve defaults when plugin options are partial
docs(contributing): add local verification checklist
chore(deps): update opentui peer dependency notes
```

Do not add `Co-Authored-By` trailers.

---

## Branch Naming

Use lowercase, descriptive branch names:

```text
feat/sidebar-expression
fix/npm-pack-files
docs/contributor-guidelines
chore/update-deps
```

Recommended pattern:

```text
^(feat|fix|chore|docs|style|refactor|perf|test|build|ci|revert)/[a-z0-9._-]+$
```

---

## Pull Request Rules

- Link an approved issue in the PR body.
- Keep scope focused: one logical change per PR.
- Add exactly one `type:*` label.
- Use a Conventional Commit-style PR title.
- Update README or contributor docs when behavior changes.
- Include manual screenshots or terminal notes for visual TUI changes when helpful.
- Do not include generated tarballs, local cache files, credentials, or user-specific OpenCode config.
- Do not configure branch protection or repository rulesets in contributor PRs unless maintainers explicitly request it.

### What Gets Closed Without Merging

- PRs without a linked approved issue.
- PRs that include unrelated drive-by changes.
- PRs that document commands or behavior that do not exist in this repository.
- Issues that are vague, duplicates, or missing reproduction details after maintainer follow-up.

---

## Code of Conduct

Be respectful and direct. Critique code and ideas, not people.

See [`CODE_OF_CONDUCT.md`](./CODE_OF_CONDUCT.md) for the full community standard.

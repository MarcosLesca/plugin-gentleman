<!--
  READ BEFORE SUBMITTING

  Every PR should:
  1. Link an approved issue with Closes/Fixes/Resolves #N
  2. Have exactly one type:* label
  3. Document the verification actually performed

  See CONTRIBUTING.md for the full workflow.
-->

## 🔗 Linked Issue

<!-- Required: replace # with the approved issue number. -->

Closes #

---

## 🏷️ PR Type

<!-- Check exactly one, then add the matching label to the PR. -->

- [ ] `type:bug` — Bug fix
- [ ] `type:feature` — New feature or enhancement
- [ ] `type:docs` — Documentation only
- [ ] `type:refactor` — Code refactoring with no behavior change
- [ ] `type:chore` — Maintenance, dependencies, packaging, tooling
- [ ] `type:breaking-change` — Breaking change

---

## 📝 Summary

<!-- What does this PR do and why? Keep it to 1-3 bullets. -->

-

## 📂 Changes

| File / Area | What Changed |
|-------------|--------------|
| `path/to/file` | Brief description |

## 🧪 Verification

<!-- Check only what you actually ran. Add notes for anything skipped. -->

- [ ] Type check passes: `npx tsc --noEmit`
- [ ] Package smoke check passes: `npm pack`
- [ ] Local OpenCode cache smoke check passes: `./mini-local-check.sh`
- [ ] Manually tested in OpenCode after restart
- [ ] Not applicable — docs/template-only change

Manual runtime notes:

<!-- For visual/TUI changes, describe what you saw. Screenshots or terminal notes help reviewers. -->

---

## ✅ Contributor Checklist

- [ ] I linked an approved issue above.
- [ ] I added exactly one `type:*` label.
- [ ] I kept this PR focused on one logical change.
- [ ] I updated documentation if behavior changed.
- [ ] My commits follow Conventional Commits.
- [ ] My commits do not include `Co-Authored-By` trailers.
- [ ] I did not include generated tarballs, local cache files, secrets, or user-specific OpenCode config.

---

## 💬 Notes for Reviewers

<!-- Optional: call out tradeoffs, risk areas, or files to review first. -->

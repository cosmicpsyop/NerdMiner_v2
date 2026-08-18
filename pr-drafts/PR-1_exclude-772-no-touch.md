# PR Draft: Exclude PR #772 changes (no touch adjustments)

**Branch name suggestion:** pr/exclude-772-no-touch

**Summary:**
This draft creates a branch and PR that intentionally excludes the fixes merged/submitted in PR #772 and makes no "touch" related adjustments. The goal is to produce a clean baseline PR that keeps current behavior while removing the specific change(s) introduced by PR #772 for investigation and testing.

**What's included:**
- No new feature changes beyond reverting/excluding the commit(s) introduced by PR #772.
- No touch adjustments (no changes to touch handling or calibration).

**Why:**
- To test behavior without the PR #772 fix and to isolate regressions introduced by that PR.

**How to create this branch locally:**

```bash
git checkout -b pr/exclude-772-no-touch origin/main
# If PR #772 was a merge commit, find its merge commit or commit(s) and revert them.
# Example (replace <merge-commit> with the merge commit SHA):
# git revert -m 1 <merge-commit>

# Or if you know the individual commit SHAs from PR #772, revert each:
# git revert <commit-sha-1> <commit-sha-2>

git push -u origin pr/exclude-772-no-touch
```

If you're not certain which commits belong to PR #772, fetch the PR remote info or inspect the GitHub PR page to identify the commits, then use `git revert` to remove them from this branch.

**Testing notes:**
- Build with PlatformIO and run the same tests used before PR #772 to compare behavior.
- Specifically validate screens, mining flow, and peripherals that may have been affected by PR #772.

**PR description (copy into GitHub):**

Title: "Exclude PR #772 changes — baseline (no touch adjustments)"

Body:
This PR establishes a baseline that excludes the changes from PR #772 and intentionally avoids any touch-related adjustments. The purpose is to allow comparison and testing between the codebase before and after PR #772, isolating any regressions.

What I did:
- Reverted the commit(s) introduced by PR #772 on a new branch.
- Did not modify any touch handling code.

How to test:
- Build with PlatformIO: `pio run` (or the project's preferred build step).
- Flash to a device and validate the core workflows.

Notes:
- If maintainers prefer, I can instead create a temporary branch that cherry-picks desired commits from `main` excluding PR #772 changes — tell me which approach you prefer.

**Checklist:**
- [ ] Confirm the exact commit(s) from PR #772 to revert (link to PR: https://github.com/BitMaker-hub/NerdMiner_v2/pull/772)
- [ ] Build passes on CI
- [ ] Manual smoke test on hardware

---

*This is a draft PR.*

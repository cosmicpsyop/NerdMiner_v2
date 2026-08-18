# PR Draft: Add vulnerability scan CI (CodeQL)

**Branch name suggestion:** pr/add-vuln-scan-codeql

**Summary:**
Add a GitHub Actions workflow to run CodeQL analysis (vulnerability and security code scanning) on push and pull requests. This PR adds the workflow configuration and documentation for the team to review and run scans in CI.

**What's included:**
- `.github/workflows/codeql-analysis.yml` — CodeQL analysis configured for C/C++ (and common languages if desired).
- PR description and testing instructions.

**Why:**
- Introduce automated security scanning in CI to detect potential code issues early.

**How to create and push the branch:**

```bash
git checkout -b pr/add-vuln-scan-codeql origin/main
# The workflow file is added in this branch; commit is already prepared in this draft.
git add .github/workflows/codeql-analysis.yml
git commit -m "ci: add CodeQL analysis workflow for vulnerability scanning"
git push -u origin pr/add-vuln-scan-codeql
```

**PR description (copy into GitHub):**

Title: "Add CodeQL-based vulnerability scanning workflow"

Body:
This PR adds a GitHub Actions workflow that enables CodeQL analysis for the repository. The workflow runs on pushes and pull requests to provide early detection of potential security issues in C/C++ code and other languages present in the repo.

Included files:
- `.github/workflows/codeql-analysis.yml` — CodeQL analysis configuration.

How to validate:
- After opening the PR, GitHub Actions will run the CodeQL job and post results in the Checks tab.
- Address any high confidence findings by creating follow-up PRs.

Notes & options:
- If you prefer to run additional scanners (Trivy, semgrep, etc.), I can add them in follow-up commits.

**Checklist:**
- [ ] Confirm CodeQL config covers the repo languages (C/C++)
- [ ] CI job triggers and completes successfully
- [ ] Review initial findings and triage

---

*This is a draft PR.*

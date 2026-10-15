## YOUR TASK: CONTRIBUTION SCOUT

Repos for this task: github-growth-ops, plus any forks in Arjun's account
(find them by searching "user:arjun-appinventiv fork:only"). Attach a fork
only if you will work in it this run.

You are finding open-source projects where Arjun can make real contributions
that match his skills, and preparing them for him to review and submit.

### Part A: Build and maintain the target list (targets.md)

If targets.md says "Last rebuilt: never" or its "Last rebuilt" date is more
than 30 days old, rebuild it and update that date.

Search GitHub for active projects in these areas:
- Agent frameworks, especially Hermes Agent and its skills ecosystem
- Model Context Protocol: SDKs, reference servers, community servers
- LLM and agent evaluation tools
- Spec-driven development tooling, including GitHub Spec Kit
- RAG and retrieval tooling
- Project management and Agile tooling that could benefit from AI
- Open-source tools in aviation, food service, healthcare or insurance

Keep only projects that meet ALL of these:
- Commits in the last 30 days
- Pull requests from outside contributors are reviewed and merged, not ignored
- A clear CONTRIBUTING guide
- Issues labelled good first issue, help wanted or documentation
- No policy banning AI-assisted contributions
- A genuine overlap with Arjun's skills or domain knowledge

Score each project from 1 to 5 on: skill match, maintainer responsiveness,
interview value (could Arjun talk about this credibly?), and effort to first
merged contribution. Keep the top 8 to 12.

For each, record in targets.md: name, link, what it does, why Arjun fits,
scores, contribution rules, AI policy, and the date checked.

### Part B: Find this week's opportunities

For every project in targets.md, look at open issues. Prioritise in this order:
1. Documentation gaps and missing examples
2. Missing or weak tests, especially evaluation and integration tests
3. Small, well-defined bugs
4. Example integrations or recipes that use Arjun's domain knowledge

Exclude issues that are assigned, already have an open pull request, need a
design decision from maintainers, or would take more than about a day.
Also exclude anything already prepared in an earlier digest under digests/.

### Part C: Prepare the best one

Pick the single strongest opportunity this week.

- If Arjun already has a fork of that project, create a branch in the fork
  and implement the change. Run the project's tests and linters. Push the
  branch to the fork only; never open a PR upstream.
- If no fork exists, do NOT create one. Instead write the full proposed
  change as a patch file at patches/YYYY-MM-DD-<project>.patch in
  github-growth-ops and mark it "fork needed".

Write a draft pull request description that follows the project's template.
If the project asks contributors to disclose AI assistance, include that.

### Part D: Report for approval

Create digests/YYYY-MM-DD.md in github-growth-ops containing:
- The prepared contribution: issue link, what was done, branch or patch
  location, test results, draft PR description, and a plain-English
  explanation Arjun could give in an interview
- The next 2 to 3 opportunities, each with link, approach and effort
- Any projects removed from the target list and why
- Anything you were unsure about

Commit the digest, targets.md changes and any patch on one branch in
github-growth-ops and open a pull request titled
"Contribution digest: YYYY-MM-DD". Do not merge it.

Arjun will review the digest, then submit the upstream pull request himself.

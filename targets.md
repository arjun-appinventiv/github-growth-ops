# Contribution targets

Last rebuilt: 2026-10-15

Scores are 1 to 5. For **Effort**, 5 means the quickest route to a first merged contribution.
All projects were checked on 2026-10-15. Activity was measured from git history, and contribution rules and AI policy were read in each repository's own files.

| # | Project | Skill | Responsiveness | Interview | Effort | Total |
|---|---|---|---|---|---|---|
| 1 | Arize Phoenix | 5 | 3 | 5 | 4 | 17 |
| 2 | MCP C# SDK | 5 | 4 | 5 | 3 | 17 |
| 3 | LlamaIndex | 5 | 5 | 4 | 3 | 17 |
| 4 | Hermes Agent | 5 | 3 | 5 | 3 | 16 |
| 5 | Haystack | 5 | 4 | 4 | 2 | 15 |
| 6 | MCP Python SDK | 5 | 2 | 5 | 2 | 14 |
| 7 | OpenEMR | 3 | 4 | 4 | 3 | 14 |
| 8 | DeepEval | 5 | 2 | 5 | 2 | 14 |

---

## 1. Arize Phoenix
- **Link:** https://github.com/Arize-ai/phoenix
- **What it does:** An open-source platform for LLM tracing and evaluation. It covers OpenTelemetry/OpenInference traces, LLM-as-judge evaluators, datasets and experiments.
- **Why Arjun fits:** This is his core strength: evaluation harnesses, ground-truth datasets, and scoring faithfulness and correctness separately. The docs also cover MCP and Claude integrations he uses daily.
- **Activity:**
  - Commits land on main daily.
  - The `documentation` label has about 46 open issues, including a weekly docs-gap audit written by a maintainer.
  - Outside fixes do get merged (for example, two from lx3133584 on 2026-10-15), although most merges come from staff.
  - Re-checked 2026-10-26: Arjun's 2026-10-16 request on #16988 still has no maintainer reply after 10 days. Treat the "wait for confirmation" gate as slow here.
- **Contribution rules (CONTRIBUTING.md):**
  - "Not actively accepting feature contributions." Small bug, reliability and maintenance fixes are welcome.
  - **An open issue is not an invitation:** wait for explicit maintainer confirmation before starting.
  - Keep PRs small and explain what changed and why.
  - The PR template is `resolves #<issue>`.
  - Run `tox run -e ruff` and `tox run -e unit_tests` for Python changes.
  - A CLA is required (CLA.md).
- **AI policy:** None published. The repo ships CLAUDE.md and AGENTS.md and runs a Claude Code Review workflow on PRs, so it is AI-friendly. Disclose anyway.

## 2. Model Context Protocol C# SDK
- **Link:** https://github.com/modelcontextprotocol/csharp-sdk
- **What it does:** The official .NET SDK for building MCP clients and servers.
- **Why Arjun fits:** It is .NET/C# combined with MCP tool layers, a rare match for both his developer background and his AI integration work.
- **Activity:**
  - Commits within the last week.
  - About 10 of the last 25 merges came from outside contributors, including docs and sample PRs.
  - The `help wanted` label has 14 issues and `documentation` has 8. There is no `good first issue` label.
  - Re-checked 2026-10-26: every `help wanted` or `documentation` issue I checked that is small enough already has a claimant or an open PR (#1806 → #1833, #889 → #950/#1880, #1126 → #1788, #1389 and #1494 claimed in comments).
- **Contribution rules:**
  - CONTRIBUTING.md says community PRs are welcome.
  - Issues labelled `help wanted` + `ready for work` need no assignment.
  - Tests use the xUnit `LoggedTest` patterns described in CONTRIBUTING.
- **AI policy:** The MCP org-wide AI_POLICY.md welcomes AI tools. AI assistance **must be disclosed** in the PR or issue, with its extent. The contributor must understand the change and provide evidence such as tests.

## 3. LlamaIndex
- **Link:** https://github.com/run-llama/llama_index
- **What it does:** A RAG and agent data framework covering indexing, retrieval, query engines and evaluation modules.
- **Why Arjun fits:** RAG in production, retrieval scoping and the evaluation module (faithfulness, pairwise and correctness evaluators).
- **Activity:**
  - Commits within the last week.
  - About 19 of the last 25 merges came from outside contributors, the best outsider responsiveness on this list.
  - There are 3 `good first issue` issues.
  - Re-checked 2026-10-26: 10 open `good first issue` issues, but the four bug reports from 2026-10-23 (#23673, #23675, #23679, #23683) each arrived with the reporter's own PR (#23674, #23676, #23680, #23684). #21610 (HotpotQA file handles) was fixed by #22113 in July, so it is no longer an opportunity.
- **Contribution rules:**
  - CONTRIBUTING.md describes per-package development under `llama-index-integrations/...` and `llama-index-core`.
  - Maintainers close duplicate PRs automatically.
  - Stale issues are closed by a bot.
- **AI policy:** "We welcome AI-assisted contributions." Be transparent about where AI was used and how the output was verified. Keep changes small; large or unreviewed AI changes are discouraged.

## 4. Hermes Agent
- **Link:** https://github.com/NousResearch/hermes-agent
- **What it does:** Nous Research's open agent framework with skills, plugins, memory providers and a desktop app.
- **Why Arjun fits:** He is Hermes Agent certified, and the skills ecosystem matches his multi-agent workflow work.
- **Activity:**
  - Very high volume: 68 commits in the last 30 days, and many merges per day.
  - The maintainer often "salvages" (re-submits) contributor PRs rather than merging them directly.
  - Docs issues use the `type/docs` label (about 247 open); P3 marks the small ones.
- **Contribution rules:**
  - The CONTRIBUTING.md is long.
  - Search open and merged PRs for duplicates first.
  - One logical change per PR.
  - `python scripts/check` must pass (a code-health ratchet).
  - The PR template includes a duplicate check.
- **AI policy:** No restriction found. The repo ships an AGENTS.md "for AI coding assistants".

## 5. Haystack
- **Link:** https://github.com/deepset-ai/haystack
- **What it does:** deepset's orchestration framework for production RAG and agent pipelines, including retrieval evaluators (MRR, MAP, NDCG, SAS).
- **Why Arjun fits:** RAG pipelines and retrieval evaluation metrics.
- **Activity:**
  - Commits daily.
  - Outside fixes are merged within days (for example #13244, #13238, #13253).
  - New issues are claimed within hours, and the `good first issue` and `Contributions wanted!` labels are currently empty.
- **Contribution rules:**
  - Conventional-commit PR titles.
  - Fill in the PR template.
  - Add a release note (reno).
  - Run pre-commit and `hatch run test:unit`.
  - A CLA is required.
  - Avoid issues labelled "handled internally".
- **AI policy:** AI assistants are allowed. Review and understand all generated code. If the PR was fully AI-generated, add a short disclaimer.

## 6. Model Context Protocol Python SDK
- **Link:** https://github.com/modelcontextprotocol/python-sdk
- **What it does:** The official Python SDK for MCP servers and clients, including FastMCP.
- **Why Arjun fits:** Python combined with MCP tool layers.
- **Activity:**
  - 40 commits in the last 30 days.
  - Outsider merges are currently rare: the last 25 merges were all by maintainers or bots.
  - There are `documentation` issues with no PR, for example #3287.
- **Contribution rules:**
  - PRs are closed automatically unless they reference an issue assigned to you or labelled `help wanted`.
  - A comment that only asks to be assigned does not count. Engage with the substance of the issue.
  - New APIs and multi-module changes need discussion first.
- **AI policy:** Allowed, with disclosure required: "one line in the PR description". You must "own it" and explain it in your own words. Undisclosed AI contributions may be closed. The org AI_POLICY.md also applies.

## 7. OpenEMR
- **Link:** https://github.com/openemr/openemr
- **What it does:** An open-source EHR and practice-management system with FHIR and REST APIs.
- **Why Arjun fits:** Healthcare domain knowledge and REST/system-integration work. The catch is that the codebase is PHP, not Python or .NET.
- **Activity:**
  - Dozens of commits per week.
  - Several outside contributors were merged recently.
  - Good first issue #12343 tracks REST API test coverage, one resource per PR.
- **Contribution rules:**
  - Discuss features first on the forum or an issue.
  - Conventional Commit titles.
  - A maintainer must approve CI for first-time contributors.
  - Coordinate on #12343 before starting to avoid duplicates.
- **AI policy:** Welcomed. Add an `Assisted-by:` (or `Generated-by:`) commit trailer when AI helped.

## 8. DeepEval
- **Link:** https://github.com/confident-ai/deepeval
- **What it does:** A pytest-style LLM evaluation framework with RAG, agent and citation-faithfulness metrics.
- **Why Arjun fits:** Agent and RAG evaluation, including the three-way scoring he already runs: citation presence, evidence support and correctness.
- **Activity:**
  - 149 commits in the last 30 days.
  - Only about 2 outside PRs were merged in the last 30 days, and many outside PRs have no maintainer reply.
  - 6 `help wanted` issues and 1 `documentation` issue, all large.
- **Contribution rules:**
  - CONTRIBUTING.md is short: fork, branch, and optionally run `black`.
  - CI failures on forks are expected.
- **AI policy:** None published.
- **Borderline:** Responsiveness to outsiders is weak. Re-check at the next rebuild and drop it if this does not improve.

---

## Considered and excluded (2026-10-15)

| Project | Reason |
|---|---|
| github/spec-kit | Active and responsive (8 of the last 25 merges from outsiders), but it has **zero** open issues labelled good first issue, help wanted or documentation, and almost every triaged issue already has a PR. It fails the label criterion, so it is on the watchlist. Disclosure there is strict: agent, model, mode and extent, plus `Assisted-by:` trailers and a 3-open-PR cap. |
| modelcontextprotocol/servers | CONTRIBUTING: "We accept issues, not pull requests." Only maintainers open PRs. |
| explodinggradients/ragas | No commits since 2026-02-24. |
| casact/chainladder-python | Strong insurance fit and active, but its governance doc **restricts** AI-assisted work: "All external contributions and project interactions must be initiated by a human", PRs must "declare you are human", and automated PRs may be closed. It also has no CONTRIBUTING file. Skipped under hard rule 7. |
| promptfoo/promptfoo | No issues under the three labels. Outside PRs sit unreviewed. |
| langfuse/langfuse | The only good-first-issue is assigned and contested. The documentation issues are vendor spam. No clear outside merges. |
| makeplane/plane | No open good-first-issues. Outside merges are rare. |
| TandoorRecipes/recipes | Only translation commits in the last 30 days, and no CONTRIBUTING file in the repo. |
| Aviation (xoolive/traffic, open-aviation/tangram, pyopensky, openap) | No project met all criteria. Most lack a CONTRIBUTING file, outside merges or labelled issues. |
| openIMIS (health insurance) | No commits since early September. |

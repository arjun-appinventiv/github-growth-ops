# Contribution targets

Last rebuilt: 2026-11-16

Scores are 1 to 5. For **Effort**, 5 means the quickest route to a first merged contribution.
All projects were checked on 2026-11-16, unless a row says otherwise.

How each project was checked:
- **Activity:** read from git history on `main`.
- **Merges:** a GitHub search for PRs merged since 2026-10-17, counting the authors.
- **Labelled issues:** a GitHub search for open, unassigned issues with no linked PR under `good first issue`, `help wanted`, `documentation`/`docs` or `type/docs`.
- **Contribution rules and AI policy:** read in each repository's own files.

| # | Project | Skill | Responsiveness | Interview | Effort | Total | Change since 2026-10-15 |
|---|---|---|---|---|---|---|---|
| 1 | Hermes Agent | 5 | 4 | 5 | 4 | 18 | Responsiveness and effort up |
| 2 | MCP C# SDK | 5 | 4 | 5 | 3 | 17 | No change |
| 3 | Inspect AI | 5 | 4 | 5 | 3 | 17 | **New** |
| 4 | Microsoft Agent Framework | 5 | 3 | 5 | 3 | 16 | **New** |
| 5 | Arize Phoenix | 5 | 2 | 5 | 3 | 15 | Responsiveness down: your comment of 2026-10-16 is unanswered |
| 6 | LlamaIndex | 5 | 3 | 4 | 3 | 15 | Responsiveness down: merge volume has collapsed |
| 7 | DeepEval | 5 | 3 | 5 | 2 | 15 | Responsiveness up: outside merges improved |
| 8 | OpenEMR | 3 | 4 | 4 | 3 | 14 | No change |

---

## 1. Hermes Agent
- **Link:** https://github.com/NousResearch/hermes-agent
- **What it does:** Nous Research's open agent framework, with skills, plugins, MCP client support, memory providers, a gateway and a desktop app.
- **Why Arjun fits:**
  - He is Hermes Agent certified.
  - The skills ecosystem and the MCP client docs match his multi-agent and MCP tool-layer work.
- **Activity:**
  - Extremely high volume: thousands of commits in the last 30 days and over 4,000 merged PRs.
  - Of a 100-PR sample of recent merges, 36 came from first-time contributors (`NONE` association), so outside PRs do land.
  - The maintainer still sometimes "salvages" (re-submits) a contributor's PR.
  - About 100 open, unassigned `type/docs` issues have no linked PR. `P3` marks the small ones.
- **Contribution rules (CONTRIBUTING.md):**
  - Before starting, search both open **and** merged PRs and issues.
  - One logical change per PR.
  - Conventional Commits, and branch names like `docs/...`.
  - `just test` and `just check` must pass.
  - Skill doc pages are generated from each skill's `SKILL.md`: edit the source and run `just docs-generate`.
  - The PR template includes a duplicate-search checkbox.
- **AI policy:** No restriction found. The repo ships an AGENTS.md for AI coding assistants. Disclose anyway.

## 2. Model Context Protocol C# SDK
- **Link:** https://github.com/modelcontextprotocol/csharp-sdk
- **What it does:** The official .NET SDK for building MCP clients and servers.
- **Why Arjun fits:** .NET/C# combined with MCP tool layers, a rare match for both his developer background and his AI integration work.
- **Activity:**
  - 43 commits since 2026-10-17.
  - 48 merged PRs, all with `CONTRIBUTOR` association.
  - 6 labelled issues are open and unassigned. Most need confirmation or a repro. #1494 and #1389 are `ready for work`, but #1389 has two contributors asking to take it.
- **Contribution rules:**
  - CONTRIBUTING.md welcomes community PRs.
  - Issues labelled `help wanted` + `ready for work` need no assignment.
  - Tests use the xUnit `LoggedTest` patterns.
- **AI policy:** The MCP org-wide AI_POLICY.md welcomes AI tools. AI assistance **must be disclosed**, with its extent. The contributor must understand the change and provide evidence such as tests.

## 3. Inspect AI (new)
- **Link:** https://github.com/UKGovernmentBEIS/inspect_ai
- **What it does:** The UK AI Security Institute's framework for LLM and agent evaluations: tasks, solvers, scorers, sandboxes and an eval log viewer.
- **Why Arjun fits:** Agent evaluation is his strongest area: ground-truth sets, automated harnesses and separate scorers. Inspect is widely used and highly credible in interviews.
- **Activity:**
  - 356 commits since 2026-10-17.
  - Of 100 recent merges, about 20 came from one-off outside contributors.
  - 7 open labelled issues, all already claimed or with PRs. 4 `accepted` issues are unassigned with no PR.
- **Contribution rules (CONTRIBUTING.md):**
  - **Issue-first.** A PR must reference an issue a maintainer has labelled `accepted`, or it is closed automatically.
  - `good first issue` implies `accepted`.
  - Trivial docs fixes (docs only, under 25 lines) are welcome without an issue.
  - Claim an issue by commenting. Claims lapse after 7 days.
  - Conventional Commits PR title.
  - The PR template has Problem, Result, Compatibility, Validation, Slow tests and **Agent review** sections.
- **AI policy:**
  - "AI-assisted contributions are welcome."
  - You must be able to explain and defend every line.
  - Note the tooling used in the PR.
  - Run review passes in a fresh context and summarise the findings in the **Agent review** section.

## 4. Microsoft Agent Framework (new)
- **Link:** https://github.com/microsoft/agent-framework
- **What it does:** Microsoft's .NET and Python framework for building agents and multi-agent workflows (the successor line to Semantic Kernel and AutoGen agents).
- **Why Arjun fits:** .NET/C# and Python, multi-agent workflows with structured handoffs, and enterprise integration.
- **Activity:**
  - 378 merged PRs since 2026-10-17, about 40% from `CONTRIBUTOR` association.
  - 5 open, unassigned `documentation` issues, for example #2352 (.NET ILoggerFactory docs) and #4629 (compaction docs).
- **Contribution rules (CONTRIBUTING.md):**
  - Except for trivial changes, wait for a maintainer to add `ready-for-implementation` or explicitly approve the direction.
  - Automated triage, assignment and silence do not count as approval.
  - A CLA is required.
- **AI policy (AI_CONTRIBUTIONS.md):**
  - Permitted.
  - Material AI assistance must be disclosed in the PR template's **AI Assistance** section.
  - You must personally verify the behaviour and validate APIs, versions and links.
  - Expect longer review waits.

## 5. Arize Phoenix
- **Link:** https://github.com/Arize-ai/phoenix
- **What it does:** An open-source platform for LLM tracing and evaluation, covering OpenTelemetry/OpenInference traces, LLM-as-judge evaluators, datasets and experiments.
- **Why Arjun fits:** Evaluation harnesses, ground-truth datasets, and scoring faithfulness and correctness separately.
- **Activity:**
  - 391 commits since 2026-10-17. 74 of 100 sampled merges have `CONTRIBUTOR` association, but most are staff.
  - The weekly docs-gap audits continue: #17092 and #17326 are new.
  - **Your 2026-10-16 comment on #16988, asking to take item 3, got no maintainer reply.** Meanwhile #17172 (merged 2026-10-22) fixed most of item 3, with no link to the audit issue.
- **Contribution rules (CONTRIBUTING.md):**
  - "Not actively accepting feature contributions."
  - "An open issue is not an invitation": wait for explicit maintainer confirmation before starting.
  - Tests now run through uv and `make test-python`, not tox.
  - The PR template was rewritten on 2026-10-29: `resolves #`, then What, Try it, and a **"How this PR was made"** section for agent-written PRs (Agent, Steering, Abandoned, Verified, Look hardest at).
  - A CLA is required.
- **AI policy:** None published. The new PR template asks agent-assisted PRs to describe how they were made. The Claude Code Review workflow was removed on 2026-11-05.

## 6. LlamaIndex
- **Link:** https://github.com/run-llama/llama_index
- **What it does:** A RAG and agent data framework covering indexing, retrieval, query engines and evaluation modules.
- **Why Arjun fits:** RAG in production, retrieval scoping and the evaluation module.
- **Activity:**
  - Only 9 merged PRs since 2026-10-17, compared with dozens per week before.
  - The README now says the company's "primary focus has shifted" to LlamaParse, and the framework is offered "as an open toolkit".
  - Outside fixes still land, for example a docs URL fix (#24017) and a dependency-pin fix (#24125).
- **Contribution rules:**
  - Per-package development under `llama-index-integrations/...` and `llama-index-core`.
  - Duplicate PRs are closed automatically.
  - Stale issues are closed by a bot.
- **AI policy:** "We welcome AI-assisted contributions." Be transparent about where AI was used and how it was verified. Keep changes small.
- **Watch:** if merge volume stays this low at the next rebuild, drop it.

## 7. DeepEval
- **Link:** https://github.com/confident-ai/deepeval
- **What it does:** A pytest-style LLM evaluation framework with RAG, agent and citation-faithfulness metrics.
- **Why Arjun fits:** Agent and RAG evaluation, including the three-way scoring he already runs.
- **Activity:**
  - 194 commits since 2026-10-17.
  - 32 merged PRs from 18 different authors, most of them one-off outside contributors. This is better than last month.
  - 6 labelled issues are open, all large or already taken.
- **Contribution rules:**
  - CONTRIBUTING.md is short: fork, branch, and optionally run `black`.
  - CI failures on forks are expected.
- **AI policy:** None published.

## 8. OpenEMR
- **Link:** https://github.com/openemr/openemr
- **What it does:** An open-source EHR and practice-management system with FHIR and REST APIs.
- **Why Arjun fits:** Healthcare domain knowledge and REST/system-integration work. The codebase is PHP.
- **Activity:**
  - 498 commits since 2026-10-17.
  - 41 of 100 sampled merges came from `CONTRIBUTOR` association.
  - #12343 (REST API test coverage, `good first issue`) is still open, one resource per PR.
- **Contribution rules:**
  - Most PRs need no prior issue.
  - Conventional Commits.
  - A new license-header check runs in CI (added 2026-11-05).
  - A legacy-directory policy was added on 2026-10-26.
  - The code of conduct was updated on 2026-11-12.
- **AI policy:** Welcomed. Add an `Assisted-By:` (or `Generated-By:`) commit trailer.

---

## Removed at this rebuild (2026-11-16)

| Project | Reason |
|---|---|
| modelcontextprotocol/python-sdk | **No outside contributor merged in the last 30 days.** All 10 merges since 2026-10-17 are by one maintainer or dependabot. Fails "outside PRs are reviewed and merged". Its docs issues are also all claimed (#3845, #3737) or awaiting scope agreement (#3861). On the watchlist. |
| deepset-ai/haystack | **Zero open issues** under good first issue, help wanted or documentation, for the second rebuild running. Outside PRs are merged quickly, but there is nothing labelled to pick up. On the watchlist. |

## Considered and excluded

| Project | Checked | Reason |
|---|---|---|
| github/spec-kit | 2026-11-16 | Active, with outside merges, but still **zero** open issues under the three labels. Strict AI disclosure (agent, model, extent, `Assisted-by:` trailers). On the watchlist. |
| comet-ml/opik | 2026-11-16 | Good evaluation fit, and AI use is allowed with an `AI-WATERMARK` section in the PR template. But it has **zero** open issues under the three labels. Outside PRs are capped at 3 open per person. |
| modelcontextprotocol/typescript-sdk | 2026-11-16 | Only 2 labelled issues, both `needs decision`. TypeScript is not a core skill. |
| pydantic/pydantic-ai | 2026-11-16 | Very active, with many outside merges. Not fully evaluated this run (its AI policy is in `docs/contributing.md`, which I did not read). Evaluate at the next rebuild. |
| modelcontextprotocol/servers | 2026-10-15 | "We accept issues, not pull requests." |
| explodinggradients/ragas | 2026-10-15 | No commits since 2026-02-24. |
| casact/chainladder-python | 2026-10-15 | Governance doc **restricts** AI-assisted work ("must be initiated by a human", "declare you are human"). Skipped under hard rule 7. |
| promptfoo/promptfoo | 2026-10-15 | No labelled issues. Outside PRs sit unreviewed. |
| langfuse/langfuse | 2026-10-15 | The only good-first-issue was contested. No clear outside merges. |
| makeplane/plane | 2026-10-15 | No open good-first-issues. Outside merges are rare. |
| TandoorRecipes/recipes | 2026-10-15 | Translation-only activity. No CONTRIBUTING file. |
| Aviation (traffic, tangram, pyopensky, openap) | 2026-10-15 | No project met all criteria. |
| openIMIS (health insurance) | 2026-10-15 | No commits since early September. |

Rows dated 2026-10-15 were carried over and **not re-checked** in this run, because of search rate limits. Re-check them at the next rebuild.

# Contribution targets

Last rebuilt: 2026-11-23

Scores are 1 to 5. For **Effort**, 5 means the quickest route to a first merged contribution.
All projects were checked on 2026-11-23. The 30-day window is 2026-10-24 to 2026-11-23.

How the numbers were measured:
- **Commits:** counted from a shallow git clone of the default branch.
- **Merged PRs and outside authors:** from GitHub search, using the first 100 merged PRs in the window. Bots are excluded, and "outside" means the PR author is not an org member or collaborator.
- **Labelled issues:** open, unassigned issues labelled good first issue, help wanted, documentation, `type/docs` or "Contributions wanted!".
- **Rules and AI policy:** read in each repository's own CONTRIBUTING, AGENTS and PR-template files.

| # | Project | Skill | Responsiveness | Interview | Effort | Total | Change since 2026-10-15 |
|---|---|---|---|---|---|---|---|
| 1 | Arize Phoenix | 5 | 3 | 5 | 4 | 17 | = |
| 2 | MCP C# SDK | 5 | 3 | 5 | 3 | 16 | Responsiveness down 1 |
| 3 | Hermes Agent | 5 | 3 | 5 | 3 | 16 | = |
| 4 | Inspect AI (UK AISI) | 5 | 4 | 5 | 2 | 16 | **New** |
| 5 | DeepEval | 5 | 3 | 5 | 2 | 15 | Responsiveness up 1 |
| 6 | LlamaIndex | 5 | 2 | 4 | 3 | 14 | Responsiveness down 3 |
| 7 | OpenEMR | 3 | 3 | 4 | 3 | 13 | Responsiveness down 1 |
| 8 | crewAI | 4 | 4 | 4 | 1 | 13 | **New** |
| 9 | smolagents | 4 | 3 | 4 | 2 | 13 | **New** |

Removed this rebuild: Haystack and MCP Python SDK. See "Considered and excluded" at the bottom.

---

## 1. Arize Phoenix
- **Link:** https://github.com/Arize-ai/phoenix
- **What it does:** An open-source platform for LLM tracing and evaluation. It covers OpenTelemetry/OpenInference traces, LLM-as-judge evaluators, datasets, experiments and cost tracking.
- **Why Arjun fits:** Evaluation harnesses and ground-truth datasets are his core strength, and the cost-tracking and MCP docs touch his daily tools. The built-in price table even carries TypeSafe JEV decision-model prices.
- **Activity (30 days):**
  - 391 commits and 410 merged PRs.
  - 12 distinct outside authors in the first 100 merges.
  - 29 labelled unassigned issues. A maintainer still publishes a "Weekly docs gap audit" issue every week (#16988, #17092, #17326, #18040).
- **Responsiveness caveat:** docs-audit items now draw outside PRs within days. For example, #17172 fixed item 3 of #16988 nine days after the audit appeared, and #18051 covers #18040.
- **Contribution rules (CONTRIBUTING.md, checked 2026-11-23):**
  - "Not actively accepting feature contributions." Small bug, reliability and maintenance fixes are welcome.
  - **An open issue is not an invitation:** wait for explicit maintainer confirmation before starting.
  - Keep PRs small, explain exactly what changed and why, and don't mix unrelated fixes.
  - A CLA is required.
  - Python tests now run with uv instead of tox (#17409). Code standards live in AGENTS.md (#17860).
- **PR template (changed on 2026-10-29, #17367):** `resolves #N`, then **What**, **Try it**, and **How this PR was made**. The last section is for agent-written PRs and lists Agent, Steering, Abandoned, Verified and "Look hardest at".
- **AI policy:** No ban. The PR template asks agent-assisted PRs to disclose the tool and model, steering, what was verified, and the riskiest hunks. The Claude Code Review workflow was removed on 2026-11-05 (#17681).

## 2. Model Context Protocol C# SDK
- **Link:** https://github.com/modelcontextprotocol/csharp-sdk
- **What it does:** The official .NET SDK for MCP clients and servers.
- **Why Arjun fits:** It combines .NET/C# with MCP tool layers, a rare match for both his developer background and his AI integration work.
- **Activity (30 days):**
  - 26 commits; the last one landed on 2026-11-06.
  - 32 merged PRs from 8 distinct outside authors.
  - 15 labelled unassigned issues.
- **Responsiveness caveat:** several "ready for work" issues have outside PRs that have stayed open for months, for example #1834 (opened Aug) and #1788 (opened Aug). So responsiveness is 3, not 4.
- **Contribution rules:**
  - Community PRs are welcome. Issues labelled `help wanted` + `ready for work` need no assignment.
  - Tests use xUnit with the `LoggedTest` patterns.
  - Requires .NET 10 SDK and Node 22 for integration tests.
- **AI policy:** The MCP org-wide AI_POLICY.md welcomes AI tools. AI assistance **must be disclosed** in the PR or issue, with its extent. The contributor must understand the change and provide evidence such as tests.

## 3. Hermes Agent
- **Link:** https://github.com/NousResearch/hermes-agent
- **What it does:** Nous Research's open agent framework, with skills, plugins, memory providers and a desktop app.
- **Why Arjun fits:** He is Hermes Agent certified, and the skills ecosystem matches his multi-agent workflow work.
- **Activity (30 days):**
  - Extremely high volume: about 4,181 merged PRs, many of them maintainer "salvages" of contributor PRs.
  - 65 distinct outside authors in the first 100 merges.
  - 287 labelled unassigned issues, most of them `type/docs`.
- **Contribution rules:**
  - Long CONTRIBUTING.md. Search open and merged PRs for duplicates first.
  - One logical change per PR, and `python scripts/check` must pass.
  - Skills credit the human contributor first in `author`.
  - There is a strict dependency supply-chain policy.
- **AI policy:** No restriction. AGENTS.md is a "development guide for AI coding assistants".

## 4. Inspect AI (new)
- **Link:** https://github.com/UKGovernmentBEIS/inspect_ai
- **What it does:** The UK AI Security Institute's framework for LLM and agent evaluations: datasets, solvers, scorers, sandboxes and model providers.
- **Why Arjun fits:** This is agent evaluation at its most credible: ground-truth datasets, scorers, and evaluation harnesses run against real model providers. It sits squarely in his strongest area.
- **Activity (30 days):**
  - 403 commits and 401 merged PRs.
  - 13 distinct outside authors in the first 100 merges.
  - 4 labelled unassigned issues (`good first issue` + `accepted`).
- **Contribution rules:**
  - **Issue-first.** Outside PRs must link an issue a maintainer has labelled `accepted`; others are closed automatically.
  - Exception: trivial docs fixes under 25 lines are always welcome.
  - Comment to claim an accepted issue. Duplicates are closed in favour of the earlier PR.
  - Issues labelled `deferred` auto-close PRs.
  - Gated slow and live-provider tests must be run locally and reported when touching providers, sandboxes, agents or async code.
- **AI policy:** "AI-assisted contributions are welcome." You must be able to explain and defend every line, and note the tooling in the PR description. Run AI review passes (preferably with a frontier model) and summarise their findings in the PR (`Agent review` format in AGENTS.md).
- **Effort caveat:** every current good-first-issue already has at least one outside PR. Opening a well-evidenced issue first is the realistic route.

## 5. DeepEval
- **Link:** https://github.com/confident-ai/deepeval
- **What it does:** A pytest-style LLM evaluation framework with RAG, agent and citation-faithfulness metrics.
- **Why Arjun fits:** Agent and RAG evaluation, including the three-way scoring he already runs: citation presence, evidence support and correctness.
- **Activity (30 days):**
  - 162 commits and 38 merged PRs.
  - **16 distinct outside authors**, up from about 2 last month, so the "borderline" flag is lifted.
  - 3 labelled unassigned issues.
- **Contribution rules:**
  - CONTRIBUTING.md is short: fork, branch, and optionally run `black`.
  - CI failures on forks are expected.
- **AI policy:** None published.

## 6. LlamaIndex
- **Link:** https://github.com/run-llama/llama_index
- **What it does:** A RAG and agent data framework covering indexing, retrieval, query engines and evaluation modules.
- **Why Arjun fits:** RAG in production, retrieval scoping and the evaluation module (faithfulness, pairwise and correctness evaluators).
- **Activity (30 days):**
  - **Sharp slowdown:** only 9 commits and 9 merged PRs, with the last commit on 2026-11-13.
  - 4 distinct outside authors.
  - 15 labelled unassigned issues.
- **Contribution rules:**
  - Per-package development under `llama-index-integrations/...` and `llama-index-core`.
  - Duplicate PRs are auto-closed, and a bot closes stale issues.
- **AI policy:** "We welcome AI-assisted contributions." Be transparent about where AI was used and how the output was verified. Keep changes small.
- **Watch:** if activity stays this low at the next rebuild, drop it.

## 7. OpenEMR
- **Link:** https://github.com/openemr/openemr
- **What it does:** An open-source EHR and practice-management system with FHIR and REST APIs.
- **Why Arjun fits:** Healthcare domain knowledge and REST/system-integration work. The catch is that the codebase is PHP.
- **Activity (30 days):**
  - 461 commits and 481 merged PRs.
  - Only 4 distinct outside authors in the first 100 merges.
  - 22 labelled unassigned issues.
- **Contribution rules:**
  - Discuss features first on the forum or an issue.
  - Conventional Commit titles.
  - A maintainer must approve CI for first-time contributors.
  - REST API test coverage is tracked in #12343, one resource per PR.
- **AI policy:** Welcomed. Add an `Assisted-By:` or `Generated-By:` commit trailer. On 2026-11-20 (#15433) the trailer rules were extended to other docs.

## 8. crewAI (new)
- **Link:** https://github.com/crewAIInc/crewAI
- **What it does:** A multi-agent orchestration framework built from crews, flows, tools and guardrails.
- **Why Arjun fits:** Multi-agent workflows with structured handoffs and human-in-the-loop review. Several open issues are about TypeSafe JEV decision tools, a tool he lists.
- **Activity (30 days):**
  - 210 commits and 215 merged PRs.
  - 26 distinct outside authors.
  - 13 labelled unassigned issues.
- **Contribution rules:**
  - uv workspace with pre-commit hooks.
  - Issues carry `difficulty:` labels.
- **AI policy:** Allowed, but **PRs or issues authored with an AI assistant must carry the `llm-generated` label**. Unlabelled AI contributions may be closed without review.
- **Effort caveat (score 1):** good-first-issues are heavily swarmed. For example, #8002 (a docs fix) has 8 PRs, 6 of them still open, and #8066 (the JEV tool) has 3 open PRs. Only worth it for a fresh, self-reported issue.

## 9. smolagents (new)
- **Link:** https://github.com/huggingface/smolagents
- **What it does:** Hugging Face's minimal agent library (code agents and tool-calling agents).
- **Why Arjun fits:** Agent reliability and tool layers, in a small codebase he could explain end to end.
- **Activity (30 days):**
  - 17 commits and 17 merged PRs.
  - 7 distinct outside authors.
  - 6 labelled unassigned issues.
- **Contribution rules:**
  - **A validated issue must be assigned to you before you open a PR**, and this applies to docs fixes too.
  - Until your first merge, you may have only one assigned issue and one open PR.
  - Report real problems with a use case; the PR template asks for one.
  - Core ships primitives, not integrations.
- **AI policy:** "Using an agent to contribute to it is entirely legitimate and welcome." You must have read the change, run the tests, and be able to explain it and answer review.

---

## Considered and excluded (2026-11-23)

| Project | Reason |
|---|---|
| deepset-ai/haystack | **Removed.** Still active (251 commits, 23 outside authors), but 0 open unassigned issues under good first issue, help wanted, documentation or "Contributions wanted!". It fails the label criterion, so it moves to the watchlist. Its AI policy is unchanged (a disclaimer is needed if a PR is fully AI-generated). |
| modelcontextprotocol/python-sdk | **Removed.** Only 9 commits (last on 2026-11-05) and 4 merged PRs in 30 days, none from outside contributors. Its policy also asks people with agents filing PRs autonomously to turn them off. That is compatible with our human-submits model, but worth knowing. |
| github/spec-kit | Very active (221 commits, 19 outside authors), but 0 labelled issues again. Still on the watchlist. Disclosure there is strict. |
| modelcontextprotocol/go-sdk | Active (54 commits, 22 outside authors) but 0 labelled issues. |
| modelcontextprotocol/typescript-sdk | 8 commits and 1 outside author in 30 days. |
| PrefectHQ/fastmcp | 3 outside authors out of 420 merges. PRs need a linked issue plus assignment or `prs welcome`, and claim-only comments are discouraged. |
| comet-ml/opik | Active and AI-friendly (disclosure block in the PR template), but 0 labelled issues. |
| HKUDS/LightRAG | Active, with 19 outside authors, but 0 labelled issues. It has no clear AI policy (none found in CONTRIBUTING). |
| pydantic/pydantic-ai | Issues need a maintainer-agreed plan and assignment before any PR, and outside PRs are not triaged otherwise. Not measured further. |
| mealie-recipes/mealie (food) | Good recipe and bill-of-materials fit, but 0 labelled issues and only 4 outside authors. It has an LLM writing-style rule (Simplified Technical English). |
| opf/openproject, makeplane/plane (PM) | Active, but 0 labelled unassigned issues. |
| explodinggradients/ragas | 12 commits in 30 days. Search metrics failed under rate limits, so it is unmeasured. Re-check next time. |
| microsoft/graphrag, chroma-core/chroma | 1 commit each in 30 days. |
| neuml/txtai, medplum/medplum | No CONTRIBUTING file at the repo root. |
| open-aviation/openap, EleutherAI/lm-evaluation-harness | No commits found since 2026-10-24. |
| modelcontextprotocol/inspector | v2 is built by maintainers through a prompt-driven workflow. Not assessed as an outside-contribution target. |
| casact/chainladder-python (insurance) | Unchanged from last month: its governance requires that contributions be "initiated by a human" and that PRs "declare you are human". Skipped under hard rule 7. |
| modelcontextprotocol/servers | Accepts issues, not pull requests. |

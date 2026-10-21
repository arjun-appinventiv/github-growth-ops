# Portfolio roadmap

Last updated: 2026-10-21

Track 2 (Portfolio Repo Builder) maintains this file. Each milestone is sized
to roughly one routine run and ends in one reviewable pull request.

**Created** means the repo exists in Arjun's account *and* is attached to the
routine. The routine never creates repos; Arjun creates and attaches them.

Build priority: agent-eval-kit and pm-agent-toolkit first, then rotate.

Every repo needs, by its first public release (v0.1.0): a README (problem,
why it matters, how it works, how to run it, example with output), an MIT
licence, tests run by a GitHub Actions workflow, synthetic data only, a short
Mermaid architecture diagram, and a CHANGELOG.

## Status

| # | Repo | Created | Milestones done | Open claude/ PR |
|---|---|---|---|---|
| 1 | agent-eval-kit (flagship) | No | 0 / 6 | – |
| 2 | agent-workflow-composer | No | 0 / 5 | – |
| 3 | mcp-airline-ops | No | 0 / 5 | – |
| 4 | mcp-qsr-ops | No | 0 / 5 | – |
| 5 | pm-agent-toolkit | No | 0 / 6 | – |
| 6 | demand-forecasting-reference | No | 0 / 5 | – |
| 7 | voice-verification-agent | No | 0 / 5 | – |

Status key for milestones: `[ ]` not started, `[~]` open PR, `[x]` merged.

---

## 1. agent-eval-kit

An evaluation harness for AI agents. Scores citation presence, evidence
support and answer correctness as three separate measures, and evaluates full
multi-step workflows rather than single steps.

- [ ] **M1 Skeleton and ground truth format.** Python package layout, typed
  data models for a ground-truth case (question, expected answer, gold
  evidence ids), a loader for a JSONL set, a small synthetic set, pytest,
  CI workflow, MIT licence, CHANGELOG.
- [ ] **M2 Three separate scorers.** Citation presence, evidence support
  (cited ids overlap gold evidence) and answer correctness (exact/normalised
  match first, pluggable judge later). Each returns its own score and reason;
  no blended single number.
- [ ] **M3 Multi-step workflow runs.** Trace format for a run with several
  steps; score each step and the end-to-end outcome; show where in the chain
  a failure first appears.
- [ ] **M4 Pluggable LLM-as-judge.** Judge interface with a deterministic
  stub for tests and an optional Claude-backed judge; judge prompts kept as
  versioned files.
- [ ] **M5 Reports.** CLI that runs a suite and writes a Markdown and JSON
  report with per-measure scores and failing cases.
- [ ] **M6 v0.1.0 release.** README with worked example and output, Mermaid
  architecture diagram, regression-gate example in CI.

## 2. agent-workflow-composer

Compose agents into reusable workflows. Each agent has its own retrieval
scope, permitted tools and structured output, with fixed contracts between
steps.

- [ ] **M1 Step contracts.** Typed step definition (inputs, output schema,
  permitted tools, retrieval scope), schema validation between steps, tests, CI.
- [ ] **M2 Workflow runner.** Sequential runner with a fake model so runs are
  deterministic in tests; clear error when a step breaks its contract.
- [ ] **M3 Scoped retrieval.** Per-step document scope over a small synthetic
  corpus; tests that a step cannot read outside its scope.
- [ ] **M4 Tool permissions and human review hook.** Deny-by-default tool
  allowlist per step; optional approval gate before a chosen step.
- [ ] **M5 v0.1.0 release.** YAML workflow definitions, example workflow,
  README, Mermaid diagram, CHANGELOG.

## 3. mcp-airline-ops

An MCP server over synthetic airline crew data: rostering, flight time
limitation checks and crew currency.

- [ ] **M1 Synthetic data and models.** Generator for crew, pairings and
  duty periods; typed models; tests; CI.
- [ ] **M2 Roster tools.** MCP server with read-only tools: crew roster for a
  date range, who is available for a pairing.
- [ ] **M3 Flight time limitation checks.** Rule engine with clearly stated,
  simplified illustrative limits (not a regulator's actual rule set); tool
  that explains which limit a proposed assignment would breach.
- [ ] **M4 Crew currency.** Recency and training-expiry checks; tool listing
  crew who lapse within N days.
- [ ] **M5 v0.1.0 release.** README with example MCP session, Mermaid
  diagram, CHANGELOG, client config example.

## 4. mcp-qsr-ops

An MCP server over synthetic restaurant data: POS transactions, inventory,
recipes and bill of materials.

- [ ] **M1 Synthetic data and models.** Generator for outlets, menu items,
  recipes/BOM, POS transactions and stock; typed models; tests; CI.
- [ ] **M2 POS tools.** Sales by outlet, item and daypart.
- [ ] **M3 BOM and theoretical usage.** Explode sales through recipes into
  ingredient usage; compare with stock movement to show variance.
- [ ] **M4 Inventory tools.** Stock on hand, days of cover, reorder
  suggestions.
- [ ] **M5 v0.1.0 release.** README with example session, Mermaid diagram,
  CHANGELOG.

## 5. pm-agent-toolkit

Claude Code skills and Hermes skills for project managers.

- [ ] **M1 Earned value calculator.** Typed Python library and CLI for PV,
  EV, AC, SV, CV, SPI, CPI, EAC, ETC, VAC, TCPI with tests against worked
  examples; CI; licence; CHANGELOG.
- [ ] **M2 RAID log skill.** Claude Code skill plus a structured RAID log
  format (Markdown/CSV) and a validator for required fields.
- [ ] **M3 Status report skill.** Build a weekly status report from a
  synthetic issue-tracker export; deterministic summariser tested on fixtures.
- [ ] **M4 Charter drafting skill.** Template-driven charter skill with a
  checklist of required sections.
- [ ] **M5 Hermes skill variants.** Package the same skills for Hermes Agent,
  sharing the core Python logic.
- [ ] **M6 v0.1.0 release.** README with an example for each skill, Mermaid
  diagram.

## 6. demand-forecasting-reference

Demand and no-show forecasting on a synthetic dataset, with a clear write-up
of approach and limits.

- [ ] **M1 Synthetic dataset.** Seeded generator with weekly seasonality,
  holidays and promotions, plus a booking table with no-show labels; data
  card; tests; CI.
- [ ] **M2 Baselines.** Naive and seasonal-naive forecasts with a backtest
  harness (rolling origin) and MAE/MAPE/WAPE.
- [ ] **M3 Demand model.** Gradient-boosted model with calendar features;
  compared honestly against baselines.
- [ ] **M4 No-show model.** Classifier with calibration check and a
  cost-based overbooking example.
- [ ] **M5 Write-up and release.** Approach, results, limits and what would
  change with real data; Mermaid pipeline diagram; CHANGELOG.

## 7. voice-verification-agent

A voice agent pattern with human review placed at the irreversible step.

- [ ] **M1 State machine.** Typed conversation states for a synthetic
  verification flow; text-only simulation; tests; CI.
- [ ] **M2 Irreversible-step gate.** Human review queue that must approve
  before the irreversible action; tests that the action cannot run without it.
- [ ] **M3 Audit trail.** Append-only event log of every decision and who
  made it.
- [ ] **M4 Voice adapter.** Optional speech-to-text / text-to-speech adapter
  behind an interface, with a fake for tests.
- [ ] **M5 v0.1.0 release.** README with transcript example, Mermaid sequence
  diagram, CHANGELOG.

---

## Run log

- **2026-10-21:** Roadmap created. No portfolio repos are attached to the
  routine yet, so no milestone was built. Next step for Arjun: create
  `agent-eval-kit` (or `pm-agent-toolkit`) and attach it to the routine.

## YOUR TASK: PORTFOLIO REPO BUILDER

Repos for this task: github-growth-ops, plus each portfolio repo below that
exists in Arjun's account (check with "user:arjun-appinventiv"). Only attach
the one you will work on this run.

You are building Arjun's own public portfolio repos, one meaningful,
tested increment per run.

### Part A: Maintain the roadmap (roadmap.md)

If roadmap.md has no repo list yet, create it from these planned repos:

1. agent-eval-kit: an evaluation harness for AI agents. Ground truth sets,
   scoring citation presence, evidence support and answer correctness
   separately, and testing full multi-step workflows rather than single steps.
   This is the flagship repo.
2. agent-workflow-composer: compose agents into reusable workflows, each
   agent with its own retrieval scope, permitted tools and structured output,
   with fixed contracts between steps.
3. mcp-airline-ops: an MCP server over synthetic airline crew data:
   rostering, flight time limitation checks, crew currency.
4. mcp-qsr-ops: an MCP server over synthetic restaurant data: POS
   transactions, inventory, recipes and bill of materials.
5. pm-agent-toolkit: Claude Code skills and Hermes skills for project
   managers: RAID log updates, status reports from issue trackers, an
   earned value calculator, charter drafting.
6. demand-forecasting-reference: demand and no-show forecasting on a
   synthetic dataset, with a clear write-up of approach and limits.
7. voice-verification-agent: a voice agent pattern with human review placed
   at the irreversible step.

Break each repo into milestones of roughly one run each. Mark which repos
Arjun has created so far. Only work on repos that already exist. Never create
a repo yourself. If none exist yet, only open the roadmap PR and stop.

### Part B: Build the next milestone

Each run, pick the next unfinished milestone in one existing repo. Rotate
across repos rather than finishing one completely, but prioritise
agent-eval-kit and pm-agent-toolkit. Skip a repo that already has an open
claude/ pull request from an earlier run; build on merged work only.

Every repo must have, by its first public release:
- A README covering the problem, why it matters, how it works, how to run it,
  and an example with output
- A licence (MIT unless Arjun has said otherwise)
- Tests, and a GitHub Actions workflow that runs them
- Synthetic example data only
- A short architecture diagram in Mermaid
- A CHANGELOG

Keep code clean, typed where the language supports it, and commented where
the reasoning is not obvious. Arjun must be able to explain every design choice.

### Part C: Report for approval

Open a pull request into the portfolio repo you worked on. The description
must include: what milestone this completes, what changed, how to test it,
test results, and the design decisions made with the reasoning behind each.

Then update roadmap.md in github-growth-ops to reflect progress, and open a
small pull request there too.

Do not merge either pull request.

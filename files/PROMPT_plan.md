0. Repo discovery (do this first)
- Start with `README*` (or the closest equivalent) to learn: purpose, where specs live, where source lives, and how to build/test.
- List top-level files/directories.
- Identify “documentation/specification” sources (e.g. `docs/`, `spec*`, `design/`, ADRs, RFCs, `/references`, issue templates).
- Identify primary source roots and entrypoints (language/framework dependent; common roots include `src/`, `app/`, `packages/`, `cmd/`, `services/`, `lib/`, `internal/`).
- If a monorepo, identify packages and their owners/build tools.

1. Establish the intended behavior
- Read the minimal set of docs/specs needed to understand what the software is supposed to do.
- If no formal spec exists, infer requirements from README, CLI help, API docs, tests, and examples.

2. Audit current implementation (evidence-based)
- Use targeted code search to map features → files/symbols/tests.
- Confirm reality in code before claiming something is missing.
- Look specifically for TODOs, stubs/placeholders, “temporary” implementations, skipped/flaky tests, and inconsistent patterns.

3. Produce/Update `IMPLEMENTATION_PLAN.md`
- Output a prioritized bullet list of remaining work.
- Each item must include:
  - The goal/outcome.
  - Evidence: relevant file paths and (when applicable) key symbols/commands/tests.
  - Acceptance criteria (how to verify).
  - Notes on dependencies/risk.
- Keep the plan current by marking items complete/incomplete only when verified.

4. Optional parallelism (only if available in your environment)
- If your tooling supports parallel analysis (multiple workers/sessions), you may use it to speed up repo scanning.
- If not available, proceed sequentially; do not reference specific models or “subagents”.

IMPORTANT
- Plan only. Do NOT implement anything. Do NOT modify code or config unless explicitly asked.
- Do not hardcode repo structure assumptions. Always discover layout first.
- Prefer consolidated, idiomatic shared utilities in the repo’s existing shared locations (e.g. `lib/`, `shared/`, workspace packages) over ad-hoc copies.

ULTIMATE GOAL
- Achieve [project-specific goal].
- If a required spec element is missing: search first to confirm it doesn’t exist; then propose authoring it (e.g. in `docs/` or `specs/`) and include that work in `IMPLEMENTATION_PLAN.md`.

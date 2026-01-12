0. Repo discovery (do this first)
- Start with `README*` (or the closest equivalent) to learn: purpose, where specs live, where source lives, and how to build/test.
- List top-level files/directories.
- Identify documentation/spec sources (e.g. `docs/`, `spec*`, ADRs/RFCs, `/references`).
- Identify primary source roots and how to run build/tests (check `package.json`, `pyproject.toml`, `go.mod`, `Cargo.toml`, `Makefile`, CI configs).
- If a monorepo, identify packages and their build/test commands.

1. Execution loop (implement one high-impact item)
- Read `IMPLEMENTATION_PLAN.md` (if present) and pick the highest-priority incomplete item.
- Before changing code, confirm current behavior via targeted search and/or the smallest relevant test/run.
- Implement the change completely (avoid placeholders/stubs).

2. Testing discipline
- Run the narrowest relevant tests first (unit/package level), then broaden only if needed.
- If unrelated tests fail, do not silently “fix everything”; document them in `IMPLEMENTATION_PLAN.md` unless they block your change.

3. Keep `IMPLEMENTATION_PLAN.md` current
- When you discover a new issue or dependency, add it to `IMPLEMENTATION_PLAN.md` with evidence (paths/symbols) and acceptance criteria.
- When you finish an item, mark it complete with the verification you ran (exact command or test).

4. Logging/debugging
- Add temporary logging only when needed; remove it before finishing unless it’s clearly valuable and low-noise.

5. Source of truth
- Prefer the repo’s established shared utilities/shared packages over ad-hoc copies.
- Avoid migrations/adapters unless the repo already standardizes on them.

IMPORTANT
- Do not hardcode repo structure assumptions; always discover layout first.
- Do not reference specific models (“Sonnet/Opus”) or “subagents”. Use parallelism only if your environment supports it.
- Do not `git commit`, `git push`, or create tags unless explicitly instructed by the user.

Documentation note
- When updating docs, capture the “why” and how to run/verify.
- Keep `AGENTS.md` operational (commands, setup). Keep progress/status in `IMPLEMENTATION_PLAN.md`.

# Everdream Studio — Repository AI and CI Policy

**Scope:** This repository. Apply alongside any existing project documentation, licensing, release, security, and test requirements. Direct user instructions and stronger project-specific safety rules prevail. This guidance changes **how work is planned**, not application behavior.

## Shared development policy — owner preference 2026-11-11

Prioritize completing the agreed core product and usable end-to-end journeys. Tie each work batch to an existing feature, acceptance criterion or confirmed blocker. Testing supports delivery; repeated small checks, speculative hardening and expanding test infrastructure must not displace the commissioned work.

### Delivery and proportionate verification

- Batch related implementation and regression fixes into coherent, reviewable changes. Avoid per-file pushes and unnecessary micro-PRs. Complete the current milestone before unrelated cleanup or hypothetical edge cases.
- During development, run the smallest meaningful checks covering changed behavior and affected boundaries. Add tests for substantive behavior, confirmed regressions and material risks; avoid tests that merely mirror implementation, duplicate coverage or validate trivial reversible edits.
- Run broader affected suites when a coherent batch is ready for review. Complete required integration and acceptance checks at the applicable merge, release or product milestone. Documentation-only and low-impact presentation changes normally need inspection and relevant lightweight validation, subject to required checks.
- Preserve mandatory security, authorization, data integrity, migration, backup, recovery and lifecycle verification. Do not weaken assertions or substitute mocks for required real-service evidence.
- Once required checks pass and review findings are resolved, proceed toward integration and the next milestone. Additional verification needs a concrete change, risk or unresolved question.

### Evidence reuse and bounded debugging

- Before a costly check, identify what changed, what uncertainty the run resolves and whether existing evidence already answers it. Check for equivalent queued, running or completed CI before dispatching another run.
- Reuse passing evidence when relevant code, dependencies, configuration and environment are unchanged and the evidence remains applicable. Record its revision and limits; never present an older result as a run on a newer commit. Preserve required checks on the actual merge or release revision and all branch-protection requirements.
- Rerun for relevant changes, invalidated assumptions, an investigated failure or a required final-candidate gate, rather than reassurance alone.
- After two attempts at the same failure without meaningful new evidence, reassess before another equivalent run. Prefer a focused reproduction or existing logs over repeating a full build, VM or end-to-end test. State the supported hypothesis, relevant correction and expected distinguishing result before the next costly attempt. This rule changes the investigation; it does not abandon required verification.
- Add diagnostics only to resolve a named uncertainty. Continue independent authorized product work around genuine blockers while keeping incomplete acceptance criteria explicit.
- Report the feature or journey now working, its verification and remaining gaps. Test counts, green checks, commits, lines changed and elapsed time are not product completion. Keep evidence and handoff records concise; avoid repetitive status narration and duplicate documents.

### Shared GitHub Actions efficiency

- Optimize for **thorough, meaningful verification per runner minute**, not for consuming an allowance. Verify the current shared allowance, runner billing multipliers, applicable organization and budget; do not treat a historical allowance as a current balance or permission to incur overages. Keep changing budget observations in the handoff or findings rather than this policy.
- **Avoid unnecessary paid overages.** Never raise budgets, enable new billable products, add billable seats, purchase larger runners, or change spending limits without express owner approval. A repository file does **not** enforce billing caps; those are controlled in GitHub's enterprise/organization billing settings.
- When several changes are pushed rapidly, prefer **one current PR verification**: use appropriately scoped `concurrency` to cancel obsolete *pull-request* runs, but do **not** cancel release/deployment or important default-branch jobs.
- Avoid duplicate builds for one commit triggered by both `push` and `pull_request`. Generally use PR verification for development branches and push verification for the default branch; retain `workflow_dispatch` for intentional full runs. Treat reusable `workflow_call` jobs separately: their concurrency must not cancel parallel caller jobs.
- Inspect standalone and reusable umbrella suites for equivalent work. Remove duplication only after preserving required status contexts and full affected acceptance coverage. Never cancel another worker's run or default-branch/release verification.
- Use **Linux runners** for portable builds; keep Windows/macOS where actual native behavior requires them. Never downgrade required OS coverage just to save minutes. Use dependency caches with lockfile-aware keys and bounded artifact retention, never cache credentials or mutable production state.
- Use a **fast relevant PR gate**, comprehensive checks when affected (and before merge), and release/cross-service/cross-platform acceptance at appropriate milestones. Path filters must not silently skip required checks or hide dangerous cross-module effects. Don't remove failures, weaken tests, disable security gates or mark unrun tests as passing.
- Before workflow changes, inspect actual triggers/calls, concurrency, build/test commands, deployment environments, required checks, runner costs, dependencies, caching and recent run evidence. Record observed waste. Prefer minimal, reviewable workflow PRs with validation, rollback and status-check implications; obtain approval before disruptive changes beyond the authorized task.
- For documentation-only changes, avoid unnecessary expensive builds where existing repository policy and required checks permit. Do not rely on `[skip ci]` where a required check would stay pending.

## Agent operating expectations

- Inspect affected products and their native entrypoints. Do not assume a repository is Java, Node, desktop or server-only based on the parent organization.
- Do not edit production deployment targets, billing/account settings, secrets, authorization, evidence history, user/world data, or persistent service state as a byproduct of CI optimization.
- Prefer a task branch and PR for behavioral/workflow changes. Do not force-push or silently rewrite unrelated work. Keep original tests and fixtures.
- In completion reports distinguish `SOURCE_REVIEWED`, `CI_CONFIG_CHANGED`, `CI_RUN_PASSED`, `RUNTIME_ACCEPTED`, and `NOT_RUN`. Include Git SHA, exact workflow/run link, platform, and remaining gaps.
- Keep these instructions accessible to future GitHub/Codex/ChatGPT workers. **This file is repository guidance, not a modification to account-level ChatGPT Memory or a substitute for GitHub billing hard stops.**
- For documentation/context-only tasks: inspect, document/reconcile, then stop. Do not repair product or CI code, deploy, merge unrelated feature PRs, change billing or touch live data unless separately authorized.

## Project scope

Read this repository's README and project-specific guidance before changes. This policy does not invent a roadmap, resume paused work or authorize releases, deployments or live-data changes.

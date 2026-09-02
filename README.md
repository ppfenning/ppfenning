# Patrick Pfenning

**Data platform engineer** — seven years building cloud-native data and ML
platforms in Python, Spark, and Terraform, and lately the governance layer
that lets LLM agents do real engineering work without anyone having to trust
them blindly.

## The agent substrate

Two repos, one thesis: **agents should earn autonomy the way engineers do —
by track record, in writing, revocably.**

[**agent-cartridges**](https://github.com/ppfenning/agent-cartridges) ·
[**agent-graphs**](https://github.com/ppfenning/agent-graphs) ·
[the architecture, drawn](https://claude.ai/code/artifact/bbb368b7-c6cb-46d0-b0b7-f580fb5fc769)

- A **graph** owns sequence and writes nothing; one **harness** owns every
  consequence — the gate, the worktree, the checks, the append-only ledger. A
  new graph inherits all of it by existing rather than by remembering to.
- **Autonomy is earned per kind of write** against the ledger, scoped to one
  cartridge hash and one provider profile — and an auto-applied write records
  no ledger row, so nothing can ratchet up its own trust. Demotion comes from
  measured signals, never model opinion.
- A **swarm driver** takes an initiative from idea to a stack of draft PRs —
  phases in dependency order, tasks fanned out in parallel worktrees — with
  **no code path that merges to main**. The irreversible act is priced by
  target, not by operation.
- **Portability is enforced by a test**, not by intention: it fails the build
  on any employer-shaped constant, and it was verified by planting a
  deliberately-bad graph and watching nine checks fire. A check nobody has
  watched fail is not a check.
- The whole suite — 366 tests across both repos — runs offline, with no
  network and no API key, against a scripted runner. Clean-room provenance is
  [documented, dated, and public](https://github.com/ppfenning/agent-cartridges/blob/main/docs/PROVENANCE.md).

## Before that

Three years at BlastPoint (2023–2026) owning a customer-intelligence data
platform end to end: a bronze/silver/gold lakehouse across 40+ client AWS
accounts, the SageMaker inference layer the data science team's models ran
on, the Terraform behind the fleet, and incident response when production ML
broke. Led the pandas→Spark migration and trained the team through it; put
LLM agents into the on-call loop for first-pass triage and PR review because
the alert volume justified it.

**Stack:** Python · SQL · PySpark · AWS (S3, Batch, Step Functions,
SageMaker, Athena) · Terraform (multi-account via AFT) · Airflow ·
Docker · PostgreSQL · Snowflake · GitHub Actions

## Elsewhere

- [Chaotic Neural Networks for Asymmetric Encryption of Audio Files](https://github.com/ppfenning/Chaotic-Neural-Networks-for-Asymmetric-Encryption-of-Audio-Files) — graduate research, MS Data Science
- BS Applied Mathematics ('17) · MS Data Science ('23) — Wentworth Institute of Technology

Off the clock: the Vermont outdoors, a Proxmox homelab, and a Neovim config
tuned well past the point of diminishing returns.

[LinkedIn](https://www.linkedin.com/in/patrick-pfenning) · [pfenningpat@gmail.com](mailto:pfenningpat@gmail.com)

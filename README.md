# Patrick Pfenning

**Data platform engineer** — seven years building cloud-native data and ML
platforms in Python, Spark, and Terraform, and lately the governance layer that
lets LLM agents do real engineering work without anyone having to trust them
blindly.

## Coxswain

*Agents pull the oars. You hold the tiller.*

[**Docs**](https://ppfenning.github.io/coxswain/latest/) ·
[**Install**](https://ppfenning.github.io/coxswain/latest/install/) ·
[**Releases**](https://ppfenning.github.io/coxswain/latest/releases/) ·
[**PyPI**](https://pypi.org/project/coxswain-tools/)

Coxswain builds software with a crew of AI agents and keeps a person on the
tiller. You describe a change; it is filed as a work item, planned, built in a
worktree under a dollar budget, reviewed by two independent reviewers who are
made to disagree, arbitrated, checked against the project's own tests as
evidence, and handed back as a pull request. Every step leaves a record you can
read.

```sh
uv tool install coxswain-tools
cox setup doctor
```

**Status: beta.** The loop runs daily on its own repositories, which is also
how its defects get found.

### Six repositories, one thesis

Agents should earn autonomy the way engineers do — by track record, in writing,
revocably. Each repository is usable alone; together they read as one sentence.

```mermaid
flowchart LR
    UMB["coxswain<br/>the umbrella<br/>docs · manifest · one-line install"]
    CART["coxswain-cartridges<br/>who a run works for<br/>roles → skills · tier → model · where writes land"]
    GRAPHS["coxswain-graphs<br/>what runs, and the harness that runs it<br/>sequence · the gate · the ledger · worktrees"]
    CREW["coxswain-crew<br/>who speaks<br/>named seats · write authority · voices"]
    HUD["coxswain-hud<br/>where you hear and see it<br/>wake word · the regatta · run events"]
    TOOLS["coxswain-tools<br/>the cox command<br/>run records · traces · landing · screens"]
    UMB -- "pins every component" --> CART
    CART -- "roles, tiers" --> GRAPHS
    CREW -- "seats bound by a cartridge's cast: block" --> CART
    GRAPHS -- "run records, usage, ledger" --> HUD
    TOOLS -- "reads and lands" --> GRAPHS
    TOOLS -- "posts" --> HUD
```

[**coxswain**](https://github.com/ppfenning/coxswain) ·
[**coxswain-cartridges**](https://github.com/ppfenning/coxswain-cartridges) ·
[**coxswain-graphs**](https://github.com/ppfenning/coxswain-graphs) ·
[**coxswain-crew**](https://github.com/ppfenning/coxswain-crew) ·
[**coxswain-hud**](https://github.com/ppfenning/coxswain-hud) ·
[**coxswain-tools**](https://github.com/ppfenning/coxswain-tools)

- A **graph** owns sequence and writes nothing; one **harness** owns every
  consequence — the gate, the worktree, the checks, the append-only ledger. A
  new graph inherits all of it by existing rather than by remembering to.
- **Autonomy is earned per kind of write** against the ledger, scoped to one
  cartridge hash and one provider profile — and an auto-applied write records no
  ledger row, so nothing can ratchet up its own trust. Demotion comes from
  measured signals, never model opinion.
- **Every change arrives as a pull request**, rebased onto the target's default
  branch and held until the project's own checks pass. What the harness may do
  on its own is a cartridge policy, not a hard-coded behaviour.
- An **epic driver** takes an initiative from idea to a stack of pull requests —
  phases in dependency order, tasks fanned out in parallel worktrees, each under
  its own budget ceiling.
- **Two runners, one contract.** Nodes run against the Messages API, or as
  headless Claude Code sessions on a subscription with per-role tool grants, a
  disposable scratch tree for the builder, dollar ceilings per tier, and a
  turn-by-turn trace. Every run writes what each node cost.
- **A standing cast of named seats** — recon, triage, review, build, ops, the
  board, writing, the scribe — defined with no employer inside them, and bound
  to a team's skills by a cartridge. Voice is decoration: every seat works typed.
- **Deterministic work is a tool, not a turn.** Summing a run's cost, counting
  what a traced node did, cleaning up after a run, drawing the live table: each
  is a tested function a seat calls, so no tokens are spent producing the same
  answer twice.

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
[**Customize**](https://ppfenning.github.io/coxswain/latest/customize/) ·
[**PyPI**](https://pypi.org/project/coxswain/)

Coxswain builds software with a crew of AI agents and keeps a person on the
tiller. You describe a change; it is filed as a work item, sized (one ticket, or
an epic broken into phases and tasks), planned, built in its own worktree under
a dollar budget, linted and run against the project's own tests before a
reviewer spends a token, reviewed by two independent reviewers who are made to
disagree, arbitrated, validated against measured evidence rather than the
builder's word, and handed back as a pull request. A cartridge's *gate* says
how far the harness may go on its own; the default is `ticket`: it proposes, a
person merges. One chair — a live session, or the `cox chair run` loop when
none is — holds the chair lease, lands finished phases,
and fills free lanes on this machine and on any lane hosts; every run leaves a
record you can read, drill into, and get a notification from.

```sh
brew install ppfenning/coxswain/cox              # or: uv tool install --python 3.14 coxswain
cox install --team my-team                       # one checkout, one venv, this machine's profile, the crew
cox setup doctor                                 # can this machine run an epic, and what is missing
cox route file  --repo R --title T --body FILE   # a work item, from a sentence or a file
cox route launch epic --initiative work/<id>     # plan → build → review ×2 → arbitrate → check → validate
cox runs top                                     # every run in flight, live
cox runs land <run> --repo R --apply             # rebase, PR, merge on green, clean up
```

**Status: beta.** The loop runs daily on its own repository, which is also
how its defects get found — and fixed, by the loop, as pull requests it opens
against itself. Since 2026.10.0 it is one repository and one package,
`coxswain`, with one command, `cox`; releases are CalVer (`YYYY.M.N`), and each
is one tag, one PyPI publish, one GitHub release and one Homebrew formula
update. The [release notes](https://ppfenning.github.io/coxswain/latest/releases/)
say what each version changed.

### One repository, one thesis

Agents should earn autonomy the way engineers do — by track record, in writing,
revocably. Four parts share one checkout, each in its own folder with its own
suite, and the terminal dashboard ships beside them; together they read as one
sentence.

```mermaid
flowchart LR
    subgraph UMB["coxswain — one repository, one package, one version"]
        TOOLS["src/tools<br/>the cox command<br/>install · route · run records · landing · the chair"]
        GRAPHS["src/graphs<br/>what runs, and the harness that runs it<br/>sequence · the gate · the ledger · worktrees"]
        CART["src/cartridges<br/>who a run works for<br/>roles → skills · tier → model · where writes land"]
        CREW["crew<br/>who speaks<br/>named seats · write authority · voices"]
    end
    DASH["coxswain-dash<br/>towpath, the terminal home<br/>the chair · spend · machines · lanes · runs"]
    CART -- "roles, tiers" --> GRAPHS
    CREW -- "seats bound by a cartridge's cast: block" --> CART
    GRAPHS -- "run records, usage, ledger" --> TOOLS
    TOOLS -- "files, launches, lands" --> GRAPHS
    TOOLS -- "cox dash --feed" --> DASH
    DASH -- "every action, as a cox command" --> TOOLS
```

[**coxswain**](https://github.com/ppfenning/coxswain) ·
[**coxswain-dash**](https://github.com/ppfenning/coxswain-dash) ·
[**homebrew-coxswain**](https://github.com/ppfenning/homebrew-coxswain)

- A **graph** owns sequence and writes nothing; one **harness** owns every
  consequence — the gate, the worktree, the checks, the append-only ledger. A
  new graph inherits all of it by existing rather than by remembering to.
- **Autonomy is earned per kind of write** against the ledger, scoped to one
  cartridge hash and one provider profile — and an auto-applied write records no
  ledger row, so nothing can ratchet up its own trust. Demotion comes from
  measured signals, never model opinion.
- **Every change arrives as a pull request**, rebased onto the target's default
  branch and held until the project's own checks pass. How far the harness may
  go on its own is a cartridge policy with four named levels, tighten-only
  through the chain, never a hard-coded behaviour.
- An **epic driver** takes an initiative from idea to a stack of pull requests —
  phases in dependency order, tasks fanned out in parallel worktrees, each under
  its own budget ceiling.
- **Three runners, one contract.** Nodes run against the Messages API, as
  headless Claude Code sessions on a subscription with per-role tool grants, a
  disposable scratch tree for the builder, dollar ceilings per tier, and a
  turn-by-turn trace — or, experimentally, against a local OpenAI-compatible
  endpoint. Every run writes what
  each node cost, a task that fails its budget is split rather than given more
  money, and a weekly spend ceiling stops new launches before the bill does.
- **A standing cast of named seats** — recon, triage, review, build, ops, the
  board, writing, the scribe, the steward, the model steward, the courier —
  defined with no employer inside them, and bound to a team's skills by a
  cartridge. Voice is decoration: every seat works typed.
- **Deterministic work is a tool, not a turn.** Summing a run's cost, counting
  what a traced node did, cleaning up after a run, drawing the live table: each
  is a tested function a seat calls, so no tokens are spent producing the same
  answer twice.

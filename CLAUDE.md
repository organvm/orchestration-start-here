# CLAUDE.md — orchestration-start-here

**ORGAN IV** (Orchestration) · `organvm-iv-taxis/orchestration-start-here`
**Status:** ACTIVE · **Branch:** `main`

## What This Repo Is

Central orchestration hub: registry, governance rules, 5 workflows, 3 Python scripts. The central nervous system of the eight-organ system.

## Stack

**Languages:** TypeScript, Python

## Directory Structure

```
📁 .github/
📁 .meta/
📁 tasks/                # Portals — reality-rectification interventions between competing futures
    <slug>/
        CLAUDE.md        # Portal nature + counter-force field + lifecycle (INJECT→PRECIPITATE→STOP)
        BRIEFING.md      # War report: front line, utopic/dystopic attractors, deliverables
        REFERENCES.md    # Keys to doors + context stream + terrain (what the war is fought over)
        SEQUENCE.md      # Intervention procedure α→ε: inject, create, operate, verify, precipitate
        RECEIPT.md       # Forward deposit (written at completion, consumed by next portal)
📁 action_ledger/
    schemas.py          # Action, Sequence, Chain, Route, ParamAxis, ParamRegistry, ActionOrigin
    ledger.py           # record() atomic, compose_chain(), close_session(), emit_session_closed(), YAML persistence
    emissions.py        # State change emission — self-recording transitions via emit_state_change()
    routes.py           # Patch bay — bidirectional route graph, lineage tracing, provenance
    cycles.py           # Cycle detection — verb sequences, trajectories, intents, stalls
    cli.py              # CLI: record, show (--origin filter), sequence, chain, routes, cycles, params
    __main__.py         # Standalone entry: python -m action_ledger
    data/               # Append-only YAML streams: actions, sequences, param_registry
📁 docs/
    adr
    autonomous-systems-design.md
    coordination-protocols
    flow-patterns
    metasystem-manifest
    seed-schema
    superproject-topology-audit.md
📁 scripts/
    calculate-metrics.py
    organ-audit.py
    validate-deps.py
📁 src/
    agents
    dreamcatcher
  .gitignore
  CHANGELOG.md
  LICENSE
  README.md
  audit-report.md
  governance-rules.json
  registry.json
  renovate.json
  seed.yaml
```

## Key Files

- `README.md` — Project documentation
- `seed.yaml` — ORGANVM orchestration metadata
- `src/` — Main source code
- `contrib_engine/` — Outbound open-source contribution engine (scanner, orchestrator, monitor)
- `docs/superproject-topology-audit.md` — SOP for structural auditing of git superprojects (7+1 steps, proven across 5 agents). Tool: `meta-organvm/tools/superproject_topology_audit.py`

## Contribution Engine (`contrib_engine/`)

The Plague Campaign — systematic open-source contribution engine with income-weighted prioritization.

```bash
python -m contrib_engine scan          # Scan signals for targets (4 sources: contacts, stars, forks, deps)
python -m contrib_engine list          # Show ranked targets
python -m contrib_engine approve <t>   # Initialize cross-organ workspace
python -m contrib_engine status        # Show active contribution states
python -m contrib_engine monitor       # Poll PRs, journal changes, determine next actions
python -m contrib_engine campaign show # Campaign sequencer — next actions, phase summary
python -m contrib_engine outreach show # Outreach tracker — relationship lifecycle
python -m contrib_engine backflow pending # Backflow pipeline — knowledge routing to organs
```

**Core modules:** `scanner.py` (4 signal sources + scoring), `orchestrator.py` (workspace init), `monitor.py` (PR lifecycle + absorption trigger), `capabilities.py` (8 capability definitions), `schemas.py` (40 Pydantic models incl. 8 StrEnum + 1 IntEnum), `github_client.py` (gh CLI wrapper), `cli.py` (dual-mode prefix registration).

**Campaign modules (S32):** `campaign.py` (phase sequencer: UNBLOCK→ENGAGE→CULTIVATE→HARVEST→INJECT), `outreach.py` (relationship scoring, event logging), `backflow.py` (6-organ routing: theory/generative/code/narrative/community/distribution).

**Absorption Protocol (S35):** `absorption.py` (inbound question detection → auto-formalization → backflow deposit). Scans tracked conversations for expansion-worthy questions using 8 heuristics + 6 reduction filters. Runs autonomously inside the monitor cycle. Protocol doc: `docs/absorption-protocol.md`.

**Fieldwork Intelligence (S-fieldwork-mvp):** `fieldwork.py` (process observations from contribution workflows). Layer 1 of 4-layer system. Records observations with 10 categories, 5-level spectrum (AVOID to ABSORB as IntEnum), 6 strategic tags, 6 sources. CLI: `fieldwork record` + `fieldwork show`. Spec: `docs/superpowers/specs/2026-03-30-fieldwork-intelligence-system-design.md`.

```bash
python -m contrib_engine fieldwork record --workspace WS --category CAT --signal "..." --spectrum N --source SRC
python -m contrib_engine fieldwork show [--workspace WS] [--category CAT] [--min-spectrum N]
```

**Data files** (committed, living state): `data/campaign.yaml` (15 actions, income-weighted), `data/outreach.yaml` (10 relationships), `data/backflow.yaml` (13 deposited items), `data/absorption.yaml` (4 detected + formalized), `data/tracked_conversations.yaml` (conversation URLs for absorption scanning), `data/ranked_targets.yaml` (scanner output), `data/fieldwork.yaml` (observation stream, append-only, created on first write).

**Artifacts:** `artifacts/dbt-mcp-patterns-absorption.md` (5 architectural patterns absorbed from dbt-mcp contribution). 4 render scripts in `artifacts/` (canvas, post001, post002, post002-audit) — standalone, no CLI integration (IRF-OSS-029).

**Testament:** 13 articles of codified writing rules formalized into logic/algorithms/math at `docs/testament-formalization.md`. Constitutional authority — governs all written output.

**Tests:** 240 passing, 0 failures.

## Action Ledger (`action_ledger/`)

System-wide process recording infrastructure — the synthesizer paradigm applied to ideas. Records semantic actions as they move through parameter space, composes them into sequences and chains, detects repeated cycles across sessions.

```bash
python -m action_ledger record --session S42 --verb explored --target fieldwork \
  --context "understanding Layer 1 MVP" --param abstraction=0.7 --param maturity=0.3
python -m action_ledger show [--session S42] [--verb explored] [--origin emitted] [--routes]
python -m action_ledger sequence show [--session S42]
python -m action_ledger sequence close --session S42 [--outcome "patterns reusable"]
python -m action_ledger chain close-session --session S42 [--essence "built recording infra"]
python -m action_ledger routes from <action_id>
python -m action_ledger routes to <target>
python -m action_ledger routes lineage <action_id> [--depth 3]
python -m action_ledger cycles [--min-recurrence 2] [--type verb_sequence|trajectory|intent|stall]
python -m action_ledger params
```

**Core modules:** `schemas.py` (Action, Sequence, Chain, Route, ParamAxis, ParamRegistry, ActionOrigin — open parameter model), `ledger.py` (atomic record() that appends+composes+registers; `close_session()` closes sequences+composes chain, `emit_session_closed()` emits AFTER caller persists — avoids stale-read race), `emissions.py` (self-recording state changes — `emit_state_change()` auto-records transitions as ledger entries with `origin: emitted`), `routes.py` (bidirectional route graph, lineage tracing, provenance injection), `cycles.py` (4 detection methods: verb sequences, trajectories, intents, stalls).

**Data files** (committed, living state): `data/actions.yaml` (append-only action stream), `data/sequences.yaml` (composed sequences with automation lanes), `data/param_registry.yaml` (discovered parameter axes).

**Conceptual prior art:** Alchemical Synthesizer (ORGAN-II) — module registry → parameter registry, patch bay → route system, CHRONOS automation → parameter trajectories, Euclidean rhythms → cycle detection.

**Design spec:** `.claude/plans/scalable-baking-conway.md`

## Intake Router (`intake_router/`)

Keyword-based operator intake router for low-token dispatch. Classifies messy ideas into routing domains, resolves the target workspace/archetype/agent, emits both the manual intake and the routed follow-up into the action ledger, and prints a ready-to-paste execution prompt sourced from the archetype plan.

```bash
python -m intake_router intake "third function build for a-organvm"
python -m intake_router table
python -m intake_router history [--domain organism] [--limit 10]
```

**Core modules:** `router.py` (keyword classification, routing table, archetype prompt loading, ledger emission), `cli.py` (standalone argparse entrypoints: intake/table/history), `__main__.py` (module entry).

**Ledger integration:** emits `received_intake` (manual) and `routed_intake` (emitted) actions with `subsystem: intake_router`, plus `RouteKind.FEEDS` routes to the destination workspace/archetype.

## ORGANVM Context

This repository is part of the **ORGANVM** eight-organ creative-institutional system.
It belongs to **ORGAN IV (Orchestration)** under the `organvm-iv-taxis` GitHub organization.

**Registry:** [`registry-v2.json`](https://github.com/meta-organvm/organvm-corpvs-testamentvm/blob/main/registry-v2.json)
**Corpus:** [`organvm-corpvs-testamentvm`](https://github.com/meta-organvm/organvm-corpvs-testamentvm)

<!-- ORGANVM:AUTO:START -->
## System Context (auto-generated — do not edit)

**Organ:** ORGAN-IV (Orchestration) | **Tier:** flagship | **Status:** GRADUATED
**Org:** `organvm-iv-taxis` | **Repo:** `orchestration-start-here`

### Edges
- **Produces** → `unspecified`: governance_rules
- **Produces** → `unspecified`: registry_data
- **Produces** → `unspecified`: dependency_validation
- **Produces** → `unspecified`: audit_reports
- **Produces** → `unspecified`: campaign_data
- **Produces** → `unspecified`: outreach_data
- **Produces** → `unspecified`: backflow_data
- **Produces** → `unspecified`: testament_formalization
- **Produces** → `unspecified`: absorption_data
- **Produces** → `unspecified`: fieldwork_data
- **Produces** → `unspecified`: action_ledger_data
- **Produces** → `unspecified`: threshold_topology
- **Consumes** ← `unspecified`: github_pr_states
- **Consumes** ← `unspecified`: github_issue_states

### Siblings in Orchestration
`petasum-super-petasum`, `universal-node-network`, `.github`, `agentic-titan`, `agent--claude-smith`, `a-i--skills`, `tool-interaction-design`, `system-governance-framework`, `reverse-engine-recursive-run`, `collective-persona-operations`, `contrib--adenhq-hive`, `contrib--ipqwery-ipapi-py`, `contrib--primeinc-github-stars`, `contrib--temporal-sdk-python`, `contrib--dbt-mcp` ... and 6 more

### Governance
- *Standard ORGANVM governance applies*

*Last synced: 2026-05-23T00:26:31Z*

## Active Handoff Protocol

If `.conductor/active-handoff.md` exists, **READ IT FIRST** before doing any work.
It contains constraints, locked files, conventions, and completed work from the
originating agent. You MUST honor all constraints listed there.

If the handoff says "CROSS-VERIFICATION REQUIRED", your self-assessment will
NOT be trusted. A different agent will verify your output against these constraints.

## Session Review Protocol

At the end of each session that produces or modifies files:
1. Run `organvm session review --latest` to get a session summary
2. Check for unimplemented plans: `organvm session plans --project .`
3. Export significant sessions: `organvm session export <id> --slug <slug>`
4. Run `organvm prompts distill --dry-run` to detect uncovered operational patterns

Transcripts are on-demand (never committed):
- `organvm session transcript <id>` — conversation summary
- `organvm session transcript <id> --unabridged` — full audit trail
- `organvm session prompts <id>` — human prompts only


## System Library

Plans: 269 indexed | Chains: 5 available | SOPs: 8 active
Discover: `organvm plans search <query>` | `organvm chains list` | `organvm sop lifecycle`
Library: `/Users/4jp/Code/organvm/praxis-perpetua/library`


## Active Directives

| Scope | Phase | Name | Description |
|-------|-------|------|-------------|
| system | any | atomic-clock | The Atomic Clock |
| system | any | execution-sequence | Execution Sequence |
| system | any | multi-agent-dispatch | Multi-Agent Dispatch |
| system | any | session-handoff-avalanche | Session Handoff Avalanche |
| system | any | system-loops | System Loops |
| system | any | prompting-standards | Prompting Standards |
| system | any | background-task-resilience | background-task-resilience |
| system | any | context-window-conservation | context-window-conservation |
| system | any | session-self-critique | session-self-critique |
| system | any | the-descent-protocol | the-descent-protocol |
| system | any | the-membrane-protocol | the-membrane-protocol |
| system | any | theory-to-concrete-gate | theory-to-concrete-gate |
| system | any | triangulation-protocol | triangulation-protocol |
| unknown | any | board-governance-toolkit | SOP-IV-BGT-001: Board Governance Toolkit |
| unknown | any | ceremony-cost-accounting | SOP-IV-CCA-001: Ceremony Cost Accounting |
| unknown | any | client-ip-identification | SOP-IV-CIP-001: Client IP Identification |
| unknown | any | communications-correspondence | SOP: Communications & Correspondence — Relay Protocol |
| unknown | any | content-to-product-pipeline | SOP-IV-CPP-001: Content-to-Product Pipeline |
| unknown | any | cross-boundary-reference-mapping | SOP-IV-CBR-001: Cross-Boundary Reference Mapping |
| unknown | any | disposition-classification | SOP-IV-DSC-001: Disposition Classification |
| unknown | any | dissection-protocol | SOP-IV-DSX-001: The Dissection Protocol |
| unknown | any | domain-cross-cut-analysis | SOP-IV-DCA-001: Domain Cross-Cut Analysis |
| unknown | any | editorial-triage-protocol | SOP-IV-ETP-001: Editorial Triage Protocol |
| unknown | any | flattened-hierarchy-audit | SOP-IV-FHA-001: Flattened Hierarchy Audit |
| unknown | any | governance-isotope-detection | SOP-IV-GID-001: Governance Isotope Detection |
| unknown | any | inflated-claims-audit | SOP-IV-ICA-001: Inflated Claims Audit |
| unknown | any | multi-perspective-reporting | SOP-IV-MPR-001: Multi-Perspective Reporting |
| unknown | any | plan-archaeology | SOP-IV-PAR-001: Plan Archaeology |
| unknown | any | protocol-precedent-constitutional | SOP-IV-PPC-001: Protocol → Precedent → Constitutional Decision Framework |
| unknown | any | registry-caching-chain-analysis | SOP-IV-RCC-001: Registry Caching Chain Analysis |
| unknown | any | severity-graded-skeleton-inventory | SOP-IV-SGS-001: Severity-Graded Skeleton Inventory |
| unknown | any | single-authority-data-model | SOP-IV-SAD-001: Single-Authority Data Model |
| unknown | any | spiral-build-methodology | SOP-IV-SBM-001: Spiral Build Methodology |
| unknown | any | staleness-mapping | SOP-IV-STL-001: Staleness Mapping |
| unknown | any | verb-assignment-protocol | SOP-IV-VAP-001: Verb Assignment Protocol |
| unknown | any | war-master-protocol | SOP: War-Master Protocol |
| unknown | any | xenograft-protocol | SOP-IV-XGR-001: The Xenograft Protocol |

Linked skills: SOP-TRIADIC-REVIEW-PROTOCOL, cicd-resilience-and-recovery, continuous-learning-agent, evaluation-to-growth, genesis-dna, multi-agent-workforce-planner, promotion-and-state-transitions, quality-gate-baseline-calibration, repo-onboarding-and-habitat-creation, session-self-critique, structural-integrity-audit, the-membrane-protocol, triple-reference


**Prompting (Anthropic)**: context 200K tokens, format: XML tags, thinking: extended thinking (budget_tokens)


## Atomization Pipeline

Run `organvm atoms pipeline --write && organvm atoms fanout --write` to generate task queue.


## System Density (auto-generated)

AMMOI: 25% | Edges: 0 | Tensions: 0 | Clusters: 0 | Adv: 27 | Events(24h): 37975
Structure: 8 organs / 148 repos / 1654 components (depth 17) | Inference: 0% | Organs: META-ORGANVM:63%, ORGAN-I:53%, ORGAN-II:48%, ORGAN-III:54% +5 more
Last pulse: 2026-05-23T00:26:28 | Δ24h: n/a | Δ7d: n/a


## Dialect Identity (Trivium)

**Dialect:** GOVERNANCE_LOGIC | **Classical Parallel:** Rhetoric | **Translation Role:** The Meta-Logic — governance rules ARE propositions

Strongest translations: I (formal), V (structural), META (structural)

Scan: `organvm trivium scan IV <OTHER>` | Matrix: `organvm trivium matrix` | Synthesize: `organvm trivium synthesize`


## Logos Documentation Layer

**Status:** ACTIVE | **Symmetry:** 0.5 (DREAM)

Nature demands a documentation counterpart. This formation maintains its narrative record in `docs/logos/`.

### The Tetradic Counterpart
- **[Telos (Idealized Form)](../docs/logos/telos.md)** — The dream and theoretical grounding.
- **[Pragma (Concrete State)](../docs/logos/pragma.md)** — The honest account of what exists.
- **[Praxis (Remediation Plan)](../docs/logos/praxis.md)** — The attack vectors for evolution.
- **[Receptio (Reception)](../docs/logos/receptio.md)** — The account of the constructed polis.

### Alchemical I/O
- **[Source & Transmutation](../docs/logos/alchemical-io.md)** — Narrative of inputs, process, and returns.

- **[Public Essay](https://organvm-v-logos.github.io/public-process/)** — System-wide narrative entry.

*Compliance: Record exists without implementation.*

<!-- ORGANVM:AUTO:END -->

















## ⚡ Conductor OS Integration
This repository is a managed component of the ORGANVM meta-workspace.
- **Orchestration:** Use `conductor patch` for system status and work queue.
- **Lifecycle:** Follow the `FRAME -> SHAPE -> BUILD -> PROVE` workflow.
- **Governance:** Promotions are managed via `conductor wip promote`.
- **Intelligence:** Conductor MCP tools are available for routing and mission synthesis.
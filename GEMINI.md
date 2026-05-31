# GEMINI.md — orchestration-start-here

See `CLAUDE.md` in this repo for full development instructions, architecture, and commands. This file provides system context for Gemini-based AI coding tools.

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


**Prompting (Google)**: context 1M tokens (Gemini 1.5 Pro), format: markdown, thinking: thinking mode (thinkingConfig)


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
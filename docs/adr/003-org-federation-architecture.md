# ADR-003: Organization Federation Architecture (Ten Orgs, Chartered)

## Status

Accepted

## Date

2026-07-05

## Context

The estate spans ten GitHub organizations: the seven organ chambers
(`organvm-i-theoria` … `organvm-vii-kerygma`), `meta-organvm` (the
front door and map), `a-organvm` (commerce), and `organvm` (the working
mass, ~180+ public repositories — 92% of the public estate). External
review flagged the structure's cost — discoverability, maintenance,
activation — and asked whether ten organizations is strategically
optimal. Until now the answer lived nowhere: the taxonomy was deliberate
and branded ("Eight organs. One system.") but the two largest orgs
carried no descriptions, and the relationship between the chambers and
the mass was de facto rather than chartered. The question "should there
be this many organizations?" kept reopening because no record owned it.

## Decision

**The federation stays at ten organizations, each justified by an
existence criterion, with an explicit chambers-vs-mass model.**

1. **Existence criterion.** An organization exists iff it provides at
   least one of: a distinct audience/persona, a distinct permission
   boundary, or a distinct deploy/billing surface. All ten pass:
   - `organvm-i` … `organvm-vii` — distinct audiences by function
     (theory, art, revenue systems, orchestration, essays, community,
     distribution);
   - `meta-organvm` — the map and public front door;
   - `a-organvm` — the commerce boundary (products, storefronts,
     revenue rails), kept separate so commercial permissions and
     billing never entangle the creative estate;
   - `organvm` — the working mass: production repos, experiments, and
     inbound lures at volume.
   Any eleventh organization must pass the same test, recorded here as
   an amendment.

2. **Chambers are showcases, not warehouses.** The numbered organs hold
   curated, portfolio-featured flagships only (currently 1–7 public
   repos each). The mass lives in `organvm`. This ratifies existing
   practice as architecture: the chambers are the museum floor, the
   mass org is the workshop.

3. **Mass migration is rejected.** Transferring ~180 repositories from
   `organvm` into the chambers is explicitly rejected unless a human
   pulls that lever in the future: it is a mass cross-org mutation
   (a gated action class) whose discoverability payoff the showcase
   model already provides at zero migration risk.

4. **Legibility is mandatory.** Every organization carries a
   description stating its role (enacted 2026-07-05 for the two that
   lacked one), and membership visibility is public so the federation
   is readable by any outside viewer — recruiters, reviewers, and
   instruments (e.g. the laurea arena) measure the same estate the
   owner sees.

## Consequences

- The "how many orgs" question is settled by criterion, not taste;
  future proposals amend this ADR rather than relitigating in chat.
- Outside viewers can now read the structure: chambers for depth,
  `organvm` for breadth, `meta-organvm` for the map.
- Flagship promotion (workshop → museum floor) remains a lightweight,
  reversible act: transfer one repo into its chamber when it earns
  portfolio placement — the inverse (mass migration) stays gated.
- Instruments measuring the public estate (percentile engines, the
  arena leaderboard) now see the true footprint, since membership and
  descriptions are public.

# Value-Locked Repository Recovery

**Find the boundary that breaks before your customers do.**

Evidence-bounded boundary audits for open-source software and AI-assisted systems.

**Paid, bounded private reviews available.** I examine software and AI-assisted systems where a local success signal may not prove the protected outcome — authority, billing, external effect, or durable state — is actually final.

**Typical boundaries**

- access revoked ≠ previously issued authority dead
- retry succeeded ≠ first external effect never happened
- billing completed ≠ every source cost recovered exactly once

**Representative proof:** In a controlled internal state-machine test, I reproduced a crash state where a run remained marked active while its documented completion and public restart path became unreachable. This is an internal validation example, not a client disclosure or a production-incident claim.

**Trust boundary:** public or explicitly authorized source; local or synthetic testing; no production probing, customer data, or real credentials unless explicitly authorized.

**Paid private review:** `siriusa.paper@gmail.com`

### External OSS trust proof

**3 independent upstream merges** across unrelated public repositories:

- [`rictaworks/questboard` PR #151](https://github.com/rictaworks/questboard/pull/151) — **MERGED**
- [`mldsveda/PyScrappy` PR #148](https://github.com/mldsveda/PyScrappy/pull/148) — **MERGED** after the maintainer locally verified the repair and regression coverage
- [`gren-lang/core` PR #135](https://github.com/gren-lang/core/pull/135) — **MERGED**

A fourth repair, [`pooza/makoto2` PR #56](https://github.com/pooza/makoto2/pull/56), has received substantive maintainer review; requested changes were addressed and re-review is pending.

These are public OSS contributions, not client engagements or evidence of paid commercial conversion.

---

## Why normal safety intuition is incomplete

Better models are valuable. They can improve reasoning, reduce answer errors, and make individual tasks more reliable.

But **better model intelligence does not automatically repair the surrounding control boundary**: the permissions, state transitions, tool execution, retries, revocation paths, and external effects around the model.

That distinction matters because many consequential failures do not begin with a bad model answer. They emerge across time, authority, execution, recovery, or scope expansion — even when each component appears to behave correctly in isolation.

These are different claims:

- **Model accuracy ≠ system integrity**
- **Local success ≠ end-to-end correctness**
- **No visible incident ≠ a boundary that is still safe**
- **Pilot-safe ≠ scale-safe**
- **Current authority ≠ previously issued authority**
- **Failure reported ≠ no external effect occurred**

### Pilot-safe does not automatically mean scale-safe

A rollout may begin with broad permission but little protected value. The pilot succeeds. Then more data, permissions, integrations, users, and consequential actions accumulate. If the original boundary is never re-qualified, evidence that the pilot was safe does not establish that the scaled system is safe.

This is not an argument against AI adoption or model improvement. It is a reason to test the system boundary again when the value, authority, or operating scope changes.

---

## What can still fail

I look for boundary failures that normal component-level checks can miss:

- authorization that survives revocation
- state that changes between validation and execution
- retries that repeat or compound external effects
- temporary capabilities that outlive the boundary that was supposed to end them
- a successful local operation that does not produce the intended durable result

The goal is not to produce the largest possible bug list.

The goal is to identify **what the product is supposed to protect**, find where that protection stops propagating, and produce a bounded, reproducible proof before the failure reaches production.

---

## What I look for

**Protected Object → Hidden Equivalence → Frozen Prediction → Local Proof → Private Disclosure**

### 1. Protected Object

First identify what actually matters:

- authorization
- customer data
- billing integrity
- funds or assets
- identity
- contractual state
- durable history
- operational continuity
- release integrity

### 2. Hidden Equivalence

Look for two things the current system treats as equivalent only because present conditions hide the difference.

Examples:

- current authority ≈ previously issued authority
- successful operation ≈ durable result
- retry ≈ idempotent recovery
- validated state ≈ executed state
- temporary credential ≈ temporary authority

---

## How I prove it

### 3. Frozen Prediction

Before building the proof, the expected failure condition, impact range, difficulty, and stop conditions are recorded.

Results are not relabeled afterward to make the discovery look easier or more important than it was.

### 4. Local Proof

Where possible, findings are reproduced with:

- public or explicitly authorized source
- fixed source state
- synthetic data
- local execution
- normal product paths
- deterministic before / after evidence

### 5. Private Disclosure

Active findings stay private while the recipient reviews them.

Public disclosure is not the default operating mode.

---

## What a qualified finding can look like

These are abstract patterns, not disclosures of active cases.

### Authority revocation

A principal loses current authority, but a capability derived from its former authority remains executable.

### Access revocation

A sharing surface is removed, but previously issued viewer state can still generate fresh access.

### Capability lifetime

A credential described as short-lived continues to authorize state-changing operations after the expected expiry boundary.

### Validation / execution drift

A state is valid when checked, but a different state is used when the consequential action actually executes.

### Recovery amplification

An operation reports failure, recovery is attempted, and an external side effect from the first attempt survives — allowing the recovery action to compound it.

### Representative validation example

The following is an internal validation example, not a client disclosure or a claim about a production incident.

In one state-machine system tested in a controlled environment, a crash could leave the run marked as still active while making the documented completion path unreachable. The local components had not necessarily failed in isolation, but the system no longer had a valid public restart point and could not reliably reach its own completion gate.

The issue was reproduced as a **state-transition and restartability failure**, rather than described as a generic reliability concern. The evidence was preserved as an as-of result instead of rewriting the interrupted run as complete.

---

## Available for private audit work

I accept bounded private engagements for:

- pre-release boundary audits
- pre-expansion boundary audits
- authorization and revocation review
- billing, retry, and state-transition integrity review
- AI-assisted workflow and agent-control review
- local deterministic reproduction of suspected failures

This is not a promise to find a vulnerability in every repository.

A valid result may also be a bounded **disproof** showing that the suspected boundary is correctly enforced.

---

## What you receive

Depending on scope, a review can produce:

- fixed as-of source state
- explicit protected object
- frozen failure hypothesis
- deterministic reproduction or disproof
- bounded impact statement
- compact private evidence package
- clear completion line

Repair and regression work can be scoped separately after qualification.

---

## Trust boundary

Unless explicitly authorized otherwise:

- public source only
- local or synthetic testing
- no production probing
- no customer data
- no real credentials
- no speculative severity inflation
- no public disclosure while private review is active
- no silent expansion beyond the agreed test boundary

Evidence is separated from interpretation.

A finding is only claimed to the extent that the reproduced result supports it.

---

## Research lineage

This work is informed by the Decision-OS research series, including work on:

- as-of evaluation and release boundaries
- survival-bounded planning
- reconnectable state and memory
- completion integrity
- compound-loop governance
- authority and protected-object boundaries

Public research:

https://github.com/shin4141/decision-os-paper

---

## Commercial availability

I am an independent researcher and practitioner behind Value-Locked Repository Recovery.

I am available for **paid, bounded private audit and review work** for repositories, AI-assisted systems, and operational workflows.

Typical engagements focus on boundaries around:

- authorization and revocation
- billing and financial state
- retries and external side effects
- migrations and historical continuity
- AI-agent permissions and execution
- state transitions that can appear locally correct while the protected outcome is not yet final

An engagement does not require a confirmed vulnerability in advance. A useful result may be either a reproducible finding or a bounded disproof showing that the suspected boundary is correctly enforced.

For paid audit work, private review, or research collaboration, contact **Shin (@shin4141)** through the contact information on the GitHub profile.

## Public OSS repair contributions

**Independent upstream merges: 3**

- [`pooza/makoto2` issue #54](https://github.com/pooza/makoto2/issues/54) — Distinguish an unreadable `/proc` boundary from a process that disappeared during enumeration, so the health result does not treat unknown state as clean. [PR #56](https://github.com/pooza/makoto2/pull/56) — **HUMAN SUBSTANTIVE REVIEWED / CHANGES ADDRESSED / RE-REVIEW PENDING**
- [`rictaworks/questboard` issue #97](https://github.com/rictaworks/questboard/issues/97) — Show an existing member's current role when a share URL is opened while preserving the first-time join flow. [PR #151](https://github.com/rictaworks/questboard/pull/151) — **MERGED**
- [`ritsth/job-autofill-extension` issue #198](https://github.com/ritsth/job-autofill-extension/issues/198) — Preserve known company and role metadata when re-saving a posting from a page that supplies blank values. [PR #215](https://github.com/ritsth/job-autofill-extension/pull/215) — **SUBMITTED**
- [`Johnkothapalli/python-code-health-analyzer` issue #16](https://github.com/Johnkothapalli/python-code-health-analyzer/issues/16) — Recover from malformed cached reports as cache misses without hiding SQLite operational failures. [PR #19](https://github.com/Johnkothapalli/python-code-health-analyzer/pull/19) — **SUBMITTED**
- [`mldsveda/PyScrappy` issue #144](https://github.com/mldsveda/PyScrappy/issues/144) — Preserve URL and adaptive-store context across derived selectors so chained adaptive selection keeps its site namespace. [PR #148](https://github.com/mldsveda/PyScrappy/pull/148) — **MERGED / HUMAN MAINTAINER LOCALLY VERIFIED**
- [`gren-lang/core` issue #134](https://github.com/gren-lang/core/issues/134) — Avoid a transient unsafe-integer intermediate while parsing `String.toInt` values near JavaScript's maximum safe integer boundary. [PR #135](https://github.com/gren-lang/core/pull/135) — **MERGED**
- [`LobsterTrap/lola` issue #224](https://github.com/LobsterTrap/lola/issues/224) — Read module files as UTF-8 with optional BOM handling and write generated files explicitly as UTF-8 across supported targets. [PR #236](https://github.com/LobsterTrap/lola/pull/236) — **SUBMITTED**
- [`griddynamics/rosetta` issue #260](https://github.com/griddynamics/rosetta/issues/260) — Carry a configurable turn limit from case or CLI input through the trial specification into the interaction engine while preserving the existing default when unset. [PR #284](https://github.com/griddynamics/rosetta/pull/284) — **SUBMITTED**
- [`papra-hq/papra` issue #1417](https://github.com/papra-hq/papra/issues/1417) — Refresh reused document previews when navigation replaces the source document, including reactive text blobs and source-keyed PDF viewer lifecycle. [PR #1426](https://github.com/papra-hq/papra/pull/1426) — **SUBMITTED**
- [`griddynamics/rosetta` issue #225](https://github.com/griddynamics/rosetta/issues/225) — Route plan create and upsert writes through the existing non-empty name validation while preserving the omitted-name default. [PR #285](https://github.com/griddynamics/rosetta/pull/285) — **SUBMITTED**
- [`bmad-code-org/bmad-loop` issue #278](https://github.com/bmad-code-org/bmad-loop/issues/278) — Reject mismatched TOML scalar types across `limits.*` policy fields before coercion can silently change policy meaning. [PR #587](https://github.com/bmad-code-org/bmad-loop/pull/587) — **SUBMITTED**

These are public OSS contributions, not client engagements.

## Private inquiries

Private audit work and research collaboration are welcome.

Contact **Shin (@shin4141)** through the contact information listed on the GitHub profile.

If you are preparing a release, expanding permissions, changing billing flows, introducing more automation, or moving into a higher-risk operating state, a bounded review can be performed before production.

---

## Disclosure note

This repository intentionally contains **no active private vulnerability details**.

Technical case evidence remains private until the applicable disclosure and release boundaries permit publication.

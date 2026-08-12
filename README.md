# Value-Locked Repository Recovery

**Find the boundary that breaks before your customers do.**

Evidence-bounded boundary audits for open-source software and AI-assisted systems.

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

## Private inquiries

Private audit work and research collaboration are welcome.

Contact **Shin (@shin4141)** through the contact information listed on the GitHub profile.

If you are preparing a release, expanding permissions, changing billing flows, introducing more automation, or moving into a higher-risk operating state, a bounded review can be performed before production.

---

## Disclosure note

This repository intentionally contains **no active private vulnerability details**.

Technical case evidence remains private until the applicable disclosure and release boundaries permit publication.

# Value-Locked Repository Recovery

**Find the boundary that breaks before your customers do.**

Evidence-bounded boundary audits for open-source software and AI-assisted systems.

I look for failures that are easy to miss when each component appears correct in isolation: authorization that survives revocation, state that changes between validation and execution, retries that repeat external effects, or temporary capabilities that outlive the boundary that was supposed to end them.

The goal is not to produce the largest possible bug list.

The goal is to identify **what the product is supposed to protect**, find where that protection stops propagating, and produce a bounded, reproducible proof before the failure reaches production.

---

## How the work is structured

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

## Why this exists

Many failures do not come from obviously bad code.

They appear when individually reasonable systems meet across time, authority, recovery, or state transitions.

The useful question is often not:

> Is this component secure?

but:

> **After the state changes, is the protected object still guarded by the same rule?**

That question is increasingly important as software gains more automation, more asynchronous execution, more agents, and more authority-bearing intermediate state.

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

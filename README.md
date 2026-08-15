# Value-Locked Repository Recovery

## Repair the transition, not just the broken point.

I investigate consequential state transitions: places where software says an action is **complete, settled, authorized, recorded, cancelled, or recovered**, while the underlying state or evidence may not fully support that meaning.

I do not compete on patch volume. The work is **boundary selection + transition integrity + completion evidence**.

> I don't just fix the broken point. I repair the transition so the system can move forward without carrying the same failure into its next state.

## Start with one consequential boundary

A one-boundary review focuses on one repository or system, one important transition, and one agreed As-of scope. Typical boundaries include:

- retry, replay, rollback, and partial progress;
- durable state and source-of-truth evidence;
- authorization, revocation, and authority changes;
- payment, refund, reconciliation, and settlement state; and
- AI-agent approval, memory, handoff, and external effects.

Depending on the agreed scope and what the evidence supports, one review can return:

- a bounded diagnosis tied to a fixed version or commit;
- a reproduced failure or a bounded disproof;
- a repair when feasible within the agreed boundary;
- focused regression and verification evidence;
- explicit residual `UNKNOWN`s; and
- a reusable condition or check for the same failure class.

### Trial entry

> You do not need to rely on me for every issue. Start with one bounded boundary. I leave the repair together with the conditions that help your team or AI question the same class of failure next time. If that proves useful, bring me back for the next consequential boundary.

## What remains after the repair

The useful residue is not only a code change. A bounded engagement is designed to leave a restartable evidence path:

```text
fixed As-of scope
-> failure condition
-> before / after evidence
-> focused verification
-> residual UNKNOWNs
-> reusable check for the next similar transition
```

That residue can help a development team or its AI recognize the same class of contradiction later. It is not a claim of future-proof software or guaranteed compatibility with unknown future changes.

## External OSS evidence

As of **2026-08-15**, there are **7 confirmed independent upstream merges** across unrelated public repositories. They demonstrate different boundary families rather than seven copies of the same repair.

| Boundary family | What the merged repair preserved | Public evidence |
| --- | --- | --- |
| Partial progress / transport integrity | A partially written FIX frame continues from its unwritten suffix before later frames advance | [`wingfoil-io/wingfoil` PR #839 — MERGED](https://github.com/wingfoil-io/wingfoil/pull/839) |
| Unknown state / truthful completion | An unreadable process boundary remains unknown instead of being treated as a disappeared, clean state | [`pooza/makoto2` PR #56 — MERGED](https://github.com/pooza/makoto2/pull/56) |
| Durable metadata / absent input | Re-saving a job with blank page values does not erase already-known company and role metadata | [`ritsth/job-autofill-extension` PR #215 — MERGED](https://github.com/ritsth/job-autofill-extension/pull/215) |
| Context transition / stale derived state | Changing workspace context clears graph state derived from the prior workspace | [`DataDave-Dev/weftmap` PR #175 — MERGED](https://github.com/DataDave-Dev/weftmap/pull/175) |
| Representation / numeric integrity | Integer parsing near JavaScript's safe-integer boundary avoids a transient rounded intermediate | [`gren-lang/core` PR #135 — MERGED](https://github.com/gren-lang/core/pull/135) |
| Derived object / source context | Chained adaptive selectors retain the URL and store context needed to preserve their meaning | [`mldsveda/PyScrappy` PR #148 — MERGED](https://github.com/mldsveda/PyScrappy/pull/148) |
| Current state / entry-path meaning | An existing member sees the current role while the first-time share-link join flow remains intact | [`rictaworks/questboard` PR #151 — MERGED](https://github.com/rictaworks/questboard/pull/151) |

These are public OSS contributions, not paid client engagements.

### Current submitted proof — open, not merged

The following repairs are public and submitted, but remain **OPEN / NOT MERGED**. They are not included in the count above, and their presence does not claim maintainer acceptance.

- **Durable transition:** materialized state is not the same as a durably recorded transition — [`vercel/workflow` PR #3575](https://github.com/vercel/workflow/pull/3575).
- **Current authority chain:** an accepted policy mutation is not the same as a currently valid authority chain — [`cerbos/cerbos` PR #3328](https://github.com/cerbos/cerbos/pull/3328).
- **Financial transition identity:** correlated payment evidence is not two independent financial transitions — [`mercurjs/mercur` PR #1399](https://github.com/mercurjs/mercur/pull/1399).

`OPEN`, approval metadata, or CI status is never counted as a merge.

## What this is not

This is not:

- high-volume AI patch production;
- a generic bug-fixing queue;
- a broad security audit or penetration test;
- a promise to find a defect in every system;
- a guarantee of future-proof software or unlimited scalability; or
- a claim that an open pull request has been accepted.

A valid bounded result may be a repair, a focused diagnosis, or evidence that disproves the suspected failure within the agreed conditions.

## Working boundary

Unless explicitly agreed otherwise:

- public or explicitly authorized source only;
- local or synthetic testing;
- no production probing, customer data, or real credentials;
- no speculative severity inflation;
- no public disclosure of active private findings; and
- no silent expansion beyond the agreed boundary.

Seller-side verification, buyer-side review, upstream acceptance, and paid closure remain separate evidence states.

## Request a one-boundary review

Email **siriusa.paper@gmail.com** with:

1. the repository, system, or workflow;
2. the transition whose meaning matters;
3. what could happen if that transition is incomplete or misleading;
4. the relevant version, commit, or As-of date; and
5. any evidence already available.

No continuing engagement is required. Scope, access, price, terms, and any corrective-care boundary are agreed separately before work begins.

You can also verify the operator through [Shin's GitHub profile](https://github.com/shin4141).

## Research lineage

This work is informed by the [Decision-OS research series](https://github.com/shin4141/decision-os-paper), including As-of evaluation, reconnectable state, completion integrity, authority boundaries, and compound learning.

---

This public repository intentionally contains no active private vulnerability details, customer-specific evidence, or claim of paid client experience.

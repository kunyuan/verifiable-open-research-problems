# Problem Selection and Audit Policy

Effective: 2026-08-01

## Purpose

This repository collects open questions that can support independent research projects. It is not limited to questions with cheap automated verification.

The first selection question is scientific:

> Would resolving the frozen question constitute a meaningful scientific result on its own?

Verification design matters because claims need a credible acceptance path. It determines **how** a result is reviewed, not whether a scientifically important problem belongs in the collection.

## Admission criteria

A problem is eligible for active promotion only when all of the following hold:

1. **A surviving open core.** A dated literature audit finds a precise unresolved claim. Failure to find an answer is evidence, not proof of openness, and the recorded status must reflect that uncertainty.
2. **Independent scientific significance.** A proof, counterexample, exact solution, classification, or other accepted answer would be a publishable or otherwise substantial scientific result by itself.
3. **A standalone research question.** The question can be motivated, stated, and evaluated without depending on one particular paper's unfinished workflow.
4. **A frozen resolution boundary.** The objects, assumptions, parameter domain, accepted answer types, and closure condition can be stated clearly enough for a reviewer to decide what has and has not been resolved.
5. **Traceable provenance.** The open-question claim and its present status are supported by inspectable sources. A mismatched or missing source blocks promotion until repaired.

Scientific significance is judged from the consequence of resolving the question: whether it would settle a recognized conjecture, determine a physically meaningful quantity or regime, expose a new phenomenon, supply a broadly useful classification or method, or remove a genuine conceptual obstruction.

## The independent-project test

Before promoting a candidate, ask:

- Could a research paper be organized around resolving this question, rather than merely using the answer as one step?
- Is the scientific consequence intelligible independently of the source paper's implementation plan?
- Would a positive or negative resolution matter to a community, model class, or general method beyond completing a local calculation?
- Does the question admit a clear final claim, even if reviewing that claim requires expert judgment?

A candidate should be deferred when the honest answer is no. Typical exclusions include an intermediate lemma needed only by one derivation, routine parameter fitting, a local code or benchmark improvement, a missing algebraic manipulation, or a technical detail whose resolution has no independent scientific consequence. Such items may be recorded as supporting tasks in the originating project, but they should not be promoted as standalone open-problem repositories.

Breadth is not the same as independence. A topic containing many questions must be split until each promoted item has one coherent scientific core. Conversely, a problem should not be cut into artificially small fragments merely to make verification cheaper.

## Review modes

Every admitted problem declares one of three primary review modes.

### Mechanical review

The decisive claim can be checked by a terminating computation, exact certificate, finite witness, formal proof, or comparably explicit replay. CI may carry much of the acceptance burden.

### Hybrid review

Mechanical checks establish important components, but an expert must also inspect specification fidelity, derivation steps, exceptional cases, or the scientific interpretation.

### Expert review

The essential result is a proof, derivation, classification, or physical argument that cannot be reduced to a complete automatic oracle. Independent domain experts review the load-bearing reasoning, scope, novelty, and relation to prior work. Computation should still test known limits, finite cases, internal consistency, or reproduced observables whenever those checks are scientifically meaningful.

**Major scientific problems may use expert review regardless of their residual verification-difficulty score.** A score of 7--10 is an acceptance-cost warning and planning input, not a rejection criterion and not a downgrade of scientific value.

Expert review does not relax the problem itself. The submission must still provide:

- the exact claim and all assumptions;
- a complete derivation or proof when the answer type requires one;
- explicit comparison with the closure condition;
- reproducible supporting calculations where applicable;
- a current novelty and literature check; and
- a clear account of unresolved branches and limitations.

Automated checks, agent review, and domain-expert acceptance are distinct evidence levels. A claimed solution remains pending until the review level required by the problem has actually been completed.

## Audit and publication workflow

The audit is intended to reach a useful decision, not to polish a candidate indefinitely.

1. Confirm provenance and perform a dated same-core literature audit.
2. Apply the independent-project test and assess scientific significance without using verification difficulty as a proxy.
3. Freeze one coherent question, its accepted answer types, and its closure condition.
4. Assign the least burdensome scientifically adequate review mode: mechanical, hybrid, or expert.
5. Publish either a problem record or a deferred record with the concrete blocking reason.

If a candidate is promising but still has a material ambiguity, publish a **problem draft awaiting feedback**. The draft should state the best current formulation, the uncertainty or decision that remains, and the evidence already checked. Do not repeatedly rewrite or expand it in the absence of new information.

Re-audit or revise a published draft when at least one of the following occurs:

- a researcher or reviewer supplies substantive feedback;
- a source conflict, scope defect, or logical error is identified;
- material new literature changes the open core; or
- the candidate is being promoted to an active problem repository.

Cosmetic refinement and speculative expansion alone are not reasons for another audit cycle.

## Minimum problem record

Each published problem or problem draft should contain:

- stable identifier and title;
- one-sentence question and exact frozen statement;
- why resolution matters scientifically;
- evidence for current open status and the audit date;
- accepted answer types and explicit closure condition;
- declared review mode and residual verification difficulty;
- feasible sanity checks or replay, if any;
- scope exclusions and known solved regimes;
- provenance and primary references;
- status: `draft_awaiting_feedback`, `likely_open`, `open`, `claimed_resolution_pending_review`, or `closed`; and
- unresolved audit questions, if the item is a draft.

The human-readable problem statement and any machine-readable registry must agree on the status, review mode, and closure condition.

## Promotion decision

| Scientific significance | Independent project? | Open core and provenance | Review path | Decision |
| --- | --- | --- | --- | --- |
| Major | Yes | Adequate | Expert only | Promote with `expert_review` |
| Major | Yes | Ambiguous but credible | Not yet final | Publish draft awaiting feedback |
| Moderate | Yes | Adequate | Mechanical, hybrid, or expert | Promote if the scope is coherent |
| Any | No | Any | Any | Defer as a supporting task or technical detail |
| Any | Yes | Closed, duplicate, or provenance-broken | Any | Close, merge, or block until repaired |

This policy deliberately permits hard-to-review landmark questions while protecting the collection from topic lists, workflow fragments, and technically precise but scientifically non-independent tasks.

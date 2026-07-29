# Verifiable Open Research Problems

This repository contains five research problems selected for an unusual but useful combination:

- they address open questions with real mathematical or physical significance;
- solving them may be very difficult;
- a successful result can usually be reviewed from the delivered answer itself, without reconstructing the solver's search or reasoning process; and
- the decisive checks are finite enough that an independent verifier, and often CI, can be designed.

The collection is intended for research agents, human researchers, and reviewer agents. Difficulty of discovery is not a rejection criterion. The central selection criterion is the separation between a hard search problem and a comparatively simple verification problem.

## The five problems

| Problem | Area | Preferred result object | Decisive verification |
| --- | --- | --- | --- |
| [ORP-0012: Spherical-rotor Griffiths inequality](problems/ORP-0012-spherical-rotor-griffiths-inequality.md) | Classical statistical physics | An explicit finite interacting $O(n)$ counterexample | Check the couplings and observables, recompute three certified expectations, and verify a strictly negative covariance |
| [ORP-0011: Arboreal-gas negative association](problems/ORP-0011-arboreal-gas-negative-association.md) | Probability and statistical physics | A finite weighted graph and two distinguished edges | Enumerate all forests with exact arithmetic and check one strict partition-sum inequality |
| [ORP-0008: Binary-answer monogamy-of-entanglement advantage](problems/ORP-0008-monogamy-of-entanglement-quantum-advantage.md) | Quantum information | A finite game and finite-dimensional quantum strategy | Validate the POVMs, enumerate classical strategies, evaluate the submitted strategy, and certify a strict quantum advantage |
| [OMP-0058: Quantum Mrs. Gerber lower bound](problems/OMP-0058-quantum-mrs-gerber-lower-bound.md) | Quantum information theory | Preferably a finite-dimensional counterexample with a certified entropy gap | Check positivity and normalization, reconstruct the combined state, and recompute the conditional entropies with rigorous bounds |
| [ORP-0010: Defect-sector Majorana spectrum](problems/ORP-0010-defect-sector-majorana-spectrum.md) | Quantum many-body dynamics | Closed-form expressions for the complete spectrum | Verify the characteristic-polynomial identity, multiplicities, branches, and exceptional parameter cases |

Each linked file is the full research-problem README from its original problem repository. It gives the scientific background, exact question, expected result, review scope, possible CI, current status audit, and references.

## What “result-only” means

Result-only is a property of review, not of the solver's method.

Delete the solver's search history and private reasoning process. If a reviewer can still decide, from the submitted answer object and a small amount of scientific explanation, that the original problem has been solved, then that answer is result-only.

Typical result objects in this collection include:

- a finite counterexample with exact or rigorously bounded quantities;
- a finite game, strategy, or matrix construction;
- a closed-form spectrum with a terminating symbolic identity;
- executable code that reproduces a decisive comparison; or
- formally checked code, when formalization is part of the submitted result.

Result-only does **not** mean “give an unexplained number.” A submission must still define its objects, state its claim precisely, identify the conventions it uses, and provide enough material for independent replay. What the reviewer should not need is the solver's exploratory trajectory or an ordinary step-by-step derivation that is not part of the claimed result.

The classification can depend on the answer branch. For example, a certified finite counterexample to the Quantum Mrs. Gerber conjecture is result-only, while a conventional proof of the full universal inequality would require substantive derivation review.

## Why these problems are useful for agents

Research agents are often good at generating candidates but expensive to review. These problems move effort toward the search side while keeping the acceptance boundary sharp:

```text
potentially difficult discovery
        ↓
finite or closed-form result object
        ↓
independent replay or exact check
        ↓
scientific reviewer confirms scope and novelty
```

This structure supports parallel search, adversarial reviewing, reproducible computation, and benchmark construction. It also reduces the chance that a plausible-looking narrative is mistaken for a result.

## Instructions for solving a problem

### 1. Read and freeze the actual problem

Treat the selected problem file as the source of truth. Record:

- the exact scientific claim;
- all admissibility conditions and conventions;
- the accepted result branch;
- what would count as a strict success; and
- what is explicitly outside scope.

Do not silently replace the question with an easier proxy. Do not assume that the answer will use Lean, a particular algorithm, or a particular numerical method unless the problem itself requires it. The solver may choose any route.

### 2. Refresh the research-status audit

Before investing substantial compute, check whether the same core problem has been solved or materially narrowed since the audit date in the problem file.

Search by:

- the original paper and its forward citations;
- the conjecture's exact terminology and mathematical objects;
- later papers by the same authors;
- stronger or equivalent formulations; and
- recent preprints, accepted papers, and relevant solution repositories.

If a major advance exists, determine the surviving core rather than declaring the entire topic closed from a related result.

### 3. Search freely, but preserve exactness early

The discovery process may use symbolic manipulation, exhaustive search, optimization, theorem proving, numerical experimentation, language models, or large-scale computation. The method is unrestricted.

However, convert promising candidates to reviewable form as early as possible:

- prefer rational or algebraic data when available;
- use certified intervals or directed rounding for transcendental quantities;
- keep floating-point evidence separate from the load-bearing claim;
- freeze basis ordering, normalization, branch conventions, and parameter domains; and
- record enough provenance to reconstruct the final object.

### 4. Build the smallest decisive answer

Do not enlarge the claim unnecessarily. A single valid counterexample is enough to refute a universal statement. A finite strategy with a certified strict gap is enough to prove an existence separation when the exact optimum is not required.

The final answer should make the decisive implication obvious:

```text
submitted object satisfies every input condition
AND
independent computation verifies the decisive equality or inequality
THEREFORE
the stated open problem is resolved in the claimed direction
```

### 5. Supply independent replay

When computation is load-bearing, provide:

- machine-readable input data;
- a pinned software environment;
- one documented replay command;
- exact arithmetic or rigorous error bounds;
- expected outputs;
- resource estimates; and
- a clear distinction between `PASS`, scientific failure, unsupported input, and resource exhaustion.

Whenever practical, use two independent implementations or compare the submitted program with a smaller reviewer-owned checker.

### 6. Self-review against the problem file

Before claiming success, ask:

1. Does the result answer the original question rather than a nearby variant?
2. Are all domain, normalization, positivity, boundary, and exactness conditions satisfied?
3. Can a reviewer reproduce the decisive check without seeing the search process?
4. Is the strict gap or symbolic identity robust under independent computation?
5. Is the conclusion limited to what the result actually establishes?
6. Has novelty been checked against current literature and other active attempts?

### 7. Package the solution

Prefer a standalone solution repository containing only what is needed to understand and verify the result:

```text
README.md          # claim, scientific meaning, and replay instructions
result/            # exact witness, formulas, or machine-readable output
verify/            # independent or submission-side verifier
environment files # pinned dependencies
tests/             # scientifically meaningful regression checks
```

Open an issue in this repository linking the solution repository and identifying the problem ID. A reviewer should then assess scientific fidelity, novelty, and the decisive result check. Passing CI is strong evidence for the encoded criterion, but it does not replace scientific scope and novelty review.

## Guidance for reviewer agents

A reviewer should begin with the final result object, not with the solver's narrative. The core questions are:

- Is the object admissible under the original problem?
- Does an independent replay reproduce the decisive claim?
- Does that claim resolve the stated scope?
- Is the result genuinely new?

Review derivations only when they are part of the answer type. For result-only submissions, do not require reconstruction of how the object was discovered.

## Status disclaimer

“Open” is a dated research judgment, not a permanent guarantee. Each problem file records its own audit and confidence. Before announcing a solution or committing major resources, refresh the literature search and inspect ongoing public attempts.

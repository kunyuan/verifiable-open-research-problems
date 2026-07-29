# Finite counterexample to the Griffiths inequality for interacting spherical rotors

Find an explicit finite interacting O(n) spherical-rotor system with n >= 3, nonnegative pair couplings with at least one nonzero coupling, and two invariant dot-product-cone observables f and g such that E[fg] < E[f]E[g].

## The Research Problem

Classical $O(n)$ spin models replace Ising variables by unit vectors; $n=2$ is the planar $XY$ model and $n=3$ the Heisenberg model. Griffiths-type inequalities express positive correlation in ferromagnets, but their extension to non-Abelian $O(n)$ symmetry is unresolved.

For $M<\infty$, let $\sigma_i\in\mathbb S^{n-1}\subset\mathbb R^n$, $n\ge3$, and let $d\nu_n$ be normalized rotation-invariant measure. With inverse temperature absorbed into symmetric couplings $J_{ij}\ge0$, $J_{ii}=0$, and at least one $J_{ij}>0$,

$$
d\mathbb P_J(\sigma)=Z_J^{-1}
\exp\!\left(\sum_{i<j}J_{ij}\sigma_i\!\cdot\!\sigma_j\right)
\prod_i d\nu_n(\sigma_i).
$$

The invariant dot-product cone consists of finite nonnegative linear combinations

$$
f(\sigma)=\sum_{\alpha=1}^{r}c_\alpha
\prod_{i<j}(\sigma_i\!\cdot\!\sigma_j)^{a_{ij}^{(\alpha)}},
$$

where $c_\alpha\ge0$ and all exponents are nonnegative integers; $g$ has the same form. Nonnegative describes the coefficients, not the pointwise sign of each monomial.

The second Griffiths inequality, or GKS2, asserts $\operatorname{Cov}_J(f,g)=\mathbb E_J[fg]-\mathbb E_J[f]\mathbb E_J[g]\ge0$. It is known in the $n=2$ and zero-interaction settings. The requested result is one finite interacting $n\ge3$ system and two explicit cone observables with rigorously negative covariance.

Against this background, this repository focuses on the following problem:

Find an explicit finite interacting O(n) spherical-rotor system with n >= 3, nonnegative pair couplings with at least one nonzero coupling, and two invariant dot-product-cone observables f and g such that E[fg] < E[f]E[g].

The specific scope of this repository is:

Finite classical isotropic O(n) spin systems with pairwise ferromagnetic dot-product interactions and invariant dot-product observables. Quantum rotors, Gaussian spins, fixed-coordinate observables, anisotropic componentwise claims, and stronger Ginibre or padded-Ginibre inequalities are excluded unless a result explicitly implies the stated covariance inequality.

## Why It Matters

The surviving question is the basic positive-correlation problem for invariant observables of non-Abelian vector-spin ferromagnets. A proof would supply a general monotonicity principle unavailable beyond the Abelian cases; a counterexample would identify a fundamental obstruction and delimit which rigorous ferromagnetic tools can extend to O(n) models.

A resolution would determine whether invariant correlations are universally monotone under ferromagnetic pair couplings for n >= 3. A counterexample would invalidate that universal tool but would not settle fixed-component inequalities, characterize all valid regimes, or refute every Ginibre-type variant. A proof would not automatically establish stronger padded or general Ginibre inequalities.

## Expected Results

A disproof by an explicit finite counterexample: a specified spin dimension n >= 3 and number of sites M, explicit symmetric couplings J_{ij} >= 0 with at least one J_{ij} > 0, and explicit observables f and g in the stated nonnegative dot-product cone, together with exact closed-form or rigorously certified terminating evaluations of E[f], E[g], and E[fg] proving E[fg] < E[f]E[g].

## Difficulty

Solving difficulty is not part of the discovery ranking. This assessment only helps a research agent estimate the knowledge, tools, and compute that may be required.
On the literature checked through the audit date, this remains a frontier open problem with substantial uncertainty about a complete solution path.
The interacting invariant-observable inequality is established for n=2 by the classical Ginibre theory, and the dot-product cone satisfies GKS2 for every n at zero interaction by Baumgartner and Herbst. For n >= 3, Abdesselam proved a large-power zero-coupling asymptotic governed by the Kirchhoff polynomial and corresponding limiting inequalities; 2025-2026 announcements report broader asymptotic evidence while stating that the non-Abelian GKS proof remains elusive. No valid finite-power interacting resolution is known.
CI availability is not a dispatch requirement and must not weaken the scientific claim.

Potentially required resources include:

- No computation was performed for this literature audit. Future review of a compact exact counterexample should normally be small-scale.
- None required for the audit; ordinary workstation CPU expected for witness replay.
- None.

## Review Scope

The reviewer should determine whether the submitted final result answers the problem, normally without reconstructing the solver's search or reasoning process.

The source asks whether a universal inequality holds, so one admissible finite counterexample with a strict violation answers the surviving core conclusively in the negative. For the declared counterexample format, an independent reviewer can decide correctness from the final witness by checking its dimension, couplings, cone membership, and directly recomputing the finitely specified expectations and strict sign; the search or derivation used to discover it is irrelevant. This resolves only the universal invariant-observable inequality and does not characterize the positive regimes or settle stronger inequalities. The result-only classification requires the expectation evaluations to be directly and terminatingly checkable, for example through explicit finite sums, standard exact special-function values, or rigorous rational enclosures. A Monte Carlo estimate or numerical quadrature needing an unreviewed convergence argument is insufficient. This classification applies to the declared disproof format; a universal proof would instead require result-and-derivation review.

Estimated review time: Approximately 4-12 expert-hours for a compact exact witness; potentially longer if nonstandard special-function reductions are load-bearing.

At minimum, the reviewer should confirm:

- Confirm n >= 3, finite M, and the stated spherical spin domain.
- Confirm every J_{ij} is nonnegative and at least one is strictly positive.
- Confirm f and g are finite nonnegative linear combinations of allowed dot-product monomials.
- Independently recompute the partition function and the three expectation numerators using the submitted exact formulas or terminating certificate.
- Verify normalization and all parameter substitutions.
- Establish with exact arithmetic or rigorous disjoint bounds that E[fg] - E[f]E[g] is strictly negative.
- Check that the witness is not merely a fixed-coordinate, Gaussian, zero-interaction, n=2, asymptotic, or stronger-Ginibre counterexample.

The review should also determine whether the submission truly answers the original problem, whether an equivalent or stronger result already exists, and whether a partial result constitutes substantive progress.

## Possible CI

A scientifically meaningful automated criterion is known, but a reusable CI implementation has not yet been supplied.

Suggested runner: Exact rational spherical-moment contraction plus outward interval bounds for the exponential-series tail.

Estimated runtime: Seconds to tens of minutes for a compact witness; pairing contractions grow combinatorially with sites, observable degree, and truncation order.

Scientifically meaningful automated checks may include:

- Read n, the finite site set, nonnegative rational couplings J_ij with at least one positive entry, and the nonnegative rational coefficients and integer exponents defining f and g in the invariant dot-product cone.
- Let H=sum J_ij(sigma_i dot sigma_j) and S=sum J_ij. For each numerator I_h=E_0[h exp(H)] with h in {1,f,g,fg}, expand exp(H) through total degree K.
- Compute every finite-order free-sphere moment exactly by the standard spherical pairing formula E[sigma_{a1}...sigma_{a,2r}]=sum_pairings(delta products)/(n(n+2)...(n+2r-2)), contracting component indices across sites.
- Bound each omitted exponential tail using |H|<=S and |each dot-product monomial|<=1, obtaining outward rigorous intervals for I_1, I_f, I_g, and I_fg.
- Interval-evaluate D=I_fg*I_1-I_f*I_g. Accept if the upper endpoint is strictly negative; otherwise increase K until the sign is certified or the CI resource limit is reached, in which case report inconclusive.

Automated checks establish only the criteria they encode. They cannot by themselves establish novelty, scientific interpretation, or claims outside the scope of this problem.

## Current Research Status

- Audit date: `2026-07-28; OpenAlex source-citation metadata updated through 2026-07-01`
- Current judgment: `confirmed_open`
- Confidence: `high`
- Surviving open core: For spin dimension n >= 3, determine whether every finite isotropic O(n) Gibbs measure with J_{ij} >= 0 and at least one J_{ij} > 0 satisfies Cov(f,g) >= 0 for all f and g in the invariant dot-product cone, or provide one exact finite counterexample. This excludes the settled n=2 case, the product-measure case J=0, Gaussian spins, large-power limiting statements, determinantal substitutes, and fixed-coordinate observables.
- Research judgment: The recent same-core literature directly continues to treat invariant-observable GKS inequalities for non-Abelian spin models as conjectural. No credible proof or counterexample for the finite-power, genuinely interacting dot-product problem was found. The closest claimed general result concerns fixed spin components rather than invariant dot products and is now withdrawn. The exact source statement should therefore remain open, with the already-settled n=2 and zero-interaction regimes removed from its surviving core.
- Treatment in later literature: The source paper's full text was checked, followed by exact-title and DOI citation searches, searches for O(n), non-Abelian, invariant-observable, GKS2, proof, and counterexample aliases, LKM paper-package and claim retrieval, and review of plausible adjacent results. The source has no indexed OpenAlex citing works, so the later treatment was reconstructed through the same-core topic chain. Abdesselam's work formulates coefficient-wise GKS2 for invariant O(n) observables with n >= 3 as a conjecture and proves only zero-coupling large-power asymptotics and corresponding determinantal toy-model inequalities. Official 2025 and 2026 research-meeting abstracts continue to describe the nonzero-coupling inequality as conjectural or proof-elusive while announcing broader asymptotic evidence. The apparent all-n fixed-component proof by Lees is scope-distinct and was withdrawn in March 2026 because its proposed bijection was invalid. Sylvester's counterexamples concern the stronger Ginibre inequality and explicitly do not refute the Griffiths inequality.

Future changes in status should update this section through commits and merge requests so that the evolution of the research judgment remains visible in Git history.

## LKM and References

### LKM

- LKM paper `867767668940210390` / open question `gcn_553bc8ca6ee8492d` / DOI `10.48550/arXiv.2209.11850` — Griffiths inequalities for non-interacting rotors. This is the source `open_questions` node that posed or preserved the problem; the problem was not inferred from an ordinary question or surrounding prose.

### References

1. [Griffiths inequalities for non-interacting rotors](https://arxiv.org/abs/2209.11850) — States the exact interacting dot-product inequality as an old open problem, records the n=2 Ginibre case, proves the all-n zero-interaction case, and notes that higher-dimensional Ginibre counterexamples do not settle this weaker Griffiths inequality.
2. [Non-Abelian correlation inequalities and stable determinantal polynomials](https://arxiv.org/abs/2207.07603) — The LKM package identifies invariant inner-product GKS2 for non-Abelian O(n) models as unresolved and separates true spin correlations from the determinantal and large-power substitutes.
3. [Large-power reduction of spin correlations to the Kirchhoff polynomial](https://arxiv.org/abs/2207.07603) — Records the zero-coupling large-power asymptotic and limiting padded ferromagnetic inequality, which provides asymptotic progress but not finite-power interacting closure.
4. [On correlation inequalities for non-Abelian spin systems and lattice gauge theories](https://math-events.uni-bonn.de/event/152/contributions/568/) — The official abstract presents invariant-observable inequalities for non-Abelian spin systems as a conjecture that would imply GKS at nonzero coupling, while reporting proof only in a large-power regime.
5. [Asymptotic Evidence for Ferromagnetism in Nonabelian Spin Models](https://www.siam.org/media/zxqcoyej/an26_abstracts.pdf) — States that proof of the GKS inequality remains elusive in non-Abelian cases and announces a new asymptotic formula supporting, rather than resolving, the conjecture.
6. [Griffiths inequalities for the O(N)-spin model](https://arxiv.org/abs/2205.12928) — The proposed theorem concerns products of a fixed spin component rather than the invariant dot-product cone. The preprint was withdrawn because the proof's purported bijection was not actually a bijection, so it supplies no closure.
7. [The Ginibre inequality](https://link.springer.com/article/10.1007/BF01198120) — Gives counterexamples to the stronger Ginibre inequality for spin dimension at least 3, while explicitly observing that this need not imply failure of the Griffiths inequalities.
8. [OpenAlex record for Griffiths inequalities for non-interacting rotors](https://openalex.org/W4297412122) — Shows zero indexed citing works for the source preprint; this supports the citation-chain coverage note but is not itself evidence of openness.

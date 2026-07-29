# Finite counterexample to pairwise edge negative association in the arboreal gas

Find a finite graph with positive edge weights and two distinct edges e,f for which the exact arboreal-gas probabilities satisfy Pβ[e,f] > Pβ[e]Pβ[f].

## The Research Problem

Random spanning forests are acyclic subgraphs sampled from a finite graph. The arboreal gas retains forests with every possible number of components, unlike a spanning-tree or fixed-component measure. The open structural question is whether the cycle constraint makes distinct edges negatively dependent.

Let $G=(V,E)$ be a finite undirected graph and give every labelled edge $h$ a strictly positive exact weight $\beta_h$. For each forest $F\subseteq E$, define

$$
w_{\boldsymbol\beta}(F)=\prod_{h\in F}\beta_h,\qquad
Z=\sum_{\substack{F\subseteq E\\F\text{ forest}}}w_{\boldsymbol\beta}(F),
\qquad \mathbb P_{\boldsymbol\beta}(F)=\frac{w_{\boldsymbol\beta}(F)}{Z}.
$$

The empty forest is included with weight one. Setting every $\beta_h=1$ gives the uniform forest model.

For distinct edges $e,f$, define

$$
Z_e=\sum_{F\ni e}w(F),\quad
Z_f=\sum_{F\ni f}w(F),\quad
Z_{ef}=\sum_{F\supseteq\{e,f\}}w(F).
$$

Pairwise negative correlation is $\mathbb P[e,f]\le\mathbb P[e]\mathbb P[f]$, equivalently $Z_{ef}Z\le Z_eZ_f$. It is the singleton-edge case of broader negative association.

The requested result is one fully explicit finite graph, positive exact weight assignment, and pair of distinct edges for which $Z_{ef}Z>Z_eZ_f$. This finite inequality can be checked by exact forest enumeration. Loops are excluded; if parallel labelled edges are used, a parallel pair is a two-edge cycle.

Against this background, this repository focuses on the following problem:

Find a finite graph with positive edge weights and two distinct edges e,f for which the exact arboreal-gas probabilities satisfy Pβ[e,f] > Pβ[e]Pβ[f].

The specific scope of this repository is:

The exact target is the full forest measure on arbitrary finite graphs with arbitrary positive, potentially heterogeneous weights. Distinct edges may be adjacent. Fixed-component forest measures, spanning-tree measures, bunkbed connectivity inequalities, and factor-2 approximate correlation bounds do not settle this claim. Although the final-result contract remains a two-edge counterexample, later work argues that universal pairwise correlation for all weights bootstraps to generalized disjoint-set product inequalities.

## Why It Matters

This is a longstanding foundational negative-dependence problem for random forests. The all-positive-weights formulation is substantially stronger than a correlation statement at one parameter value: later literature relates it to monotonicity under every edge weight and derives generalized product inequalities by conditioning. The source also connects factor-1 correlation to infinite-volume constructions. Resolution would therefore affect the structural correlation theory of the model, although it would not itself determine its phase diagram.

A counterexample would refute the universal pairwise claim and, since singleton edge events are included, rule out unrestricted negative association for the same measure. It would also identify a boundary that all future infinite-volume or monotonicity arguments must respect. A universal proof would establish exact factor-1 edge anticorrelation and support the generalized product consequences discussed in later literature. Neither outcome alone determines critical exponents, percolation thresholds, or all infinite-volume behavior.

## Expected Results

An explicit finite graph with positive edge weights and two identified distinct edges for which exact arboreal-gas probabilities satisfy Pβ[e,f] > Pβ[e]Pβ[f], including the complete graph and weight specification and exact values of the relevant forest partition sums or probabilities.

## Difficulty

Solving difficulty is not part of the discovery ranking. This assessment only helps a research agent estimate the knowledge, tools, and compute that may be required.
On the literature checked through the audit date, this remains a frontier open problem with substantial uncertainty about a complete solution path.
For arbitrary finite graphs and positive weights, the best universal quantitative replacement remains Pβ[e,f] ≤ 2Pβ[e]Pβ[f]. This follows from the 2-Rayleigh consequences of [Brändén–Huh's Lorentzian-polynomial theory](https://arxiv.org/abs/1902.03719), applied to the homogenized forest generating polynomial and preserved under positive external fields, which supplies the weighted extension. Exact factor 1 is known only in restricted cases: spanning trees; verified small uniform graphs; sufficiently large complete graphs at β=1; Huang's ladder, adjacent-edge/large-β, and complete-graph extreme-β regimes; small complete-graph symbolic checks; and 2026 fixed-component complete-graph truncations.
No proof attempt, counterexample search, or novel scientific computation was performed during the literature audit.

Potentially required resources include:

- A compact exact witness with at most a few tens of edges is expected for automatic review. This audit performed retrieval only.
- One CPU core is sufficient for exact enumeration of compact submissions.
- None.

## Review Scope

The reviewer should determine whether the submitted final result answers the problem, normally without reconstructing the solver's search or reasoning process.

The retained expected result is a source-faithful disproof of a universal statement. An independent reviewer can decide correctness from the submitted graph, exact positive weights, designated edges, and exact partition sums: enumerate all forests, recompute Z, Ze, Zf, and Zef, and check Zef·Z > Ze·Zf. No reconstruction of how the witness was discovered or substantive mathematical derivation is required. Later special-case results do not invalidate this contract; they only require that a valid witness fall outside their hypotheses. Acceptance disproves the universal claim and broader negative association, but does not characterize the remaining positive graph classes, provide a replacement theorem, or settle phase-transition questions.

Estimated review time: Approximately 15–60 minutes for a compact rational-weight witness; potentially several hours for a large graph or exact algebraic weights.

At minimum, the reviewer should confirm:

- Confirm that the submitted object is a finite graph and that every specified edge weight is exact and strictly positive.
- Confirm that e and f are distinct edges and that probabilities use the full arboreal-gas measure over all forests, not a fixed-component, connected-subgraph, spanning-tree, or bunkbed measure.
- Enumerate all acyclic edge subsets and recompute Z, Ze, Zf, and Zef using exact arithmetic.
- Verify the strict inequality Zef·Z > Ze·Zf exactly; floating-point evidence alone is insufficient.
- Check that graph conventions such as parallel edges or loops are represented consistently and do not create an identity mismatch with the source claim.

The review should also determine whether the submission truly answers the original problem, whether an equivalent or stronger result already exists, and whether a partial result constitutes substantive progress.

## Possible CI

A scientifically meaningful automated criterion is known, but a reusable CI implementation has not yet been supplied.

Suggested runner: Proposed: uv run python verify/arboreal_counterexample.py submission.json

Estimated runtime: O(2^m · m · α(n)); normally seconds for a compact witness with roughly twenty edges, with a 10-minute hard limit.

Scientifically meaningful automated checks may include:

- Read the submitted finite graph, exact positive rational edge weights, and distinct designated edges e and f.
- Reject malformed graphs, nonpositive weights, or identical/nonexistent designated edges.
- Enumerate every edge subset and retain exactly the acyclic subsets using union-find.
- With exact rational arithmetic, accumulate Z over all forests and Ze, Zf, and Zef over the relevant restricted forests.
- Accept exactly when Zef * Z > Ze * Zf; otherwise reject and report the four exact sums.

Automated checks establish only the criteria they encode. They cannot by themselves establish novelty, scientific interpretation, or claims outside the scope of this problem.

## Current Research Status

- Audit date: `2026-07-28`
- Current judgment: `confirmed_open`
- Confidence: `high`
- Surviving open core: Determine whether the full weighted forest measure has pairwise edge negative correlation on every finite graph for arbitrary positive weights, including heterogeneous weights and graph/edge configurations outside the ladder and structural-reduction cases and outside the known asymptotic uniform-activity regimes. Results for forests conditioned to have exactly k components do not settle this core because the arboreal gas mixes all component counts. In the retained dispatch format, one exact counterexample in this surviving class would refute the universal claim.
- Research judgment: The arbitrary-weight claim contains the β=1 uniform-forest conjecture as a subcase, and that subcase is explicitly still conjectural in March 2026. The September 2025 same-core treatment likewise states that P(e)P(f) ≥ P(e,f) remains unresolved. Later exact results cover only restricted graphs, activities, edge configurations, or fixed-component measures, so none closes or refutes the universal statement.
- Major progress and its effect: narrows
- Treatment in later literature: The source formulated the weighted conjecture with a universal factor-2 bound already known. The 2023 ICM survey [Spin systems with hyperbolic symmetry](https://arxiv.org/abs/2109.02566) explicitly stated that even pairwise negative correlation for all weights remained open. Huang's 2024 paper proved several restricted cases and related the all-weight pairwise and generalized product formulations. In September 2025, [Ayyer–Linusson–Ravichandran](https://arxiv.org/abs/2509.18788) called the same edge inequality the Kahn–Grimmett–Winkler problem and described it as far from resolution. Most decisively, [Tang–Zhang](https://arxiv.org/abs/2603.10738) still formulated even the β=1 arbitrary-graph subcase as a conjecture in March 2026. Searches of the same-core terminology, arXiv corpus, LKM, and forward citation chains through 2026-07-28 found no subsequent proof or counterexample; plausible later p-NC results concern different measures or restricted complete-graph families.

Future changes in status should update this section through commits and merge requests so that the evolution of the research judgment remains visible in Git history.

## LKM and References

### LKM

- LKM paper `812534450641436674` / open question `gcn_553723c659954050` / DOI `10.1007/s00220-020-03921-y` — Random Spanning Forests and Hyperbolic Symmetry. This is the source `open_questions` node that posed or preserved the problem; the problem was not inferred from an ordinary question or surrounding prose.

### References

1. [Random Spanning Forests and Hyperbolic Symmetry](https://link.springer.com/article/10.1007/s00220-020-03921-y) — Source LKM open-question record formulates the arbitrary-finite-graph positive-weight pairwise inequality and generalized product inequalities as unresolved.
2. [Spin systems with hyperbolic symmetry: a survey](https://arxiv.org/abs/2109.02566) — States that even pairwise negative correlation for distinct arboreal-gas edges remains open for all weights and relates it to monotonicity of connection probabilities in every weight.
3. [Lorentzian polynomials](https://arxiv.org/abs/1902.03719) — Propositions 4.21 and 4.25 give the 2-Rayleigh consequences used for the homogenized forest generating polynomial; closure under positive external fields supplies arbitrary positive edge weights and hence Pβ[e,f] ≤ 2Pβ[e]Pβ[f].
4. [On negative correlation of Arboreal Gas for specific parameters](https://arxiv.org/abs/2311.00965) — Proves adjacent-edge large-activity, complete-graph extreme-activity, ladder, and structural-reduction cases while explicitly leaving the general problem open; also states an equivalence between universal pairwise and disjoint-set product inequalities.
5. [Correlations in random cluster model at q=1](https://arxiv.org/abs/2507.09520) — Provides a correlation formula at q=1 and describes negative correlation for 0≤q≤1 as conjectural; it does not settle the q→0, p=βq arboreal-gas limit.
6. [The bunkbed problem and the random cluster model](https://arxiv.org/abs/2509.18788) — Identifies P(e)P(f)≥P(e,f) as the Kahn–Grimmett–Winkler forest problem and says it remains mysterious and far from resolution; reports bounded complete-graph symbolic checks of a stronger inequality.
7. [Pairwise Negative Correlation for Uniform Spanning Subgraphs of the Complete Graph](https://arxiv.org/abs/2603.10738) — Still states pairwise negative correlation for the β=1 uniform forest measure on arbitrary finite connected graphs as Conjecture 1.3, so the broader arbitrary-weight candidate remains open.

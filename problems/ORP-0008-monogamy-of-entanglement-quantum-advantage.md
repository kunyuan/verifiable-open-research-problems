# Monogamy-of-entanglement quantum advantage with fewer answers

Determine whether a finite monogamy-of-entanglement game with ω(G) < ω*(G) can have fewer answers than the cited MUB-based example with |Γ| = 3; equivalently, whether any such game exists with |Γ| = 2.

## The Research Problem

A monogamy-of-entanglement game asks two noncommunicating players to predict one quantum-measurement outcome held by a referee. It turns the monogamy principle—the limits on sharing quantum correlations among several parties—into an operational task. Formally, $G=(\Sigma,\Gamma,\pi,\{R_x^a\})$ has finite question and answer sets, a distribution $\pi$, and referee POVMs

$$
R_x^a\succeq0,\qquad \sum_{a\in\Gamma}R_x^a=I_R.
$$

The same sampled question $x$ is sent to both players, and they win exactly when both answers equal the referee outcome $a$.

Without shared entanglement, it is enough to consider a deterministic common response $f:\Sigma\to\Gamma$. The optimal value is

$$
\omega(G)=\max_{f:\Sigma\to\Gamma}
\lambda_{\max}\!\left(\sum_{x\in\Sigma}\pi(x)R_x^{f(x)}\right),
$$

With entanglement, a finite-dimensional strategy consists of a state $\rho$ on $\mathcal H_R\otimes\mathcal H_A\otimes\mathcal H_B$ and player POVMs $\{A_x^a\}$, $\{B_x^a\}$. Its winning probability is

$$
p(G,\rho,A,B)=\sum_{x,a}\pi(x)\operatorname{Tr}[
(R_x^a\otimes A_x^a\otimes B_x^a)\rho],
$$

and $\omega^*(G)$ is the supremum over all finite-dimensional legal strategies.

The source gave a strict separation using mutually unbiased bases (MUBs), whose measurement outcome distributions are uniform when a state from another basis is measured, but required three answers. The open branch asks whether a standard game with exactly two answers can satisfy $\omega(G)<\omega^*(G)$. One explicit legal strategy with $p(G,\rho,A,B)>\omega(G)$ is sufficient; the exact value of $\omega^*(G)$ is unnecessary. A one-answer game is trivial.

Against this background, this repository focuses on the following problem:

Determine whether a finite monogamy-of-entanglement game with ω(G) < ω*(G) can have fewer answers than the cited MUB-based example with |Γ| = 3; equivalently, whether any such game exists with |Γ| = 2.

The specific scope of this repository is:

Finite standard monogamy-of-entanglement games in the source's sense, with unrestricted finite referee dimension, POVMs, question distribution, and number of questions, but exactly two referee outcomes/player answers. The fewer-question branch, general extended nonlocal games, lossy or constrained variants, and decision games not representable as binary-outcome MoE games are outside the claim.

## Why It Matters

A positive witness would locate quantum advantage at the minimal nontrivial answer alphabet and show that the accumulating binary-family equality results are not universal. A universal negative theorem would instead establish ternary answers as necessary. Either outcome sharpens the resource boundary, but the question remains narrower than a structural characterization of MoE quantum advantage.

The later results make another isolated numerical search within standard qubit MUB or parity-product families less scientifically decisive: a valid positive result must escape the established equality regimes. Conversely, a broader negative theorem would now unify several exact special cases. Progress would clarify whether the three-answer requirement of the only audited positive example is incidental or structural.

## Expected Results

An explicit, fully specified finite standard monogamy-of-entanglement game G with |Γ|=2, together with a fully specified finite-dimensional standard quantum strategy S and exact values or rigorous certified bounds establishing p(G,S)>ω(G). Determining the exact value of ω*(G) is unnecessary because ω*(G)≥p(G,S).

## Difficulty

Solving difficulty is not part of the discovery ranking. This assessment only helps a research agent estimate the knowledge, tools, and compute that may be required.
On the literature checked through the audit date, this remains a frontier open problem with substantial uncertainty about a complete solution path.
In the audited chain, the smallest positive example remains the four-question, three-answer MUB game with ω(G)=(3+√5)/8≈0.6545 and a standard quantum strategy attaining at least 0.660986. Equality ω=ω* is known for every two-question MoE game. Later exact binary-answer results include the three Pauli-basis qubit game, with optimum 1/2+√3/6, and the XOR-repetition family, with optimum cos²(π/8); both optima are attained without entanglement.
This audit performed no solving computation. The compute estimate concerns only a future submitted-witness verifier.

Potentially required resources include:

- Small finite exact-arithmetic verification; 2^|Σ| payoff operators plus one strategy contraction.
- A conventional multicore CPU is sufficient; deterministic-response cases can be parallelized.
- Not needed for the acceptance calculation.

## Review Scope

The reviewer should determine whether the submitted final result answers the problem, normally without reconstructing the solver's search or reasoning process.

For the retained positive-witness answer format, the game and strategy are themselves the naturally required final result. An independent reviewer can validate the finite POVMs and strategy, compute ω(G) by finite enumeration of deterministic response functions and certified finite-matrix eigenvalue calculations, evaluate p(G,S), and compare the two without reconstructing how the witness was discovered. The strict inequality immediately gives ω*(G)≥p(G,S)>ω(G), genuinely answering the surviving existence question. This establishes only one binary-answer separation: it would not settle the fewer-question branch, characterize all binary-answer games, prove an exact entangled optimum, or establish novelty beyond the checked literature. A universal negative answer would instead require substantive proof review and would be result-and-derivation, outside this positive-witness contract.

Estimated review time: Approximately 2–6 expert-hours for a small algebraically specified witness; submission-dependent for larger question sets or matrix dimensions.

At minimum, the reviewer should confirm:

- Confirm that the submission defines a finite standard MoE game—not merely a lossy, constrained, or general extended game—and that |Γ|=2.
- Check π is a normalized nonnegative distribution and that each referee family {R(a|x)} consists of positive semidefinite operators summing to the identity.
- Check the submitted finite-dimensional state and both players' measurement families satisfy positivity, normalization, and dimension constraints.
- Independently enumerate all f:Σ→Γ, compute λmax(∑x π(x)R(f(x)|x)) with certified exact or interval arithmetic, and take the maximum as ω(G).
- Independently contract the submitted strategy to obtain p(G,S) and verify a rigorously separated strict inequality p(G,S)>ω(G).
- Confirm the conclusion is limited to existence of a binary-answer separation and does not claim the exact value of ω*(G), a fewer-question result, or a general characterization.

The review should also determine whether the submission truly answers the original problem, whether an equivalent or stronger result already exists, and whether a partial result constitutes substantive progress.

## Possible CI

A scientifically meaningful automated criterion is known, but a reusable CI implementation has not yet been supplied.

Suggested runner: No runner is implemented in the discovery toolkit. A future problem-specific verifier may implement the exact-arithmetic operations above in the generated problem repository.

Estimated runtime: Typically minutes for a small witness; exponential in |Σ| through 2^|Σ| deterministic-response enumeration and polynomial in matrix dimension per certified eigenvalue computation.

Scientifically meaningful automated checks may include:

- Parse the finite game and strategy using exact algebraic numbers or certified rational intervals; validate dimensions, normalization, Hermiticity, and positive semidefiniteness, and require |Γ|=2.
- Enumerate all 2^|Σ| deterministic functions f:Σ→Γ. For each, construct H_f=∑x π(x)R(f(x)|x) and isolate its largest eigenvalue using exact characteristic-polynomial root isolation or certified rational interval linear algebra.
- Take the certified maximum of those eigenvalues as ω(G).
- Evaluate p(G,S)=∑x,a π(x)Tr[(R(a|x)⊗A_a^x⊗B_a^x)ρ] using the same exact or certified interval arithmetic.
- Accept only when the certified lower bound for p(G,S) is strictly greater than the certified upper bound for ω(G); otherwise return inconclusive or reject.

Automated checks establish only the criteria they encode. They cannot by themselves establish novelty, scientific interpretation, or claims outside the scope of this problem.

## Current Research Status

- Audit date: `2026-07-28`
- Current judgment: `likely_open`
- Confidence: `medium`
- Surviving open core: Does any finite standard monogamy-of-entanglement game with |Γ|=2 and necessarily |Σ|≥3 satisfy ω(G)<ω*(G)? The known two-question theorem excludes |Σ|≤2, while the three-Pauli-basis qubit game and the parity-coarse-grained BB84/XOR family are additional no-advantage regimes. All other finite binary-outcome MoE games remain within the surviving core.
- Research judgment: The source establishes universal equality for every two-question MoE game and a strict separation for a four-question, three-answer game. Later work directly settles the natural three-question qubit MUB game: its exact quantum optimum is attained by an unentangled fixed-state, deterministic-answer strategy, including the lossless binary-answer case. A 2026 paper proves the same absence of advantage for an infinite parity/XOR family; representing its decision predicate as a standard binary-outcome MoE game requires parity-coarse-graining of the referee PVM, so that relation is treated as an identity inference rather than direct closure language from the paper. Later BB84 rigidity remains inside the already excluded two-question regime. These papers repeatedly treat only scoped families and leave a nonempty class of general binary-answer, at-least-three-question POVM games. A systematic same-core and forward-citation search found no credible closure. This supports still_open/likely_open at medium confidence rather than confirmed openness.
- Major progress and its effect: narrows
- Treatment in later literature: The audit started from the thesis, arXiv and journal identifiers, then combined conceptual and exact-phrase LKM searches with primary-web searches for binary/two-outcome games, quantum-versus-unentangled values, proofs, counterexamples, and open-problem treatments. Forward-citation lists for the 2016 paper and 2017 thesis were screened through 2026-07-28; plausibly relevant MoE papers were checked at abstract or primary-text level. Later literature concentrates on two-question BB84 rigidity, cryptographic/coset variants, lossy extended games, and decision variants. The most pertinent results prove equality of quantum and unentangled performance for particular binary-answer families; none supplies a binary-answer separation or a universal no-separation theorem.

Future changes in status should update this section through commits and merge requests so that the evolution of the research judgment remains visible in Git history.

## LKM and References

### LKM

- LKM paper `867767203083059688` / open question `gcn_732d54ef8f904b00` / DOI `10.48550/arXiv.1704.07375` — Extended Nonlocal Games. This is the source `open_questions` node that posed or preserved the problem; the problem was not inferred from an ordinary question or surrounding prose.

### References

1. [Extended Nonlocal Games](https://arxiv.org/abs/1704.07375) — Vincent Russo's thesis explicitly asks whether the four-question, three-answer separation can be improved to fewer questions or fewer answers and distinguishes these branches.
2. [Extended non-local games and monogamy-of-entanglement games](https://pmc.ncbi.nlm.nih.gov/articles/PMC4893182/) — Johnston, Mittal, Russo, and Watrous prove ω(G)=ω*(G) for every two-question MoE game and give the four-question, three-answer MUB separation with ω=(3+√5)/8 and ω*≥0.660986.
3. [Lossy-and-Constrained Extended Non-Local Games with Applications to Quantum Cryptography](https://quantum-journal.org/papers/q-2025-04-18-1712/) — Escolà-Farràs and Speelman exactly analyze the three-question, binary-outcome Pauli MUB game. At loss rate η=1 its quantum optimum is 1/2+√3/6 and is achieved by preparing one qubit and answering deterministically, hence there is no entangled advantage for this natural binary-answer candidate.
4. [Lossy-and-Constrained Extended Non-Local Games with Applications to Cryptography: BC, QKD and QPV](https://arxiv.org/abs/2405.13717) — The LKM claim records the piecewise exact value and explicit unentangled optimal strategies for the three-basis binary game; primary-text inspection was used for the load-bearing η=1 scope.
5. [The Curious Case of "XOR Repetition" of Monogamy-Of-Entanglement Games](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.ITCS.2026.41) — Coladangelo, Liu, and Xie prove that for every n the XOR decision variant has optimal quantum value cos²(π/8), attained by a strategy with the referee register unentangled from the players. Treating it as a standard binary-answer MoE family uses the inferred parity-coarse-graining of the referee's projective measurement.
6. [Rigidity for Monogamy-Of-Entanglement Games](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.ITCS.2023.28) — Broadbent and Culf show that optimal BB84 MoE strategies are convex combinations of four unentangled Breidbart-state strategies and prove a robust near-optimal version; this deepens but does not extend beyond the two-question no-advantage regime.

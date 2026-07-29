# The Quantum Mrs. Gerber Lower-Bound Conjecture

This file is the canonical English specification.

## The Research Problem

A binary classical–quantum (cq) state has the form

$$
\rho_{XB}=\sum_{x\in\{0,1\}}p_x|x\rangle\langle x|\otimes\rho_x^B,
$$

where $X$ is a classical bit and $B$ is arbitrary quantum side information. Consider two independent cq states $\rho_{X_1B_1}$ and $\rho_{X_2B_2}$ and combine their classical inputs by the binary XOR operation $X_1\oplus X_2$, equivalently the classical action of a CNOT gate. Write

$$
H_i=H(X_i|B_i),\qquad L=\log 2.
$$

Let $h_2(p)=-p\log p-(1-p)\log(1-p)$ be the binary entropy in the same logarithm base, let $h_2^{-1}:[0,L]\to[0,\tfrac12]$ be its restricted inverse, and define binary convolution by $a*b=a(1-b)+(1-a)b$.

Conjecture VII.1 of *Bounds on Information Combining With Quantum Side Information* proposes the optimal lower envelope

$$
H(X_1\oplus X_2|B_1B_2)\geq
\begin{cases}
h_2\!\left(h_2^{-1}(H_1)*h_2^{-1}(H_2)\right),
& H_1+H_2\leq L,\\
H_1+H_2-L+
h_2\!\left(h_2^{-1}(L-H_1)*h_2^{-1}(L-H_2)\right),
& H_1+H_2\geq L.
\end{cases}
$$

The research problem is to prove this inequality for all binary cq inputs with arbitrary quantum side information, or to give a finite-dimensional cq counterexample with a rigorously certified strict violation.

## Why It Matters

Mrs. Gerber's Lemma is the optimal classical lower bound for binary information combining. Quantum side information invalidates the classical conditioning argument, so the conjecture identifies the proposed replacement at the simplest nontrivial classical alphabet.

The bound also controls how quickly binary-input cq channels polarize. The source paper proves a close-to-optimal lower bound and obtains subexponential block-length scaling; Conjecture VII.1 would upgrade the relevant polar-coding conclusion to polynomial block length in the gap to capacity. A counterexample would show that the expected classical/quantum symmetry of the optimal envelope is wrong and would redirect the search for sharp entropy inequalities.

## Expected Results

A complete result may be:

- a rigorous proof of the displayed piecewise inequality for every allowed pair of independent binary cq states; or
- an explicit finite-dimensional pair of cq states for which the left-hand side is strictly below the applicable branch of the conjectured envelope.

A counterexample should specify all probabilities and density matrices exactly or algebraically, together with directed-rounding entropy bounds that leave a strictly negative gap. Floating-point output without certified error bounds is not sufficient.

Rigorous proofs for new, nontrivial subclasses, equality-case classifications, or certified dimension-bounded searches are useful partial progress, but they must not be presented as resolving the arbitrary-side-information statement.

## Difficulty

The expected research difficulty is very high. Classical proofs rely on expressing conditional entropy as an average over classical conditioning values; no analogous decomposition exists for general quantum side information. The two branches of the conjecture also meet at $H_1+H_2=L$, so an argument must control both the classical-like and dual quantum regimes.

Counterexample search is finite at any fixed side-information dimension, but the optimization is nonconvex and entropy depends on matrix spectra. Numerical absence of a violation at small dimension neither proves the inequality nor excludes higher-dimensional counterexamples.

## Review Scope

A finite counterexample with certified interval bounds is result-only. The Reviewer checks that each submitted matrix is positive semidefinite and normalized, reconstructs the XOR-combined cq state, recomputes all conditional entropies with outward rounding, selects the correct branch, and confirms a strictly negative gap. The solver's search trajectory is irrelevant.

An ordinary proof of the full conjecture requires substantive derivation review; checking a list of numerical lemmas is not enough. A special-case theorem must state its input class precisely and may only be accepted for that scope. Before any novelty claim is accepted, the Reviewer must refresh both the literature audit and pending AgentGitLab merge requests.

For a practical finite-dimensional certificate, the pool estimates 10–30 minutes of review after an independent checker is available.

## Possible CI

No substantive checker is installed on the main branch. A counterexample verifier could:

1. parse rational or algebraic probabilities and Hermitian density matrices;
2. certify positivity and unit trace;
3. build the product input and the cq state for $X_1\oplus X_2$;
4. enclose every required eigenvalue and von Neumann entropy using directed-rounding interval arithmetic;
5. evaluate the appropriate branch of the displayed lower envelope; and
6. accept only if the interval upper bound on the conjecture gap is strictly negative.

This remains a pseudocode CI contract. The expected runtime is 2–30 minutes for a practical candidate, with a hard timeout of 120 minutes. CI may certify a finite violation or replay finite lemmas, but it cannot by itself certify a general written proof or scientific priority.

## Current Research Status

As of the mainline audit on **2026-07-25**, the conjecture was assessed as **still open and likely open** (medium confidence). The original paper proves an almost-optimal lower bound. A follow-up entropy paper restates the optimal formula as a conjecture, while audited Rényi-entropy and classical information-combining results concern different statements. No accepted proof or counterexample to the displayed von Neumann-entropy inequality was found in that citation chain.

As of **2026-07-29**, AgentGitLab merge request !3 is open and pending review. It reports a rigorous theorem for the special case in which either input is a uniform binary flagged-erasure cq state, while the other input may have arbitrary prior, arbitrary finite dimension, and noncommuting conditional states. With entropies measured in bits, the merge request derives

$$
H(X_1\oplus X_2|B_1B_2)=H_1+H_2-H_1H_2
$$

for that class and reduces both conjecture branches to a scalar chord inequality. It also reports a complete parameter-reduced numerical search over pairs of qubit-output cq states with no counterexample, but explicitly labels that search as numerical evidence rather than a proof. Because the merge request is unmerged, the special-case theorem is recorded here as pending-review progress; the full conjecture remains open.

## LKM and References

- LKM open-question node `gcn_daea3df985244cda`, paper ID `813031540849115137` — records Conjecture VII.1 and related unresolved extensions.
- Christoph Hirche and David Reeb, [Bounds on Information Combining With Quantum Side Information](https://arxiv.org/abs/1706.09752), *IEEE Transactions on Information Theory* 64 (2018), DOI [10.1109/TIT.2018.2842180](https://doi.org/10.1109/TIT.2018.2842180) — proves the almost-optimal bound and states the displayed optimal lower envelope as Conjecture VII.1.
- [From Asymptotic Hypothesis Testing to Entropy Inequalities](https://arxiv.org/abs/1812.05142), 2018 — reformulates the same optimal bound as a conjecture rather than closing it.
- AgentGitLab merge request !3, “Draft: Flagged-erasure theorem and complete qubit adversarial search” — unmerged, pending-review special-case theorem and numerical evidence as of 2026-07-29.

# Closed-form spectrum of the defect-sector Majorana matrix

Obtain closed-form analytic expressions for the full spectrum of the physical defect-sector Majorana matrix A defined by Eqs. (81)/(82), beyond the existing ansatz, boundary-deformed comparison, and numerical diagonalization.

## The Research Problem

In the quantum asymmetric exclusion process studied by the source, operator space fragments into dynamically invariant sectors. On a defect-free segment the Lindblad generator becomes quadratic in Majorana superoperators, reducing the many-body dynamics to the spectrum of a finite $2M\times2M$ matrix $A$.

Let $K\in\mathbb C^{M\times M}$ have entries $K_{jk}=\delta_{j,k-1}$ for $1\le j,k\le M$, and let

$$
C=\begin{pmatrix}J_-&-2iJ_+\\0&J_-\end{pmatrix}.
$$

The physical defect-sector matrix is

$$
A=K\otimes C-K^T\otimes C^T.
$$

Here $T$ is ordinary transpose and the tensor-product basis is ordered by site and the two Majorana components; hence $A^T=-A$.

The nonnegative rates obey

$$
2J_+=J_1+J_2=J_3+J_4,\qquad 2J_-=J_1-J_2.
$$

On the balanced line, $J_3=J_4$ and $\mu=0$, equivalently $J_1=J_++J_-$, $J_2=J_+-J_-$, $J_3=J_4=J_+$, with $J_+\ge|J_-|$.

The source diagonalized $A$ numerically and obtained an analytic spectrum only after replacing it by a distinct, unphysical boundary-deformed matrix $A'$. The research task is to give the full multiset of all $2M$ eigenvalues of the undeformed $A$, with algebraic multiplicities, explicit indexing, branch conventions, degeneracies, and exceptional cases, for every positive integer $M$ and every admissible balanced-rate choice.

An unevaluated characteristic polynomial or implicit quantization condition is insufficient. A valid formula must reproduce the antisymmetry-induced $\lambda\leftrightarrow-\lambda$ pairing and the required complex-conjugation symmetry, including at degeneracies.

Against this background, this repository focuses on the following problem:

Obtain closed-form analytic expressions for the full spectrum of the physical defect-sector Majorana matrix A defined by Eqs. (81)/(82), beyond the existing ansatz, boundary-deformed comparison, and numerical diagonalization.

The specific scope of this repository is:

The undeformed finite-size matrix A for every positive integer M and all admissible nonnegative rates on the source paper's balanced free-fermion line. The question concerns eigenvalues only, not eigenvectors, Jordan structure, correlators, entanglement, general initial states, or other Lindbladian families.

## Why It Matters

The surviving core is a concrete structural gap in an exact solution of a fragmented quantum asymmetric exclusion process. Closing it would expose every defect-sector mode and its system-size and parameter dependence analytically. Its scientific reach remains bounded to this particular Majorana-matrix family and does not independently resolve the model's broader entanglement, initial-state, or physical-applicability questions.

No major later progress changes the target, importance assessment, expected result, or Solution Review boundary. The intrinsic-triage contract is preserved.

## Expected Results

Closed-form analytic expressions for every eigenvalue of the defect-sector Majorana matrix A defined by Eqs. (81)/(82), valid across the stated system sizes and admissible model parameters, with algebraic multiplicities and all necessary branch conventions, degeneracies, and exceptional parameter cases explicitly covered. Eigenvectors or a derivation are not required unless needed to make the spectral expressions well-defined.

## Difficulty

Solving difficulty is not part of the discovery ranking. This assessment only helps a research agent estimate the knowledge, tools, and compute that may be required.
On the literature checked through the audit date, this remains a frontier open problem with substantial uncertainty about a complete solution path.

**Verification difficulty: 2.** A submitted exact spectrum can be evaluated independently and compared with direct finite-size diagonalization of the original Majorana matrix across documented sizes, generic parameter values, branch boundaries, and exceptional cases. This score measures verification burden, not the difficulty of discovering or proving the formulas.

For the physical A, the source establishes antisymmetric ± pairing, conjugation symmetry, numerical spectra, and a small real pair near zero. It then solves the unphysical boundary-deformed matrix A′ using an ansatz with (z^{2M}−(−1)^M)(Δz²−2z−Δ)=0 and λ_z=2J_++J_−(z^{-1}−z), using reflection to recover the full A′ spectrum. The 2024 thesis reproduces this treatment. No better same-core result was found.
No solver run, novel construction, proof attempt, or experimental computation was performed.

Potentially required resources include:

- Literature audit required no scientific computation. Future review may construct symbolic 2M×2M matrices for modest M and evaluate exact identities, while the general-M claim remains a symbolic review task.
- A standard workstation is sufficient for auxiliary exact small-M checks.
- None.

## Review Scope

The reviewer should determine whether the submitted final result answers the problem, normally without reconstructing the solver's search or reasoning process.

The declared final result is the requested closed-form full spectrum itself. An independent reviewer can decide correctness without reconstructing the solver's reasoning by forming A from Eqs. (81)/(82), checking that the submitted indexed formulas yield exactly 2M roots with the stated multiplicities, and verifying the characteristic-polynomial identity det(λI−A)=∏_{j=1}^{2M}(λ−λ_j), or an equivalent exact terminating recurrence identity. Direct exact recomputation at finite M can supplement the symbolic identity. The submission must cover the physical A uniformly in M and admissible parameters; formulas only for A′, isolated parameter choices, asymptotics, or numerical eigenvalues do not answer the core. The accepted claim remains limited to eigenvalues and algebraic multiplicities and does not establish eigenvectors, Jordan structure, diagonalizability, dynamics, entanglement, or broader Lindbladian generality.

Estimated review time: Approximately 4–8 expert-hours for symbolic identity review, exceptional-case audit, and exact finite-M cross-checks.

At minimum, the reviewer should confirm:

- Confirm that the submitted formulas apply to the undeformed physical matrix A, not only to A′ or another quadratic Lindbladian.
- Confirm that every positive integer M and the full admissible balanced-rate parameter domain are covered.
- Check that branch conventions and indexing produce exactly 2M eigenvalues counted with algebraic multiplicity.
- Verify an exact characteristic-polynomial or equivalent named terminating recurrence identity for general M and parameters.
- Check degeneracies and exceptional parameter values, including cases where A may fail to be diagonalizable, without requiring Jordan data beyond what is needed for algebraic multiplicities.
- Check consistency with the mandatory ± spectral symmetry and complex-conjugation symmetry.
- Use exact small-M characteristic polynomials and numerical spot checks only as secondary validation, not as a substitute for the general identity.
- Reject a restatement as unevaluated roots of det(λI−A), an unsolved recurrence or quantization condition, numerical diagonalization, asymptotics alone, or formulas covering only the boundary-deformed matrix.

The review should also determine whether the submission truly answers the original problem, whether an equivalent or stronger result already exists, and whether a partial result constitutes substantive progress.

## Possible CI

No automated criterion currently captures the scientific conclusion well enough; evaluation should primarily rely on reviewer judgment.

Automated checks establish only the criteria they encode. They cannot by themselves establish novelty, scientific interpretation, or claims outside the scope of this problem.

## Current Research Status

- Audit date: `2026-07-28`
- Current judgment: `likely_open`
- Confidence: `medium`
- Surviving open core: Give explicit closed-form analytic expressions for all 2M eigenvalues of the undeformed matrix A=K⊗C−K^T⊗C^T for arbitrary finite M and every admissible balanced-rate parameter choice, including algebraic multiplicities, degeneracies, branch conventions, and exceptional parameter cases. The analytic solution of A′ and numerical diagonalization of A do not settle this core.
- Research judgment: The precise object remains identifiable and nonempty. The 2024 thesis is direct later evidence that the source author still treated the physical spectrum through numerical diagonalization and the analytically soluble deformation A′. Later papers citing the work through 2026 use it as background for different models or methods and do not claim the spectrum of A. No external paper was found that resolves, refutes, or materially narrows the requested all-M, all-admissible-parameter result. This supports still_open/likely_open with medium rather than high confidence because an uncited or differently described matrix-analysis result could have been missed.
- Treatment in later literature: The audit fixed the target from the source's Eqs. (81)/(82), searched its exact matrix formula and terminology in LKM and on the web, and reconstructed the union of 14 unique direct citing works returned by INSPIRE and OpenAlex through 2026. Accessible primary texts or abstracts were inspected for the target matrix, defect-sector terminology, Majorana spectra, and the source citation context. These works study adjacent topics—other quantum exclusion processes, dephasing chains, non-Bloch stochastic topology, fragmented Lindbladians, hydrodynamic projections, or general fragmentation—and do not provide formulas for A. Most importantly, Robertson's 2024 thesis reproduces the same physical matrix and again retains the statement that its closed-form analytic spectrum is not straightforward, followed by the same unphysical boundary deformation. LKM exact-formula and DOI searches recovered the source open-question node but no later same-core result. Thus the conclusion is not based merely on failure to find a solution: a later same-author treatment continues the limitation, while the broad forward chain contains no credible closure or conflicting claim.

Future changes in status should update this section through commits and merge requests so that the evolution of the research judgment remains visible in Git history.

## LKM and References

### LKM

- LKM paper `867761719210935008` / open question `gcn_9ffcba6429a249f5` / DOI `10.48550/arXiv.2105.08828` — Exact solution of a quantum asymmetric exclusion process with particle creation and annihilation. This is the source `open_questions` node that posed or preserved the problem; the problem was not inferred from an ordinary question or surrounding prose.

### References

1. [Exact solution of a quantum asymmetric exclusion process with particle creation and annihilation — dedicated open-question node](https://arxiv.org/abs/2105.08828) — Identifies the requested closed-form full spectrum of A as an explicit unresolved item, distinct from the ansatz and numerical diagonalization.
2. [Exact solution of a quantum asymmetric exclusion process with particle creation and annihilation](https://arxiv.org/abs/2105.08828) — Defines A in Eqs. (81)/(82), states that a closed-form analytic spectrum is not simple to obtain, and instead solves the unphysical boundary-deformed A′ while diagonalizing A numerically.
3. [Quantum quenches in closed and open spin chains: a thesis in two parts](https://ora.ox.ac.uk/objects/uuid:66b5ada4-fbf4-4d98-8932-ca5cccf1742f) — The source paper's first author reproduces the same matrix and limitation in the later thesis, retaining the boundary-deformation treatment rather than giving the physical spectrum.
4. [Effects of quantum pair creation and annihilation on a classical exclusion process: the transverse XY model with TASEP](https://arxiv.org/abs/2110.08283) — Uses a canonical Majorana superoperator basis to estimate a Liouvillian gap in a different transverse-XY-plus-TASEP model; it cites the source but does not diagonalize its defect-sector matrix A.
5. [Dynamics of fluctuations in quantum simple exclusion processes](https://arxiv.org/abs/2107.02662) — Studies fluctuation-sector Lindbladians for Q-ASEP/Q-SSEP and cites the source as related fragmented-Lindbladian work; its spectral calculations concern different blocks.
6. [Exact dynamics of quantum dissipative XX models: Wannier-Stark localization in the fragmented operator space](https://arxiv.org/abs/2405.17310) — Provides exact dynamics for dissipative XX models and cites Robertson–Essler as operator-space-fragmentation background, but explicitly concerns another generator and offers no spectrum for A.
7. [Exact density profile in a tight-binding chain with dephasing noise](https://arxiv.org/abs/2501.07095) — Derives exact time-dependent density results in a dephasing chain and cites the source among Bethe-ansatz-solvable Lindbladians; it does not treat the candidate matrix.
8. [Linear response and exact hydrodynamic projections in Lindblad equations with decoupled Bogoliubov hierarchies](https://arxiv.org/abs/2507.13867) — A recent Essler coauthored paper cites the source but derives spectra and hydrodynamic projections for a distinct class of BBGKY-decoupled Lindblad models, without addressing A.
9. [Complexity of Quantum Trajectories](https://arxiv.org/abs/2602.00232) — Cites the source in a survey of dissipative integrability and studies trajectory complexity and spectral statistics in other models; it contains no same-core spectral result.
10. [INSPIRE literature record for the Robertson–Essler paper](https://inspirehep.net/literature/1864223) — Provided a 12-record direct-citation chain, combined with OpenAlex to identify 14 unique citing works for primary-source inspection.

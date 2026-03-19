# Feasibility Dossier: Ionic-Core Clock-State Targets in Circular Rydberg Atoms

**Dossier ID:** FD-2026-CRS-ClockTargets  
**Version:** 1.0 (2026-03-19)  
**Type:** Feasibility study / candidate programme design  
**Scope:** Local proposal. No performance claims beyond analysed targets.  
**Status:** Open working document (v1.0)  
**Author:** Ulrich Warring, Physikalisches Institut, Albert-Ludwigs-Universität Freiburg  
**Origin:** Inspired by a lab visit to the circular Rydberg state experiment at the 5. Physikalisches Institut, Universität Stuttgart (Meinert group), and by the published work of that group  
**Constraint selection rule:** CANONICAL-SUPPORTED (peer-reviewed literature as primary anchor; preprints admitted provisionally)  
**Domain:** Precision atomic physics / ionic clock systematics  
**Strategic framing:** Orthogonal systematics. Not a competition with ion clocks for absolute accuracy, but a differential probe of atomic structure under distinct electromagnetic boundary conditions.

**Anchor statement:** The CRS platform is promising not because it obviously beats ion clocks in absolute precision, but because it offers a differently sourced and potentially better modelled rank-2 perturbation for extracting quadrupole-sensitive ionic-core quantities.

**Target classification legend:**

- **A1** = High-potential, direct: CRS advantage plausible, extraction depends primarily on spectroscopic data and well-characterised leading-order physics
- **A2** = High-potential, model-dependent: CRS advantage plausible, but extraction requires a validated forward model with non-trivial corrections
- **B** = Complementary only: CRS provides an independent cross-check but is unlikely to surpass conventional methods
- **B-deferred** = Longer-horizon exploratory: plausible in principle but dependent on undemonstrated capabilities (e.g. isotope preparation)
- **C** = Not competitive: unrealistic with current or near-term CRS linewidths

**Anti-aggregation notice:** The per-target classifications below are independent assessments. They cannot be combined into a programmatic value score, portfolio ranking, or aggregate feasibility metric without violating the epistemic discipline of this dossier.

---

## 1. Problem Definition

**Question:** Which atomic-structure targets relevant to ionic clocks could be measured or constrained using the divalent-atom circular Rydberg state (CRS) platform, and for which of these does the CRS environment offer a genuine advantage over conventional trapped-ion methods?

### 1.1 Target class

The candidate targets fall into three groups:

**Quadrupole-sensitive quantities** — targets whose measurement depends on knowledge of or sensitivity to the electric-field gradient at the ionic core:

- Electric quadrupole moment Θ(D₅/₂) and Θ(D₃/₂) of ⁸⁸Sr⁺ (state constants)
- E2 transition matrix elements ⟨D‖Q‖S⟩ (atomic-structure quantities)
- Nuclear quadrupole moment Q(⁸⁷Sr) via hyperfine structure of the D states (nuclear constant, indirect)

**Tensor-shift quantities** — targets whose measurement is complicated by entanglement of tensor Stark shifts with the electric quadrupole shift in conventional traps:

- Differential tensor polarisability Δα₂ of the Sr⁺ clock transition (atomic-structure quantity)
- Individual Zeeman-sublevel differential shifts under controlled field gradients (observables)

**Scalar/BBR quantities** — targets where conventional ion clocks are already at or approaching the 10⁻¹⁹ level:

- Differential static scalar polarisability Δα₀ of the clock transition (atomic-structure quantity)
- BBR shift coefficient (derived quantity)
- Absolute clock transition frequency (benchmark quantity)

### 1.2 Exclusion

The scalar/BBR quantities are excluded from the primary target list. The current best measurement of Δα₀ for ⁸⁸Sr⁺ achieves 4.1 × 10⁻⁴ fractional uncertainty [Lindvall-2025b], and the PTB clock operates at 7.9 × 10⁻¹⁹ systematic uncertainty [Lindvall-2025a]. Competing on these quantities requires Hz-level spectroscopy on the 674 nm transition inside the CRS — currently three orders of magnitude beyond demonstrated resolution. These quantities are listed under Category C.

---

## 2. Platform Mechanism

### 2.1 Core idea

The circular Rydberg electron in state |n, ℓ = n−1, m = n−1⟩ generates a Coulomb electric field and field gradient at the position of the ionic core. Because the circular state has maximal angular momentum and a well-defined orbital geometry (a thin ring of radius ⟨r⟩ ≈ n²a₀), this field has a simpler geometric provenance than externally applied trap gradients:

- **Internally generated** — not dependent on external electrode geometry, patch fields, or calibration drift
- **Geometrically constrained at leading order** — the leading-order field gradient is determined by the ideal circular-state quantum numbers (n, ℓ, m) and fundamental constants, though metrological use requires state-resolved forward modelling including corrections (§2.2)
- **Orientation-locked** — the gradient tensor orientation is set by the magnetic quantum number m = n−1 relative to the quantisation axis

The interaction Hamiltonian between the ionic core and the Rydberg electron's field can be represented schematically as:

H_int = −α₀|E_Ryd|² − α₂ T₂(E_Ryd) · T₂(D) + Θ · ∇E_Ryd + ...

This expression indicates coupling structure only. In the full forward model, all terms must be written consistently in irreducible tensor form with proper angular-momentum coupling coefficients. Here:

- α₀, α₂ are the scalar and tensor polarisabilities of the clock states
- Θ is the electric quadrupole moment of the D-state
- E_Ryd is the electric field from the Rydberg electron
- ∇E_Ryd is the electric-field gradient from the Rydberg electron
- T₂ denotes rank-2 tensor components

The Rydberg electron's field at the core position scales as:

|E_Ryd| ~ e/(n²a₀)² ~ e/(n⁴a₀²)

and the gradient as:

|∇E_Ryd| ~ e/(n²a₀)³ ~ e/(n⁶a₀³)

Both decrease rapidly with n. For n = 79 (the published CRS value): |∇E_Ryd| is on the order of 10⁸ V/m², comfortably in the range needed for kHz-scale quadrupole shifts. The geometric origin of this gradient is conceptually simpler than that of externally applied trap gradients, but the measurable quantity is not simply ⟨∇E_Ryd⟩ — it is the effective rank-2 coupling tensor seen by the ionic core after averaging over the actual (possibly dressed) CRS state and external perturbations.

### 2.2 Non-ideal terms (mandatory)

The field gradient is not "known" — it is "modelled with corrections." The following non-ideal contributions must be quantified in any metrological extraction:

1. **State impurity (coupled to item 2):** Admixture of elliptical states (ℓ < n−1) changes the field-gradient tensor. This is not merely a scalar dilution: stray dc electric fields that induce ℓ-mixing simultaneously distort the spatial symmetry of the electron wavefunction, producing a tensor perturbation to ∇E_Ryd that couples to the quadrupole interaction. State impurity and stray-field perturbations are therefore systematically coupled and must be treated jointly in the forward model.

2. **External stray electric fields (coupled to item 1):** Couple to the CRS polarisability (scaling as n⁷) and shift the circular orbit off-axis, modifying the field gradient at the core. Through ℓ-mixing, these fields also degrade the geometric purity of the gradient tensor. Residual fields at the ~mV/m level produce perturbations that grow with n.

3. **Cavity-induced modifications:** The ITO-coated capacitor plates provide microwave-frequency mode suppression (BBR suppression), but this applies to thermal photon occupation, not necessarily to static field quality. Static and low-frequency field distortions from the plates and ring electrodes are less constrained.

4. **Tweezer-induced perturbations:** The trapping light field interacts with the Rydberg electron (ponderomotive effect, growing with n) and with the ionic core (ac Stark shift, characterised). The former introduces a position-dependent perturbation to the orbital geometry.

5. **Wavefunction averaging:** The naïve point-charge model must be replaced by ⟨n,ℓ,m|∇E|n,ℓ,m⟩. For circular states this is tractable but corrections from finite orbital width are non-negligible at the precision level required.

6. **Relativistic and QED corrections:** At the ~10⁻⁴ level, relevant and calculable but must be included.

---

## 3. Candidate Targets — Ranked

### 3.0 Target-selection rule

Primary programme targets should maximise: (i) directness of coupling to the Rydberg-electron gradient, (ii) signal size at demonstrated n values, and (iii) shortness of the inferential chain from measured spectroscopic signal to extracted quantity — while minimising dependence on undemonstrated apparatus capabilities. This rule determines the A1 > A2 > B ordering.

### 3.1 Summary table

| # | Target | Type | Coupling | Current best | Ion-trap limitation | CRS advantage | CRS limitation | Class |
|---|--------|------|----------|-------------|-------------------|--------------|---------------|-------|
| 1 | Θ(D₃/₂) of ⁸⁸Sr⁺ | State constant | Quadrupole / ∇E_Ryd | Theory only (~5%) | Not attempted | Demonstrated D₃/₂ coupling (Wirth 2024) | Purity; model; resolution | **A1** |
| 2 | Θ(D₅/₂) of ⁸⁸Sr⁺ | State constant | Quadrupole / ∇E_Ryd | 2.6(3) ea₀² (~12%, Barwood 2004) | External gradient calibration | Internal gradient; simpler geometry | Same; D₅/₂ not yet demonstrated in CRS | **A1** |
| 3 | E2 matrix elements ⟨D‖Q‖S⟩ | Atomic-structure quantity | E2 driven by ∇E_Ryd | Theory ~few %; indirect via lifetime | No direct spectroscopic access | Direct gradient-driven transitions | Deconvolution; model-dependent | **A2** |
| 4 | Δα₂ (tensor pol.) | Atomic-structure quantity | Tensor Stark / E_Ryd | Not independently measured | EQS/tensor co-vary in Paul trap | Known E/∇E ratio separates them | ~100 Hz resolution needed | **B** (→A2) |
| 5 | Zeeman-sublevel shifts | Observable | EQS + tensor on m_J | Averaged over (6-pair cancellation) | Individual info destroyed | Controlled gradient; probes sublevels | Purity must ensure single-valued gradient | **B** |
| 6 | Q(⁸⁷Sr) nuclear | Nuclear constant (indirect) | Hyperfine E2: B_hf = eQq_J | 305(2) mb (~0.7%); ~10% theory discrepancy | Theory-limited on q_J | Could constrain q_J via E2 data | Indirect; ⁸⁷Sr CRS not demonstrated | **B-def.** |
| 7 | Δα₀ (scalar pol.) | Atomic-structure quantity | Scalar Stark | 4.1×10⁻⁴ frac. (2025) | Well controlled | No advantage | Resolution gap | **C** |
| 8 | BBR shift coeff. | Derived quantity | Thermal Stark | < 10⁻¹⁸ | Mature methods | No advantage | — | **C** |
| 9 | Absolute ν_clock | Benchmark quantity | Frequency | 9.8×10⁻¹⁷ frac. (PTB 2025) | Laser + comb + averaging | No path | Resolution, stability | **C** |

### 3.2 Category A1 — direct, high-potential

**#1: Θ(D₃/₂)** — Lowest-hanging fruit. Builds on [Wirth-2024]. kHz-scale differential shift already observed. No direct experimental measurement exists. Even ~10% extraction would be a new result.

**#2: Θ(D₅/₂)** — Most clock-relevant. Current best: 12% uncertainty [Barwood-2004], limited by external gradient calibration. CRS replaces this with forward-model uncertainty. Signal ~5–10 kHz at n = 79. If n-consistency, purity, and sub-kHz spectroscopy are all achieved, a percent-level extraction becomes plausible in principle. D₅/₂ coupling inside CRS not yet demonstrated (requires Step 2).

### 3.3 Category A2 — high-potential, model-dependent

**#3: E2 matrix elements** — ∇E_Ryd drives E2 transitions; [Wirth-2024] shows coherent driving on all eight D₃/₂ Zeeman components. Extraction requires comparing Rabi frequency with calculated gradient — longer inference chain than Θ extraction. More model-dependent.

### 3.4 Category B

**#4: Δα₂** — PTB explicitly cannot separate EQS from tensor Stark in Paul trap [Lindvall-2025b]. CRS geometry fixes the E/∇E ratio, making them separable in principle. But requires ~100 Hz resolution and validated Θ from #1–2. Category B now, potentially A2 at improved resolution.

**#5: Zeeman-sublevel shifts** — CRS probes individual m_J responses without the averaging that clock cancellation schemes [Dubé-2005] impose. Useful for testing atomic-structure calculations.

### 3.5 Category B-deferred

**#6: Q(⁸⁷Sr)** — Long inference chain: CRS → E2 → q_J → Q. Recent ~10% theory discrepancy [Zhang-2025]. Requires ⁸⁷Sr CRS (SPECULATIVE). Retained for completeness, deferred from primary programme.

---

## 4. Signal Model vs. Noise Model

### 4.1 Signal scaling

At n = 79: |∇E_Ryd| ≈ 1.6 × 10⁸ V/m²; δν_Q ≈ 5–10 kHz.
At n = 103: |∇E_Ryd| ≈ 3.6 × 10⁷ V/m²; δν_Q ≈ 1–2 kHz.

Signal favours lower n. Sweet spot: n ≈ 79–89 (signal + lifetime both sufficient).

### 4.2 Noise sources

| Source | Origin | n-scaling | Current magnitude | Dominant for |
|--------|--------|-----------|-------------------|-------------|
| Laser linewidth | 674 nm not cavity-stabilised | n-independent | ~kHz | All targets |
| Stray E-fields | Patch potentials, ITO charging | n⁷ (pol.) | ~mV/m inferred | All (high n) |
| ℓ-mixing (coupled to stray fields) | Imperfect circularisation + Stark mixing | Increases with n | Not quantified | A1, A2 targets |
| Cavity/tweezer | Static fields; ponderomotive | n² (tweezer) | Light shift measured; static fields not | All |
| Forward model | Wavefunction averaging; QED | Hydrogenic modelling error decreases with n, but total model uncertainty need not: field sensitivity and ℓ-manifold crowding worsen | Not evaluated | A1, A2 targets |
| Decoherence T₂ | Field fluctuations | n⁷ | ~100 μs Ramsey; ~ms echo | Long interrogation |

### 4.3 Precision estimate

**Near-term (1–2 yr):** Θ extraction at ~5–10%, comparable to Barwood et al. The near-term advantage is not yet ultimate precision but a cleaner and orthogonal gradient provenance, which could later translate into superior precision once the forward model is validated.

**Medium-term (3–5 yr, sub-kHz resolution + purity):** Potentially at the few-percent to ~1% level, contingent on DC-F1 through DC-F4.

**Δα₂:** Not feasible at current resolution (needs ~100 Hz).

---

## 5. Comparison to Standard Ion Experiments

| Target | Ion-trap best | Ion limitation | CRS removes it? | CRS new limitation |
|--------|-------------|---------------|-----------------|-------------------|
| Θ(D₅/₂) | 2.6(3) ea₀² (~12%) | External gradient calibration | **Yes** — simpler gradient provenance | Forward model; purity |
| Θ(D₃/₂) | Theory (~5%) | Not attempted | **Yes** — demonstrated access | Same |
| E2 matrix elements | Theory (~few %) | No direct spectroscopic access | **Partially** — gradient-driven transitions | Deconvolution; model |
| Δα₂ | Not measured independently | EQS/tensor co-vary | **In principle** — fixed E/∇E ratio | Resolution gap |
| Δα₀ | 4.1×10⁻⁴ | Well controlled | **No** | Resolution gap |
| Absolute ν | 9.8×10⁻¹⁷ | Laser + comb | **No** | All |

---

## 6. Discriminant Conditions (Feasibility Gates)

These are conjunctive: all must be satisfied for full metrological viability.

**DC-F1: Core spectroscopy resolution ≤ 1 kHz.** Technical-noise-limited (D₅/₂ Fourier limit is ~0.4 Hz). Single most critical gate. [Plausible within 12–24 months given demonstrated spin-echo coherence of ~ms; requires no new principle but substantial technical work]

**DC-F2: CRS purity.** Quantitative characterisation of the circular-state preparation fidelity must be published, with purity high enough that admixture-induced gradient-tensor uncertainty remains below 1% of δν_Q. The working target is ≥ 99% purity (ℓ-mixing below 1%); the exact threshold depends on the forward model's mapping from admixture fraction to tensor perturbation magnitude. [Plausible within current apparatus trajectory]

**DC-F3: Stray-field-bounded gradient uncertainty < 1% of δν_Q.** At n = 79, δν_Q ≈ 5 kHz → stray-field shifts must be bounded below ~50 Hz. This includes both direct field perturbation and indirect ℓ-mixing perturbation. [Plausible with standard compensation techniques plus Stark-spectroscopy calibration]

**DC-F4: n-consistency ≤ 1%.** Θ extracted at n = 79 and n = 89 must agree within mutual uncertainties. Decisive test. [Working expectation: 2–3 years]

**DC-F5: Cross-comparison.** CRS extraction compared with conventional value at informative precision. [Working expectation: 3–5 years]

**No-go criterion:** If the n-consistency check (DC-F4) fails at the > 5% level after inclusion of all identified correction terms from §2.2, the programme should not be framed as precision extraction of atomic constants. It should revert to qualitative cross-check or model-validation status. This is the hard stop condition.

---

## 7. Minimal Experimental Path

**Step 1 (12–18 mo):** Reproduce Wirth et al. D₃/₂ coupling with sub-kHz resolution; characterise purity; publish first direct Θ(D₃/₂) extraction with quantified uncertainty budget, plausibly 5–10%.

**Step 2 (18–36 mo):** Extend to D₅/₂; n-consistency check at n = 79 and 89; aim for a ≤ 5% extraction of Θ(D₅/₂), conditional on successful D₅/₂ coupling demonstration and n-consistency; compare with Barwood et al.

**Step 3 (3–5 yr):** Cross-compare; if resolution permits (~100 Hz), attempt Δα₂ separation; explore ⁸⁷Sr CRS.

---

## 8. Failure Modes

**8.1 Forward-model breakdown.** n-consistency check fails → model corrections dominate. Mitigate: ≥ 3 n-values; exploit distinct n-scaling of corrections.

**8.2 Insufficient resolution.** 674 nm laser cannot reach sub-kHz in CRS apparatus. Mitigate: clock-lab technology transfer; spin echo.

**8.3 Purity ceiling.** ℓ-mixing saturates at ~5% due to stray-field coupling (§2.2 items 1–2). Purity and field problems cannot be solved independently. Mitigate: joint purity + field diagnostics; improved circularisation.

**8.4 Decoherence at signal-optimal n.** T₂ too short at n ≈ 79–89. Mitigate: field compensation; slightly higher n (trade signal for coherence).

---

## 9. Strategic Positioning

**CRS is not a replacement for ion clocks. It is a differential probe of atomic structure under distinct electromagnetic boundary conditions.**

The core ion inside a CRS sees no Paul-trap micromotion, no ion-ion Coulomb coupling, an internally generated field gradient, and a cavity-modified BBR environment. Agreement or disagreement with ion-clock values is scientifically informative — but only if the CRS measurement itself is interpretable, i.e. only if DC-F2 (purity), DC-F3 (field bounds), and DC-F4 (model validation) are satisfied. A discrepancy arising from unmodelled ℓ-mixing rather than genuine Θ physics would be noise, not signal. The "either way informative" claim is conditional on the feasibility gates.

Publication path: reproduce → extract → compare (§7).

---

## 10. Pending Items and Load-Bearing Assumptions

### 10.1 Pending

- **Forward model** at n = 79 with all §2.2 corrections, including stray-field/ℓ-mixing coupling. True bottleneck.
- **n-dependence study** for model validation.
- **⁸⁷Sr CRS** preparation (SPECULATIVE).
- **Frequency comb** integration.

### 10.2 Load-bearing assumptions

1. CRS purity quantifiable at < 1% admixture level.
2. Forward model validatable across n (DC-F4).
3. Sub-kHz ionic-core spectroscopy achievable (technology transfer, not new physics).
4. External field perturbations boundable below model uncertainty.
5. Stray-field / ℓ-mixing coupling can be modelled or measured independently. If not, the "self-referenced" advantage is lost.

### 10.3 Next technical task

The immediate bottleneck is no longer prose architecture. It is the forward-model derivation. The required steps are:

1. **Ideal circular-state gradient.** Write ⟨n, n−1, n−1|∇E|n, n−1, n−1⟩ in irreducible tensor form using hydrogen-like wavefunctions with quantum-defect corrections for Sr. Express the result as a function of n and fundamental constants. Identify the exact rank-2 tensor structure coupling to the ionic-core D-state quadrupole moment.

2. **Finite-width wavefunction correction.** Replace the point-charge gradient with the full expectation value over the circular-state radial probability distribution. Estimate the fractional correction relative to the leading-order point-charge result as a function of n.

3. **Stray-field / ℓ-mixing coupled correction.** For a given stray dc electric field magnitude |E_stray|, calculate the resulting admixture amplitude of ℓ = n−2 and ℓ = n−3 states via Stark mixing. Compute the tensor perturbation to ∇E_Ryd caused by this admixture. Express the result as Δ(∇E)/∇E as a function of |E_stray| and n.

4. **Observable-to-target inversion for Θ(D₃/₂).** Define the explicit formula: Θ = measured δν_Q × h / (calculated ∇E_Ryd), and propagate uncertainties from spectroscopic noise, forward-model uncertainty, and purity bounds through to the final Θ uncertainty.

This four-layer scaffold is the minimum needed to convert the feasibility dossier into an actionable measurement protocol.

---

## 11. Bibliography and Reference Links

This section collects the primary literature grounding this dossier, organised by topic. Each entry includes a brief description of its relevance. Where available, stable URLs are provided.

### 11.1 Stuttgart CRS programme — core publications

**[Hölzl-2024]** C. Hölzl, A. Götzelmann, E. Pultinevicius, M. Wirth, F. Meinert, *Long-Lived Circular Rydberg Qubits of Alkaline-Earth Atoms in Optical Tweezers*, Phys. Rev. X **14**, 021024 (2024). [https://arxiv.org/abs/2401.10625](https://arxiv.org/abs/2401.10625)
— First realisation of alkaline-earth CRS in optical tweezers. Demonstrates n = 79 circular states of ⁸⁸Sr with 2.55 ms lifetime at room temperature via cavity-assisted BBR suppression. Characterises tweezer trapping and microwave qubit coherence. The foundational paper for the entire programme.

**[Wirth-2024]** M. Wirth, C. Hölzl, A. Götzelmann, E. Pultinevicius, F. Meinert, *Quadrupole Coupling of Circular Rydberg Qubits to Inner Shell Excitations*, Phys. Rev. Lett. **133**, 123403 (2024). [https://arxiv.org/abs/2405.20476](https://arxiv.org/abs/2405.20476)
— Demonstrates electric quadrupole coupling between the Sr⁺ ionic core (D₃/₂ level) and the n = 79 circular Rydberg qubit. Measures kHz-scale differential shifts via beat-node Ramsey interferometry with spin echo. The direct experimental predecessor of this dossier's proposed programme.

**[Pultinevicius-2025]** E. Pultinevicius, A. Götzelmann, F. Thielemann, C. Hölzl, F. Meinert, *Long-Lived Giant Circular Rydberg Atoms at Room Temperature*, arXiv:2510.27471 (2025). [https://arxiv.org/abs/2510.27471](https://arxiv.org/abs/2510.27471)
— Extends CRS preparation to n = 103 with lifetimes exceeding 10 ms. Demonstrates Purcell suppression via ITO-coated cavity at room temperature. Reports tweezer trapping on the few-hundred-millisecond scale. Preprint; not yet peer-reviewed.

### 11.2 Sr⁺ ion clock — state of the art

**[Lindvall-2025a]** T. Lindvall et al., *⁸⁸Sr⁺ Optical Clock with 7.9 × 10⁻¹⁹ Systematic Uncertainty and Measurement of Its Absolute Frequency with 9.8 × 10⁻¹⁷ Uncertainty*, Phys. Rev. Applied **24**, 044082 (2025). [https://arxiv.org/abs/2509.05964](https://arxiv.org/abs/2509.05964)
— PTB single-ion Sr⁺ clock achieving among the lowest systematic uncertainties reported. Includes detailed BBR evaluation, differential polarisability measurement, and the explicit statement that tensor polarisability cannot be separated from the electric quadrupole shift in the Paul trap. Essential reference for understanding what CRS could complement.

**[Lindvall-2025b]** T. Lindvall et al., *Measurement of the Differential Static Scalar Polarizability of the ⁸⁸Sr⁺ Clock Transition*, arXiv:2507.02603 (2025). [https://arxiv.org/abs/2507.02603](https://arxiv.org/abs/2507.02603)
— Precision measurement of Δα₀ with 4.1 × 10⁻⁴ fractional uncertainty. Demonstrates the "magic drive frequency" method. Key source for the ion-trap comparison in §5.

**[Barwood-2004]** G. P. Barwood et al., *Measurement of the Electric Quadrupole Moment of the 4d ²D₅/₂ Level in ⁸⁸Sr⁺*, Phys. Rev. Lett. **93**, 133001 (2004). [https://doi.org/10.1103/PhysRevLett.93.133001](https://doi.org/10.1103/PhysRevLett.93.133001)
— The only direct experimental measurement of Θ(D₅/₂) in ⁸⁸Sr⁺: 2.6(3) ea₀², i.e. ~12% uncertainty. Performed by varying the dc quadrupole potential in an endcap trap. The benchmark that the CRS programme aims to improve upon.

**[Dubé-2005]** P. Dubé, A. A. Madej, J. E. Bernard, *Electric Quadrupole Shift Cancellation in Single-Ion Optical Frequency Standards*, Phys. Rev. Lett. **95**, 033001 (2005). [https://doi.org/10.1103/PhysRevLett.95.033001](https://doi.org/10.1103/PhysRevLett.95.033001)
— Introduces the six-pair Zeeman averaging method for cancelling the electric quadrupole shift in ion clocks. Achieves 5 × 10⁻¹⁸ fractional uncertainty on the cancelled shift. Essential context for understanding what information is lost by averaging (§3.4, target #5).

### 11.3 Neutral Sr lattice clocks — BBR and multipolar shifts

**[Aeppli-2024]** A. Aeppli et al., *Clock with 8.1 × 10⁻¹⁹ Total Systematic Uncertainty*, Phys. Rev. Lett. (2024). [https://arxiv.org/abs/2403.10664](https://arxiv.org/abs/2403.10664)
— JILA strontium lattice clock: lowest total systematic uncertainty reported to date. Includes revised BBR shift evaluation requiring precise measurement of the 5s4d ¹D₃ lifetime. Context for §4.1.

**[Sanner-2021]** C. Sanner et al., *Blackbody Radiation Shift in Strontium Lattice Clocks Revisited*, Phys. Rev. Research **3**, L042036 (2021). [https://doi.org/10.1103/PhysRevResearch.3.L042036](https://doi.org/10.1103/PhysRevResearch.3.L042036)
— Reevaluates the BBR-induced ac-Stark shift of the Sr clock transition. Finds a 4 × 10⁻¹⁸ correction at 300 K — larger than the then-quoted uncertainty. Demonstrates why Rydberg-series data matters for clock accuracy.

**[Dörscher-2023]** S. Dörscher et al., *Experimental Determination of the E2–M1 Polarizability of the Strontium Clock Transition*, Phys. Rev. Research **5**, L012013 (2023). [https://doi.org/10.1103/PhysRevResearch.5.L012013](https://doi.org/10.1103/PhysRevResearch.5.L012013)
— Experimental determination of the E2–M1 polarisability difference for the neutral Sr clock states. Addresses the discrepancy between previous theoretical and experimental values. Context for §3.3.

### 11.4 Competing CRS programmes

**[Méhaignerie-2025]** P. Méhaignerie et al., *Interacting Circular Rydberg Atoms Trapped in Optical Tweezers*, PRX Quantum **6**, 010353 (2025). [https://doi.org/10.1103/PRXQuantum.6.010353](https://doi.org/10.1103/PRXQuantum.6.010353)
— Paris group: first observation of dipole-dipole interaction between two individually trapped circular Rydberg atoms (Rb, n ≈ 52). Demonstrates dynamic E-field control of interaction strength.

**[Machu-2025]** Y. Machu et al., *Non-Destructive Optical Read-Out and Manipulation of Circular Rydberg Atoms*, arXiv:2509.24691 (2025). [https://arxiv.org/abs/2509.24691](https://arxiv.org/abs/2509.24691)
— Paris group: hybrid dual-Rydberg platform combining circular logical qubits with laser-accessible ancilla atoms. Quantum non-demolition detection via Förster-resonance blockade.

### 11.5 Nuclear structure and quadrupole moments

**[Zhang-2025]** Y.-H. Zhang et al., *Determination of Nuclear Quadrupole Moments of ²⁵Mg, ⁸⁷Sr, and ¹³⁵,¹³⁷Ba via CI+CC Approach*, arXiv:2512.07603 (2025). [https://arxiv.org/abs/2512.07603](https://arxiv.org/abs/2512.07603)
— Reports ~10% discrepancy between the CI+CC-extracted Q(⁸⁷Sr) and the currently adopted value. Context for target #6 (B-deferred).

### 11.6 Rydberg physics — foundations

**[Gallagher-1994]** T. F. Gallagher, *Rydberg Atoms*, Cambridge University Press (1994). ISBN 978-0-521-02166-1.
— The standard textbook on Rydberg atom physics. Covers quantum defects, Stark effect, circular states, and blackbody radiation interactions. Essential background for understanding the field-gradient scaling arguments in §2 and §4.

**[Haroche-2006]** S. Haroche and J.-M. Raimond, *Exploring the Quantum: Atoms, Cavities, and Photons*, Oxford University Press (2006). ISBN 978-0-19-850914-1.
— Nobel-level treatment of cavity QED with circular Rydberg atoms. Provides the historical and conceptual foundation for the CRS platform. Covers Purcell suppression, circular-state preparation, and the coupling between Rydberg atoms and microwave fields.

### 11.7 Atomic structure theory

**[Safronova-2018]** M. S. Safronova et al., *Search for New Physics with Atoms and Molecules*, Rev. Mod. Phys. **90**, 025008 (2018). [https://doi.org/10.1103/RevModPhys.90.025008](https://doi.org/10.1103/RevModPhys.90.025008)
— Comprehensive review of how precision atomic measurements constrain new physics. Includes discussion of polarisabilities, quadrupole moments, and clock systematics across multiple species including Sr and Sr⁺. Provides the broader scientific motivation for why improving these constants matters.

### 11.8 Open-source control software

**[atomiq ONE]** Atomiq ONE — open-source quantum hardware orchestration framework. [https://atomiq.one/](https://atomiq.one/)
— The control software used by the Stuttgart CRS experiment, built as a convenience layer on ARTIQ/Sinara. Relevant context for understanding the experimental infrastructure.

---

## 12. Tutorial: Reading This Dossier as a PhD Student

This section provides the background needed to understand the scientific arguments in this dossier. It is written for a PhD student in atomic physics or quantum optics who is familiar with basic quantum mechanics and laser physics but may not have worked with Rydberg atoms or ionic clocks specifically.

### 12.1 What is a circular Rydberg state?

An atom in a Rydberg state has its outermost electron excited to a very high energy level, characterised by a large principal quantum number n (in this dossier, n ≈ 79–103). In a "circular" Rydberg state, the electron also has the maximum possible orbital angular momentum: ℓ = n − 1, m = n − 1. Classically, this corresponds to the electron orbiting the nucleus in a thin ring, much like a planet in a circular orbit around a star. The orbital radius scales as n²a₀ (where a₀ ≈ 0.053 nm is the Bohr radius), so at n = 79 the electron orbits at roughly 0.3 μm from the nucleus — a macroscopic distance by atomic standards.

**Why circular states are special.** Ordinary (low-ℓ) Rydberg states decay by spontaneous emission on timescales of ~10–100 μs. Circular states are long-lived because the radiative decay pathways are highly constrained by angular-momentum selection rules: the only allowed optical transitions connect to states with ℓ differing by one unit, leading to a slow, restricted cascade rather than the fast multi-channel decay of low-ℓ states. This makes blackbody-radiation-induced transitions the comparatively dominant loss mechanism, which can be suppressed by placing the atom inside a microwave cavity. The Stuttgart group uses ITO-coated glass plates separated by ~1 cm to suppress the relevant BBR modes, achieving lifetimes exceeding 10 ms at room temperature.

### 12.2 Why strontium? The divalent advantage

Most Rydberg experiments use alkali atoms (Rb, Cs), which have a single valence electron. When that electron is excited to a Rydberg state, there is no remaining optical electron — the atom cannot be probed or manipulated with laser light while in the Rydberg state.

Strontium is a divalent (alkaline-earth) atom: it has two valence electrons. When one electron is excited to a circular Rydberg state, the other electron remains bound to the Sr²⁺ core, forming an Sr⁺-like ion. This "ionic core" retains its own electronic structure — including the S₁/₂, P₁/₂, D₃/₂, and D₅/₂ states familiar from Sr⁺ ion-trap experiments. Crucially, these states can be addressed with standard laser wavelengths (422 nm for cooling/fluorescence, 674 nm for the clock transition, 1092 nm for repumping) even while the outer electron is in the circular Rydberg state.

This separation — Rydberg electron for long-range interactions and long lifetime, ionic core for optical control and readout — is the defining structural feature of divalent-atom CRS platforms.

### 12.3 What is the electric quadrupole shift, and why does it matter for clocks?

An optical atomic clock measures the frequency of a specific electronic transition with extraordinary precision. For ⁸⁸Sr⁺ ion clocks, the reference is the S₁/₂ → D₅/₂ transition at 674 nm (~445 THz). Any effect that shifts this frequency away from its "true" value is a systematic error.

The **electric quadrupole shift** (EQS) arises because the D₅/₂ state has a non-spherical charge distribution (a "quadrupole moment" Θ). When this charge distribution sits in an electric-field gradient ∇E, the energy of the state shifts by an amount proportional to Θ × ∇E. In a Paul trap, the field gradient comes from the trap electrodes. In a CRS, it comes from the circular Rydberg electron.

The EQS is one of the largest systematic shifts in Sr⁺ clocks. Clock groups deal with it by averaging over multiple Zeeman sublevels (the six-pair cancellation method of Dubé et al. [Dubé-2005]), which eliminates the shift but also destroys information about the quadrupole moment itself. The current best measurement of Θ(D₅/₂) — by Barwood et al. [Barwood-2004] — has only 12% precision, because calibrating the external field gradient is difficult.

### 12.4 The core idea of this dossier

This dossier asks: can we use the circular Rydberg electron's electric-field gradient as a "calibrated" source for measuring the ionic core's quadrupole moment and related quantities?

The argument goes like this:

1. The circular Rydberg electron orbits at a known radius (~n²a₀) in a known geometry (a ring in the plane perpendicular to the quantisation axis).
2. This orbit generates an electric field and a field gradient at the position of the ionic core.
3. The leading-order magnitude of this gradient is calculable from n and fundamental constants.
4. By measuring the quadrupole shift of the ionic core's D-state levels inside the CRS, and comparing with the calculated gradient, one can extract Θ.

The CRS gradient has a simpler geometric origin than a Paul-trap gradient — it does not depend on electrode geometry, patch potentials, or the ion's position within the trap. However (and this is the central tension of the dossier), it is not truly "known" — it must be modelled, and the model must account for state impurity, stray fields, wavefunction averaging, and other non-ideal effects (§2.2). Throughout this dossier, "calibrated" should be read only in the conditional sense of "model-constrained and testable by n-consistency," not as "known independently of modelling."

### 12.5 The A/B/C classification explained

The dossier ranks candidate measurement targets by asking three questions for each:

1. **Is the CRS gradient the right kind of perturbation?** Quadrupole moments couple to field gradients → yes. Scalar polarisabilities couple to field amplitude → yes in principle, but the signal is not uniquely advantaged.
2. **Is the CRS measurement likely to be better than conventional methods?** For Θ: possibly, because the gradient provenance is simpler. For Δα₀: no, because ion clocks already achieve 10⁻⁴ fractional precision.
3. **Is the inferential chain short enough to be trustworthy?** For Θ: relatively short (measured shift ÷ calculated gradient = Θ). For E2 matrix elements: longer (requires deconvolution of multiple coupling channels).

Targets that score well on all three questions are **A1** (direct, high-potential). Targets that require a validated forward model for the deconvolution step are **A2**. Targets where CRS provides only an independent cross-check are **B**. Targets where conventional methods are clearly superior are **C**.

### 12.6 What the forward model needs to do

The "forward model" is the theoretical machinery that converts a measured spectroscopic shift into an extracted atomic constant. For this programme, it must:

1. **Calculate the ideal gradient.** For a perfect circular state |n, n−1, n−1⟩, compute ⟨ψ|∇E|ψ⟩ using the hydrogen-like wavefunctions (tractable analytically, with known quantum-defect corrections for Sr).
2. **Add corrections.** Include the effects of finite orbital width, relativistic corrections, and QED shifts. These are small (10⁻³–10⁻⁴ level) but calculable.
3. **Model the non-ideal terms.** Account for ℓ-mixing from stray fields, cavity perturbations, and tweezer effects. These are the hard parts — they couple state purity to the field environment and may require joint treatment.
4. **Propagate uncertainty.** Assign uncertainties to each correction and combine them to get a total model uncertainty. This determines the precision ceiling for the extracted constant.

The decisive test is the **n-consistency check** (DC-F4): if the same constant Θ is extracted at two different n values and the results agree, the model is validated. If they disagree, the corrections are not under control.

### 12.7 How to read the feasibility gates

The discriminant conditions (DC-F1 through DC-F5) are pass/fail criteria. They answer the question: "What must be true for this programme to produce a metrologically meaningful result?" They are listed in rough order of when they can be tested:

- DC-F1 (resolution) and DC-F2 (purity) are apparatus diagnostics — achievable with the current setup plus technology upgrades.
- DC-F3 (field bounds) requires careful characterisation of the electromagnetic environment.
- DC-F4 (n-consistency) is the decisive physics test — it validates the forward model.
- DC-F5 (cross-comparison) is the scientific payoff — it compares CRS results with conventional measurements.

The **no-go criterion** states that if DC-F4 fails badly (> 5% inconsistency), the programme should not claim precision extraction. This is how the dossier protects against producing numbers that look precise but are actually dominated by uncontrolled model errors.

### 12.8 Where to start reading the literature

For a PhD student approaching this topic:

**Start here:**
- [Gallagher-1994] chapters 1–5 for Rydberg atom basics (quantum defects, Stark effect, lifetimes).
- [Haroche-2006] chapter 3 for circular states and cavity QED.
- [Hölzl-2024] for the specific experimental setup.
- [Wirth-2024] for the quadrupole coupling measurement that this dossier builds on.

**Then read:**
- [Barwood-2004] to understand the current state of Θ(D₅/₂) measurement and what limits it.
- [Lindvall-2025a] to understand the Sr⁺ clock systematic budget and the EQS/tensor-Stark degeneracy.
- [Dubé-2005] for the six-pair cancellation method.

**For broader context:**
- [Safronova-2018] for why precision atomic constants matter for fundamental physics.
- [Sanner-2021] for why Rydberg-series data feeds into clock accuracy.

---

**Endorsement Marker:** Feasibility/candidate programme document under local stewardship. Proposes measurements and estimates viability; does not claim demonstrated precision. All estimates order-of-magnitude, subject to forward-model revision. Per-target classifications are independent and must not be aggregated.

**Cite as:** Ulrich Warring, *Feasibility Dossier: Ionic-Core Clock-State Targets in Circular Rydberg Atoms*, FD-2026-CRS-ClockTargets v1.0 (2026). [https://threehouse-plus-ec.github.io/crs-clocktargets/](https://threehouse-plus-ec.github.io/crs-clocktargets/)

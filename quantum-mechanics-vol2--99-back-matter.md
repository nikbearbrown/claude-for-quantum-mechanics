<!--
    99-back-matter.md
    BACK MATTER — everything that appears after the final chapter.

    Sections in order:
      1. Acknowledgments
      2. About the Authors
      3. About Humanitarians AI
      4. Notes
      5. References
      6. A Note on the Index
      7. Glossary
-->

---

## Acknowledgments

Our thanks go first to the Fellows of the Humanitarians AI Fellows Program, who stress-tested the simulation prompts, broke the early capstone exercises in instructive ways, and improved both. We are grateful to the students who worked through draft chapters and refused to let unclear passages stand, and to the open-source physics education community, whose freely shared lecture notes, problem sets, and visualizations form the intellectual commons this series draws on and hopes to repay. The errors that remain are our own.

---

## About the Authors

**Nik Bear Brown** is an Associate Teaching Professor at the College of Engineering, Northeastern University, where his teaching spans AI, data science, and visualization. His PhD in computer science is from UCLA, with research in computational and systems biology and minors in AI and statistics; he also holds an MS in Information Design and Data Visualization and an MBA from Northeastern, and has worked as a part-time postdoctoral researcher at Harvard Medical School. He founded Humanitarians AI, a 501(c)(3) nonprofit, and Bear Brown & Company, and his current work centers on AI infrastructure for education — including the Irreducibly Human curriculum framework within which this series sits. He is the author of the Computational Skepticism for AI series and the "with LLMs" line of AI-era textbooks.

**Srinivas Sridhar** is University Distinguished Professor of Physics, Bioengineering and Chemical Engineering at Northeastern University, and Lecturer on Radiation Oncology at Harvard Medical School. His research career has ranged across exactly the physics this volume teaches in its applied forms: quantum chaos, superconductivity, collective excitations in materials, nanophotonics, and metamaterials, alongside nanomedicine and neurotechnology — a body of work comprising more than 450 journal articles, patents, and technical reports. His 2003 Nature paper was named among the journal Science's "Breakthroughs of 2003." At Northeastern he served as Vice Provost for Research from 2004 to 2008, founded and directs the Nanomedicine Innovation Center, and directs the Nanomedicine Academy and the NIH CaNCURE program as principal investigator. He is an elected Fellow of the American Physical Society, the American Institute for Medical and Biological Engineering, and the National Academy of Inventors, received the 2016 Biomedical Engineering Society Diversity Award, and has taught and mentored more than 1,200 students. His current research spans nanomedicine, neurotechnology, and quantitative MRI. More at srinivassridhar.com.

The two authors previously collaborated on the open-source textbook *Cancer Biology and Therapeutics* and a 2026 review in *Nano Today*.

---

## About Humanitarians AI

Humanitarians AI Incorporated is a 501(c)(3) nonprofit founded in 2019 in Boston, Massachusetts (EIN 33-1984805). Its Fellows Program mentors early-career researchers and engineers building AI projects in the public interest, and its educational mission is anchored by the Irreducibly Human curriculum — teaching the capabilities AI cannot replace alongside fluent, honest use of the capabilities it provides. Learn more at humanitarians.ai.

---

## Notes

Endnote-style notes appear within the chapters where they arise; this section is reserved for edition notes in future printings.

---

## References

These are the texts a reader of this volume should know, at and just above its level.

- Griffiths, David J., and Darrell F. Schroeter. *Introduction to Quantum Mechanics*. Cambridge University Press.
- Shankar, Ramamurti. *Principles of Quantum Mechanics*. Springer.
- Sakurai, J. J., and Jim Napolitano. *Modern Quantum Mechanics*. Cambridge University Press.
- Cohen-Tannoudji, Claude, Bernard Diu, and Franck Laloë. *Quantum Mechanics*. Wiley.
- Feynman, Richard P., Robert B. Leighton, and Matthew Sands. *The Feynman Lectures on Physics, Volume III: Quantum Mechanics*. Basic Books.
- Nielsen, Michael A., and Isaac L. Chuang. *Quantum Computation and Quantum Information*. Cambridge University Press.

---

## A Note on the Index

There is no index in this book, by design. This is a reflowable Kindle and online edition: page numbers do not exist in any stable sense, so a page-anchored index would be an artifact pointing at nothing. Full-text search performs the lookup function an index once served, for every term rather than a chosen subset. Beyond search, this book is built for integration with Medhavy (medhavy.com), the intelligent-textbook platform from Humanitarians AI — the name is Sanskrit, मेधावी, "intellectually brilliant" — which provides semantic lookup (find the concept, not just the string) and adaptive navigation through the book's structure. In a reflowable, AI-navigable book, the traditional index is the one tool that no longer earns its pages.

---

## Glossary

**Hilbert space** — The complete complex inner-product space in which quantum states live as vectors.

**Ket (|ψ⟩)** — A vector in Hilbert space representing a quantum state, independent of any choice of basis.

**Bra (⟨φ|)** — The linear functional paired with a ket; acting on a ket it produces the inner product, a complex number.

**Inner product (⟨φ|ψ⟩)** — The complex-valued overlap between two states, whose squared modulus gives transition probabilities.

**Adjoint (†)** — The conjugate-transpose of an operator; the operator playing its role on the other side of an inner product.

**Hermitian operator** — An operator equal to its own adjoint, with real eigenvalues and orthogonal eigenstates; the mathematical form of every observable.

**Spectral theorem** — The guarantee that a Hermitian operator's eigenstates form a complete basis, so any state can be expanded in measurement outcomes.

**Projector** — An operator of the form |a⟩⟨a| that picks out a state's component along one basis direction.

**Commutator ([A, B])** — The difference AB minus BA; zero for compatible observables, and the source of uncertainty relations when nonzero.

**Compatible observables** — Observables whose operators commute and therefore share a complete set of simultaneous eigenstates.

**CSCO (complete set of commuting observables)** — A maximal set of mutually commuting operators whose joint eigenvalues uniquely label every state; the reason quantum numbers exist.

**Generalized uncertainty principle** — Robertson's theorem bounding the product of two observables' spreads by the expectation value of their commutator.

**Unitary operator** — A norm-preserving operator; time evolution is unitary because probability must be conserved.

**Heisenberg picture** — The formulation in which states stay fixed and operators carry the time dependence, related to the Schrödinger picture by a unitary transformation.

**Ehrenfest's theorem** — The result that expectation values of position and momentum obey (nearly) classical equations of motion.

**Central potential** — A potential depending only on the distance r, whose rotational symmetry makes energy, L², and L_z simultaneously sharp.

**Spherical harmonics (Yₗᵐ)** — The universal angular eigenfunctions for every central potential, labeled by ℓ and m.

**Ladder operators (L±, a±)** — Operators that step a state up or down in a quantized spectrum, generating the entire spectrum algebraically.

**Spin** — Intrinsic angular momentum with no spatial rotation behind it; an internal degree of freedom obeying the angular momentum algebra, with half-integer values allowed.

**Pauli matrices (σₓ, σᵧ, σ_z)** — The three 2×2 matrices whose algebra completely describes spin-½ and every other two-level system.

**Bloch sphere** — The unit sphere on which every pure state of a qubit or spin-½ corresponds to one point.

**Clebsch-Gordan coefficients** — The entries of the unitary transformation between the uncoupled and coupled bases when two angular momenta are added.

**Singlet and triplet** — The antisymmetric (J = 0) and symmetric (J = 1) combinations of two spin-½ particles, differing by one minus sign and, in hydrogen, by the 21-centimeter photon.

**Reduced mass (μ)** — The effective mass of the relative coordinate when a two-body problem is reduced to one body.

**Degeneracy** — Multiple distinct states sharing one energy eigenvalue, typically reflecting a symmetry of the Hamiltonian.

**Fermion** — A half-integer-spin particle whose multi-particle wave function must be antisymmetric under exchange; electrons are the relevant case.

**Boson** — An integer-spin particle whose multi-particle wave function must be symmetric under exchange, allowing pile-up into one state.

**Slater determinant** — The determinant construction that builds a properly antisymmetric many-fermion state from single-particle orbitals.

**Pauli exclusion principle** — The consequence of antisymmetry that no two identical fermions can occupy the same quantum state; the structural law of the periodic table.

**Screening** — The reduction of the nuclear charge an outer electron experiences due to inner electrons, which breaks hydrogen's ℓ-degeneracy in multi-electron atoms.

**Hund's rules** — The empirical ordering rules — maximize spin, then orbital angular momentum, then fix J by filling fraction — that select an atom's ground-state term.

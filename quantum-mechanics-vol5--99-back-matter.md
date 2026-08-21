<!--
    99-back-matter.md
    BACK MATTER — everything that appears after the final module.
    Back matter continues the arabic page numbering from where
    the final chapter ended. No page restart.
-->

---

## Acknowledgments

This volume, like the four physics volumes it serves, was shaped by the Fellows of Humanitarians AI, who stress-tested modules, caught errors, and insisted that every derivation justify its presence with a quantum problem. Our deepest debt is to our students at Northeastern University, whose questions over many years told us precisely which mathematical tools break down, where, and why — this book is, in a real sense, an organized transcript of their honest confusion and our attempts to answer it.

---

## About the Authors

**Nik Bear Brown** is an Associate Teaching Professor at Northeastern University's College of Engineering. He holds a PhD in Computer Science from UCLA, where his research focused on computational and systems biology with minors in artificial intelligence and statistics, as well as an MS in Information Design and Data Visualization and an MBA. He completed a part-time postdoctoral fellowship at Harvard Medical School. He is the founder of Humanitarians AI, a 501(c)(3) nonprofit dedicated to ethical AI in education, and of Bear Brown & Company. His teaching and writing center on the Irreducibly Human framework — identifying what remains essentially human in learning as AI absorbs the rest — and he is the author of *Computational Skepticism for AI*. His courses span machine learning, AI engineering, and data science, taught to students from widely varying mathematical backgrounds, an experience that directly shaped this volume's just-in-time design.

**Srinivas Sridhar** is University Distinguished Professor of Physics, Bioengineering and Chemical Engineering at Northeastern University and Lecturer on Radiation Oncology at Harvard Medical School. He is the founding director of the Nanomedicine Innovation Center and director of the Nanomedicine Academy and the NIH CaNCURE program, and served as Northeastern's Vice Provost for Research from 2004 to 2008. He is a Fellow of the American Physical Society, the American Institute for Medical and Biological Engineering, and the National Academy of Inventors. His more than 450 publications span quantum chaos, superconductivity, collective excitations, nanophotonics, metamaterials, nanomedicine, and neurotechnology; his 2003 *Nature* paper on negative refraction was named among *Science* magazine's "Breakthroughs of 2003." He received the 2016 Biomedical Engineering Society Diversity Award and has taught more than 1,200 students across physics and engineering. He can be found online at srinivassridhar.com.

The authors' previous collaborations include the open-source *Cancer Biology and Therapeutics* textbook and a 2026 review in *Nano Today*.

---

## About Humanitarians AI

Humanitarians AI Incorporated is a 501(c)(3) nonprofit organization (EIN 33-1984805) founded in 2019 and based in Boston, Massachusetts. Through its Fellows Program, it mentors students and early-career researchers in building open educational resources, and through its Irreducibly Human curriculum it develops teaching materials that pair AI tools with the human judgment AI cannot replace. Learn more at humanitarians.ai.

---

## Notes

This section is reserved for notes and corrections in future editions.

---

## References

The modules in this volume compress material treated at full length in the standard mathematical-methods literature. Readers who want more depth, more rigor, or more breadth should go to these books.

- Boas, Mary L. *Mathematical Methods in the Physical Sciences*. Wiley.
- Arfken, George B., Hans J. Weber, and Frank E. Harris. *Mathematical Methods for Physicists*. Academic Press.
- Riley, K. F., M. P. Hobson, and S. J. Bence. *Mathematical Methods for Physics and Engineering*. Cambridge University Press.
- Strang, Gilbert. *Introduction to Linear Algebra*. Wellesley-Cambridge Press.
- Shankar, R. *Principles of Quantum Mechanics*. Springer. (In particular the opening chapter on the mathematical introduction to linear vector spaces, which extends Modules M-07 through M-09 of this volume.)

---

## A Note on the Index

This book has no index, and that is a decision rather than an omission. It is published as a Kindle and online edition in reflowable text, where page numbers are an artifact of your font size — a page-anchored index would point at nothing stable. Full-text search already does what a printed index did, and does it better. Beyond search, this volume is designed for integration with Medhavy (medhavy.com), the intelligent-textbook platform from Humanitarians AI — the name comes from the Sanskrit मेधावी, "intellectually brilliant" — which provides semantic lookup and adaptive navigation: ask for "the trick for getting rid of a complex denominator" and it will take you to the right part of Module M-01, no alphabetization required.

---

## Glossary

**boundary conditions** — Constraints imposed on a differential equation's solution at the edges of its domain; in quantum mechanics, they select the physically allowed wavefunctions and quantize energy.

**bra** — In Dirac notation, the dual vector ⟨ψ|, which combines with a ket to form an inner product.

**combinatorial multiplicity** — The number of microscopic arrangements consistent with a macroscopic description; the raw count behind entropy and state-counting.

**complex conjugate** — The number z* = a − bi obtained from z = a + bi by flipping the sign of the imaginary part; conjugation underlies the modulus and the inner product.

**determinant** — A scalar computed from a square matrix that measures volume scaling and detects invertibility; det(A − λI) = 0 yields the eigenvalues.

**diagonalization** — Rewriting a matrix in a basis of its own eigenvectors so it acts by simple scaling; the mathematical heart of measurement in quantum mechanics.

**eigenvalue** — A scalar λ for which Av = λv has a nonzero solution v; in quantum mechanics, the possible outcomes of measuring an observable.

**eigenvector** — A nonzero vector that an operator merely rescales; the states with definite values of an observable.

**Euler's formula** — The identity e^(iθ) = cos θ + i sin θ, which converts oscillation into complex exponential arithmetic.

**expectation value** — The probability-weighted average of a quantity over many trials; the bridge between a quantum state and measured statistics.

**Fourier series** — The expansion of a periodic function as a sum of sines and cosines (or complex exponentials) with coefficients extracted by orthogonality.

**Fourier transform** — The continuum limit of the Fourier series, decomposing a function into contributions at every wavenumber; in quantum mechanics it relates the position and momentum representations.

**Hermitian operator** — An operator equal to its own conjugate transpose; its eigenvalues are real and its eigenvectors orthogonal, which is why observables are Hermitian.

**Hilbert space** — A complete vector space equipped with an inner product; the arena in which quantum states live.

**inner product** — A rule assigning a (complex) number to a pair of vectors, generalizing the dot product; it defines length, angle, and orthogonality.

**ket** — In Dirac notation, the state vector |ψ⟩.

**modulus** — The length |z| = √(a² + b²) of a complex number; the modulus squared of an amplitude gives a probability.

**normalization** — Scaling a state or probability distribution so total probability equals one.

**orthogonality** — Zero inner product between two vectors or functions; the property that lets expansion coefficients be extracted one at a time.

**separation of variables** — The technique of seeking solutions as products of single-variable functions, splitting a partial differential equation into ordinary ones.

**spectral theorem** — The guarantee that a Hermitian operator has a complete orthonormal set of eigenvectors with real eigenvalues; the license behind expanding any state in measurement outcomes.

**spherical harmonics** — The functions Yₗᵐ(θ, φ) that solve the angular part of the Schrödinger equation in any central potential; the shapes of atomic orbitals.

**stationarity** — The condition that a functional's value is unchanged to first order under small variations; the calculus-of-variations principle behind the variational method.

**Taylor series** — The expansion of a function in powers of the distance from a chosen point; the engine of approximation throughout physics.

**tensor product** — The construction that combines the state spaces of two systems into the state space of the composite; the home of entanglement.

**unitary matrix** — A matrix whose conjugate transpose is its inverse; unitary evolution preserves inner products and total probability, and quantum gates are unitary.

---

## Acknowledgments

This book exists because of the community around it. We thank the Fellows of the Humanitarians AI Fellows Program, who built simulations, checked derivations, and pushed back on explanations that were clear only to the people who wrote them. We thank the students who stress-tested early drafts of these chapters and whose confusions — always more instructive than their successes — reshaped the hardest sections. And we owe a standing debt to the open-source physics education community, whose tradition of freely shared lecture notes, problem sets, and simulation code set the standard this series tries to live up to.

---

## About the Authors

**Nik Bear Brown** is an Associate Teaching Professor at Northeastern University's College of Engineering, where he teaches artificial intelligence, data science, and information visualization. He holds a PhD in computer science from UCLA, where his work centered on computational and systems biology with minors in AI and statistics, along with an MS in Information Design and Data Visualization and an MBA from Northeastern University. He has also served as a part-time postdoctoral researcher at Harvard Medical School. He is the founder of Humanitarians AI, a 501(c)(3) nonprofit, and of Bear Brown & Company, through which he builds AI infrastructure for education, including the Irreducibly Human curriculum framework that shapes this series. He is the author of *Computational Skepticism for AI* and the "with LLMs" series of technical books on learning and building with large language models.

**Srinivas Sridhar** is University Distinguished Professor of Physics, Bioengineering and Chemical Engineering at Northeastern University and Lecturer on Radiation Oncology at Harvard Medical School. He is the founding director of the Nanomedicine Innovation Center and director and principal investigator of the Nanomedicine Academy and the NIH CaNCURE program, and served as Northeastern's Vice Provost for Research from 2004 to 2008. An elected Fellow of the American Physical Society, the American Institute for Medical and Biological Engineering, and the National Academy of Inventors, he has produced more than 450 journal articles, patents, and technical reports spanning quantum chaos, superconductivity, collective excitations in materials, nanophotonics, metamaterials, nanomedicine, and neurotechnology — a career spent measuring exactly the kinds of real quantum systems this volume teaches students to model. His 2003 *Nature* paper on negative refraction in photonic crystals was listed among the journal *Science*'s "Breakthroughs of 2003." His current research spans nanomedicine, neurotechnology, and quantitative MRI. He received the Biomedical Engineering Society Diversity Award in 2016 and has taught and mentored more than 1,200 students. He can be found online at srinivassridhar.com.

The authors previously collaborated on the open-source *Cancer Biology and Therapeutics* textbook and a 2026 review in *Nano Today*.

---

## About Humanitarians AI

Humanitarians AI Incorporated is a 501(c)(3) nonprofit organization founded in 2019 and based in Boston, Massachusetts (EIN 33-1984805). Through its Fellows Program, it gives early-career researchers and builders mentored experience creating real educational tools, and through its Irreducibly Human curriculum it develops teaching materials for the skills that remain essentially human in an age of capable machines. Learn more at humanitarians.ai.

---

## Notes

Notes and references for specific claims appear within the chapters where they arise; this section is reserved for edition notes in future printings.

---

## References

The following texts shaped this volume and are the natural next steps for readers who want greater depth.

- Griffiths, David J., and Darrell F. Schroeter. *Introduction to Quantum Mechanics*. Cambridge University Press.
- Shankar, Ramamurti. *Principles of Quantum Mechanics*. Springer.
- Sakurai, J. J., and Jim Napolitano. *Modern Quantum Mechanics*. Cambridge University Press.
- Cohen-Tannoudji, Claude, Bernard Diu, and Franck Laloë. *Quantum Mechanics*. Wiley.
- Bender, Carl M., and Steven A. Orszag. *Advanced Mathematical Methods for Scientists and Engineers: Asymptotic Methods and Perturbation Theory*. Springer.

---

## A Note on the Index

This edition has no index, and the omission is deliberate. This book is published as a reflowable Kindle and online edition, where text repaginates with every font size and screen, making page-anchored index entries meaningless. Full-text search already does what a printed index was invented to do. More importantly, this book is designed for integration with Medhavy (medhavy.com), Humanitarians AI's intelligent-textbook platform — the name is Sanskrit, मेधावी, "intellectually brilliant" — which provides semantic lookup, adaptive navigation, and concept-level cross-referencing that no static index could match.

---

## Glossary

**Perturbation theory** — A method for finding approximate energies and states by expanding around a solvable Hamiltonian in powers of a small correction.

**First-order energy correction** — The expectation value of the perturbation in the unperturbed state; the leading shift in an energy level.

**Degenerate subspace** — The set of states sharing a single unperturbed energy, within which the perturbation must be diagonalized before standard formulas apply.

**Good zeroth-order states** — The particular combinations of degenerate states that connect smoothly to the true eigenstates as the perturbation is turned on.

**Fine structure** — The small splittings of hydrogen's energy levels caused by relativistic corrections and spin-orbit coupling.

**Variational principle** — The theorem that any normalized trial state's energy expectation value is an upper bound on the true ground-state energy.

**Trial wave function** — A guessed, parameter-dependent wave function whose energy is minimized to approximate a ground state.

**WKB approximation** — A semiclassical method valid when the potential varies slowly over a de Broglie wavelength, giving wave functions built from the local classical momentum.

**Tunneling** — Quantum passage through a classically forbidden barrier, with probability exponentially sensitive to barrier height and width.

**Turning point** — A position where a particle's energy equals the potential, separating classically allowed from forbidden regions.

**Interaction picture** — A reference frame that rotates away the known part of the time evolution so that only the perturbation drives the dynamics.

**Rabi oscillation** — The coherent cycling of population between two levels driven by a resonant oscillating field.

**Fermi's golden rule** — The formula giving a constant transition rate into a continuum: proportional to the squared matrix element times the density of final states.

**Density of states** — The number of quantum states available per unit energy at a given energy.

**Selection rules** — Conditions on quantum numbers (such as a change of one unit of orbital angular momentum) that determine which radiative transitions are allowed.

**Scattering amplitude** — The complex function of angle whose squared magnitude gives the differential cross-section of a collision.

**Partial wave** — One angular-momentum channel of a scattering problem, characterized entirely by its phase shift.

**Phase shift** — The single real number by which a potential delays or advances each partial wave far from the scatterer.

**Cross-section** — The effective target area a scatterer presents to an incoming beam, measurable by counting deflected particles.

**Born approximation** — The first term of the scattering series, valid for weak potentials or high energies, giving the amplitude as a Fourier transform of the potential.

**Landé g-factor** — The number encoding how orbital and spin angular momentum combine to set an atomic level's magnetic energy splitting.

**Zeeman effect** — The splitting of atomic energy levels in an applied magnetic field.

**Stark effect** — The shifting and splitting of atomic energy levels in an applied electric field.

**Bloch's theorem** — The result that energy eigenstates in a periodic potential are plane waves modulated by a lattice-periodic function, so a perfect crystal does not scatter electrons.

**Band gap** — A range of energies in a crystal containing no allowed states, whose size and filling distinguish metals, insulators, and semiconductors.

**Brillouin zone** — The fundamental interval of crystal momentum containing every physically distinct Bloch state.

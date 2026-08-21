---

## Acknowledgments

Books like this one are collective efforts wearing two names. We are grateful to the Fellows of the Humanitarians AI Fellows Program, who turned chapter prompts into working simulations and caught errors that mattered. We thank the students who worked through draft chapters and told us, with the precision only a confused student has, exactly where the explanations failed. And we acknowledge a broad debt to the open-source physics education community — the freely published lecture notes, simulation libraries, and problem archives that have made quantum information one of the most generously taught subjects in science.

---

## About the Authors

**Nik Bear Brown** is an Associate Teaching Professor in the College of Engineering at Northeastern University, teaching artificial intelligence, data science, and visualization. His PhD in computer science is from UCLA, with research in computational and systems biology and minors in AI and statistics; he also holds an MS in Information Design and Data Visualization and an MBA from Northeastern, and has worked as a part-time postdoctoral researcher at Harvard Medical School. He founded Humanitarians AI, a 501(c)(3) nonprofit that builds AI infrastructure for education, and Bear Brown & Company, and is the architect of the Irreducibly Human curriculum framework on which this series rests. His books include *Computational Skepticism for AI* and the "with LLMs" series on learning and building with large language models — a perspective that shaped this volume's treatment of studying quantum computing in the company of classical AI.

**Srinivas Sridhar** is University Distinguished Professor of Physics, Bioengineering and Chemical Engineering at Northeastern University and Lecturer on Radiation Oncology at Harvard Medical School. His experimental career maps directly onto this volume's subject matter: his group's measurements of quantum chaos in microwave billiards and of superconductivity and collective excitations in materials are the laboratory reality behind the open systems, decoherence, and hardware physics taught here, and his 2003 *Nature* paper on negative refraction was named among the journal *Science*'s "Breakthroughs of 2003." He is the founding director of the Nanomedicine Innovation Center, director and principal investigator of the Nanomedicine Academy and the NIH CaNCURE program, and served as Vice Provost for Research at Northeastern from 2004 to 2008. He is an elected Fellow of the American Physical Society, the American Institute for Medical and Biological Engineering, and the National Academy of Inventors, with more than 450 journal articles, patents, and technical reports across quantum chaos, superconductivity, nanophotonics, metamaterials, nanomedicine, and neurotechnology. His current research spans nanomedicine, neurotechnology, and quantitative MRI; he received the 2016 Biomedical Engineering Society Diversity Award and has taught and mentored more than 1,200 students. He is online at srinivassridhar.com.

The authors previously collaborated on the open-source *Cancer Biology and Therapeutics* textbook and a 2026 review in *Nano Today*.

---

## About Humanitarians AI

Humanitarians AI Incorporated is a 501(c)(3) nonprofit organization founded in 2019 in Boston, Massachusetts (EIN 33-1984805). Its Fellows Program mentors early-career researchers and engineers through the creation of real educational tools, and its Irreducibly Human curriculum focuses on the capabilities that remain essentially human alongside increasingly capable machines. Learn more at humanitarians.ai.

---

## Notes

Notes and citations for specific claims appear within the chapters where they arise; this section is reserved for edition notes in future printings.

---

## References

The following works shaped this volume and are the standard next steps for deeper study.

- Nielsen, Michael A., and Isaac L. Chuang. *Quantum Computation and Quantum Information*. Cambridge University Press.
- Preskill, John. *Lecture Notes for Physics 219: Quantum Computation*. California Institute of Technology.
- Wiseman, Howard M., and Gerard J. Milburn. *Quantum Measurement and Control*. Cambridge University Press.
- Breuer, Heinz-Peter, and Francesco Petruccione. *The Theory of Open Quantum Systems*. Oxford University Press.
- Sakurai, J. J., and Jim Napolitano. *Modern Quantum Mechanics*. Cambridge University Press.

---

## A Note on the Index

There is no index in this edition, by design. The book ships as a reflowable Kindle and online edition, where pagination changes with every device and font setting, so page-anchored index entries would point at nothing. Full-text search performs the lookup function a printed index once served. Beyond that, this book is built for integration with Medhavy (medhavy.com), the intelligent-textbook platform from Humanitarians AI — the name is Sanskrit, मेधावी, meaning "intellectually brilliant" — which provides semantic lookup and adaptive navigation that follow concepts rather than page numbers.

---

## Glossary

**Density operator** — The mathematical object describing a quantum state under uncertainty, combining classical probabilities with quantum amplitudes in a single matrix.

**Pure state** — A state described completely by a single state vector; its density matrix satisfies purity equal to one.

**Mixed state** — A statistical mixture of quantum states, with purity less than one; the generic condition of real systems.

**Purity** — The trace of the squared density matrix, ranging from one for pure states down to the inverse dimension for maximal mixing.

**Partial trace** — The operation that averages over an inaccessible subsystem, producing the reduced density matrix of what remains.

**Reduced density matrix** — The state of one part of a composite system, obtained by tracing out the rest; mixed whenever the parts are entangled.

**Tensor product** — The rule for combining Hilbert spaces, multiplying dimensions rather than adding them, which creates the room where entanglement lives.

**Entanglement** — Correlation between subsystems that no product of individual states can reproduce; the signature resource of quantum information.

**Schmidt decomposition** — The canonical two-subsystem form of a pure state, whose coefficients quantify exactly how entangled it is.

**Bell state** — One of four maximally entangled two-qubit states; the standard unit of shared entanglement.

**CHSH parameter** — The combination of four correlation measurements bounded by 2 under local realism and reaching two times the square root of two in quantum mechanics.

**Local realism** — The assumption that outcomes are predetermined by hidden variables and unaffected by distant measurement choices; refuted by Bell-test experiments.

**Unitary gate** — A reversible, norm-preserving linear operation on qubits; the only evolutions a closed quantum system permits.

**No-cloning theorem** — The proof that no physical operation can copy an arbitrary unknown quantum state.

**Bloch sphere** — The geometric picture of a single qubit, with pure states on the surface and mixed states inside.

**Quantum teleportation** — The protocol that moves an unknown qubit state using one shared Bell pair and two classical bits, destroying the original.

**Decoherence** — The decay of a system's off-diagonal density matrix elements as the environment acquires information about its state.

**Lindblad equation** — The standard master equation governing how an open quantum system's density matrix evolves under both Hamiltonian dynamics and environmental noise.

**Coherence time (T2)** — The timescale over which a qubit's superposition survives before dephasing renders it effectively classical.

**Measurement problem** — The unresolved tension between unitary evolution, which preserves superpositions, and observed measurements, which yield single outcomes.

**Pointer states** — The states selected by environmental interaction as the stable, effectively classical alternatives of a measurement apparatus.

**Transmon** — A superconducting qubit built from an anharmonic oscillator circuit, operated at millikelvin temperatures.

**NV center** — A nitrogen-vacancy defect in diamond whose electron spin serves as a qubit and a nanoscale magnetic sensor, even at room temperature.

**DiVincenzo criteria** — The five requirements — scalability, initialization, coherence, universal gates, and readout — that any quantum computing platform must satisfy.

**Syndrome measurement** — The act of measuring parity relationships among qubits to locate errors without reading, and thus destroying, the encoded state.

**Code distance** — The size of the smallest physical error that can corrupt a logical qubit undetected; larger distance means stronger protection.

**Threshold theorem** — The result that if physical error rates are below a critical value, error correction can suppress logical errors to any desired level.

# Introduction

In 1989, a team at Hitachi's research laboratory led by Akira Tonomura aimed a beam of electrons at a detector, with an electron biprism — the electron-optics equivalent of a double slit — in between. They turned the beam intensity down so low that only one electron was in flight at a time. Each electron arrived as a single bright dot at one definite spot on the screen. A dot is what a particle does. Then they let the experiment run. Ten electrons: scattered dots, no pattern. A few hundred: still noise. Seventy thousand electrons later, the dots had organized themselves into clean, alternating stripes — an interference pattern, which is what a wave does. No electron interacted with any other electron. Each one, alone, somehow carried the wave pattern inside its own statistics. If your picture of the world is built from billiard balls and water waves, that video is a direct assault on it, and you can watch it today, frame by frame.

The gap this book fills is simple to state: most students meet quantum mechanics as a stack of equations to be trusted, when it has become possible — cheaply, on a laptop, this year — to meet it as a thing you build, run, and check.

Our central claim, which not every physicist will endorse, is that a simulation you have built and verified yourself is a legitimate unit of physical intuition — that watching a wave packet you coded tunnel through a barrier you specified, and confirming the transmission against the analytic formula, produces understanding of the same kind that working the integral produces, and that a first course should demand both. Plenty of instructors believe the simulation is dessert, to be served only after the analytic vegetables. We have organized an entire book around the opposite bet.

If you are a sophomore or junior who has finished introductory mechanics and waves, knows single-variable calculus, has met ordinary differential equations and complex numbers at least once, and is now facing a first real course in quantum mechanics — this book was written for you. It works equally well for the self-learner with no course at all, which is part of the point of the series it opens.

What this book is: a complete first course in one-dimensional quantum mechanics, from the experimental wreckage of classical physics through the wave function, the Schrödinger equation, the canonical solvable systems, operators and uncertainty, and a first encounter with measurement and the qubit. Every chapter pairs the standard derivations with a simulation you build using a language model as your coding assistant, under explicit verification rules. A chapter equals roughly a week of a standard course.

What this book is not: it is not a course in the formal machinery of quantum mechanics. Hilbert space, Dirac notation, the spectral theorem, three-dimensional problems, angular momentum, spin, and the hydrogen atom belong to Volume 2 of this series, and we resist the temptation to smuggle them in early. It is not a programming textbook — you will read, modify, and verify code, but we assume your AI tools write the first draft. And it does not pause to teach mathematics: when a gap opens between your calculus and what a derivation needs, Volume 5 of the series, *Math for Quantum Physics*, carries just-in-time support indexed to each chapter here.

One concept recurs so often that you should start watching for it now: **the wave function is the complete description of a quantum system, and yet you never observe it directly — only $|\psi|^2$, the probability density, ever touches an experiment.** Nearly every conceptual knot in this book — normalization, superposition, why $\psi$ must be complex, what measurement does, what the qubit is — unties into some version of that one strange arrangement between the mathematics and the world.

There is also a running thread you can choose to follow or not: the simulations accumulate. Chapter by chapter you build wave packets, wells, barriers, oscillators, and measurement statistics, and in Chapter 11 the parts assemble into a configurable one-dimensional Schrödinger solver — a sandbox that can reproduce every spectrum in the book. Readers who skip the simulation exercises will still get a coherent analytic course; readers who do them will end the book owning a small laboratory.

**How this book is organized.** The eleven chapters fall into three movements.

*Movement I — The world forces the issue (Chapters 1–3).* Chapter 1, **Why Classical Physics Failed: Blackbody, Photoelectric, and the Photon**, shows exactly which experiment broke which classical assumption, and why Planck's quantum was a desperate remedy rather than a bold guess. Chapter 2, **Matter Waves: de Broglie, Davisson–Germer, and the Double Slit**, reverses Einstein's relation to give every particle a wavelength and confirms it with an accidental nickel crystal. Chapter 3, **The Wave Function and Born's Rule**, establishes what $\psi$ means, why it must be complex, and how a probability density differs from a probability.

*Movement II — The equation and its solvable worlds (Chapters 4–8).* Chapter 4, **The Schrödinger Equation and Stationary States**, separates time from space and turns dynamics into an eigenvalue problem. Chapter 5, **The Infinite Square Well**, derives energy quantization from nothing but confinement and boundary conditions. Chapter 6, **Finite Wells, Steps, and Barriers**, lowers the walls and discovers tunneling, from molecular dissociation to alpha decay. Chapter 7, **The Quantum Harmonic Oscillator**, solves the most important potential in physics twice — once by ladder operators, once by brute force — and explains why every stable equilibrium reduces to it. Chapter 8, **The Free Particle and Wave Packets**, confronts the plane wave that cannot be normalized and builds the localized packet that can, complete with group velocity and spreading.

*Movement III — Operators, measurement, and the build (Chapters 9–11).* Chapter 9, **Operators and Uncertainty**, makes observables into Hermitian operators and derives the uncertainty principle as a theorem about states, not a statement about clumsy apparatus. Chapter 10, **Measurement, Superposition, and the Qubit**, states the measurement postulate precisely and applies it to the two-level systems that power quantum computing. Chapter 11, **Capstone: A One-Dimensional Quantum Sandbox**, assembles everything into a general numerical solver and — the real lesson — validates it against the exact results you derived along the way.

**How to read this book.** In order. The chapters build, and Movement II leans hard on Movement I's vocabulary. If you are reviewing rather than learning fresh, Chapters 1–2 can be skimmed, and Chapter 11 can be deferred — though it is where the book pays off. Each chapter closes with worked problems and an LLM exercise block: a copy-paste prompt for building the chapter's core simulation, exploration tasks, and an extension. Do the exercises with pencil first; the section below explains why.

## A Note About AI

This book belongs to a series written explicitly for the AI era, and it would be strange — dishonest, even — to pretend the elephant is not in the room. You have access to language models that can solve every standard problem in this book in seconds. Asked for the energy levels of the finite square well, they will produce the transcendental equation, the graphical solution, and a tidy explanation, instantly and mostly correctly. So we need to be clear about what that means for how you should work.

Here is the physics of the situation, so to speak. Learning happens during *productive struggle* — the stretch of time when you are stuck, when the integral will not come out, when your boundary conditions contradict each other and you have to figure out which assumption is wrong. That discomfort is not an obstacle on the way to understanding; it is the mechanism of understanding. When you hand a problem to an AI before attempting it, you skip the struggle and receive the artifact that struggle would have produced. The solution looks the same in your notebook. It is not the same in your head. You have read a route description; you have not walked the route. And quantum mechanics, more than almost any subject, cannot be learned by recognition. It must be learned by computation, because its results are precisely the ones your intuition will vote against.

So we propose a contract, and the book is structured around it. **Attempt first, always.** Give every problem an honest attempt — twenty minutes minimum of real effort — before any AI sees it. **Then use AI as a colleague, not an oracle.** After your attempt, the model becomes genuinely powerful: ask it to find the error in *your* work rather than to produce its own; ask it for a second derivation of a result you already have; ask it why the boundary term vanishes, or what happens to your answer when $\hbar \to 0$ or $V_0 \to \infty$. Checking limiting cases is a physicist's oldest verification habit, and AI makes it cheap. **Verify everything.** Language models produce confident errors — wrong signs, dropped factors of 2, normalization constants quietly fudged. Every formula an AI gives you is a claim, not a fact, until you have checked it against a known case.

The simulation exercises are where this contract becomes concrete. There, you *should* let the AI write code — that is the exercise. But the chapter prompts force you to specify the physics yourself and to validate the output against analytic results you derived by hand: does the ground-state energy match $\pi^2\hbar^2/2mL^2$? Does the norm stay at 1 as the packet evolves? Does the transmission coefficient reproduce the formula from Chapter 6? An AI that writes beautiful, plausible, wrong code is not a hypothetical; you will meet one. Catching it is the skill. Used this way, the tools in your pocket make you a better physicist than we could have become at your age. Used as an answer machine, they will carry you, smiling, straight past the entire subject.

Go back to the Hitachi laboratory for a moment. Seventy thousand electrons, one at a time, each arriving as a dot, all of them conspiring to paint a wave. By the end of this book you will be able to derive that pattern, predict its spacing, simulate it on your own machine, and verify the simulation against the prediction — which means the strangest experimental result of the twentieth century will be something you can check rather than something you must believe. That is the whole offer of this book. Turn to Chapter 1, where the trouble starts with a glowing piece of iron.

Tags: quantum mechanics, introductory quantum mechanics, wave function, Schrödinger equation, quantum tunneling, harmonic oscillator, uncertainty principle, qubit, physics simulation, AI-assisted learning, undergraduate physics, self-study physics

---

## CLI Simulation Exercise

**Project:** The 1D Quantum Sandbox · **Module this chapter adds:** the sandbox repo skeleton, a SI-internal / eV-display constants-and-units harness, and a D3 smoke-test plot that renders a static Gaussian.

**Tool:** Claude Code (default; Codex CLI or Cowork work identically — in Cowork, open `index.html` in the built-in file preview instead of an external browser).
**Skill level:** Beginner — pure scaffolding and unit bookkeeping; no physics solver is built yet.

**Setup — confirm before you start:**

- [ ] An empty project folder with Claude Code open in it.
- [ ] Node ≥ 18 (plain ES modules) installed to run the checks; a browser to view the D3 smoke plot.
- [ ] Add the standing rule (bottom of this block) to `CLAUDE.md` — this is the first file the project needs.

**The Task — paste into your CLI:**

```
Set up the skeleton of a single-page JavaScript + D3 app called the "1D Quantum Sandbox". Create ONLY these files; do not create or delete anything else, and do not overwrite files that already exist:

1. package.json with { "type": "module" } so .mjs/.js run as ES modules.
2. src/constants.js exporting the physical constants the whole app will use, in SI, with the unit in each name: HBAR_J_S, H_J_S, M_E_KG, E_CHARGE_C, KB_J_PER_K, plus a display helper HC_EV_NM (photon hc in eV·nm). Also export joulesToEv(E_J) and evToJoules(E_eV). IMPORTANT: look these constants up from CODATA — do NOT type them from memory or invent digits; if you are unsure of a value, leave a // LOOK UP comment rather than guessing.
3. src/plot.js: a small D3 helper drawFilledCurve(svgSelector, x, y) that draws a blue filled curve; and index.html that loads D3 (CDN) and calls it on a sampled Gaussian exp(-x^2/2) over x in [-5,5] as a smoke test.
4. test/check-constants.mjs that: (a) asserts evToJoules(joulesToEv(E)) === E to < 1e-12 relative error for several E; (b) asserts HC_EV_NM equals the looked-up value 1239.84 eV·nm to within 0.01; and prints one line "PASS/FAIL units round-trip (max rel err = ...)" and "PASS/FAIL hc = ... eV·nm".

Then RUN `node test/check-constants.mjs` and show me its output, and confirm index.html renders the blue Gaussian. Stop after that.
```

**Expected output:** `package.json`, `src/constants.js`, `src/plot.js`, `index.html`, `test/check-constants.mjs` — and a printed `PASS units round-trip (max rel err ≈ 2e-16)` / `PASS hc = 1239.84 eV·nm`, with `index.html` showing a blue filled Gaussian.

**The golden check (what makes this simulation trustworthy):** the J↔eV conversion round-trips to < 1e-12 relative error, and the harness's constants equal the looked-up CODATA values (ħ = 1.054571817×10⁻³⁴ J·s, hc = 1239.84 eV·nm) — no number invented from memory.

**What to inspect:** that `package.json` has `"type": "module"`; that every constant's name carries its unit; that the smoke-plot curve is blue, filled, and never negative.

**If it goes wrong:** the most likely failure is a constant typed from memory (e.g. `e = 1.6e-19` instead of `1.602176634e-19`), which silently biases every later eV readout. The round-trip test will not catch a wrong-but-consistent constant — so paste CODATA values directly and eyeball each against the source; do not accept "close enough" digits.

**CLAUDE.md note:** add the standing project rule verbatim: "The assistant may write, refactor, and plot numerical code, but must never assert that a result is physically correct. Every solver ships with a check against an analytic limit, a conservation law, or normalization (∑|ψ|²·h = 1); the human confirms the physics. Never invent physical constants or 'expected' numbers — say when a value must be looked up. Never silently fix a sign or a factor of 2 — surface it."

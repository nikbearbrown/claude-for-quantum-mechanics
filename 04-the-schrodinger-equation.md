# Chapter 4 — The Schrödinger Equation and Stationary States

In January 1926, Erwin Schrödinger sought a wave equation for matter. He had been reading de Broglie's 1924 thesis, which argued that particles have wave properties, and he required the equation to reproduce the Bohr energy levels of hydrogen as a consequence rather than a postulate. Within six months he submitted four foundational papers to *Annalen der Physik*. At the center of all of them is

$$i\hbar\,\frac{\partial \Psi}{\partial t} = \hat{H}\,\Psi.$$

This is the time-dependent Schrödinger equation (TDSE). It is a partial differential equation, first order in time and second order in space. When the potential $V$ is time-independent — as it is for the infinite square well, the harmonic oscillator, the hydrogen atom, and nearly every system in this book — the equation can be solved by a standard separation-of-variables method. This chapter develops that method and the stationary-state solutions it produces.

---

## Separation of Variables

The full TDSE in one dimension is

$$i\hbar\,\frac{\partial \Psi}{\partial t} = -\frac{\hbar^2}{2m}\,\frac{\partial^2 \Psi}{\partial x^2} + V(x)\,\Psi.$$

The left side involves only the time derivative; the right side mixes a spatial derivative with $V(x)$. They are coupled, and that coupling is what makes the equation a PDE.

The guess — called the product ansatz — is to try $\Psi(x, t) = \psi(x)\,\phi(t)$. Substitute:

$$i\hbar\,\psi(x)\,\phi'(t) = \phi(t)\,\hat{H}\psi(x).$$

Divide both sides by $\psi(x)\phi(t)$:

$$i\hbar\,\frac{\phi'(t)}{\phi(t)} = \frac{\hat{H}\psi(x)}{\psi(x)}.$$

The left side is a function of $t$ only; the right side is a function of $x$ only. For the two to be equal at every $x$ and every $t$, both sides must equal the same constant. Call that constant $E$.

We now have two separate ordinary differential equations:

$$i\hbar\,\phi'(t) = E\,\phi(t), \tag{4.1}$$

$$\hat{H}\,\psi(x) = E\,\psi(x). \tag{4.2}$$

![Flowchart of the separation of variables: TDSE splits into time ODE and TISE](../images/04-the-schrodinger-equation-fig-01.png)
*Figure 4.1 — Separation of variables applied to the TDSE: the product ansatz decouples time and space, the separation constant E forks the equation into the trivial time ODE and the eigenvalue problem (TISE), with each branch yielding its own solution.*

Equation (4.1) is trivial: it says $\phi(t) = e^{-iEt/\hbar}$, a phase rotating at angular frequency $E/\hbar$. This is a universal form, the same regardless of the potential or the energy level.

Equation (4.2) is the **time-independent Schrödinger equation** (TISE):

$$\boxed{-\frac{\hbar^2}{2m}\,\frac{d^2\psi}{dx^2} + V(x)\,\psi(x) = E\,\psi(x).}$$

This is an eigenvalue problem: find the functions $\psi$ such that $\hat{H}$ acting on $\psi$ returns $\psi$ multiplied by a constant. Those functions are the **stationary states** (or energy eigenstates), and the constants $E$ are the **energy eigenvalues**. The time evolution has been completely factored out — a rotating phase attached to each state — and all the interesting physics now lives in the spatial equation.

---

## What the Constant $E$ Actually Means

The letter $E$ was not chosen arbitrarily. It is the energy, in a precise and operational sense. For any state $\Psi$, the expectation value of the Hamiltonian is

$$\langle \hat{H} \rangle = \int \Psi^*(x,t)\,\hat{H}\,\Psi(x,t)\,dx.$$

For a stationary state $\Psi_n = \psi_n(x)\,e^{-iE_n t/\hbar}$, plug in. The phase $e^{+iE_n t/\hbar}$ from the complex conjugate and the phase $e^{-iE_n t/\hbar}$ from the state multiply to 1. The eigenvalue equation $\hat{H}\psi_n = E_n\psi_n$ pulls $E_n$ out of the integral, and normalization sets $\int|\psi_n|^2\,dx = 1$. The result:

$$\langle \hat{H} \rangle = E_n.$$

That is more than just the average energy. The variance is also zero: $\langle \hat{H}^2\rangle - \langle \hat{H}\rangle^2 = 0$. Every single energy measurement on a particle in state $\psi_n$ returns exactly $E_n$ — no spread, no uncertainty, no distribution. That is what it means to be an eigenstate of an operator. The particle is in a state with a definite energy.

There is also a consistency check. If $E$ were complex with a nonzero imaginary part, the factor $|e^{-iEt/\hbar}|^2 = e^{2\,\mathrm{Im}(E)\,t/\hbar}$ would cause the probability to grow or decay over time, and conservation of probability forbids that. Self-adjoint Hamiltonians — which is what you get with real potentials and physical boundary conditions — have only real eigenvalues. The $E_n$ are always real numbers.

---

## Stationary in What Sense

The full stationary state is

$$\Psi_n(x, t) = \psi_n(x)\,e^{-iE_n t/\hbar}.$$

The probability density is

$$|\Psi_n(x, t)|^2 = |\psi_n(x)|^2\cdot|e^{-iE_n t/\hbar}|^2 = |\psi_n(x)|^2.$$

The time dependence is gone. The probability of finding the particle in any region is constant in time. That is what "stationary" means.

What "stationary" does *not* mean is that the wave function itself is time-independent. $\Psi_n$ is a complex function rotating in the complex plane at angular frequency $E_n/\hbar$. Its real part goes as $\psi_n(x)\cos(E_n t/\hbar)$ and its imaginary part as $-\psi_n(x)\sin(E_n t/\hbar)$. They oscillate 90 degrees out of phase, like the two components of a clock hand. The wave function is a clock; the probability density is the clock's shadow on the floor. The shadow does not move, but the clock is spinning.

![Three-panel diagram showing Re Ψ and Im Ψ oscillating while |Ψ|² remains frozen](../images/04-the-schrodinger-equation-fig-02.png)
*Figure 4.2 — The stationary-state clock: Re Ψ (top) and Im Ψ (middle) oscillate 90° out of phase at three time snapshots, while the probability density |Ψ|² (bottom) is identical at all three times.*

The simulation for this chapter makes this visible. For a single eigenstate, the Re $\Psi$ and Im $\Psi$ panels animate while the $|\Psi|^2$ panel sits frozen. If $|\Psi|^2$ moves when only one eigenstate is populated, the phase is not canceling correctly and the code is wrong.

---

## Why the Laser Cavity Is the Same Problem

Consider a laser cavity: two mirrors facing each other with a gain medium between them. The cavity produces a single, monochromatic, phase-coherent beam at specific frequencies, and not others, because it only sustains standing waves that fit exactly between the mirrors. A wave that does not vanish at both mirror surfaces destroys itself on each round trip through destructive interference. A wave that does vanish at both surfaces builds up coherently. The cavity selects, from a continuous range of possible frequencies, the discrete set that satisfies its boundary conditions.

Quantization in quantum mechanics is this same phenomenon at atomic scales and with a different wave equation. The confining potential supplies the walls; only the spatial modes satisfying the boundary conditions survive; those modes are the stationary states; their discrete spatial frequencies correspond to discrete energies. The Schrödinger equation is the wave equation that determines which modes fit.

---

## Global Phase and Relative Phase

Multiplying the entire wave function by $e^{i\alpha}$ for any real $\alpha$ — a global phase — leaves all observable quantities unchanged. The factor cancels in every probability density $|\Psi|^2$ and every expectation value. States are therefore defined only up to a global phase.

The rotating phase $e^{-iE_n t/\hbar}$ in a stationary state is a global phase for that single state, so it too is unobservable. A stationary state is stationary precisely because the rotating phase carries no measurable information.

When two stationary states are combined, the situation changes. Form the superposition

$$\Psi(x, t) = c_1\,\psi_1(x)\,e^{-iE_1 t/\hbar} + c_2\,\psi_2(x)\,e^{-iE_2 t/\hbar}.$$

The probability density is

$$|\Psi|^2 = |c_1|^2|\psi_1|^2 + |c_2|^2|\psi_2|^2 + 2\,\mathrm{Re}\!\left[c_1^*c_2\,\psi_1^*\psi_2\,e^{-i(E_2-E_1)t/\hbar}\right].$$

The first two terms are frozen. The third oscillates at angular frequency $\omega_{12} = (E_2 - E_1)/\hbar$ — the beat frequency between the two levels. This is the interference term, and it is the signature of superposition. Two states with different energies rotate at different rates; the angle between them in the complex plane grows steadily; and the resulting interference pattern shifts continuously across space. That is the sloshing.

The energy expectation value, by contrast, does not slosh. For any superposition:

$$\langle \hat{H}\rangle = \sum_n |c_n|^2\,E_n.$$

This is a weighted average of the eigenvalues with weights $|c_n|^2$. The cross terms that carry the time dependence vanish by orthogonality of the eigenstates, so the result is exactly time-independent. The probability distribution oscillates across the well while the total energy remains constant — quantum energy conservation expressed in this language.

![Two-column comparison of a single eigenstate (frozen) vs. a two-state superposition (sloshing) at two time snapshots](../images/04-the-schrodinger-equation-fig-03.png)
*Figure 4.3 — Stationary vs. non-stationary: the single eigenstate (left column) shows identical probability densities at both time snapshots; the equal superposition of two eigenstates (right column) shifts its probability peak from the left half to the right half of the well after half a beat period.*

---

## Worked Example — A Single Eigenstate Against a Superposition

Take the ground state of the infinite square well (details in Chapter 5):

$$\psi_1(x) = \sqrt{\frac{2}{L}}\,\sin\!\left(\frac{\pi x}{L}\right), \quad 0 \leq x \leq L.$$

Its stationary state is $\Psi_1(x,t) = \psi_1(x)\,e^{-iE_1 t/\hbar}$, and the probability density follows as:

$$|\Psi_1(x,t)|^2 = \frac{2}{L}\sin^2\!\left(\frac{\pi x}{L}\right).$$

No $t$. The expectation of position:

$$\langle x\rangle = \int_0^L x\cdot\frac{2}{L}\sin^2\!\left(\frac{\pi x}{L}\right)dx = \frac{L}{2},$$

by symmetry. This value sits fixed for all time.

Now mix in the first excited state:

$$\Psi(x,t) = \frac{1}{\sqrt{2}}\,\psi_1(x)\,e^{-iE_1 t/\hbar} + \frac{1}{\sqrt{2}}\,\psi_2(x)\,e^{-iE_2 t/\hbar}.$$

Since both $\psi_1$ and $\psi_2$ are real, the probability density becomes:

$$|\Psi(x,t)|^2 = \frac{1}{2}\!\left[\psi_1^2 + \psi_2^2 + 2\,\psi_1\psi_2\,\cos\!\left(\frac{(E_2-E_1)t}{\hbar}\right)\right].$$

Now $|\Psi|^2$ oscillates, and the probability sloshes back and forth across the well at the beat frequency. The "stationary" property is gone — not through any error, but because a superposition of eigenstates at different energies is genuinely not a stationary state. Stationarity is the privilege of a pure energy eigenstate, and pure energy eigenstates are special.

---

## Building a General Solution

Suppose $\hat{H}$ comes with a complete, orthonormal set of eigenstates $\{\psi_n\}$ and eigenvalues $\{E_n\}$. "Complete" means that any physically reasonable wave function can be built as a superposition of the $\psi_n$; "orthonormal" means $\langle\psi_m|\psi_n\rangle = \delta_{mn}$. For the self-adjoint operators of quantum mechanics, both properties are guaranteed by the spectral theorem of functional analysis — a result of mathematics, not a fresh quantum postulate.

The completeness of the eigenstates for the infinite well is the Fourier sine series theorem, which Fourier proved (for the heat equation) in 1822. The quantum application adds only the probabilistic interpretation and the phase rotation; the completeness itself is a century older than quantum mechanics. There is no quantum mystery here, only old mathematics in new clothing.

Given an initial state $\Psi(x, 0)$, expand it:

$$\Psi(x, 0) = \sum_n c_n\,\psi_n(x), \qquad c_n = \int \psi_n^*(x)\,\Psi(x, 0)\,dx.$$

Because the basis is orthonormal, each projection is exact and unique. We then hang the time-evolution phases on the terms:

$$\Psi(x, t) = \sum_n c_n\,\psi_n(x)\,e^{-iE_n t/\hbar}.$$

This is the complete general solution of the TDSE for any time-independent potential. There are three steps: solve the eigenvalue problem to find $\{\psi_n, E_n\}$; project the initial condition to find $\{c_n\}$; attach the rotating phases. Step one is the hard one. Steps two and three are a calculation.

Stopping at step one gives the stationary states but misses everything that happens when the particle is not in a pure eigenstate. Finding the eigenstates completes the setup, not the problem.

---

## References

- Schrödinger, E. (1926). Quantisierung als Eigenwertproblem. *Annalen der Physik*, 79, 361–376. (First paper on the wave equation. English translation in: Schrödinger, E. *Collected Papers on Wave Mechanics*, Blackie and Son, 1928.)
- Griffiths, D.J., & Schroeter, D.F. (2018). *Introduction to Quantum Mechanics* (3rd ed.). Cambridge University Press. §2.1.
- Shankar, R. (1994). *Principles of Quantum Mechanics* (2nd ed.). Plenum. §5.1.
- von Neumann, J. (1932). *Mathematische Grundlagen der Quantenmechanik*. Springer. (Modern spectral theory and self-adjointness; English translation: *Mathematical Foundations of Quantum Mechanics*, Princeton University Press, 1955.)
- Stein, E.M., & Shakarchi, R. (2003). *Fourier Analysis: An Introduction*. Princeton University Press. Ch. 4.
- Reed, M., & Simon, B. (1975). *Methods of Modern Mathematical Physics, Vol. 2: Fourier Analysis, Self-Adjointness*. Academic Press.

---

*Chapter 5 follows: the infinite square well is the simplest potential with walls. We solve the TISE for* $V = 0$ *inside and* $V = \infty$ *at the boundaries, find the sine-function eigenstates and* $n^2$-*spaced energy levels, and use the results as the concrete basis for everything in this chapter.*

---

## CLI Simulation Exercise

**Project:** The 1D Quantum Sandbox · **Module this chapter adds:** the tridiagonal Hamiltonian builder (diagonal 2t_k + V_j, off-diagonal −t_k) and the ⟨Ĥ⟩ evaluator plus a stationary-phase propagator for a single eigenstate.

**Tool:** Claude Code (default; Codex CLI or Cowork work identically — the check is a `node` script; no browser required for this module).
**Skill level:** Intermediate — the central-difference stencil becomes a matrix, and the factor of 2 on the diagonal is where projects go wrong.

**Setup — confirm before you start:**

- [ ] `src/grid.js` (Chapter 2), `src/wavefn.js` (Chapter 3), `src/constants.js` (Chapter 0) exist and pass their checks.
- [ ] Node ≥ 18 (plain ES modules).
- [ ] The standing rule is in `CLAUDE.md`.

**The Task — paste into your CLI:**

```
Read src/grid.js, src/wavefn.js, src/constants.js (do NOT modify them). Create ONLY the new files below; leave all other files alone.

1. src/hamiltonian.js, exporting:
   - buildH(grid, Varray, mass) -> a tridiagonal Hamiltonian for -hbar^2/2m d^2/dx^2 + V, stored as { diag: Float64Array, off: Float64Array } with t_k = hbar^2/(2*mass*h^2), diag_j = 2*t_k + V_j, off = -t_k. (This is Chapter 4's TISE operator, discretized.)
   - applyH(H, psi) -> complex H*psi (acts on {re, im} arrays).
   - expectationH(H, psi, h) -> sum_j conj(psi_j) * (H psi)_j * h, returned as { re, im }.

2. src/timephase.js, exporting phaseRotate(psi, E_eV, t) that multiplies psi by e^{-iEt/hbar} (Chapter 4's stationary-state phase).

3. test/check-hamiltonian.mjs that:
   - asserts H is real-symmetric: off is constant and diag is real.
   - samples psi_1 = sin(pi x / L) on a hard-wall grid and asserts applyH returns approximately (hbar^2 (pi/L)^2 / 2m) * psi_1 (the free-interior kinetic eigenvalue) to < 1%.
   - asserts expectationH has imaginary part ~ 0 (< 1e-9 of the real part).
   - forms (psi_1 + psi_2)/sqrt(2), phaseRotates each part at its own E, and asserts expectationH is constant across several t to < 1e-9, while |psi|^2 changes (sloshes).
   - asserts a single phaseRotated eigenstate has |psi(t)|^2 equal to |psi(0)|^2 to < 1e-12 at several t (stationarity).
   - prints PASS/FAIL with numbers.

Then RUN `node test/check-hamiltonian.mjs` and show the output. Stop.
```

**Expected output:** `src/hamiltonian.js`, `src/timephase.js`, `test/check-hamiltonian.mjs`, and printed `PASS H symmetric`, `PASS applyH(sin) ≈ (ℏ²k²/2m)·sin`, `PASS ⟨Ĥ⟩ real`, `PASS single eigenstate |Ψ|² frozen`, `PASS superposition ⟨Ĥ⟩ constant while |Ψ|² sloshes`.

**The golden check (what makes this simulation trustworthy):** a single stationary state Ψₙ(x,t) = ψₙ e^(−iEₙt/ℏ) has |Ψₙ(x,t)|² independent of t to < 1e-12 (the phase cancels), and for an equal two-state superposition ⟨Ĥ⟩ = ½E₁ + ½E₂ stays constant in t while |Ψ|² oscillates — the "energy does not slosh" result of this chapter.

**What to inspect:** that the diagonal is 2t_k + V_j (not t_k + V_j); that ⟨Ĥ⟩ comes out real; that the one-eigenstate panel is frozen while the two-state panel moves.

**If it goes wrong:** putting t_k instead of 2t_k on the diagonal makes every energy wrong by roughly a factor of 2. The tell is `applyH(sin)` returning about half (or twice) the expected ℏ²k²/2m — surface the discrepancy rather than "adjusting" t_k to make one number match.

**CLAUDE.md note:** Already covered by the project rule.


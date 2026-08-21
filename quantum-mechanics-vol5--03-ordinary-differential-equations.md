# Module M-03 — Ordinary Differential Equations and Boundary Conditions
*When you need this: the time-independent Schrödinger equation is a second-order linear ODE, and every 1D bound-state and scattering problem in QM Vol. I Chs. 4–7 is solved by the methods here.*

The time-independent Schrödinger equation for a particle in a box is a second-order ordinary differential equation. Everything that follows from it — the allowed energies, the wave functions, the nodes, the quantization — is determined by solving that equation subject to boundary conditions. Understanding the ODE makes all of this accessible.

A differential equation for a function $u(x)$ is an equation relating $u$ to its own derivatives. Its solution is a function — a whole curve, not a number — determined up to free constants that are fixed by boundary or initial conditions. A **second-order** ODE contains $u''$ as the highest derivative; its general solution always has exactly two free constants. This reflects the physical fact that specifying a particle's position and momentum at one point determines its entire trajectory under Newton's law, which is also a second-order equation.

---

## The Characteristic-Equation Method

The central form in quantum mechanics is:

$$u'' + pu' + qu = 0, \qquad p, q \in \mathbb{R} \text{ (constants)}.$$

This equation is **linear**: no term has $u$ or its derivatives raised to a power higher than one. Linearity gives us **superposition**: if $u_1$ and $u_2$ are both solutions, then $Au_1 + Bu_2$ is also a solution for any constants $A$ and $B$. The two-parameter family $Au_1 + Bu_2$ is the general solution.

The characteristic-equation method, due to Euler in the 1740s, proceeds as follows. We assume $u = e^{rx}$, so $u' = re^{rx}$ and $u'' = r^2e^{rx}$. Substituting into the ODE and dividing by $e^{rx}$, which is never zero:

$$r^2 + pr + q = 0.$$

This is a polynomial in $r$ — the **characteristic equation**. Solving the quadratic, the roots $r_1$ and $r_2$ determine the solution family. The discriminant $\Delta = p^2 - 4q$ determines which of three cases applies:

**Two distinct real roots** ($\Delta > 0$): $u = Ae^{r_1 x} + Be^{r_2 x}$.

**Complex conjugate roots** ($\Delta < 0$): write $r = \alpha \pm i\beta$. Then $u = e^{\alpha x}(A\cos\beta x + B\sin\beta x)$.

**Repeated real root** ($\Delta = 0$): $u = (A + Bx)e^{r_0 x}$.

The method is algorithmic. Propose an exponential, substitute, get a polynomial, solve it. The solution can be verified by differentiating and substituting back.

---

## The Two Solution Families in Quantum Mechanics

In quantum mechanics, the potential $V(x)$ divides the real line into regions where $E > V$ and regions where $E < V$. The TISE has a different character in each.

**Oscillatory solution: classically allowed region (**$E > V$).

$$u'' = -k^2 u, \qquad k^2 = \frac{2m(E-V)}{\hbar^2} > 0.$$

Characteristic equation: $r^2 + k^2 = 0$, roots $r = \pm ik$. General solution in two equivalent bases:

$$u(x) = A\cos(kx) + B\sin(kx) \quad\text{(trigonometric basis)}$$
$$= Ce^{ikx} + De^{-ikx} \quad\text{(exponential basis)}$$

Both span the same two-dimensional space. The trigonometric basis is convenient when boundary conditions are at specific points (a condition $u(0) = 0$ immediately eliminates the cosine). The exponential basis is more natural for traveling waves and scattering states.

**Evanescent solution: classically forbidden region (**$E < V$).

$$u'' = +\kappa^2 u, \qquad \kappa^2 = \frac{2m(V-E)}{\hbar^2} > 0.$$

Characteristic equation: $r^2 - \kappa^2 = 0$, roots $r = \pm\kappa$. General solution:

$$u(x) = Ae^{\kappa x} + Be^{-\kappa x}.$$

Both terms are present inside a finite forbidden region. Only when the forbidden region is semi-infinite — extending to $x \to +\infty$, say — does normalizability eliminate the growing term $e^{\kappa x}$, because it diverges.

The sign of $E - V$ determines which case applies. This parallels the three damping regimes of the classical oscillator, with the quantum allowed and forbidden regions corresponding to the classical underdamped (oscillatory) and overdamped (real-exponential) regimes respectively.

![Two-panel figure: oscillatory sinusoidal solution and evanescent exponential solutions](../images/03-ordinary-differential-equations-fig-01.png)
*Figure 3.1 — Two solution families of the TISE: (left) oscillatory sinusoidal solution in the classically allowed region (E > V); (right) decaying normalizable exponential (solid) and growing non-normalizable exponential (dashed) in the classically forbidden region (E < V).*

---

## Boundary Conditions and Quantization

The ODE is satisfied for every value of $E$. The general solution $Ae^{ikx} + Be^{-ikx}$ exists for any positive $E > V$. Nothing in the equation itself restricts $E$ to a discrete set.

Quantization comes from boundary conditions. The logic is:

1. The ODE generates a continuous two-parameter family of solutions at each $E$.
2. Physical boundary conditions — $\psi = 0$ at an infinite wall, $\psi \to 0$ as $x \to \pm\infty$ — are additional constraints.
3. For generic $E$, no solution satisfies all the boundary conditions simultaneously.
4. Only at specific values $E_n$ (the **eigenvalues**) does a non-trivial, physically acceptable solution exist.

The ODE provides the solution families; the boundary conditions select the allowed $E$.

**Matching conditions at potential interfaces.** At a finite step in the potential, both $\psi(x)$ and $\psi'(x)$ must be continuous. This gives two matching conditions at each interface. Combined with the boundary conditions at the edges, the resulting linear system has non-trivial solutions only for specific $E$ values.

If the potential has an infinite jump — the infinite square well — only $\psi$ is matched (to zero at the wall); $\psi'$ may be discontinuous there. A finite-step potential can supply only finite force, requiring $\psi'$ to be continuous; an infinite-step potential can supply an infinite impulse and allows $\psi'$ to jump.

![Step potential with oscillatory ψ for x<0 smoothly matched to decaying ψ for x>0](../images/03-ordinary-differential-equations-fig-03.png)
*Figure 3.3 — Matching conditions at a potential step: oscillatory ψ arriving from the left joins a decaying exponential on the right with equal value and slope at the interface, marked by a junction dot.*

---

## Worked Example: The Infinite Square Well

The TISE inside the well ($0 < x < L$, $V = 0$):

$$\psi'' = -k^2\psi, \qquad k^2 = \frac{2mE}{\hbar^2}.$$

Characteristic equation: $r^2 + k^2 = 0$, roots $r = \pm ik$. General solution:

$$\psi(x) = A\sin(kx) + B\cos(kx).$$

**Boundary condition at** $x = 0$: $\psi(0) = B = 0$. So $\psi(x) = A\sin(kx)$.

**Boundary condition at** $x = L$: $\psi(L) = A\sin(kL) = 0$. For $A \neq 0$: $kL = n\pi$, $n = 1, 2, 3, \ldots$

Allowed wave numbers: $k_n = n\pi/L$.

Allowed energies:

$$\boxed{E_n = \frac{\hbar^2 k_n^2}{2m} = \frac{n^2\pi^2\hbar^2}{2mL^2}.}$$

The constant $A$ is fixed separately by normalization, not by the ODE or boundary conditions.

The energy grows as $n^2$ — a result that follows directly from $k_n = n\pi/L$ and $E \propto k^2$. The discrete energy levels emerge from requiring a standing wave to fit exactly $n$ half-wavelengths into the box.

![Infinite square well with three accepted standing-wave eigenfunctions and one rejected solution](../images/03-ordinary-differential-equations-fig-02.png)
*Figure 3.2 — Quantization from boundary conditions: n = 1, 2, 3 standing waves each touching zero at both walls, placed on baselines at heights proportional to n², and one dashed rejected curve that fails to vanish at the right wall.*

---

## Where These Methods Appear in the Quantum Series

**Vol. I, Ch. 4 — The time-independent Schrödinger equation.** The TISE is a second-order linear ODE in $x$. The strategy — write it as $\psi'' = f(x)\psi$, identify the sign of $f$, write the appropriate general solution, apply boundary conditions, extract $E_n$ — is the characteristic-equation method of this module.

**Vol. I, Ch. 5 — The infinite square well.** The worked example above, carried to completion with normalization. The key point — that quantization emerges from the boundary conditions $\psi(0) = \psi(L) = 0$, not from any special property of the ODE — is the eigenvalue idea of this module.

**Vol. I, Ch. 6 — The quantum harmonic oscillator.** The QHO TISE is not constant-coefficient — the coefficient of $\psi$ depends on $x$ — so the characteristic-equation method applies only asymptotically ($|x| \to \infty$, where $x^2$ dominates). The $\text{large-}|x|$ analysis gives $\psi \sim e^{-m\omega x^2/2\hbar}$, the normalizable choice. Substituting $\psi(x) = H(x)\,e^{-m\omega x^2/2\hbar}$ leads to Hermite's equation for $H(x)$. The termination condition for the resulting series — that $H(x)$ must be a polynomial to preserve normalizability — is the QHO's eigenvalue condition. The foundation is the same ODE logic; the technique is extended to non-constant coefficients.

**Vol. I, Ch. 7 — The finite square well and scattering states.** The finite square well has three regions: interior ($|x| < a$, oscillatory) and exterior ($|x| > a$, evanescent for bound states). The general solution is written in each region; $\psi$ and $\psi'$ are matched at $x = \pm a$. The four matching equations plus normalizability conditions reduce to a transcendental equation for the allowed energies.

For **scattering states** ($E > 0$), both regions have oscillatory solutions. The matching conditions at the interfaces give transmission and reflection amplitudes; the transmission probability $T = |t|^2$ where $t$ is the ratio of transmitted to incident complex amplitude. The exponential basis $e^{\pm ikx}$ is natural here — traveling waves, not standing waves.

**Vol. III, Ch. 5 — WKB approximation.** The WKB approximation treats the TISE as locally constant-coefficient in each infinitesimal region, with local wave number $k(x) = \sqrt{2m(E - V(x))}/\hbar$ varying slowly from point to point. In a classically allowed region the solution is $\psi \approx A(x)\,e^{i\int k\,dx}$. In a forbidden region, $k(x) \to i\kappa(x)$ and the solution is evanescent. At a **turning point** ($E = V(x_0)$, $k = 0$), neither approximation holds and the two WKB solutions are connected by **connection formulas** derived from the exact solution near the turning point (typically Airy functions).

---

## Conventions and Pitfalls

**The sign of the** $\psi''$ **coefficient determines oscillatory vs. evanescent.** Write the TISE as $\psi'' = f(x)\psi$. If $f < 0$ (i.e., $E > V$): oscillatory, use $\sin$ and $\cos$. If $f > 0$ (i.e., $E < V$): evanescent, use $e^{\pm\kappa x}$. The sign is determined by the sign of $E - V$, which changes at the classical turning points.

**Both constants are needed inside a finite well.** Inside a finite square well the solution is oscillatory, and both $\sin(kx)$ and $\cos(kx)$ appear in the general solution. Dropping the cosine by analogy with the infinite well is a common error — in the finite well there is no boundary condition at the center that forces it out. Both terms survive until the matching conditions at the edges are applied.

**Two separate steps: boundary conditions, then normalization.** The ODE gives a two-parameter family; boundary conditions fix one or both constants and select the eigenvalue $E_n$; normalization fixes the remaining overall amplitude. These steps are sequential, not simultaneous. Normalizing before applying boundary conditions is a common source of confusion.

**Continuity of** $\psi'$ **is required at every finite step.** At a finite discontinuity in $V$, both $\psi$ and $\psi'$ must match. At an infinite wall, only $\psi$ matches (to zero); $\psi'$ may jump. Forgetting to match $\psi'$ — not just $\psi$ — is the most common error in finite-well and barrier problems.

**Quantization from boundary conditions, not the ODE.** The ODE is satisfied for every value of $E > V_\text{min}$. Discrete energy levels emerge only when the boundary conditions are imposed.

---

## Quick Practice

1. Show by direct substitution that $\psi(x) = A\sin(kx) + B\cos(kx)$ satisfies $\psi'' = -k^2\psi$. Then apply the boundary conditions $\psi(0) = 0$ and $\psi(L) = 0$ and find the allowed values of $k$ for $A \neq 0$.

2. For the TISE in a region where $V > E$ (classically forbidden), write the general solution. A particle is in the region $x > 0$ only, with $\psi(x) \to 0$ as $x \to +\infty$. Which term in the general solution survives, and why?

3. Write the general solution in each of three regions for a finite square well: region I ($x < -a$), region II ($-a < x < a$, $V = -V_0$), and region III ($x > a$). List the four matching conditions at $x = \pm a$ without solving them. Count: how many equations, how many unknowns (the free constants), and what does this imply about when a non-trivial solution exists?

---

## Go Deeper

The source for this module is *Mathematics for Physics*, Vol. 1, Ch. 11, which develops the characteristic-equation method for the damped oscillator (the classical three-regime picture) and the general second-order linear constant-coefficient framework. For non-constant-coefficient ODEs (needed for the QHO and hydrogen atom), see *Mathematics for Physics*, Vol. 2, Ch. 7, on special functions and separation of variables.

For the QM side, Griffiths, *Introduction to Quantum Mechanics*, 3rd ed., Chs. 2–3 works through the infinite well, harmonic oscillator, and free particle using exactly the ODE methods of this module. Shankar, *Principles of Quantum Mechanics*, Ch. 5 treats the harmonic oscillator with the algebraic (ladder operator) method, which bypasses the ODE but does not replace it for wells and barriers. Cohen-Tannoudji, *Quantum Mechanics*, Vol. 1, Ch. II gives a careful treatment of the one-dimensional Schrödinger equation and matching conditions.

---

## References

Euler, L. "De integratione aequationum differentialium altiorum graduum" (1743, Euler Archive E62) — the exponential substitution $u = e^{rx}$ reducing a linear ODE to its characteristic equation.

Schrödinger, E. (1926). Quantisierung als Eigenwertproblem. *Annalen der Physik*, 79, 361–376. The Schrödinger equation as an eigenvalue problem; energy quantization from boundary conditions.

Griffiths, D. J., & Schroeter, D. F. (2018). *Introduction to Quantum Mechanics* (3rd ed.). Cambridge University Press. Chapters 2–3.

Shankar, R. (1994). *Principles of Quantum Mechanics* (2nd ed.). Plenum. Chapter 5.

Cohen-Tannoudji, C., Diu, B., & Laloë, F. (1977). *Quantum Mechanics*, Vol. 1. Wiley. Chapter II.

---

## CLI Simulation Exercise

**Project:** The QM Math Toolkit · **Module this chapter adds:** `ode.py` — a fixed-step RK4 integrator for second-order linear ODEs, checked against the closed-form solution of `u'' = −k²u` and against the analytic infinite-square-well spectrum.

**Tool:** Claude Code (default; Codex CLI or Cowork work identically — you may let it use `scipy.integrate.solve_ivp` as a cross-check, but the hand-written RK4 is the deliverable).
**Skill level:** Intermediate — writing a correct RK4 step and reducing a 2nd-order ODE to a first-order system is the new skill.

**Setup — confirm before you start:**

- [ ] `qmtoolkit/probability.py` from Chapter 2 (used later to normalize eigenfunctions).
- [ ] Python ≥3.10 with numpy, scipy, matplotlib.
- [ ] Add the standing rule (bottom of this block) to `CLAUDE.md` if it isn't there yet.

**The Task — paste into your CLI:**

```
Add an ODE integrator to qmtoolkit. The time-independent Schrödinger equation is a
2nd-order linear ODE; Vol. I Chs. 4–7 (bound states and scattering) are all solved by
integrating ψ'' = f(x)ψ with boundary conditions.

Create qmtoolkit/ode.py with:
  - rk4_second_order(f, u0, up0, x): integrate u'' = f(x)*u on grid x with initial
    u(x0)=u0, u'(x0)=up0, by reducing to a first-order system [u, u'] and stepping RK4.
    Return the array u(x).
  - box_energies(n_max, m=1.0, L=1.0, hbar=1.0): return the analytic infinite-square-well
    levels E_n = n^2 * pi^2 * hbar^2 / (2 m L^2) for n = 1..n_max.
Leave other files untouched.

Create tests/test_ode.py:
  1. Integrate u'' = -k^2 u with k=3, u(0)=1, u'(0)=0 on x=linspace(0,2,2000). Compare to
     the exact solution cos(k x): max|u_num - cos(k x)| < 1e-6.
  2. Integrate the same with u(0)=0, u'(0)=k and compare to sin(k x): max error < 1e-6.
  3. box_energies: check E_1 : E_2 : E_3 = 1 : 4 : 9 exactly (E_n ∝ n^2), and that
     E_1 equals pi^2*hbar^2/(2 m L^2) to 1e-12. Derive targets from the boxed formula;
     do not hardcode a decimal you did not compute.

Then RUN `pytest -q`. Print the max ODE error for each case and the E_n ratios with
PASS/FAIL. Do not touch unrelated files. Stop after the pytest summary and numbers.
```

**Expected output:** `qmtoolkit/ode.py` and `tests/test_ode.py` added; `pytest` passes; printed `max|u − cos| = 3e-8 PASS`, `max|u − sin| = 3e-8 PASS`, and `E_1:E_2:E_3 = 1:4:9 PASS`.

**The golden check (what makes this routine trustworthy):** RK4 on `u'' = −k²u` reproduces the analytic `cos(kx)` / `sin(kx)` to `1e-6`, and the infinite-well eigenvalues satisfy `E_n = n²π²ℏ²/(2mL²)` — so `E_n ∝ n²`, i.e. the ratios are exactly `1 : 4 : 9` and `E_1 = π²ℏ²/(2mL²)` to machine precision.

**What to inspect:** the RK4 error should fall roughly as step⁴ — halve the grid spacing and the max error should drop by ~16× (confirming a true 4th-order method, not accidental Euler); the energy ratios should be exact integers, since they come from the closed form, not the integrator.

**If it goes wrong:** if the ODE error is ~1e-2 and shrinks only linearly with step size, the "RK4" is actually forward Euler — check that all four slope stages `k1..k4` are used with weights `(k1+2k2+2k3+k4)/6`. A sign slip (`u'' = +k²u`) gives exponential blow-up instead of oscillation — the solution will diverge, not merely be inaccurate.

**CLAUDE.md note:** Already covered by the project rule.

---

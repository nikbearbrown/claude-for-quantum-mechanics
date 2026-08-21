# Module M-02 — Probability, Normalization, and Expectation Values
*Understanding what* $|\psi(x)|^2$ *represents and how to work with it.*

The Born rule tells us that $|\psi(x,t)|^2$ is the probability density for finding a particle at position $x$. The key word here is "density." A density evaluated at a single point is not a probability — it is a density. The probability lives in the integral over a region.

This module develops the probability tools that Born's rule requires: probability densities, normalization, expectation values, and standard deviations. These concepts appear throughout the quantum mechanics that follows, expressed in $\psi$ notation.

---

## Probability Density versus Probability

For a continuous random variable $X$, a **probability density function** (PDF) $f(x)$ satisfies:

$$f(x) \geq 0, \qquad \int_{-\infty}^{\infty} f(x)\,dx = 1.$$

The probability that $X$ falls in the interval $[a, b]$ is

$$P(a \leq X \leq b) = \int_a^b f(x)\,dx.$$

There are three important points to keep in mind. First, $f(x)$ is not itself a probability — it is a density, and it can exceed 1. For example, $f(x) = 2$ for $x\in[0, \frac{1}{2}]$ and zero elsewhere is a perfectly valid PDF. Second, the probability of finding $X$ at exactly one specific value $x_0$ is zero. Only intervals carry nonzero probability. Third, the integral of $f$ over any interval is a number between 0 and 1; the function $f$ itself is not so constrained.

This distinction is fundamental when applying Born's rule. The probability of finding the particle at the single point $x_0$ is zero — not $|\psi(x_0)|^2$. The probability of finding it between $x_0$ and $x_0 + dx$ is $|\psi(x_0)|^2\,dx$ — a density times a width. Normalization requires integrating the density to one, not setting the density equal to one at some point.

![Gaussian PDF with mean dashed line, σ bracket, and shaded probability strip](../images/02-probability-normalization-and-expectation-fig-01.png)
*Figure 2.1 — Probability density function: Gaussian curve with mean marked by a dashed vertical line, standard deviation σ indicated by a bracket, and a shaded strip showing that probability is the area under the curve over an interval, not the function value at a point.*

---

## Mean, Expectation Value, and Variance

The **mean** (expectation value) of $X$ is the probability-weighted average:

$$\mu \equiv \langle X\rangle = \int_{-\infty}^{\infty} x\,f(x)\,dx.$$

The expectation of any function $g(X)$ is:

$$\langle g(X)\rangle = \int_{-\infty}^{\infty} g(x)\,f(x)\,dx.$$

Expectation is **linear**: $\langle aX + b\rangle = a\langle X\rangle + b$ for any constants $a$, $b$. This follows directly from linearity of the integral and does not require any special property of $f$.

The **variance** measures spread as the mean squared deviation from the mean:

$$\sigma^2 = \langle(X - \mu)^2\rangle = \langle X^2\rangle - \langle X\rangle^2.$$

The second form — "mean of the square minus the square of the mean" — comes from expanding $(X-\mu)^2 = X^2 - 2\mu X + \mu^2$ and taking the expectation:

$$\langle X^2 - 2\mu X + \mu^2\rangle = \langle X^2\rangle - 2\mu\langle X\rangle + \mu^2 = \langle X^2\rangle - 2\mu^2 + \mu^2 = \langle X^2\rangle - \mu^2.$$

The **standard deviation** $\sigma = \sqrt{\sigma^2}$ has the same units as $X$ and is the natural measure of the width of a distribution.

The mean is not the same as the most probable value. For a symmetric, unimodal distribution they coincide — and many textbook examples are symmetric — but for asymmetric distributions they can differ substantially. The expectation value $\langle x\rangle$ is the probability-weighted average position, not the location where $|\psi|^2$ peaks.

![Two-panel figure: symmetric distribution where mean equals peak, and skewed distribution where they differ](../images/02-probability-normalization-and-expectation-fig-02.png)
*Figure 2.2 — Mean versus mode: (left) symmetric distribution where the peak and mean coincide; (right) right-skewed distribution with separate dashed lines for the mode and the mean, showing they need not coincide.*

---

## The Gaussian Integral

The most frequently used integral in normalization and expectation-value calculations is

$$\int_{-\infty}^{\infty} e^{-\alpha x^2}\,dx = \sqrt{\frac{\pi}{\alpha}}, \qquad \alpha > 0.$$

To derive this, let $I = \int_{-\infty}^\infty e^{-\alpha x^2}dx$. We square it:

$$I^2 = \left(\int_{-\infty}^\infty e^{-\alpha x^2}dx\right)\!\left(\int_{-\infty}^\infty e^{-\alpha y^2}dy\right) = \int_{-\infty}^\infty\int_{-\infty}^\infty e^{-\alpha(x^2+y^2)}\,dx\,dy.$$

Switching to polar coordinates with $x^2+y^2 = r^2$ and $dx\,dy = r\,dr\,d\theta$, where $r\in[0,\infty)$ and $\theta\in[0,2\pi)$:

$$I^2 = \int_0^{2\pi}d\theta\int_0^\infty e^{-\alpha r^2}r\,dr = 2\pi\cdot\frac{1}{2\alpha} = \frac{\pi}{\alpha}.$$

The $r$-integral follows via $u = \alpha r^2$: $\int_0^\infty e^{-\alpha r^2}r\,dr = 1/(2\alpha)$. Therefore $I = \sqrt{\pi/\alpha}$.

Two extensions follow by differentiating with respect to $\alpha$:

$$\int_{-\infty}^{\infty} x^2 e^{-\alpha x^2}\,dx = \frac{\sqrt{\pi}}{2\alpha^{3/2}}, \qquad \int_{-\infty}^{\infty} x^4 e^{-\alpha x^2}\,dx = \frac{3\sqrt{\pi}}{4\alpha^{5/2}}.$$

Odd-powered integrands $x^{2n+1}e^{-\alpha x^2}$ vanish by symmetry — the integrand is an odd function on a symmetric domain.

---

## Delta-Function Normalization for Plane Waves

The plane wave $\psi_k(x) = e^{ikx}$ is not square-integrable — $\int|e^{ikx}|^2\,dx = \int dx$ diverges. Free-particle states cannot be normalized with a finite constant. They are handled by **Dirac-delta normalization**:

$$\int_{-\infty}^\infty e^{ik'x}e^{-ikx}\,dx = 2\pi\,\delta(k'-k),$$

or, with the convention $\psi_k(x) = e^{ikx}/\sqrt{2\pi}$: $\langle\psi_{k'}|\psi_k\rangle = \delta(k'-k)$.

The delta function replaces the Kronecker delta of discrete bound states: $\langle m|n\rangle = \delta_{mn}$ for a complete orthonormal basis of bound states becomes $\langle k'|k\rangle = \delta(k'-k)$ for free-particle states. Physical observables involve wave packets rather than individual plane waves. A wave packet $\psi(x) = \int\phi(k)e^{ikx}dk/\sqrt{2\pi}$ normalized in position space ($\int|\psi|^2\,dx = 1$) has $\phi(k)$ normalized in momentum space ($\int|\phi|^2\,dk = 1$) by Parseval's theorem. Each plane wave contributes to the integral with weight $|\phi(k)|^2$; no individual plane wave is a physical state, but the superposition is.

---

## Worked Example: The Gaussian Wave Packet

The Gaussian is the central example in quantum mechanics because it minimizes the product $\Delta x\,\Delta p$. Computing its normalization and standard deviation illustrates the template for every expectation-value calculation.

**The wave function.** We take

$$\psi(x) = N\,e^{-x^2/(4\sigma^2)},$$

where $\sigma$ is a given length scale and $N$ is the normalization constant to be determined.

**Normalization.** We compute $\int|\psi|^2\,dx = N^2\int e^{-x^2/(2\sigma^2)}\,dx$. Applying the Gaussian integral with $\alpha = 1/(2\sigma^2)$:

$$N^2\sqrt{\frac{\pi}{1/(2\sigma^2)}} = N^2\sigma\sqrt{2\pi} = 1 \implies N = \frac{1}{(2\pi\sigma^2)^{1/4}}.$$

**Mean position.** The integrand $x|\psi|^2 = N^2 x\,e^{-x^2/(2\sigma^2)}$ is an odd function of $x$ on the symmetric domain $(-\infty, \infty)$. The integral vanishes: $\langle x\rangle = 0$.

**Mean squared position.** Applying $\int x^2 e^{-\alpha x^2}\,dx = \sqrt{\pi}/(2\alpha^{3/2})$ with $\alpha = 1/(2\sigma^2)$:

$$\langle x^2\rangle = N^2\cdot\frac{\sqrt{\pi}}{2(1/(2\sigma^2))^{3/2}} = \frac{1}{(2\pi\sigma^2)^{1/2}}\cdot\frac{\sqrt{\pi}}{2}\cdot(2\sigma^2)^{3/2} = \sigma^2.$$

**Standard deviation.** $\Delta x = \sqrt{\langle x^2\rangle - \langle x\rangle^2} = \sqrt{\sigma^2 - 0} = \sigma$.

The width parameter $\sigma$ in the exponent of the Gaussian is the standard deviation of the position distribution. The Gaussian is the minimum-uncertainty state: its momentum-space wavefunction $\phi(k)$ (the Fourier transform of $\psi(x)$) is also Gaussian with width $1/(2\sigma)$, giving $\Delta p = \hbar/(2\sigma)$ and therefore $\Delta x\,\Delta p = \sigma\cdot\hbar/(2\sigma) = \hbar/2$ — the lower bound in the uncertainty principle.

![Two-panel figure: narrow Gaussian in position space paired with wide Gaussian in momentum space](../images/02-probability-normalization-and-expectation-fig-03.png)
*Figure 2.3 — Gaussian wave packet as a Fourier pair: (left) narrow, tall |ψ(x)|² localized in position; (right) broad, flat |φ̃(p)|² spread in momentum — the reciprocal-width trade-off that saturates the uncertainty bound.*

---

## Normalization Is Preserved in Time

The Schrödinger equation with a Hermitian Hamiltonian $\hat{H} = \hat{H}^\dagger$ preserves normalization: if $\int|\psi(x,0)|^2\,dx = 1$, then $\int|\psi(x,t)|^2\,dx = 1$ for all $t$. The proof uses the continuity equation — the probability current $j = (\hbar/2mi)(\psi^*\partial_x\psi - \psi\partial_x\psi^*)$ satisfies $\partial_t|\psi|^2 + \partial_x j = 0$, and integrating over all space with $j\to0$ at $\pm\infty$ gives $d/dt\int|\psi|^2\,dx = 0$.

This means normalization is an initial condition, not something we must re-impose at every time step. Approximation methods or numerical truncations can violate it; checking that $\int|\psi|^2\,dx$ remains 1 after an approximation is a useful diagnostic.

---

## Where This Appears in the Quantum Series

**Vol. I, Ch. 3 — Born's rule.** The entire chapter is the continuous-distribution formalism of this module applied to $|\psi|^2$: the probability of finding the particle in $[a,b]$ is $\int_a^b|\psi|^2\,dx$; the expectation value of position is $\langle x\rangle = \int x|\psi|^2\,dx$; normalization is $\int|\psi|^2\,dx = 1$. The complex modulus $|\psi|^2 = \psi^*\psi$ requires the complex-number tools of M-01.

**Vol. I, Ch. 9 — The uncertainty principle.** The quantities $\Delta x$ and $\Delta p$ in $\Delta x\,\Delta p \geq \hbar/2$ are standard deviations of position and momentum distributions:

$$(\Delta x)^2 = \langle x^2\rangle - \langle x\rangle^2, \qquad (\Delta p)^2 = \langle p^2\rangle - \langle p\rangle^2.$$

This is $\sigma^2 = \langle X^2\rangle - \langle X\rangle^2$ from this module, applied twice. The Gaussian saturates the bound because the Fourier transform of a Gaussian is a Gaussian, and Fourier transform pairs obey the product inequality $\Delta x\,\Delta k \geq 1/2$ as a theorem of harmonic analysis.

**Vol. IV, Ch. 1 — Measurement theory.** The expectation value of a general observable $\hat{A}$ in state $\psi$ is $\langle\hat{A}\rangle = \langle\psi|\hat{A}|\psi\rangle = \int\psi^*(x)\hat{A}\psi(x)\,dx$. The squared uncertainty is $(\Delta A)^2 = \langle\hat{A}^2\rangle - \langle\hat{A}\rangle^2$ — exactly the variance formula $\sigma^2 = \langle X^2\rangle - \mu^2$. Observable measurement in QM is continuous-distribution probability theory in function-space notation.

---

## Exercises

**Warm-up**

1. *Difficulty: Warm-up — tests the density vs. probability distinction.*
   A wave function has $|\psi(x_0)|^2 = 3\,\text{nm}^{-1}$ at a particular point $x_0$. (a) Is this a probability? Explain why or why not. (b) What is the probability of finding the particle in the interval $[x_0, x_0 + 0.01\,\text{nm}]$, assuming $|\psi|^2$ is approximately constant over this tiny interval? (c) Can $|\psi(x)|^2 > 1$? If so, give an example.
   *Tests: the density-vs-probability distinction and the role of the integration measure.*

2. *Difficulty: Warm-up — tests linearity of expectation and the variance formula.*
   A random variable $X$ has $\langle X\rangle = 3$ and $\langle X^2\rangle = 13$. (a) Compute $\sigma^2 = \langle X^2\rangle - \langle X\rangle^2$ and $\sigma$. (b) Compute $\langle 2X + 5\rangle$ using linearity. (c) Compute $\text{Var}(2X + 5)$ using $\text{Var}(aX + b) = a^2\text{Var}(X)$.
   *Tests: variance formula; linearity of expectation; how variance transforms under linear rescaling.*

3. *Difficulty: Warm-up — tests the Gaussian integral.*
   Evaluate the following integrals directly from the Gaussian integral formula $\int_{-\infty}^\infty e^{-\alpha x^2}\,dx = \sqrt{\pi/\alpha}$ and its derivatives: (a) $\int_{-\infty}^\infty e^{-3x^2}\,dx$; (b) $\int_{-\infty}^\infty x^2 e^{-3x^2}\,dx$; (c) $\int_{-\infty}^\infty x\,e^{-3x^2}\,dx$. For (c), explain why the result is zero without computing the integral.
   *Tests: applying the Gaussian integral formula and its extensions; symmetry argument for odd integrands.*

**Application**

4. *Difficulty: Application — normalization and expectation values for a double-exponential.*
   For the wave function $\psi(x) = Ne^{-\alpha|x|}$ with $\alpha > 0$: (a) find $N$ by normalization (split the integral at $x = 0$); (b) compute $\langle x\rangle$ (explain why it vanishes without computing); (c) compute $\langle x^2\rangle$ and hence $\Delta x = \sqrt{\langle x^2\rangle - \langle x\rangle^2}$; (d) compare the shape of $|\psi|^2$ to the Gaussian — which falls off faster at large $|x|$, and how does this affect the width?
   *Tests: normalization with absolute value; using symmetry to avoid computation; comparison of Gaussian vs. exponential tails.*

5. *Difficulty: Application — two-state superposition and energy uncertainty.*
   A two-state superposition $|\psi\rangle = \tfrac{1}{\sqrt{2}}(|\psi_1\rangle + |\psi_2\rangle)$, where $\langle\psi_m|\psi_n\rangle = \delta_{mn}$ and $\hat{H}|\psi_n\rangle = E_n|\psi_n\rangle$. (a) Show $|\psi\rangle$ is normalized. (b) Compute $\langle\hat{H}\rangle$. (c) Compute $\langle\hat{H}^2\rangle = \langle\psi|\hat{H}^2|\psi\rangle$. (d) Compute $(\Delta H)^2 = \langle\hat{H}^2\rangle - \langle\hat{H}\rangle^2$. (e) The variance is nonzero even though each $|\psi_n\rangle$ is an energy eigenstate. Explain physically: what does a nonzero $\Delta H$ mean about a measurement of energy on this state?
   *Tests: expectation values for superpositions; why energy variance is nonzero for non-eigenstates; connecting algebra to physical interpretation.*

6. *Difficulty: Application — Cauchy distribution and the failure of the mean.*
   The Cauchy-Lorentz distribution $f(x) = 1/(\pi(1+x^2))$ is normalized: $\int_{-\infty}^\infty f(x)\,dx = 1$. (a) Verify the normalization using the antiderivative $\arctan(x)$. (b) Attempt to compute the mean $\langle x\rangle = \int_{-\infty}^\infty x/(\pi(1+x^2))\,dx$ by splitting into $\int_{-\infty}^0$ and $\int_0^\infty$. What goes wrong? (c) This is a distribution with heavy tails ($f(x) \sim 1/x^2$ for large $|x|$). What does this tell you about whether a normalized distribution always has a finite mean? What does it imply for the uncertainty principle if $|\psi|^2$ has heavy tails?
   *Tests: normalization via antiderivative; recognizing a conditionally convergent integral; heavy tails and infinite moments.*

**Synthesis**

7. *Difficulty: Synthesis — Gaussian as the minimum-uncertainty state.*
   For the Gaussian $\psi(x) = (2\pi\sigma^2)^{-1/4}e^{-x^2/(4\sigma^2)}$: (a) the position standard deviation is $\Delta x = \sigma$ (derived in the text); compute $\Delta p$ by Fourier transforming $\psi(x)$ to get $\phi(k)$ and computing $\Delta k$, then using $p = \hbar k$; (b) verify $\Delta x\,\Delta p = \hbar/2$; (c) now shift the Gaussian in momentum space: $\psi(x) = (2\pi\sigma^2)^{-1/4}e^{-x^2/(4\sigma^2)}e^{ik_0 x}$ for real $k_0$. Compute $\langle x\rangle$, $\langle p\rangle$, $\Delta x$, and $\Delta p$. Does $k_0$ change the uncertainty product?
   *Tests: Fourier transform of the Gaussian; the uncertainty product; how a momentum boost shifts the mean without changing the spread.*

8. *Difficulty: Synthesis — preserving normalization under the Schrödinger equation.*
   Let $\psi(x,t)$ satisfy $i\hbar\partial_t\psi = \hat{H}\psi$ with $\hat{H}$ Hermitian. (a) Compute $d/dt\int|\psi|^2\,dx$ by differentiating under the integral and substituting the Schrödinger equation and its complex conjugate. (b) Show the result is $-i/\hbar\int(\psi^*\hat{H}\psi - (\hat{H}\psi)^*\psi)\,dx = 0$ using the definition of Hermiticity $\langle\phi|\hat{H}\psi\rangle = \langle\hat{H}\phi|\psi\rangle$. (c) Identify what would go wrong with normalization conservation if $\hat{H}$ were not Hermitian — give a toy example.
   *Tests: the preservation of normalization as a consequence of Hermiticity; identifying what breaks when Hermiticity fails.*

**Challenge**

9. *Difficulty: Challenge — delta-function normalization and the Parseval bridge.*
   A wave packet is $\psi(x) = \int_{-\infty}^\infty \phi(k)e^{ikx}dk/\sqrt{2\pi}$. (a) Compute $\int|\psi(x)|^2\,dx$ by substituting the Fourier representation and using the Dirac-delta formula $\int e^{i(k'-k)x}\,dx = 2\pi\delta(k'-k)$. Show the result is $\int|\phi(k)|^2\,dk$. This is Parseval's theorem: $L^2$ norm is preserved by the Fourier transform. (b) If $\psi(x)$ is normalized in position space, what does Parseval say about $\phi(k)$? (c) The plane wave $\psi_k(x) = e^{ikx}/\sqrt{2\pi}$ is not in $L^2(\mathbb{R})$ but satisfies $\langle k'|k\rangle = \delta(k'-k)$. Compute $\langle k'|k\rangle$ explicitly by evaluating $\int\psi_{k'}^*(x)\psi_k(x)\,dx$ and identifying the result as a Dirac delta. (d) Explain in one sentence why individual plane waves are not physical states but wave packets are.
   *Tests: Parseval's theorem from the Fourier integral; Dirac-delta normalization by direct calculation; the physical status of plane waves.*

---

## Quick Practice

1. Show that $f(x) = 1/(\pi(1+x^2))$ (the Cauchy-Lorentz distribution) is normalized. Then attempt to compute $\langle x\rangle = \int x/(\pi(1+x^2))\,dx$. What goes wrong, and what does this tell you about whether every normalized distribution has a finite mean?

2. For the wave function $\psi(x) = Ne^{-\alpha|x|}$ with $\alpha > 0$: find $N$ by normalization, compute $\langle x\rangle$ and $\langle x^2\rangle$ by explicit integration (split the domain at $x=0$), and give $\Delta x$.

3. A two-state superposition $\psi = \tfrac{1}{\sqrt{2}}(\psi_1 + \psi_2)$, where $\langle\psi_m|\psi_n\rangle = \delta_{mn}$ and $\hat{H}\psi_n = E_n\psi_n$. Show $\psi$ is normalized. Compute $\langle\hat{H}\rangle$ and $(\Delta H)^2$. The variance is nonzero even though each $\psi_n$ is an energy eigenstate — explain physically what this means about a measurement of energy on this state.

---

## References

Born, M. (1926). Zur Quantenmechanik der Stoßvorgänge. *Zeitschrift für Physik*, 37, 863.

Griffiths, D. J. (2018). *Introduction to Quantum Mechanics* (3rd ed.). Cambridge University Press. Sections 1.2–1.6.

Shankar, R. (1994). *Principles of Quantum Mechanics* (2nd ed.). Plenum. Chapter 4.

Cohen-Tannoudji, C., Diu, B., & Laloë, F. (1977). *Quantum Mechanics*, Vol. 1. Wiley. Chapter III.

---

## CLI Simulation Exercise

**Project:** The QM Math Toolkit · **Module this chapter adds:** `probability.py` — normalize a wavefunction on a grid and compute `⟨x⟩`, `⟨x²⟩`, and `Δx` by numerical integration with the correct `dx` weight, the statistical language Born's rule needs.

**Tool:** Claude Code (default; Codex CLI or Cowork work identically — no difference here).
**Skill level:** Beginner–Intermediate — the only subtlety is remembering the `dx` weight in every integral.

**Setup — confirm before you start:**

- [ ] `qmtoolkit/complex_tools.py` from Chapter 1 (so `|ψ|²` is computed with the complex modulus, not `ψ²`).
- [ ] Python ≥3.10 with numpy, scipy, matplotlib.
- [ ] Add the standing rule (bottom of this block) to `CLAUDE.md` if it isn't there yet.

**The Task — paste into your CLI:**

```
Add probability/normalization tools to qmtoolkit. Vol. I Ch. 3 (Born's rule) and Ch. 9
(the uncertainty principle) use exactly these operations: normalize |ψ|², then compute
expectation values and standard deviations.

Create qmtoolkit/probability.py with:
  - norm_integral(psi, x): return trapezoidal ∫|psi|^2 dx over grid x (use np.abs**2,
    never psi**2; include the dx weight via np.trapz).
  - normalize(psi, x): return psi / sqrt(norm_integral(psi, x)).
  - expectation(psi, x, power=1): return ∫ x^power |psi|^2 dx for a normalized psi.
  - stddev(psi, x): return sqrt(<x^2> - <x>^2).
Leave other files untouched.

Create tests/test_probability.py using the Gaussian ψ(x) = N exp(-x^2/(4σ^2)) whose
analytic results are derived in this chapter:
  1. After normalize(), norm_integral ≈ 1 to 1e-8 (grid: x = linspace(-12σ, 12σ, 4000)).
  2. <x> ≈ 0 to 1e-8 (odd integrand on symmetric domain).
  3. stddev ≈ σ to 1e-6 — the width parameter IS the position standard deviation.
  Pick σ = 1.3 and DERIVE the targets from the closed forms (⟨x²⟩ = σ²); do not hardcode
  a number you did not derive.

Then RUN `pytest -q`. Print each computed value beside its analytic target with PASS/FAIL,
e.g. "Δx = 1.2999998  target σ = 1.3  PASS". Do not touch unrelated files. Stop after the
pytest summary and printed numbers.
```

**Expected output:** `qmtoolkit/probability.py` and `tests/test_probability.py` added; `pytest` passes; printed lines `∫|ψ|²dx = 1.0000000 PASS`, `⟨x⟩ = 3e-16 PASS`, `Δx = 1.29999… target 1.3 PASS`.

**The golden check (what makes this routine trustworthy):** for the normalized Gaussian `ψ = (2πσ²)^{-1/4} e^{-x²/(4σ²)}`, three closed-form facts from this chapter hold — `∫|ψ|²dx = 1` (to `1e-8`), `⟨x⟩ = 0` by symmetry, and `Δx = √(⟨x²⟩ − ⟨x⟩²) = σ` exactly (to `1e-6`, grid-limited).

**What to inspect:** that the normalization integral is 1 and not `1/√(2π)` or `√(2π)` (a missing or doubled `dx`/√-factor); that `Δx` equals σ and not `2σ` or `σ/√2` (confusing the `4σ²` in the exponent with the variance); that `⟨x⟩` is at the rounding floor, confirming the grid is symmetric.

**If it goes wrong:** the usual failure is `∫|ψ|²dx ≈ 2.5` or `0.4` — a dropped `dx` weight (use `np.trapz(..., x)`, not `np.sum`). If `Δx = 2σ`, the code read the exponent's `4σ²` as the variance; the variance of `e^{-x²/(4σ²)}` is `σ²`, so surface that √-factor rather than absorbing it.

**CLAUDE.md note:** Already covered by the project rule.

---

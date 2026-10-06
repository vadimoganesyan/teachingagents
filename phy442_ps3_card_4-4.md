# PHY442 PS3, problem 4.4: verifier card

*Rectangular barrier of height V0 and width a, particle incident from the left (extended to tunneling)*

**How to use this card.** It does not contain the answers. For each part it lists
tests you can run on *your own* result: plug in the numbers given, take the limits,
try the special cases. A result that passes every test is probably right; a result
that fails one has gone wrong somewhere, and the "wrong turns" list names the usual
places. Check the conventions first: the tests assume exactly the symbols and signs
defined below.

> 4.4 (extended to tunneling). Rectangular barrier of height V₀ and width a, particle incident from the left.

## Conventions

- Regions: I ($x<0$), II ($0<x<a$), III ($x>a$); the particle comes in from the left with amplitude 1.
- $k=\sqrt{2mE}/\hbar$ outside (both sides), $k_2=\sqrt{2m(E-V_0)}/\hbar$ inside for $E>V_0$, $\kappa=\sqrt{2m(V_0-E)}/\hbar$ inside for $E<V_0$.
- $g\equiv 2mV_0a^2/\hbar^2$ is the only dimensionless combination of the barrier parameters; $T$ depends only on $E/V_0$ and $g$.
- $T$ is the transmitted probability flux over the incident flux. Since $k$ is the same on both sides, $T=|t|^2$ with no velocity ratio.

## Symbols

| Symbol | Meaning | Units | Assumptions |
|---|---|---|---|
| $E$ | energy of the incident particle | J (or eV) | E > 0 |
| $V_{0}$ | barrier height | J (or eV) | V_0 > 0 |
| $a$ | barrier width (barrier occupies 0 < x < a) | m | a > 0 |
| $m$ | particle mass | kg | m > 0 |
| $k$ | wavenumber outside the barrier, $k=\sqrt{2mE}/\hbar$ | 1/m | same on both sides |
| $k_{2}$ | wavenumber inside for $E>V_0$, $k_2=\sqrt{2m(E-V_0)}/\hbar$ | 1/m | E > V_0 |
| $\kappa$ | decay constant inside for $E<V_0$, $\kappa=\sqrt{2m(V_0-E)}/\hbar$ | 1/m | E < V_0 |
| $g$ | dimensionless barrier strength, $g = 2mV_0a^2/\hbar^2$; note $k_2a=\sqrt{g(E/V_0-1)}$ and $\kappa a=\sqrt{g(1-E/V_0)}$ | none | g > 0 |
| $T$ | transmission probability $|t|^2$ (incident amplitude 1) | none | 0 < T <= 1 |

**Spot checks.** The spot checks give dimensionless inputs $E/V_0$ and $g=2mV_0a^2/\hbar^2$ (equivalently, work in units $\hbar=m=V_0=1$ with $a=\sqrt{g/2}$). From them $k_2a=\sqrt{g(E/V_0-1)}$ and $\kappa a=\sqrt{g(1-E/V_0)}$; those values are listed too so you can check your intermediate step.

## Part (a)

> (a) For E > V₀, obtain T(E). Show that T = 1 exactly when k₂a = nπ (k₂ the wavenumber inside) and interpret the resonance.

**Spot checks** (relative tolerance 0.001):

| Check | Inputs | Derived | Your result should be |
|---|---|---|---|
| a.S1 | E/V0 = 1.054, g = 7.908 | k_2 a = 0.653477 | T = 0.381176 |
| a.S2 | E/V0 = 3.038, g = 55.2 | k_2 a = 10.606489 | T = 0.966587 |
| a.S3 | E/V0 = 3.064, g = 12.84 | k_2 a = 5.147986 | T = 0.96853 |

**Other checks:**

- **a.L1** (Limit). As $E\to\infty$ (at fixed barrier), $T\to 1$.
- **a.L2** (Limit). As $E\to V_0^+$, $T\to (1+g/4)^{-1}$, which is less than 1: the top of the barrier is not a resonance.
- **a.P1** (Special case). At $E=V_0+\pi^2\hbar^2/2ma^2$ (so $k_2a=\pi$, the $n=1$ resonance), $T=1$ exactly.
- **a.P2** (Special case). At $E=V_0+4\pi^2\hbar^2/2ma^2$ ($k_2a=2\pi$), $T=1$ exactly.
- **a.C1** (Dependence). With $k_2$ treated as given, $T$ depends on $k_2$ and $a$ only through the product $k_2a$ (the number of half-wavelengths in the barrier).
- **a.C2** (Dependence). With $k_2a$ held fixed, $T$ depends on $E$ and $V_0$ only through the ratio $E/V_0$.
- **a.T1** (Structure). $T\le 1$ for every $E>V_0$, with equality exactly at $\sin(k_2a)=0$, i.e. $k_2a=n\pi$ with $n=1,2,\dots$ (an integer number of half-wavelengths $\lambda_2/2$ fits in the barrier, so the reflections from the two edges cancel; same mechanism as a half-wave antireflection film).
- **a.T2** (Structure). Every resonance energy lies above the barrier: $E_n=V_0+n^2\pi^2\hbar^2/2ma^2$, i.e. $E_n/V_0=1+n^2\pi^2/g$.
- **a.T3** (Structure). Between resonances $T$ dips to minima $[1+V_0^2/(4E(E-V_0))]^{-1}$ (where $\sin^2 k_2a=1$); these minima rise toward 1 as $E$ grows.

**Wrong turns** (the check in brackets catches it):

- *a.W1*: multiplying $|t|^2$ by a velocity ratio $k_2/k$ (or $k/k_2$) as if the two outer regions had different wavenumbers [a.S1, a.S2, a.S3]
- *a.W2*: losing the factor 4 in the denominator $4E(E-V_0)$ [a.S1, a.S2, a.S3]
- *a.W3*: writing $E^2$ (or $V_0^2$) in place of $E(E-V_0)$ under the $\sin^2$ [a.S1, a.S2, a.S3]
- *a.W4*: counting $k_2a=0$ ($n=0$, i.e. $E=V_0$) as a resonance with $T=1$ [a.L2, a.T1]
- *a.W5*: placing the resonances at $E_n=n^2\pi^2\hbar^2/2ma^2$ without adding $V_0$ [a.P1, a.P2, a.T2]
- *a.W6*: using the outside wavenumber $k$ instead of $k_2$ inside the sine [a.S1, a.S2, a.S3, a.P1]

## Part (b)

> (b) For E < V₀, obtain T(E) by k₂ → iκ, κ = √(2m(V₀ − E))/ħ, in terms of sinh(κa).

**Spot checks** (relative tolerance 0.001):

| Check | Inputs | Derived | Your result should be |
|---|---|---|---|
| b.S1 | E/V0 = 0.05324, g = 35.16 | kappa a = 5.769582 | T = 7.85611e-06 |
| b.S2 | E/V0 = 0.9267, g = 8.165 | kappa a = 0.773624 | T = 0.271831 |
| b.S3 | E/V0 = 0.835, g = 56.15 | kappa a = 3.043805 | T = 0.00500347 |

**Other checks:**

- **b.L1** (Limit). As $E\to 0^+$, $T\to 0$ (linearly in $E$).
- **b.L2** (Limit). As $E\to V_0^-$, $T\to(1+g/4)^{-1}$: finite, and the same value part (a) gives from above.
- **b.P1** (Special case). At $E=V_0/2$ exactly, $T=\mathrm{sech}^2(\kappa a)=1/\cosh^2(\kappa a)$.
- **b.Y1** (Symmetry). $T$ is unchanged under $\kappa\to-\kappa$ (it contains $\kappa$ only through $\sinh^2\kappa a$).
- **b.C1** (Dependence). With $\kappa$ treated as given, $T$ depends on $\kappa$ and $a$ only through $\kappa a$.
- **b.C2** (Dependence). With $\kappa a$ held fixed, $T$ depends on $E$ and $V_0$ only through $E/V_0$.
- **b.K1** (Continuity). Your (b) and (a) results meet at $E=V_0$: both tend to $(1+g/4)^{-1}$, so $T(E)$ is continuous through the top of the barrier.
- **b.T1** (Structure). $0<T<1$ for every $0<E<V_0$ and every $a>0$; a value above 1 or below 0 means a sign error.

**Wrong turns** (the check in brackets catches it):

- *b.W1*: replacing $\sin\to\sinh$ without flipping the sign of $E-V_0\to-(V_0-E)$ (the result exceeds 1 or turns negative) [b.S1, b.S2, b.S3, b.L2, b.P1, b.K1, b.T1]
- *b.W2*: keeping $\sin(\kappa a)$ instead of $\sinh(\kappa a)$ after $k_2\to i\kappa$ [b.S1, b.S2, b.S3, b.L2, b.P1, b.K1]
- *b.W3*: promoting the $E=V_0/2$ result $\mathrm{sech}^2(\kappa a)$ to all energies [b.S1, b.S2, b.S3, b.L2]
- *b.W4*: losing the factor 4 in $4E(V_0-E)$ [b.S1, b.S2, b.S3, b.L2, b.P1]

## Part (c)

> (c) Opaque barrier, κa ≫ 1: show T ≈ 16 (E/V₀)(1 − E/V₀) e^{−2κa}.

- The spot values below are values of the opaque-barrier *approximation* itself, not of the exact (b) result; the identity check says how far apart they are.

**Spot checks** (relative tolerance 0.001):

| Check | Inputs | Derived | Your result should be |
|---|---|---|---|
| c.S1 | E/V0 = 0.5484, g = 118.4 | kappa a = 7.31228 | T_approx = 1.76443e-06 |
| c.S2 | E/V0 = 0.7049, g = 33.9 | kappa a = 3.162893 | T_approx = 0.00595611 |
| c.S3 | E/V0 = 0.2895, g = 58.21 | kappa a = 6.431035 | T_approx = 8.539e-06 |

**Other checks:**

- **c.L1** (Limit). As $\kappa a\to\infty$ (here: $a\to\infty$ at fixed $E<V_0$), the ratio of your approximation to the exact (b) result tends to 1.
- **c.L2** (Limit). As $E\to 0^+$, $T_{\rm approx}\to 0$ linearly in $E$.
- **c.P1** (Special case). At $E=V_0/2$ the prefactor is 4: $T_{\rm approx}=4e^{-2\kappa a}$ (compare $\mathrm{sech}^2\kappa a\approx 4e^{-2\kappa a}$ from part (b)).
- **c.Y1** (Symmetry). At fixed $\kappa a$ the prefactor $16(E/V_0)(1-E/V_0)$ is symmetric under $E\leftrightarrow V_0-E$ and maximal (= 4) at $E=V_0/2$.
- **c.C1** (Dependence). $T_{\rm approx}$ depends on $\kappa$ and $a$ only through $\kappa a$.
- **c.I1** (Identity). Exactly: $T_{\rm approx}/T_{\rm exact}=1+\big[16(E/V_0)(1-E/V_0)-2\big]e^{-2\kappa a}+e^{-4\kappa a}$, so the relative error of the approximation is of order $e^{-2\kappa a}$ (about $10^{-4}$ at $\kappa a=5$).

**Wrong turns** (the check in brackets catches it):

- *c.W1*: writing $T\approx e^{-2\kappa a}$ with no prefactor (a factor 4 off at $E=V_0/2$, worse elsewhere) [c.S1, c.S2, c.S3, c.L1, c.P1, c.I1]
- *c.W2*: approximating $\sinh\kappa a\approx e^{\kappa a}$ instead of $e^{\kappa a}/2$ (prefactor 4 instead of 16) [c.S1, c.S2, c.S3, c.L1, c.P1, c.I1]
- *c.W3*: ending with $e^{-\kappa a}$: the square of $\sinh$ was not carried through [c.S1, c.S2, c.S3, c.L1, c.P1, c.I1]

## Part (d)

> (d) Numbers. Electron, E = 1 eV, V₀ = 2 eV, a = 1 nm: compute κ and T. By what factor does T change if a = 2 nm? If the particle is a proton at the same E, V₀, a?

- Constants used for the expected values: $\hbar=1.054571817\times10^{-34}$ J s, $m_e=9.1093837015\times10^{-31}$ kg, $m_p=1.67262192369\times10^{-27}$ kg, 1 eV $=1.602176634\times10^{-19}$ J. Use at least six significant figures: because $T\sim e^{-2\kappa a}$, a relative error $\delta$ in $\kappa$ changes $T$ by $2\kappa a\,\delta$, and four-digit constants ($\hbar=1.055\times10^{-34}$ etc.) already move $T$ by about 0.5% at $\kappa a\approx5$, more than the tolerance below.
- Inputs $E$, $V_0$ in eV and $a$ in nm; $\kappa$ is reported in nm$^{-1}$. $T$ is the exact (b) formula. $T(2a)/T(a)$ is the ratio of the exact values. For the proton report $\log_{10}T_p$, since $T_p$ underflows double precision.

| Symbol | Meaning | Units | Assumptions |
|---|---|---|---|
| $E$ | energy in eV | eV | 0 < E < V_0 |
| $V_{0}$ | barrier height in eV | eV |  |
| $a$ | barrier width in nm | nm |  |

**Spot checks** (relative tolerance 0.002):

| Check | Inputs | Your result should be |
|---|---|---|
| d.S1 | E [eV] = 1.29, V0 [eV] = 1.964, a [nm] = 1.101 | kappa_e [1/nm] = 4.20599; T_e = 0.000342579; T_e(2a)/T_e(a) = 9.50182e-05; log10 T_p = -171.798 |
| d.S2 | E [eV] = 0.4013, V0 [eV] = 2.701, a [nm] = 0.4667 | kappa_e [1/nm] = 7.76916; T_e = 0.00143488; T_e(2a)/T_e(a) = 0.000708956; log10 T_p = -134.646 |
| d.S3 | E [eV] = 1.031, V0 [eV] = 1.643, a [nm] = 0.405 | kappa_e [1/nm] = 4.00788; T_e = 0.136114; T_e(2a)/T_e(a) = 0.0414991; log10 T_p = -59.8412 |

**Other checks:**

- **d.I1** (Identity). $\kappa_p/\kappa_e=\sqrt{m_p/m_e}=42.85$ at the same $E$ and $V_0$.
- **d.T1** (Structure). Doubling $a$ multiplies $T$ by very nearly $e^{-2\kappa a}$ (the ratio of exact values differs from this by a relative amount of order $e^{-2\kappa a}$ itself), not by $e^{-4\kappa a}$.
- **d.T2** (Structure). Useful rule for electrons: $\kappa\approx 5.12\,\mathrm{nm}^{-1}\times\sqrt{(V_0-E)/\mathrm{eV}}$ (equivalently $0.512$ Å$^{-1}$ per $\sqrt{\mathrm{eV}}$). Check your unit handling against it.
- **d.T3** (Structure). For the proton $\kappa a$ is in the hundreds, so $T_p$ is far below $10^{-100}$ but not zero; a calculator or double-precision code will show 0. Report the logarithm.

**Wrong turns** (the check in brackets catches it):

- *d.W1*: forgetting eV $\to$ J inside the square root (κ off by a factor $\sim 10^{9.4}$) [d.S1, d.S2, d.S3, d.T2]
- *d.W2*: computing the factor for $a=2$ nm as $e^{-2\kappa\cdot 2\,\mathrm{nm}}$ instead of the ratio $T(2a)/T(a)\approx e^{-2\kappa\,\Delta a}$ [d.S1, d.S2, d.S3, d.T1]
- *d.W3*: forgetting that $\kappa\propto\sqrt m$ when switching to the proton [d.S1, d.S2, d.S3, d.I1]
- *d.W4*: reporting the proton transmission as exactly 0 (double-precision underflow); give $\log_{10}T_p$ instead [d.S1, d.S2, d.S3, d.T3]
- *d.W5*: losing the factor 2 in $\sqrt{2m(V_0-E)}$ [d.S1, d.S2, d.S3, d.T2]

## Part (e)

> (e) Sketch T(E) for 0 < E < 3V₀ from (a)–(c), marking the resonances.

**Other checks:**

- **e.L1** (Limit). The curve starts at $T=0$ for $E\to 0^+$ and rises linearly in $E$.
- **e.L2** (Limit). For $E\gg V_0$ the curve approaches $T=1$ from below.
- **e.L3** (Limit). The lower envelope of the oscillations, $[1+V_0^2/4E(E-V_0)]^{-1}$, also tends to 1: the dips get shallower with increasing $E$.
- **e.P1** (Special case). $T=1$ at $E_1/V_0=1+\pi^2/g$, and again at $E_n/V_0=1+n^2\pi^2/g$; mark these. The number of resonances below $3V_0$ is the number of integers $n$ with $n^2\pi^2/g<2$.
- **e.K1** (Continuity). At $E=V_0$ the curve passes smoothly through $T=(1+g/4)^{-1}$, well below 1: no cusp, no peak.
- **e.T1** (Structure). Below $V_0$ the curve increases monotonically (tunneling, $T\sim e^{-2\kappa a}$ for $\kappa a\gg1$, so it is tiny over most of the range on a linear plot); above $V_0$ it oscillates between 1 at the resonances and minima that approach 1.
- **e.T2** (Structure). The first resonance is above $V_0$ by $\pi^2\hbar^2/2ma^2$; the resonances are not equally spaced in $E$ (spacing grows like $n$).

**Wrong turns** (the check in brackets catches it):

- *e.W1*: drawing a peak, cusp or $T=1$ at $E=V_0$ [e.K1, e.T1]
- *e.W2*: marking resonances at $n^2\pi^2\hbar^2/2ma^2$ (below the barrier) or equally spaced [e.P1, e.T2]

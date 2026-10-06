# PHY240 PS2, problem 7: verifier card

*Standing waves (counter-propagating waves, E-B misalignment, energy sloshing, zero net energy flow)*

**How to use this card.** It does not contain the answers. For each part it lists
tests you can run on *your own* result: plug in the numbers given, take the limits,
try the special cases. A result that passes every test is probably right; a result
that fails one has gone wrong somewhere, and the "wrong turns" list names the usual
places. Check the conventions first: the tests assume exactly the symbols and signs
defined below.

> The two waves are $\vec E_1(x,t)=E_{10}\cos(kx-\omega t)\,\hat y$ and $\vec E_2(x,t)=E_{20}\cos(kx+\omega t+\phi)\,\hat y$.

## Conventions

- Phases: $a=kx-\omega t$ for wave 1 (moving toward $+\hat x$), $b=kx+\omega t+\phi$ for wave 2 (moving toward $-\hat x$). Both electric fields are along $\hat y$.
- $\vec B$ follows from Faraday's law, $\partial_t B_z=-\partial_x E_y$, with the integration constant set to zero; for a single plane wave this gives $\vec B=\hat k\times\vec E/c$ with $\hat k$ the direction of travel of *that* wave.
- $\mu_0=1/(\epsilon_0c^2)$, so $u_B=B^2/2\mu_0=\epsilon_0(cB)^2/2$ and $\vec S=\vec E\times\vec B/\mu_0=\epsilon_0c\,\vec E\times(c\vec B)$.
- Parts 2-4 assume $E_{10}=E_{20}\equiv E_0$ and use $X=kx+\phi/2$, $T=\omega t+\phi/2$.

## Symbols

| Symbol | Meaning | Units | Assumptions |
|---|---|---|---|
| $E_{10}$ | amplitude of wave 1 (travels toward $+\hat x$) | V/m | E_{10} > 0 |
| $E_{20}$ | amplitude of wave 2 (travels toward $-\hat x$) | V/m | E_{20} > 0 |
| $E_{0}$ | common amplitude when $E_{10}=E_{20}$ (parts 2-4) | V/m | E_0 > 0 |
| $k$ | wavenumber, $k=\omega/c=2\pi/\lambda$ | 1/m | k > 0 |
| $\omega$ | angular frequency | 1/s | \omega > 0 |
| $\phi$ | phase of wave 2 relative to wave 1 at $x=t=0$ | rad | any real value |
| $a$ | $a = kx-\omega t$ (phase of wave 1) | rad |  |
| $b$ | $b = kx+\omega t+\phi$ (phase of wave 2) | rad |  |
| $X$ | $X = kx+\phi/2$ (standing-wave spatial phase, parts 2-4) | rad |  |
| $T$ | $T = \omega t+\phi/2$ (standing-wave temporal phase, parts 2-4) | rad |  |
| $cB_{z}$ | $c$ times the $\hat z$ component of $\vec B$ (same units as $E$) | V/m |  |
| $u$ | energy density $u=u_E+u_B$, $u_E=\epsilon_0E^2/2$, $u_B=B^2/2\mu_0$ | J/m^3 |  |
| $S_{x}$ | $\hat x$ component of the Poynting vector $\vec S=\vec E\times\vec B/\mu_0$ | W/m^2 |  |

**Spot checks.** Spot checks give the phases $kx$ and $\omega t$ (radians) and $\phi$ directly, so you never need numerical values of $k$ or $\omega$. Magnetic fields are quoted as $cB$ (in V/m); energy densities as $u/(\epsilon_0E_0^2)$; the Poynting vector as $S_x/(\epsilon_0cE_0^2)$. Components not listed are zero.

## Part (1)

> 1. Find $\vec B_1$ and $\vec B_2$ and the total $\vec B$. Show that $|\vec B|\neq|\vec E|/c$ in general: find a point and time where $\vec E=0$ but $\vec B\neq0$, and vice versa.

**Spot checks** (relative tolerance 0.001):

| Check | Inputs | Your result should be |
|---|---|---|
| 1.S1 | E10 [V/m] = 0.853, E20 [V/m] = 1.848, phi [rad] = 0.6166, kx [rad] = 4.617, omega t [rad] = 5.371 | E = (0, -0.0824533, 0); cB = (0, 0, 1.32605) |
| 1.S2 | E10 [V/m] = 2.899, E20 [V/m] = 2.179, phi [rad] = 3.806, kx [rad] = 0.4034, omega t [rad] = 0.8686 | E = (0, 3.36996, 0); cB = (0, 0, 1.81189) |
| 1.S3 | E10 [V/m] = 1.556, E20 [V/m] = 2.455, phi [rad] = 5.589, kx [rad] = 6.062, omega t [rad] = 0.9066 | E = (0, 3.1219, 0); cB = (0, 0, -1.78791) |

**Other checks:**

- **1.P1** (Special case). Example of $\vec E=0$, $\vec B\neq0$: with $E_{20}=E_{10}$ and $\phi=0$, at $kx=\pi/2$ the total $E_y=0$ for every $t$ ...
- **1.P2** (Special case). ... while there $cB_z=2E_{10}\sin\omega t$, which is nonzero except at isolated instants. (With $\hat x\times\vec E_2/c$ for wave 2 you would get $B=0$ there too.)
- **1.I1** (Identity). Faraday's law, $\partial_tB_z=-\partial_xE_y$, holds for your *total* fields (use $\omega=ck$). It is linear, so it must hold wave by wave as well.
- **1.I2** (Identity). The Ampère-Maxwell law in vacuum, $\partial_xB_z=-c^{-2}\partial_tE_y$, holds as well; together the two fix the sign of each $\vec B_j$ relative to its direction of travel.
- **1.I3** (Identity). $E_y+cB_z=2E_{10}\cos a$ (wave 2 cancels): so wherever $\vec E=0$, $cB_z=2E_{10}\cos a$, and wherever $\vec B=0$, $E_y=2E_{10}\cos a$.
- **1.I4** (Identity). $E_y-cB_z=2E_{20}\cos b$ (wave 1 cancels).
- **1.I5** (Identity). $c^2B^2-E^2=-4E_{10}E_{20}\cos a\cos b$, which is not identically zero: $|\vec B|\ne|\vec E|/c$ in general (for a single travelling wave the left side vanishes).
- **1.T1** (Structure). $\vec B_1=(E_{10}/c)\cos a\,\hat z=\hat x\times\vec E_1/c$ and $\vec B_2=(-\hat x)\times\vec E_2/c$: each wave's $\vec E\times\vec B$ points along its own direction of travel. Both $\vec B$'s are along $\hat z$.
- **1.T2** (Structure). Points with $\vec E=0$, $\vec B\ne0$ (and vice versa) exist for *any* amplitudes $E_{10},E_{20}$: at fixed $t$, $E_y(x)$ is a sinusoid in $x$ and has zeros; at a zero of $E_y$, $cB_z=2E_{10}\cos a\ne0$ unless $\cos a=0$ there as well. (An older wording, '$E$ maximal with $B=0$', holds only for equal amplitudes.)

**Wrong turns** (the check in brackets catches it):

- *1.W1*: using $\hat x\times\vec E_2/c$ for the backward wave (wave 2 travels toward $-\hat x$); this makes $c\vec B$ equal to $\vec E$ rotated, puts the $B$-nodes on the $E$-nodes later, and gives $S\propto E^2\ge0$ [1.S1, 1.S2, 1.S3, 1.P2, 1.I1, 1.I2, 1.I3, 1.I4, 1.I5, 1.T1]
- *1.W2*: getting both $\vec B_1$ and $\vec B_2$ with the wrong overall sign (check $\vec E_1\times\vec B_1$ must point toward $+\hat x$) [1.S1, 1.S2, 1.S3, 1.I1, 1.I2, 1.I3, 1.I4, 1.T1]
- *1.W3*: putting $\vec B$ along $\hat y$ (parallel to $\vec E$) instead of $\hat z$ [1.S1, 1.S2, 1.S3, 1.T1]
- *1.W4*: copying the phase $a=kx-\omega t$ into wave 2 instead of using $b=kx+\omega t+\phi$ [1.S1, 1.S2, 1.S3, 1.I1, 1.I2, 1.I3, 1.I4]

## Part (2)

> 2. What condition on $E_{10}$ and $E_{20}$ makes the total electric field a standing wave, i.e. of the form $f(x)\,g(t)$? Assume it from now on. Write $\vec E$ and $\vec B$ in standing-wave form and find the nodes of each for arbitrary $\phi$. By how much are the $E$-nodes and $B$-nodes displaced from one another in space?

**Spot checks** (relative tolerance 0.001):

| Check | Inputs | Your result should be |
|---|---|---|
| 2.S1 | E0 [V/m] = 1.02, phi [rad] = 2.97, kx [rad] = 1.919, omega t [rad] = 1.167 | E = (0, 1.73872, 0); cB = (0, 0, -0.24886) |
| 2.S2 | E0 [V/m] = 2.285, phi [rad] = 0.4153, kx [rad] = 5.957, omega t [rad] = 4.872 | E = (0, 1.62939, 0); cB = (0, 0, 0.504399) |
| 2.S3 | E0 [V/m] = 1.556, phi [rad] = 4.872, kx [rad] = 2.531, omega t [rad] = 6.021 | E = (0, -0.444527, 0); cB = (0, 0, -2.4805) |

**Other checks:**

- **2.P1** (Special case). At $X=\pi/2$ (i.e. $kx=\pi/2-\phi/2$) $E_y=0$ for all $t$: an $E$-node, for every $\phi$.
- **2.P2** (Special case). At that same $E$-node, $cB_z=2E_0\sin T$: a $B$-antinode.
- **2.P3** (Special case). At $X=0$ (i.e. $kx=-\phi/2$) $cB_z=0$ for all $t$: a $B$-node, one quarter wavelength from the $E$-node above.
- **2.Y1** (Symmetry). Reflecting about an $E$-antinode ($X\to-X$, i.e. $x\to-x-\phi/k$) leaves $E_y$ unchanged ...
- **2.Y2** (Symmetry). ... and reverses the sign of $cB_z$: $B$ is odd about the $E$-antinodes.
- **2.C1** (Dependence). $\vec E$ and $\vec B$ depend on $x$, $t$ and $\phi$ only through $X=kx+\phi/2$ and $T=\omega t+\phi/2$: changing $\phi$ just shifts the whole pattern by $-\phi/2k$ in $x$ and $-\phi/2\omega$ in $t$.
- **2.I1** (Identity). Your product form must equal the sum form: $2E_0\cos X\cos T=E_0\cos a+E_0\cos b$ for all $x,t,\phi$ (sum-to-product identity with $X=(a+b)/2$, $T=(b-a)/2$).
- **2.I2** (Identity). Likewise $2E_0\sin X\sin T=E_0\cos a-E_0\cos b$.
- **2.T1** (Structure). Standing wave requires $E_{10}=E_{20}$. For $E_{10}\ne E_{20}$ the sum is a standing wave of amplitude $2E_{20}$ plus a travelling wave of amplitude $E_{10}-E_{20}$ (or the reverse), not of the form $f(x)g(t)$.
- **2.T2** (Structure). $E$-nodes at $X=\pi/2+m\pi$, $B$-nodes at $X=m\pi$: they alternate every $\lambda/4$, so the $E$- and $B$-nodes are displaced by $\lambda/4$ from each other.

**Wrong turns** (the check in brackets catches it):

- *2.W1*: carrying the $+\hat x\times\vec E_2/c$ error of part 1 forward: $c\vec B$ comes out with the same $\cos X\cos T$ form as $\vec E$, so the $B$-nodes sit on the $E$-nodes [2.S1, 2.S2, 2.S3, 2.P2, 2.P3, 2.Y2, 2.I2, 2.T2]
- *2.W2*: dropping or misplacing the $\phi/2$ shifts (putting all of $\phi$ into the time factor, or into the space factor, or dropping it) [2.S1, 2.S2, 2.S3, 2.P1, 2.P3, 2.Y1, 2.C1, 2.I1, 2.I2]
- *2.W3*: overall sign error in $\vec B$ (equivalent to $\vec B_1$ along $-\hat z$) [2.S1, 2.S2, 2.S3, 2.I2]
- *2.W4*: believing $\phi=0$ is needed for a standing wave; $\phi$ only translates the pattern in $x$ and $t$ [2.C1, 2.T1]

## Part (3)

> 3. Compute $u_E(x,t)$ and $u_B(x,t)$. Show that they are offset by a quarter wavelength in space and a quarter period in time, so that energy sloshes between electric and magnetic form. Find the total $u(x,t)$ and its time average, and compare the latter with the co-propagating result.

**Spot checks** (relative tolerance 0.001):

| Check | Inputs | Your result should be |
|---|---|---|
| 3.S1 | phi [rad] = 0.9182, kx [rad] = 2.22, omega t [rad] = 1.27 | u_E/(eps0 E0^2) = 0.0398081; u_B/(eps0 E0^2) = 0.388259; u/(eps0 E0^2) = 0.428067 |
| 3.S2 | phi [rad] = 5.963, kx [rad] = 1.376, omega t [rad] = 5.853 | u_E/(eps0 E0^2) = 0.16668; u_B/(eps0 E0^2) = 0.544776; u/(eps0 E0^2) = 0.711456 |
| 3.S3 | phi [rad] = 5.952, kx [rad] = 5.596, omega t [rad] = 1.892 | u_E/(eps0 E0^2) = 0.0207928; u_B/(eps0 E0^2) = 1.1071; u/(eps0 E0^2) = 1.1279 |

**Other checks:**

- **3.P1** (Special case). At an $E$-antinode ($X=0$): $u=\epsilon_0E_0^2[1+\cos 2T]=2\epsilon_0E_0^2\cos^2T$, purely electric, oscillating between 0 and $2\epsilon_0E_0^2$.
- **3.P2** (Special case). Halfway between a node and an antinode ($X=\pi/4$): $u=\epsilon_0E_0^2$, constant in time; energy flows through this point but does not accumulate there.
- **3.Y1** (Symmetry). $u$ is even about every $E$-antinode and every $B$-antinode ($X\to-X$).
- **3.Y2** (Symmetry). $u$ is even in time about the instants of maximal $E$ ($T\to-T$).
- **3.C1** (Dependence). $u_E$, $u_B$, $u$ depend on $x,t,\phi$ only through $X$ and $T$.
- **3.I1** (Identity). $u_E(x,t)=u_B(x+\lambda/4,\,t+\tau/4)$: the magnetic pattern is the electric one shifted by a quarter wavelength and a quarter period ($\tau=2\pi/\omega$).
- **3.I2** (Identity). $u=\epsilon_0E_0^2\big[1+\cos(2kx+\phi)\cos(2\omega t+\phi)\big]$.
- **3.I3** (Identity). Time average over a period: $\langle u\rangle=\epsilon_0E_0^2$, the same at every $x$ and for every $\phi$.
- **3.I4** (Identity). For comparison, two co-propagating waves of the same amplitude $E_0$ (problem 6) have $\langle u\rangle=\epsilon_0E_0^2(1+\cos\phi)$, anywhere between 0 and $2\epsilon_0E_0^2$ depending on $\phi$; the standing wave always has the $\phi$-independent value $\epsilon_0E_0^2$, the incoherent sum of the two waves' averages.
- **3.T1** (Structure). $u_E\propto\cos^2X\cos^2T$ and $u_B\propto\sin^2X\sin^2T$ with the same prefactor $2\epsilon_0E_0^2$: at an $E$-antinode the energy is all electric at $T=0$ and all gone a quarter period later, when it sits in the magnetic field a quarter wavelength away.

**Wrong turns** (the check in brackets catches it):

- *3.W1*: taking $u=\epsilon_0E^2/2$ as the *total* energy density (that is $u_E$ alone; in a standing wave $u_B\ne u_E$, so you cannot just double it either) [3.S1, 3.S2, 3.S3, 3.P2, 3.I2, 3.I3, 3.T1]
- *3.W2*: using the wrong-sign $\vec B_2$ from part 1, which makes $u_B=u_E$ everywhere and $u=\epsilon_0E^2$ with no sloshing [3.S1, 3.S2, 3.S3, 3.P1, 3.P2, 3.I1, 3.I2, 3.I3, 3.T1]
- *3.W3*: dropping the $\phi/2$ shifts, so the $\phi$-dependence of $u$ comes out wrong (it must enter only as $\cos(2kx+\phi)\cos(2\omega t+\phi)$) [3.S1, 3.S2, 3.S3, 3.C1, 3.I2]
- *3.W4*: comparing $\langle u\rangle$ with a $\phi$-dependent co-propagating value without saying the amplitudes are equal there too [3.I4]

## Part (4)

> 4. Compute $\vec S(x,t)$ and its time average. Where does $\vec S$ point at a given instant, and why is its time average zero everywhere? Reconcile this with the fact that $u$ oscillates locally.

**Spot checks** (relative tolerance 0.001):

| Check | Inputs | Your result should be |
|---|---|---|
| 4.S1 | phi [rad] = 0.9137, kx [rad] = 6.021, omega t [rad] = 1.387 | S_x/(eps0 c E0^2) = -0.197134 |
| 4.S2 | phi [rad] = 5.884, kx [rad] = 0.3697, omega t [rad] = 5.642 | S_x/(eps0 c E0^2) = -0.331645 |
| 4.S3 | phi [rad] = 0.9502, kx [rad] = 0.393, omega t [rad] = 2.843 | S_x/(eps0 c E0^2) = 0.34101 |

**Other checks:**

- **4.P1** (Special case). $S_x=0$ at every $B$-node ($X=m\pi$) for all $t$ ...
- **4.P2** (Special case). ... and at every $E$-node ($X=\pi/2+m\pi$): energy never crosses a node, so each $\lambda/4$ cell between an $E$-node and a $B$-node is energetically closed.
- **4.P3** (Special case). At $X=\pi/4$ (where $u$ is constant in time), $S_x=\epsilon_0cE_0^2\sin 2T$: the flow is largest where the energy density does not change.
- **4.Y1** (Symmetry). $S_x$ is odd about every node and antinode ($X\to-X$): at a given instant it points away from (or toward) an $E$-antinode symmetrically on both sides.
- **4.Y2** (Symmetry). $S_x$ is odd in time about the instants of maximal $E$ ($T\to-T$): the flow reverses every quarter period.
- **4.C1** (Dependence). $S_x$ depends on $x,t,\phi$ only through $X$ and $T$.
- **4.I1** (Identity). $S_x=\epsilon_0cE_0^2\sin(2kx+\phi)\sin(2\omega t+\phi)$ (double-angle identities).
- **4.I2** (Identity). Energy conservation holds locally: $\partial_tu+\partial_xS_x=0$ with your $u$ from part 3 and your $S_x$, once $\omega=ck$ is used. (Try it: a sign error in $\vec B$ breaks it.)
- **4.I3** (Identity). $\langle S_x\rangle=0$ at every $x$: no net energy transport.
- **4.T1** (Structure). At a given instant $\vec S$ alternates in direction from one $\lambda/4$ cell to the next: energy flows from the $E$-antinodes toward the $B$-antinodes while $u_E$ decreases, and back a quarter period later. $\langle S_x\rangle$ is independent of $x$ (since $\partial_x\langle S_x\rangle=-\langle\partial_tu\rangle=0$) and vanishes at the nodes, hence vanishes everywhere; a time-oscillating $u$ with zero mean flow is consistent because $\partial_tu=-\partial_xS_x$ averages to zero over a period.

**Wrong turns** (the check in brackets catches it):

- *4.W1*: carrying the $+\hat x\times\vec E_2/c$ error forward: $S\propto E^2\ge0$ always points toward $+\hat x$ and has a nonzero average [4.S1, 4.S2, 4.S3, 4.P1, 4.P2, 4.P3, 4.Y1, 4.Y2, 4.I1, 4.I2, 4.I3, 4.T1]
- *4.W2*: reusing the co-propagating result $\vec S=cu\,\hat x$, which does not hold here (there is no single $\hat k$) [4.S1, 4.S2, 4.S3, 4.P1, 4.P2, 4.P3, 4.Y1, 4.Y2, 4.I1, 4.I2, 4.I3]
- *4.W3*: dropping the $\phi/2$ shifts [4.S1, 4.S2, 4.S3, 4.P1, 4.P2, 4.C1, 4.I1]
- *4.W4*: overall sign error (from a sign error in $\vec B$) [4.S1, 4.S2, 4.S3, 4.I2]

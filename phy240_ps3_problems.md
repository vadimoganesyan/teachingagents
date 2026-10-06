## Problem Set 3:
- Assigned: 10/5; Due: Oct. 21
- Same rules as PS2: most problems will be too difficult on a first pass; use any means to solve *and* understand them, and expect to explain what you understand to peers, relatives, strangers on the street, and the instructor.
- Exam 1 (Mon 10/26) is based on PS2 and PS3.
- Topics covered: interference and diffraction, thin films, momentum of light, light in matter (D vs E, Lorentz model, dispersion and absorption), wave packets and group velocity

<!-- v3 (2026-10-05): corrections from the isolated review (see REVIEW LOG at the end). v2 changes from v1: optical rotation (old 9) dropped; new problem 8 (wave packets, group velocity from superposition) inserted before the Lorentz group-velocity problem (now 9); 9.3 corrected (undamped Lorentz has a stop band above ω0, not superluminal v_g); explain-style parts removed or made deductive (1.1, 5.5, 6.6, 7.4, 9.3, 9.5); all figures in place except none outstanding. Every numbered CHECK still needs independent verification before release.
     Recycled problems are rewritten from last year's bank files (240/problems/*), which are stale starting points, not canonical.
     Format follows ps2_240F26.md (self-contained, not the thin-manifest layout in .claude/skills/problem-set). No points and no logistics block, as in PS2b. -->

## Contents
<!-- TOC -->
1. [Unpolarized light and polarizer chains](#polarizer-chain)
2. [Double slit with a glass plate](#double-slit)
3. [Diffraction: single slit, grating, resolution](#diffraction)
4. [Anti-reflection coating](#thin-film)
5. [Light carries momentum](#momentum)
6. [Dielectric capacitor: D vs E and the Lorentz step response](#dielectric-capacitor)
7. [Lorentz model: dispersion and absorption from data](#lorentz-dispersion)
8. [Wave packets: where the group velocity comes from](#wave-packets)
9. [Group velocity in a Lorentz medium; the ionosphere](#group-velocity)
<!-- /TOC -->
---

1. <a id="polarizer-chain"></a> **[Unpolarized light and polarizer chains](#contents)**

   *key ideas: unpolarized light as a mixture, Malus' law averaged, sequential projections, continuum limit*

   <!-- NEW. Source: em_review_extras.md slides "unpolarized" and "polarizer-chain"; three-polarizer demo. Difficulty 1–2, [A][N]. Opens the set. -->

   In PS2 you analyzed a beam with fixed $E_{0y}/E_{0x}$ and $\phi$. Sunlight and lamp light are not like that: the polarization direction and relative phase wander randomly on a timescale $\tau_c\sim1/\Delta\nu$ (femtoseconds), far shorter than any detector's response. Such light is *unpolarized*: a mixture of polarizations, not a superposition.


   1. Model unpolarized light as linearly polarized at an angle $\psi$ that is uniformly random over $[0,2\pi)$. Show that a single polarizer at any angle transmits $I_0/2$, and that no polarizer angle extinguishes the beam.
   2. Two polarizers with transmission axes at $0^\circ$ and $90^\circ$ transmit nothing. Insert a third polarizer at angle $\theta$ between them and compute the transmitted intensity $I(\theta)$ for unpolarized input $I_0$. Show that it is maximal at $\theta=45^\circ$ and find the maximal value. Write down the field direction after each sheet for $\theta=45^\circ$: an extra absorber *increases* transmission because it changes the field, not only the intensity.
   3. Replace the middle polarizer by $N-1$ polarizers at equal angular steps, so that the $N+1$ sheets (first at $0^\circ$, last at $90^\circ$) rotate the transmission axis by $90^\circ$ in $N$ steps of $\pi/2N$. Find $I_N/I_0$ for polarized input along $\hat x$ and show that $I_N/I_0\to1$ as $N\to\infty$. (Hint: $\cos^{2N}(\pi/2N)$; expand the logarithm.) How many sheets are needed for $90\%$ transmission? <!-- CHECK C1.1: 1 − I_N/I_0 ≈ π²/(4N) → N ≈ 25 for 90%. Decide whether to connect to the LCD slide. -->
   4. Light reflected at a glancing angle from a horizontal surface (road, water) is partly polarized: take as given that the reflected glare is a mixture of $70\%$ unpolarized light and $30\%$ linearly polarized light with $\vec E$ horizontal. Find the transmitted glare intensity through a polarizer as a function of the angle of its axis from vertical, and the angle that minimizes it. What fraction of the glare does the best orientation remove, and what fraction of a fully unpolarized view of the scenery does it cost? <!-- CHECK C1.2: the 70/30 split is illustrative, not measured; Brewster's angle not assumed. Best: axis vertical, transmits 0.35 I_glare (65% removed), costs 50% of scenery. -->

2. <a id="double-slit"></a> **[Double slit with a glass plate](#contents)**

   *key ideas: path difference, fringe spacing, finite number of fringes, optical path length, coherence*

   <!-- RECYCLED from 05_em_double-slit (ps2_240S26). Parts (a)–(c) of the original are PHY160 material and are compressed into a single warm-up; the content is (d)–(f) plus the new coherence part 5. Difficulty 2, [A][N]. -->

   ![Double slit](figs/doubleSlit.png)

   A Young's double slit has slit separation $d=0.5\,$mm, screen distance $L=1\,$m, wavelength $\lambda=532\,$nm. Point $P$ is at height $y$ on the screen; the path lengths from slits 1 and 2 to $P$ are $L_1$ and $L_2$.

   1. Warm-up. Express $\Delta L=L_2-L_1$ in terms of $d$ and $\theta$, state the bright/dark conditions on $\Delta L/\lambda$, and for small angles find the fringe positions $y_m$ and spacing $\Delta y$ (numerically).
   2. Fringes do not continue indefinitely. Find the maximum number of bright and dark fringes on each side of center (correct to $\pm1$), and the angle $\theta$ of the last bright fringe without the small-angle approximation.
   3. A glass plate of thickness $t$ and index $n=1.6$ covers slit 1. Find the change in optical path difference and the shift of the whole pattern in terms of $n$, $t$, $L$, $d$. State the direction of the shift (toward or away from the covered slit) and justify it in one sentence without calculation.
   4. Find the minimum $t$ that shifts the pattern by exactly three fringe spacings (numerically). If the fringe shift can be read to $0.1$ fringe, to what precision does this measure $n$ for a $t=25\,\mu$m plate? <!-- CHECK C2.1 (λ changed to 532 nm so d/λ = 939.8 is not an integer): Δy = 1.064 mm, m_max = 939, last bright at sinθ = 0.99915, θ ≈ 87.6°; t = 3λ/(n−1) = 2.66 μm; 25 μm plate shifts 28 fringes, 0.1 fringe → δn ≈ 2×10⁻³. -->
   5. The plate also *delays* the light from slit 1 by $(n-1)t/c$. For a source with coherence time $\tau_c$, estimate the plate thickness beyond which the fringes wash out at a fixed point near the original center, $y\approx0$. Evaluate for a laser ($\tau_c\sim 1\,\mu$s) and for a filtered lamp ($\Delta\nu\sim10^{12}\,$Hz). <!-- CHECK C2.2: coherence time appears on the em_review_extras "unpolarized" slide; Vadim will cover it in class. t ≈ cτ_c/(n−1): 500 m (laser), 0.5 mm (lamp). -->

3. <a id="diffraction"></a> **[Diffraction: single slit, grating, resolution](#contents)**

   *key ideas: Huygens sources, phasor sum, grating resolving power, Rayleigh criterion, Bragg reflection*

   <!-- NEW. Fills the only lecture section (lec_intdiff_LMatter: single slit, circular aperture, grating, Bragg) with no problem. Difficulty 3, [A][N]. No figure: the phasor sum is the point and should be drawn by the student. -->

   Interference with two sources gave $I=4I_0\cos^2(\phi/2)$. Diffraction is the same calculation with many sources. Here you do it for $N$ slits and then let $N\to\infty$ (a single wide slit) and $N$ large but finite (a grating).

   1. $N$ equally spaced slits (spacing $d$) each contribute a field of amplitude $E_0$ with successive phase lag $\delta=kd\sin\theta$. Sum the geometric series $\sum_{j=0}^{N-1}e^{ij\delta}$ and show
      $$I(\theta)=I_0\,\frac{\sin^2(N\delta/2)}{\sin^2(\delta/2)}.$$
      Check $N=2$ against the two-slit result. Where are the principal maxima and what is their height?
   2. Show that the first zero next to a principal maximum is at $\Delta\delta=2\pi/N$, hence the angular half-width of a grating line is $\Delta\theta\approx\lambda/(Nd\cos\theta)$. Using the Rayleigh criterion (one line's maximum on the other's first zero), derive the resolving power $R=\lambda/\Delta\lambda=Nm$ in order $m$.
   3. The sodium D lines are at $589.0$ and $589.6\,$nm. How many grating lines must be illuminated to resolve them in first order? In third order? A grating has $300$ lines/mm: check that third order exists for this wavelength, and find the illuminated width needed in each case. <!-- CHECK C3.1: R = 982 → N ≥ 983 (m=1), 328 (m=3); at 300 lines/mm (d = 3.33 μm) third order is at sinθ = 0.53, fine; widths ≈ 3.3 mm / 1.1 mm. (600 lines/mm, as in v2, has no third order: sinθ = 1.06.) -->
   4. Single slit of width $a$: let $N\to\infty$ with $Nd=a$ fixed and $E_0\propto1/N$. Show that $I(\theta)=I_0(\sin\alpha/\alpha)^2$ with $\alpha=\pi a\sin\theta/\lambda$, and recover the dark-fringe condition $a\sin\theta=m\lambda$, $m\neq0$. Find the ratio of the first side maximum to the central one. <!-- CHECK C3.2: side maximum ≈ 0.045 at α ≈ 1.43π. -->
   5. For a circular aperture the first dark ring is at $\sin\theta=1.22\lambda/D$ (take as given). At night, the two headlights of an approaching car ($1.5\,$m apart) merge into a single light once the car is farther than about $7\,$km. Deduce the diameter of the observer's pupil ($\lambda=550\,$nm). In daylight the pupil shrinks to $2\,$mm: at what distance do the headlights merge then? Apply the same criterion to a $2.4\,$m telescope mirror: what is the smallest separation it resolves on the Moon ($3.8\times10^5\,$km)? <!-- CHECK C3.3: 1.5 m / 7 km = 2.1×10⁻⁴ rad → D ≈ 3.1 mm; 2 mm → ≈ 4.5 km; mirror 2.8×10⁻⁷ rad → ≈ 110 m on the Moon. -->
   6. Bragg reflection: the atomic planes of a crystal, spaced $d$, act as a grating with maxima at $2d\sin\theta=m\lambda$ (take as given). Copper K$\alpha$ X-rays ($\lambda=0.154\,$nm) reflected from NaCl show a first-order peak at $\theta=15.9^\circ$. Deduce the plane spacing $d$. Then find the longest wavelength for which *any* Bragg peak exists for this set of planes, and name the part of the spectrum it lies in. <!-- CHECK C3.4: d = 0.154/(2 sin 15.9°) = 0.281 nm (NaCl (200): 0.282 nm); λ_max = 2d = 0.56 nm, soft X-ray. -->

4. <a id="thin-film"></a> **[Anti-reflection coating](#contents)**

   *key ideas: reflection phase flips, thin-film interference, unequal reflection amplitudes, index matching, bandwidth*

   <!-- RECYCLED from 10_em_thin-film-ar (ps3_240S26). Original (b) assumed equal reflection amplitudes and (d) asked for a "Fourier principle"; replaced by parts 3 and 4. Difficulty 2, [A][N]. Figure redrawn (figs/make_figs3.py). -->

   ![AR coating](figs/arCoating.png)

   A glass lens ($n_g=1.52$) is coated with MgF$_2$ ($n_f=1.38$) to reduce reflection at normal incidence. Rays 1 and 2 reflect from the air–MgF$_2$ and MgF$_2$–glass interfaces respectively (drawn at a slight angle for clarity). At normal incidence the reflected amplitude at an interface from $n_1$ into $n_2$ is $r=(n_1-n_2)/(n_1+n_2)$ (take as given; a negative $r$ is the "phase flip").

   1. Identify which of the two reflections flip phase. Write the condition on $d$ for destructive interference between rays 1 and 2 at $\lambda_0=550\,$nm and find the minimum $d$.
   2. With this $d$, compute the phase difference $\Delta\phi$ between rays 1 and 2 at $450$ and $650\,$nm. Assuming for now equal amplitudes, the reflected intensity is $\propto|1+e^{i\Delta\phi}|^2=4\cos^2(\Delta\phi/2)$: compute $\cos^2(\Delta\phi/2)$ at the three wavelengths (this is the reflectance relative to its maximum, both reflections in phase). Which colors dominate the reflection from a coated lens in white light? <!-- CHECK C4.1: 2n_f d = 275 nm; cos²(Δφ/2) ≈ 0.117 (450), 0 (550), 0.057 (650): blue and red survive, hence purple. Normalization now stated explicitly and matched to part 4. -->
   3. Now use the actual amplitudes $r_1$ (air→MgF$_2$) and $r_2$ (MgF$_2$→glass). Neglecting multiple reflections and transmission factors, show the reflected intensity at $\lambda_0$ is $\propto(|r_1|-|r_2|)^2$, compare it to the bare-glass reflectance $\propto r_g^2$, and find the coating index $n_f$ that would give exact cancellation. <!-- CHECK C4.2: r1 = −0.160, r2 = −0.048, r_g = −0.206; reflectance 1.25% vs 4.3%; n_f = √1.52 = 1.233 (no durable solid has it; MgF₂ is the lowest practical). -->
   4. Bandwidth of the coating. With equal amplitudes the reflectance relative to its maximum is $\cos^2(\Delta\phi/2)$ as in part 2, with $\Delta\phi=4\pi n_fd/\lambda$ (both reflections flip, so no extra $\pi$). Find the two wavelengths at which it has climbed back to one quarter of the maximum, and hence the bandwidth $\Delta\lambda/\lambda_0$ of a single-layer coating. Does it cover the visible band ($400$–$700\,$nm)? <!-- CHECK C4.3: with 2n_f d = λ0/2, Δφ = πλ0/λ; cos²(Δφ/2) = 1/4 at Δφ = 2π/3, 4π/3 → λ = 3λ0/2 = 825 nm and 3λ0/4 = 412 nm; Δλ/λ0 ≈ 0.75. -->

5. <a id="momentum"></a> **[Light carries momentum](#contents)**

   *key ideas: force on a driven charge, momentum density $\vec g=\vec S/c^2$, radiation pressure, solar sails*

   <!-- REWRITE of 01_em_laser-beam (ps2_240S26): original parts (a)–(c) retained as a warm-up; the problem now centers on momentum, following em_review_extras.md slides "em-momentum", "radiation-pressure". Tweezers part cut (open-ended). Difficulty 2, [A][N]. -->

   ![Charge driven by a wave](figs/lightMomentum.png)

   A laser beam propagates along $+z$, polarized along $\hat x$, power $P=5\,$mW, $\lambda=532\,$nm, uniform circular cross-section of radius $w=1\,$mm.

   1. Warm-up. Write $\vec E$ and $\vec B$ as a plane wave; from $I=\tfrac12c\epsilon_0E_0^2$ and the beam area find $E_0$ numerically; show $u_E=u_B$ and hence $\langle u\rangle=I/c$.
   2. A charge $q$ in an absorbing medium is dragged by $\vec E$ against friction, so its velocity is in phase with the field, $\vec v\parallel\vec E$ at every instant (ignore $\vec B$ for this step; a free charge would instead have $\vec v$ a quarter cycle out of phase, and the time-averaged force below would vanish). Show that the magnetic force $q\vec v\times\vec B$ points along $\hat k$ in both half-cycles (figure). Show that the charge absorbs energy at rate $qEv$ and momentum at rate $qEv/c$, and conclude that the field carries momentum $p=U/c$, i.e. momentum density $\vec g=\vec S/c^2$.
   3. Radiation pressure on a perfect absorber is $I/c$ and on a perfect mirror $2I/c$: derive both from part 2, compute the force of the beam on a flat absorber and on a flat mirror numerically. The beam is now focused onto a perfectly absorbing dust grain of radius $10\,\mu$m and density $1000\,$kg/m$^3$ (spot smaller than the grain): compare the force with the grain's weight and find the beam power that levitates it. <!-- CHECK C5.1: F_abs ≈ 1.7×10⁻¹¹ N, F_mirror ≈ 3.3×10⁻¹¹ N, weight ≈ 4.1×10⁻¹¹ N → ≈ 12 mW absorbed. Focusing stated (unfocused 1 mm beam hits 10⁻⁴ of its power on the grain). Mirror case for the grain dropped: a reflecting sphere feels I/c, not 2I/c. -->
   4. Sunlight at Earth has $I\approx1361\,$W/m$^2$. Find the pressure on a perfectly reflecting sail and the acceleration of a $1\,$kg craft with a $100\,$m$^2$ sail. How long to reach $1\,$km/s? Compare the sail's acceleration with the Sun's gravitational acceleration at Earth's orbit ($5.9\times10^{-3}\,$m/s$^2$) and find the sail area per kilogram at which the two balance. <!-- CHECK C5.2: 9.1 μPa, 9.1×10⁻⁴ m/s², ≈ 13 days; balance at ≈ 650 m²/kg. Both I and g_sun scale as 1/r², so the ratio is distance-independent. -->

6. <a id="dielectric-capacitor"></a> **[Dielectric capacitor: D vs E and the Lorentz step response](#contents)**

   *key ideas: Gauss's law in matter, bound charge, energy in a dielectric, step response of a damped oscillator*

   <!-- RECYCLED from 06_em_dielectric-lorentz (ps3_240S26), unchanged except part 4 (Poynting-flux sign check replaces the "direction of B" hint) and part 6 (overshoot made quantitative). Difficulty 3, [A]. No figure. -->

   A thin parallel-plate capacitor (area $A$, separation $d\ll\sqrt A$) is filled with a linear dielectric described by the Lorentz model, $m\ddot x+m\gamma\dot x+m\omega_0^2x=qE$, polarization $P=Nqx$. At $t=0$ free surface charge $\pm\sigma_fA$ is deposited nearly instantaneously on the plates and then held fixed. Write $\omega_p^2=Nq^2/m\epsilon_0$.

   1. For $t$ much shorter than every response time of the oscillators ($t\ll1/\omega_0$ and $t\ll1/\gamma$) they have not moved ($P=0$). Use Gauss's law to find $\vec D$, $\vec E$, and the initial voltage $V_0$.
   2. For $t\to\infty$ (long compared with every response time) use the $\omega\to0$ limit of the Lorentz model to find $P_\infty$, hence $\vec E$, $V_\infty$, $\epsilon_r$, and the bound surface charge $\sigma_b$ on the dielectric faces.
   3. Show that $\vec D$ is the same in both limits. What about $\vec E$? Which quantity is "sourced by free charge only"?
   4. Sketch $E(t)$ and $P(t)$ on the same axes, marking the two limits. Compute $U=\tfrac12\int\vec E\cdot\vec D\,dV$ in both limits; which is larger? Where did the difference go? Show from the Ampère–Maxwell law in matter, $\nabla\times\vec H=\vec J_f+\partial_t\vec D$, that $\vec B=0$ throughout the relaxation, so no energy enters or leaves through the rim. Then show that the power per unit volume delivered by the field to the oscillators is $\vec E\cdot\partial_t\vec P$, and that its time integral equals $U_0-U_\infty$ plus the potential energy $\tfrac12 Nm\omega_0^2x_\infty^2$ stored in the stretched oscillators; conclude that $U_0-U_\infty$ is exactly the heat produced by the damping $\gamma$. (Hint: $\epsilon_0\partial_t\vec E=-\partial_t\vec P$ since $\vec D$ is constant.) <!-- CHECK C6.1 (rewritten after review: v1/v2 and last year's problem asked for a Poynting-flux sign check at the rim, which is wrong — ∂_tD = 0 ⇒ B = 0, S = 0). Verify: work on oscillators = ½ε0(E0²−E∞²)V; spring energy = ½P∞E∞V; difference = ½ε0E0(E0−E∞)V = U0 − U∞. -->
   5. Dilute limit: take $E\approx E_0=\sigma_f/\epsilon_0$ as the driving field so the Lorentz equation is the step response of a damped oscillator with $x(0)=\dot x(0)=0$. Solve for $x(t)$ and $E(t)=E_0-Nqx(t)/\epsilon_0$ in the overdamped ($\omega_0<\gamma/2$) and underdamped ($\omega_0>\gamma/2$) cases; sketch both, identifying the oscillation frequency $\Omega_d=\sqrt{\omega_0^2-\gamma^2/4}$ and the $e^{-\gamma t/2}$ envelope. <!-- CHECK C6.2: boundary ω0 ≶ γ/2 confirmed by review. The transient with initial conditions is not in the decks; students need their ODE background (reviewer's note). -->
   6. In the underdamped case $E(t)$ overshoots below $E_\infty$. Find the time of the first minimum of $E(t)$ and the overshoot $(E_\infty-E_{\min})/(E_0-E_\infty)$ in terms of $\gamma/\Omega_d$. Which of $D$, $E$, $V$ overshoot? <!-- CHECK C6.3: first minimum at t = π/Ω_d, overshoot = exp(−πγ/2Ω_d); D fixed by σ_f, E and V = Ed overshoot. -->

7. <a id="lorentz-dispersion"></a> **[Lorentz model: dispersion and absorption from data](#contents)**

   *key ideas: driven oscillator, complex index, Cauchy plot, normal/anomalous dispersion, Beer–Lambert law*

   <!-- RECYCLED from 09_em_lorentz-dispersion (ps3_240S26). Parts 1–3 retained; part 4 reduced to the comparison; part 5 made numerical using the N, ω0 extracted in part 2. Difficulty 3, [A][N]. -->

   ![Cauchy plot](figs/cauchyPlot.png) ![Density vs index](figs/densityIndex.png)

   <!-- Figures extracted from last year's ps3.pdf. GAP G7.2: source/licence of the density-vs-index plot unknown. -->

   An atom in a dielectric responds to $E(t)=\mathrm{Re}[\tilde Ee^{-i\omega t}]$ as a damped oscillator, $m\ddot x+m\gamma\dot x+m\omega_0^2x=qE(t)$; $P=Nqx$ and $n^2=1+P/(\epsilon_0E)$.

   1. Solve for $\tilde x/\tilde E$ and derive $n^2(\omega)=1+\dfrac{Nq^2/m\epsilon_0}{\omega_0^2-\omega^2-i\gamma\omega}$.
   2. With $\gamma=0$, show that $(n^2-1)^{-1}$ is linear in $\lambda^{-2}$. From the slope and intercept of the plot (left), extract $\omega_0$ and $N$ (use $q=e$, $m=m_e$). Is $\omega_0$ in the UV, visible, or IR? Compare $N$ to the number density of atoms in glass ($\approx6.6\times10^{28}\,$m$^{-3}$). <!-- CHECK C7.1: with (n²−1)⁻¹ = A − Bλ⁻²: λ0 = √(B/A), N = (2πc)² mε0/(B e²). From the figure A ≈ 0.7525, B ≈ 0.0525/(6.5×10⁻⁶ nm⁻²) ≈ 8.1×10³ nm² → λ0 ≈ 104 nm (UV, ~12 eV), N ≈ 1.4×10²⁹ m⁻³ ≈ 2 oscillators per atom. -->
   3. Sketch $n(\omega)$ for $\gamma=0$; mark normal and anomalous dispersion, $\omega_0$, and the width $\gamma$ once damping is restored.
   4. Dilute medium: show $n-1\propto N$, hence $n-1\propto$ mass density. Compare with the plot (right), reading the main (SiO$_2$–PbO) branch: is $\rho$ linear in $n$? Is it *proportional* to $n-1$ (does the line extrapolate to $\rho=0$ at $n=1$)? Report the slope $d\rho/dn$. <!-- CHECK C7.2: linear, slope ≈ 8 g/cm³ per unit n, but extrapolates to ρ = 0 near n ≈ 1.2, not 1: linear, not proportional. Dense glass is outside the dilute (χ = Nα) regime; Lorentz–Lorenz would fix it but is not in the decks, so the question only asks students to notice the offset. -->
   5. Restore $\gamma$ and write $n=n'+i\kappa$. For $E\propto e^{i(kz-\omega t)}$, $k=n\omega/c$, show that intensity decays as $e^{-\alpha z}$ with $\alpha=2\kappa\omega/c$. At exact resonance with $\gamma\ll\omega_0$ find $\kappa$ and the absorption length $1/\alpha$; evaluate numerically with $N$, $\omega_0$ from part 2 and $\gamma/\omega_0=10^{-2}$. (Hint: $\kappa$ is not small here; use $\epsilon'=n'^2-\kappa^2$, $\epsilon''=2n'\kappa$ from lecture rather than expanding.) Compare to the thickness of a window. <!-- CHECK C7.3: at resonance n² = 1 + iω_p²/(γω0); for ω_p² ≫ γω0, κ ≈ √(ω_p²/2γω0). With N, λ0 from C7.1: ω_p² ≈ 4.4×10³² s⁻², ω0 ≈ 1.8×10¹⁶ s⁻¹, ω_p²/(γω0) ≈ 130 → κ ≈ 8, 1/α ≈ 1 nm. Dilute model far outside validity here; the point is only "opaque". -->

8. <a id="wave-packets"></a> **[Wave packets: where the group velocity comes from](#contents)**

   *key ideas: superposition, envelope vs carrier, dispersion relation, group velocity, spreading*

   <!-- NEW (Vadim's suggestion): build v_g from the simplest superposition, first with linear dispersion, then with curvature. Source: unfinished_lec2_waves_tight.md (beats, wave packets, v_g = dω/dk, the chain). Difficulty 2–3, [A][N]. Figure: figs/wavePacket.png (make_figs3.py). -->

   ![Wave packets](figs/wavePacket.png)

   In lecture, $v_g=d\omega/dk$ came from Taylor-expanding $\omega(k)$. Here you build it from the simplest possible superposition and watch what the curvature of $\omega(k)$ does. Throughout, $\omega(k)$ is the dispersion relation of some medium; its shape is all that matters.

   1. Add two waves of equal amplitude and nearby wavenumbers, $A\cos(k_1x-\omega_1t)+A\cos(k_2x-\omega_2t)$ with $k_{1,2}=k_0\pm\Delta k$ and $\omega_{1,2}=\omega(k_{1,2})$; write $\bar\omega=(\omega_1+\omega_2)/2$ and $\Delta\omega=(\omega_2-\omega_1)/2$. Show the sum is $2A\cos(\Delta k\,x-\Delta\omega\,t)\cos(k_0x-\bar\omega t)$. Identify the carrier and the envelope, give the distance between successive envelope zeros, and show that the carrier crests move at $\bar\omega/k_0$ while the envelope moves at $\Delta\omega/\Delta k$.
   2. Linear dispersion, $\omega=vk$. Show that both speeds equal $v$, so the pattern translates rigidly (top row of the figure). Write the sum as a function of $x-vt$ alone.
   3. General $\omega(k)$. Let $\Delta k\to0$ and show the envelope speed becomes $v_g=d\omega/dk|_{k_0}$, in general different from $v_p=\omega(k_0)/k_0$ (bottom row: the crests outrun the envelope). Apply to deep-water waves, $\omega=\sqrt{gk}$: show $v_g=v_p/2$ and evaluate both for a swell of wavelength $100\,$m. <!-- CHECK C8.1: v_p = √(gλ/2π) ≈ 12.5 m/s, v_g ≈ 6.2 m/s. -->
   4. Apply to the chain of coupled masses from lecture, $\omega(k)=2\sqrt{\kappa/m}\,|\sin(ka/2)|$. Find $v_g(k)$; show it equals $a\sqrt{\kappa/m}$ for $ka\ll1$ and vanishes at $k=\pi/a$. Write out the displacements $u_j(t)$ for $k=\pi/a$ and show that this mode transports nothing: it is a standing pattern in which neighbors move in antiphase.
   5. Spreading. Keep three waves, $k_0$ and $k_0\pm\Delta k$, with $\omega(k)\approx\omega(k_0)+v_g(k-k_0)+\tfrac12\beta(k-k_0)^2$, $\beta=\omega''(k_0)$. In the frame moving at $v_g$, show that the two side components acquire a phase $\tfrac12\beta\Delta k^2\,t$ relative to the center, so the envelope shape changes appreciably once $\tfrac12|\beta|\Delta k^2\,t\sim1$. For a packet of half-width $\sigma$ the relevant spread in $k$ is $\Delta k\sim1/\sigma$: estimate the spreading time $\tau\sim\sigma^2/|\beta|$ for the deep-water swell of part 3 if the packet half-width is five wavelengths. <!-- CHECK C8.2: β = ω'' = −¼√(g/k³) ≈ −50 m²/s for λ = 100 m; σ = 500 m → τ ≈ 5×10³ s ≈ 1.4 h. Reviewer confirmed the formula; 2π ambiguity removed by stating the criterion. -->

9.  <a id="group-velocity"></a> **[Group velocity in a Lorentz medium; the ionosphere](#contents)**

   *key ideas: phase vs group velocity, $k=n(\omega)\omega/c$, stop band, plasma frequency*

   <!-- NEW. Joins problem 8 to the Lorentz model. Difficulty 3, [A][N]. Closes the set; seeds the relativity unit. Figure: figs/lorentzGroupVel.png. v1 part 3 claimed v_g > c just above ω0 for γ = 0; wrong — with γ = 0 that band has n² < 0 (stop band). Superluminal v_g appears only with damping, inside the absorption line. Part 3 rewritten accordingly. Awaiting Vadim's comments on this problem. -->

   ![Lorentz n and v_g; plasma](figs/lorentzGroupVel.png)

   A wave packet moves at $v_g=d\omega/dk$, while its crests move at $v_p=\omega/k$. In vacuum both equal $c$. In a dispersive medium $k=n(\omega)\omega/c$ and the two differ; this problem works out by how much, and what happens where $n$ stops being real.

   1. Show that $v_g=\dfrac{c}{n+\omega\,dn/d\omega}$. Conclude that normal dispersion ($dn/d\omega>0$) gives $v_g<v_p$ and that $v_g<c$ whenever $n>1$ and $dn/d\omega>0$.
   2. Take the undamped Lorentz model $n^2=1+\omega_p^2/(\omega_0^2-\omega^2)$ with $\omega_p^2=Nq^2/m\epsilon_0$. Compute $n+\omega\,dn/d\omega$ and show that $v_g/c=n\,\dfrac{(\omega_0^2-\omega^2)^2}{(\omega_0^2-\omega^2)^2+\omega_p^2\omega_0^2}$ for $\omega<\omega_0$. Evaluate $v_g/c$ at $\omega\to0$ and at $\omega\to\omega_0^-$; compare with the figure (left). <!-- CHECK C9.1: v2 had a 1/n prefactor; review derived n, consistent with v_g(0) = c/n(0) and with the figure (0.79 for ω_p² = 0.6 ω0²). Fixed. -->
   3. Show that $n^2<0$ for $\omega_0<\omega<\sqrt{\omega_0^2+\omega_p^2}$. Write the wave in this band as $e^{-z/\ell}e^{-i\omega t}$ and find the penetration depth $\ell(\omega)$; what happens to a wave incident on the medium at such a frequency? Find the width of this band for the glass of problem 7 (use its $\omega_p$ and $\omega_0$) in eV. <!-- CHECK C9.2: ℓ = c/(ω|n|); total reflection (no energy flow in a lossless evanescent wave). Width: √(ω0²+ω_p²) − ω0 ≈ ω_p²/2ω0 for ω_p ≪ ω0; with the problem 7 numbers ω_p² ≈ 4.4×10³², ω0 ≈ 1.8×10¹⁶ → ω_p ≈ 2.1×10¹⁶ ≈ ω0, so use the exact expression: √(ω0²+ω_p²) − ω0 ≈ 0.54 ω0 ≈ 6 eV. Check. -->
   4. Free electrons: set $\omega_0=0$ (the ionosphere, $N\sim10^{12}\,$m$^{-3}$). Show $n^2=1-\omega_p^2/\omega^2$, so $n<1$ and $v_p>c$ for $\omega>\omega_p$, and show $v_pv_g=c^2$ (figure, right). Compute $f_p=\omega_p/2\pi$ numerically. <!-- CHECK C9.3: f_p ≈ 9 MHz for N = 10¹² m⁻³. -->
   5. Below $f_p$ the ionosphere reflects (part 3 with $\omega_0=0$). Using $f_p$ from part 4, state which of AM radio ($1\,$MHz), FM ($100\,$MHz) and GPS ($1.5\,$GHz) are reflected and which pass. For a signal that passes, the extra travel time through a layer of thickness $h$ is $\Delta t=\int(1/v_g-1/c)\,dz$: show that for $\omega\gg\omega_p$ this is $\Delta t\approx h\,\omega_p^2/(2c\,\omega^2)$ and evaluate it for GPS with $h=300\,$km. Why does GPS broadcast on two frequencies? <!-- CHECK C9.4: Δt ≈ 300e3 × (9e6/1.5e9)² / (2 × 3e8) ≈ 18 ns ≈ 5 m of range error at this N; real daytime columns give tens of ns. Two frequencies: 1/ω² scaling lets the delay be solved for. The last question is a one-line deduction from the 1/ω² dependence, not an open "explain". -->

<!-- REVIEW LOG (2026-10-05, isolated referee pass on the comment-stripped student text; reviewer solved all parts). Blocking issues found and fixed in v3: 9.2 prefactor (1/n → n); 6.4 Poynting sign check was false physics (∂_tD = 0 ⇒ B = 0; rewritten as a local-dissipation energy balance; the same flaw was in last year's problem); 3.3 no third order at 600 lines/mm (→ 300); 4.2/4.4 inconsistent normalization (now cos²(Δφ/2) relative to maximum in both); 5.3 beam must be focused on the grain, reflecting-sphere case dropped; 6.1/6.2 timescales (1/ω0 as well as 1/γ). Minor fixes: 1.3 sheet count, 2.2 λ → 532 nm and ask for the angle, 2.5 fixed-point wording, 3.6 "this set of planes", 4.3 approximation stated, 5.2 in-phase charge, 6 ω_p defined, 7.4 reframed, 7.5 hint, 8.1 ω̄ vs ω(k0), 8.5 single criterion. Not acted on: reviewer's total-time estimate ≈ 8 h (problems 6, 7, 9 at difficulty 3); 3.5 night pupil 3 mm is unrealistic (eye not diffraction-limited) but the arithmetic stands; symbol reuse κ (chain vs Im n) and d across problems; third-party figure sources (G7.2). Reviewer's numbers agree with all other CHECK values. -->
<!-- RESERVE (not in the set): 08_em_displacement-current-coaxial — same structure as PS2 problem 10 in cylindrical geometry; hold for Exam 1. Optical rotation (v1 problem 9) dropped: regurgitates the wave-plate math, niche topic. -->
<!-- TAG BALANCE: no [Q] problem, by Vadim's instruction (no open-ended parts on an exam-bound set); the problem-set skill's "at least one [Q]" is overridden here. -->
<!-- BANK BOOKKEEPING on release: add ps3_240F26 to used_in of 05, 06, 09, 10 (and 01 if the rewrite is counted as reuse); correct 08 used_in (ps2_240F26 is wrong — PS2b has only the disk). New problems 1, 3, 5, 8, 9 need bank files via problem-write. -->

## Problem Set 2:
- Assigned: 9/28; Due: Oct. 12
- Most of these problems will be too difficult to solve on a first pass. Feel free to use any means to solve *and* understand them. Expect to be able to explain what you understand to your peers, relatives, strangers on the street, and the instructor.
- Your first exam will be based on this and the next problem set.
- Topics covered: ray optics and Fermat's least-time principle, phase-space dynamics, EM waves (polarization, interference, antenna)
- Errata (Oct 5), applied in the text below:
   - 7.1: "a point and time where $\vec E$ is at its maximum but $\vec B=0$" exists only for equal amplitudes; now reads "where $\vec E=0$ but $\vec B\neq0$, and vice versa", which holds for any $E_{10},E_{20}$.
   - 8.5: the current density is now written out explicitly; it is a *sum* of the two delta functions, not a difference like $\rho$.
   - 8.4: wording tightened; Gauss's law fixes $\vec E_L$ at each instant, and $\dot{\vec E}_L=-\vec J_L/\epsilon_0$ is a consequence of it together with continuity. No change to what you are asked to show.
## Contents
<!-- TOC -->
1. [Where does Snell's law come from? Fermat's principle](#snells-law)
2. [Light guiding in a graded-index fiber](#graded-index)
3. [Physical pendulum in phase space](#pendulum-separatrix)
4. [Polarization diagnostics with a linear polarizer](#polarization)
5. [Birefringence and wave plates](#birefringence)
6. [Interference of co-propagating waves](#em-interference)
7. [Standing waves](#em-standing-waves)
8. [Dipole antenna](#em-generation)
9. [Heating in a resistive wire](#poynting-wire)
10. [Displacement current — parallel-plate capacitor](#displacement-disk)
<!-- /TOC -->
---
1. <a id="snells-law"></a> **[Where does Snell's law come from? Fermat's principle](#contents)**

   *key ideas: ray (geometric) optics, Fermat's least-time principle, Snell's law*

   ![Snell's law](figs/hwk1_1.png)

   Snell's law for refraction, $n_1\sin\theta_1=n_2\sin\theta_2$, was found experimentally (like many old physics "laws"). Fermat was inspired by Hero of Alexandria's explanation of **reflections** by a least-*pathlength* rule to try and find a new principle that explains **refractions**, where light does NOT follow the shortest (straight) path.

   Light travels from $A=(0,a)$, $a>0$, in medium 1 (index $n_1$) to $B=(L,-b)$, $b>0$, in medium 2 (index $n_2$), crossing the flat interface $y=0$ at $P=(x,0)$. Assume the ray is straight within each medium, and use $v=c/n$ (least time is then equivalent to least optical path length).

   1. Show that the travel time is $T(x)=\frac{n_1}{c}\sqrt{x^2+a^2}+\frac{n_2}{c}\sqrt{(L-x)^2+b^2}$.
   2. Set $dT/dx=0$ and show that $\frac{n_1\,x}{\sqrt{x^2+a^2}}=\frac{n_2\,(L-x)}{\sqrt{(L-x)^2+b^2}}$.
   3. Let $\theta_1$ be the angle between the incident segment and the normal (the $y$ axis), and $\theta_2$ the corresponding angle for the refracted segment. Show geometrically that $\sin\theta_1=\frac{x}{\sqrt{x^2+a^2}}$ and $\sin\theta_2=\frac{L-x}{\sqrt{(L-x)^2+b^2}}$.
   4. Combine the previous two results to obtain Snell's law, $n_1\sin\theta_1=n_2\sin\theta_2$.
   5. Show that this $P$ *minimizes* the travel time (compute the sign of $d^2T/dx^2$).
   6. Checks:
      1. If $n_1=n_2$, find $x$ and interpret the result.
      2. If $n_2\to\infty$ with $n_1$ fixed, what happens to the ray as it enters medium 2?

2. <a id="graded-index"></a> **[Light guiding in a graded-index fiber](#contents)**

   *key ideas: Snell's law as a conservation law, ray equation, graded-index optical fiber*

   ![Graded-index fiber](figs/gradedIndex.png)

   When the refractive index varies continuously there is no single interface at which to apply Snell's law, yet rays still bend. A graded-index optical fiber exploits this: its index is highest on the axis and decreases outward, so a ray that strays from the axis is steered back toward it. The trick is to read Snell's law as a conservation law.

   Take the fiber axis along $x$ and let $y$ be the distance from the axis. Consider a ray that stays in the $x$–$y$ plane (a *meridional* ray) in a medium with $n=n(y)$. Let $\theta$ be the angle between the ray and the $y$ axis (the normal to the layers of constant $n$), so a ray along the fiber axis has $\theta=\pi/2$; equivalently, let $\phi=\pi/2-\theta$ be the angle from the axis. The ray is launched on the axis, $y=0$, with angle $\theta_0$ (i.e. $\phi_0$).

   1. Slice the medium into thin layers of thickness $\Delta y$, each with its own index $n_j$, and apply Snell's law $n_j\sin\theta_j=n_{j+1}\sin\theta_{j+1}$ at each interface. Let $\Delta y\to0$: identify the quantity $K$ conserved along the ray and determine it from the launch conditions.
   2. To turn this into an equation for the path $y(x)$, note that $\tan\phi=dy/dx$. Show that $\sin\theta=\cos\phi=\left[1+(dy/dx)^2\right]^{-1/2}$.
   3. Combine parts 1 and 2 to obtain a first-order ODE for the trajectory, $\frac{dy}{dx}=\pm\sqrt{\left(n(y)/K\right)^2-1}$. What determines the sign? The ray turns around where $dy/dx=0$: what is $n$ there, and why must $n$ decrease away from the axis for the ray to be guided?
   4. Differentiate the ODE with respect to $x$ and show that it becomes $\frac{d^2y}{dx^2}=\frac{1}{2K^2}\frac{d(n^2)}{dy}$. (*Hint:* differentiate $(dy/dx)^2$ with the chain rule and cancel the common factor $dy/dx$. Second-order form is easier to solve for the profile below.)
   5. A standard fiber profile is parabolic, $n^2(y)=n_0^2\left(1-2\Delta\,y^2/a^2\right)$ for $|y|<a$, with $\Delta\ll1$ and $a$ the core radius. Show that the ray equation becomes the simple-harmonic-oscillator equation $y''=-\kappa^2y$, find $\kappa$ in terms of $n_0$, $K$, $\Delta$, $a$, and write the ray path $y(x)$ for the launch conditions above. (*Hint:* $x$ plays the role of time; compare the pendulum in the next problem.)
   6. For the ray to remain inside the core its amplitude must be less than $a$. Show that this requires $\sin\phi_0<\sqrt{2\Delta}$. For small $\phi_0$, show that the spatial period of the ray is $2\pi a/\sqrt{2\Delta}$, independent of $\phi_0$. Why is this property useful for a fiber that carries pulses?

3. <a id="pendulum-separatrix"></a> **[Physical pendulum in phase space](#contents)**

   *key ideas: phase-space dynamics, libration vs. rotation, separatrix, unstable fixed point*

   ![Pendulum: real space and phase space](figs/pendulumPhase.png)

   A pendulum given a small push oscillates; one spun hard enough goes round and round. The curve in phase space that separates these two motions, the separatrix, has properties that recur throughout physics.

   A physical pendulum has moment of inertia $I$ about its pivot, mass $m$, and center of mass a distance $l$ from the pivot. Its coordinate is the angle $\theta$ from the downward vertical, with conjugate momentum $p=I\dot\theta$ and energy
   $$E=\frac{p^2}{2I}+U(\theta),\qquad U(\theta)=mgl\,(1-\cos\theta).$$

   1. Find the fixed points in the phase plane $(\theta,p)$ and classify each as stable or unstable. Locate them in the figure.
   2. Show that the separatrix energy is $E_\mathrm{sep}=2mgl$. In the figure, identify which phase-space curves are librations and which are rotations, and what the dashed curve is. Why do the rotation curves not close?
   3. Using energy conservation, derive an integral formula for the period of a libration, $T(E)=2\int_{\theta_-}^{\theta_+}\frac{d\theta}{\dot\theta}$, where $\theta_\pm$ are the turning points. Write it explicitly in terms of $E$, $U(\theta)$, and $I$, eliminating $\dot\theta$.
   4. Let $E=E_\mathrm{sep}-\varepsilon$ with $0<\varepsilon\ll mgl$. Show that the period diverges logarithmically as $\varepsilon\to0^+$, $T(E)\sim A\ln(B/\varepsilon)$, and determine $A$ and $B$ up to order-one factors.

      *Hint:* the divergence comes from the neighborhood of the top. Set $\theta=\pi-\varphi$ with $|\varphi|\ll1$, use $\cos(\pi-\varphi)\approx-1+\varphi^2/2$, and isolate the part of the integral responsible for the divergence.
   5. (One sentence each.) Explain the statements "a trajectory on the separatrix is stuck there forever" and "motion near the separatrix is infinitely susceptible to disturbances" in terms of the time spent near the unstable fixed point.

4. <a id="polarization"></a> **[Polarization diagnostics with a linear polarizer](#contents)**

   *key ideas: phasor notation, Malus' law, linear vs. circular polarization*

   A rotatable linear polarizer in front of a photodetector is the simplest polarization diagnostic. Here you work out exactly what such a measurement can tell you.

   A monochromatic beam travelling in the $+z$ direction has electric field $\vec E(z,t)=\hat x\,E_{0x}\cos(kz-\omega t)+\hat y\,E_{0y}\cos(kz-\omega t+\phi)$, with real amplitudes $E_{0x},E_{0y}\ge0$ and relative phase $\phi\in[0,2\pi)$, all unknown.

   1. Write $\vec E(z,t)=\mathrm{Re}\!\left[\tilde{\vec E}_0\,e^{i(kz-\omega t)}\right]$ and show that the complex amplitude vector is $\tilde{\vec E}_0=E_{0x}\hat x+E_{0y}e^{i\phi}\hat y$. What do the ratio $E_{0y}/E_{0x}$ and the phase $\phi$ encode about the polarization state?
   2. The polarizer's transmission axis is $\hat n=\cos\theta\,\hat x+\sin\theta\,\hat y$; it transmits the complex amplitude $\tilde E_\theta=\hat n\cdot\tilde{\vec E}_0$. Show that the transmitted intensity $I(\theta)=\tfrac12c\epsilon_0|\tilde E_\theta|^2$ is $I(\theta)=\tfrac12c\epsilon_0\left[E_{0x}^2\cos^2\theta+E_{0y}^2\sin^2\theta+2E_{0x}E_{0y}\cos\phi\,\sin\theta\cos\theta\right]$. Malus' law, $I(\theta)=I_0\cos^2\theta$, applies only to linearly polarized light; the simplest case is a purely $x$-polarized beam, $E_{0y}=0$. Check that you recover it.
   3. Define *linear* polarization by the property that some polarizer angle $\theta$ extinguishes the beam completely, $I(\theta)=0$. Show that this happens if and only if $\phi=0$ or $\phi=\pi$ (assuming both amplitudes are nonzero), and find the extinction angle in each case. Sketch the field vector's motion in the $x$–$y$ plane for these two cases.
   4. Define *circular* polarization by the property that $I(\theta)$ is independent of $\theta$. What relationship must $E_{0x}$ and $E_{0y}$ obey, and what values of $\phi$ are allowed? Sketch the field vector's motion for each allowed $\phi$.
   5. Suppose the measured $I(\theta)$ has a nonzero minimum. What can you conclude about the polarization, and what does this measurement leave undetermined?

5. <a id="birefringence"></a> **[Birefringence and wave plates](#contents)**

   *key ideas: birefringence, phase retardation, half- and quarter-wave plates*

   ![Wave plate](figs/waveplate.png)

   A birefringent crystal has different indices for the two transverse polarization components, so they accumulate phase at different rates. Cut to the right thickness, the crystal becomes a device that manipulates polarization: a wave plate.

   A uniaxial crystal has ordinary index $n_o$ for $\hat y$-polarized light and extraordinary index $n_e<n_o$ for $\hat x$-polarized light, so $\hat x$ is the *fast* axis. A beam of vacuum wavelength $\lambda$ propagates in the $+\hat z$ direction, linearly polarized at angle $\theta$ to $\hat x$, and enters the crystal at $z=0$.

   1. Write $\vec E(z=0,t)$ at the entrance face.
   2. Write $\vec E(z,t)$ inside the crystal for $z>0$, keeping track of the different propagation speeds of the two components. Show that the phase lag of the $\hat y$ component relative to the $\hat x$ component is $\Delta\phi=\frac{2\pi z}{\lambda}(n_o-n_e)$.
   3. Describe the polarization state as a function of $z$. At what thickness does the polarization first return to linear? Is it the same linear polarization as at the entrance?
   4. For what minimum thickness $L$ is the output polarization the incident polarization reflected about the $\hat x$ axis? Express $L$ in terms of $\lambda$, $n_o$, $n_e$. What thickness gives reflection about the $\hat y$ axis? Compare the two answers and explain.
   5. For what minimum thickness $L$ is the output circularly polarized? State the required $\theta$. Compare with the preceding results.

6. <a id="em-interference"></a> **[Interference of co-propagating waves](#contents)**

   *key ideas: superposition, $\vec B=\hat k\times\vec E/c$, energy density, Poynting vector, intensity*

   Superposing two plane waves travelling the same way is the simplest case of interference. Before computing anything about energy flow, check how the magnetic field of the sum is related to its electric field: for a single plane wave $\vec B=\hat k\times\vec E/c$, and the first question is whether that survives superposition.

   Two coherent electromagnetic waves of the same frequency propagate in vacuum in the $+x$ direction:
   $$\vec E_1(x,t)=E_{10}\cos(kx-\omega t)\,\hat y,\qquad \vec E_2(x,t)=E_{20}\cos(kx-\omega t+\phi)\,\hat y.$$

   1. Find $\vec B_1$ and $\vec B_2$ from Faraday's law. Write the total fields $\vec E=\vec E_1+\vec E_2$ and $\vec B=\vec B_1+\vec B_2$ and show that $\vec B=\hat x\times\vec E/c$ still holds at every $x$ and $t$. Explain in one sentence why superposition preserved this relation here.
   2. Compute the electric and magnetic energy densities, $u_E=\epsilon_0E^2/2$ and $u_B=B^2/2\mu_0$, for the total field. Show that $u_E=u_B$ at every $x$ and $t$, and write the total $u(x,t)$.
   3. Compute the Poynting vector $\vec S=\vec E\times\vec B/\mu_0$ and check that $\vec S=c\,u\,\hat x$. Time-average to get the intensity $I$, and write it in the form $I=I_1+I_2+2\sqrt{I_1I_2}\cos\phi$ with $I_{1,2}$ the intensities of the individual waves. Check that the $\phi=0$ and $\phi=\pi$ cases match what you expect.

7. <a id="em-standing-waves"></a> **[Standing waves](#contents)**

   *key ideas: counter-propagating waves, $E$–$B$ misalignment, energy sloshing, zero net energy flow*

   Now let the two waves travel in opposite directions. The sum is a standing wave, and the relation $\vec B=\hat k\times\vec E/c$ that survived in the previous problem fails here: there is no single $\hat k$. The consequences for energy are the point of this problem.

   The two waves are $\vec E_1(x,t)=E_{10}\cos(kx-\omega t)\,\hat y$ and $\vec E_2(x,t)=E_{20}\cos(kx+\omega t+\phi)\,\hat y$.

   1. Find $\vec B_1$ and $\vec B_2$ and the total $\vec B$. Show that $|\vec B|\neq|\vec E|/c$ in general: find a point and time where $\vec E=0$ but $\vec B\neq0$, and vice versa.
   2. What condition on $E_{10}$ and $E_{20}$ makes the total electric field a standing wave, i.e. of the form $f(x)\,g(t)$? Assume it from now on. Write $\vec E$ and $\vec B$ in standing-wave form and find the nodes of each for arbitrary $\phi$. By how much are the $E$-nodes and $B$-nodes displaced from one another in space?
   3. Compute $u_E(x,t)$ and $u_B(x,t)$. Show that they are offset by a quarter wavelength in space and a quarter period in time, so that energy sloshes between electric and magnetic form. Find the total $u(x,t)$ and its time average, and compare the latter with the co-propagating result.
   4. Compute $\vec S(x,t)$ and its time average. Where does $\vec S$ point at a given instant, and why is its time average zero everywhere? Reconcile this with the fact that $u$ oscillates locally.

9. <a id="poynting-wire"></a> **[Heating in a resistive wire](#contents)**

   *key ideas: Joule heating, Poynting vector, energy flow in circuits*

   A resistor gets hot, so energy flows into it. But energy is carried by the fields, not by the wire: where does it enter? The Poynting vector answers this.

   A long straight wire of radius $r$, length $L$, and resistivity $\rho$ carries a steady current $I$ distributed uniformly over its cross-section.

   1. *Warmup.* Give the resistance $R$ in terms of $\rho$, $r$, $L$, and the Joule power $P$ in terms of $I$ and $R$.
   2. Find $\vec E$ inside the wire (uniform, parallel to the axis) and $\vec B$ just outside from Ampère's law. Sketch both, showing directions clearly.
   3. Assume the same $\vec E$ (magnitude and direction) exists just outside the wire. Compute $\vec S=\vec E\times\vec B/\mu_0$ just outside the surface and state whether it points along the wire, into it, or away from it.
   4. Integrate $\vec S$ over the lateral surface of the wire (radius $r$, length $L$) and compare with the Joule power $P$ from the warmup. What does this say about where the energy dissipated in a circuit element comes from?
   5. For a copper wire ($\rho=1.7\times10^{-8}\,\Omega\cdot\mathrm m$, $r=1\,\mathrm{mm}$, $L=1\,\mathrm m$) carrying $I=1\,\mathrm A$, compute $|\vec S|$ at the surface numerically.

10. <a id="displacement-disk"></a> **[Displacement current — parallel-plate capacitor](#contents)**

    *key ideas: displacement current, Poynting vector, energy conservation*

    ![Parallel-plate disk capacitor](figs/capacitorDisk.png)

    While a capacitor charges, no charge crosses the gap, yet a magnetic field appears there and energy flows into it. This is the displacement current at work; here you check the energy accounting explicitly.

    Two conducting disks of radius $R$ separated by a gap $d\ll R$ are held at voltage $V(t)$, which rises linearly from $0$ to $V_0$ between $t_1$ and $t_2$ and is constant otherwise. Neglect fringing fields.

    1. Write $\vec E$ between the plates as a function of position and time. (*Hint:* the field is uniform.)
    2. Compute the total energy $U(t)$ stored in the gap.
    3. Find the displacement current density $\vec J_d=\epsilon_0\,\partial\vec E/\partial t$ and the total displacement current through a cross-section of the gap. Compare it with the current $I(t)$ in the wires.
    4. Apply the Ampère–Maxwell law to find $\vec B(r,t)$ in the gap for $r<R$ and $r>R$. Sketch the field lines.
    5. Compute $\vec S=\vec E\times\vec B/\mu_0$ at the rim $r=R$, integrate over the appropriate surface, and verify that $\oint\vec S\cdot d\vec A=dU/dt$ (mind the sign convention for $d\vec A$).


8. <a id="em-generation"></a> **[Dipole antenna](#contents)**

   *key ideas: Fourier transforms of vector fields, longitudinal vs. transverse components, driven oscillators, generation of EM waves*

   ![Dipole and radiation pattern](figs/dipoleAntenna.png)

   How does an oscillating charge distribution launch a propagating electromagnetic wave? Working one spatial Fourier mode at a time turns Maxwell's equations into algebra plus a driven harmonic oscillator for each mode, and makes clear which part of the current radiates and in which directions.

   We use the spatial Fourier-transform convention $f(\vec Q,t)=\int d^3r\,e^{-i\vec Q\cdot\vec r}f(\vec r,t)$, so that $\nabla\to i\vec Q$. For any vector field $\vec F(\vec Q,t)$, the Helmholtz decomposition defines **longitudinal** and **transverse** parts relative to $\vec Q$: $\vec F_L=\hat Q(\hat Q\cdot\vec F)$ and $\vec F_T=\vec F-\vec F_L$, so that $\vec Q\times\vec F_L=0$ and $\vec Q\cdot\vec F_T=0$. Equivalently, $\vec F_L=P_L\vec F$ and $\vec F_T=P_T\vec F$ with projectors $P_L=\hat Q\otimes\hat Q$ and $P_T=1-P_L$.

   Two frequencies appear below and must not be confused: $\omega_Q\equiv cQ$, the natural frequency of a free wave with wavevector $\vec Q$, and $\Omega$, the frequency at which the antenna is driven.

   1. *Warming up with electrostatics.* Fourier transform Gauss's law, $\nabla\cdot\vec E=\rho/\epsilon_0$, and show that it determines the longitudinal field $\vec E_L(\vec Q)$ in terms of $\rho(\vec Q)$. In electrostatics $\nabla\times\vec E=0$: what does this imply about $\vec E_T$?
   2. Write all four Maxwell equations, with sources $\rho$ and $\vec J$, in spatial Fourier space.
   3. Eliminate $\vec B$: differentiate the Ampère–Maxwell equation with respect to time and use Faraday's law to show that $\ddot{\vec E}+\omega_Q^2\,\vec E_T=-\dot{\vec J}/\epsilon_0$. Why is it only $\vec E_T$ that appears multiplied by $\omega_Q^2$?
   4. Project this equation onto the longitudinal and transverse directions. The transverse part, $\ddot{\vec E}_T+\omega_Q^2\vec E_T=-\dot{\vec J}_T/\epsilon_0$, is a familiar system (you solved it in phy120): name it, its natural frequency, and what plays the role of the driving force. The longitudinal part, $\ddot{\vec E}_L=-\dot{\vec J}_L/\epsilon_0$, is not a new dynamical equation: Fourier transform the continuity equation $\dot\rho+\nabla\cdot\vec J=0$ and combine it with Gauss's law (part 1) to show that $\dot{\vec E}_L=-\vec J_L/\epsilon_0$ follows from them. Gauss's law thus fixes $\vec E_L$ at each instant by $\rho(\vec Q,t)$ alone: the instantaneous Coulomb field, which does not propagate.
   5. *The source: an oscillating dipole.* Two charges $\pm q$ at $\pm\vec d(t)/2$ form a dipole with moment $\vec p=q\vec d$, charge density $\rho(\vec r,t)=q\left[\delta^{(3)}(\vec r-\vec d/2)-\delta^{(3)}(\vec r+\vec d/2)\right]$, and current density $\vec J(\vec r,t)=\frac{q\dot{\vec d}}{2}\left[\delta^{(3)}(\vec r-\vec d/2)+\delta^{(3)}(\vec r+\vec d/2)\right]$, built from the charge velocities $\pm\dot{\vec d}/2$ (check the sign of the second term from the charge and velocity of the particle at $-\vec d/2$). Fourier transform both (*Hint:* $\mathrm{FT}[\delta^{(3)}(\vec r-\vec a)]=e^{-i\vec Q\cdot\vec a}$), check that the total charge $\rho(\vec Q\to0)$ vanishes, and show that for $Qd\ll1$, $\rho(\vec Q,t)\approx-i\vec Q\cdot\vec p(t)$ and $\vec J(\vec Q,t)\approx\dot{\vec p}(t)$. Verify continuity, and note that it involves only $\vec J_L$: the charge density determines $\vec J_L$ and says nothing about $\vec J_T$, which is the part that drives the transverse oscillators of part 4.
   6. *Driven modes.* Let $\vec p(t)=\vec p_0\cos\Omega t$, keeping $Qd\ll1$. Find $\vec J_T(\vec Q,t)$ and the steady-state (particular) solution of the transverse equation. Show that the field of mode $\vec Q$ oscillates at the *drive* frequency $\Omega$, not at $\omega_Q$, with amplitude proportional to $\frac{\Omega^2\,\vec p_{0T}}{\omega_Q^2-\Omega^2}$. (The divergence at $\omega_Q=\Omega$ marks the free modes that the antenna pumps energy into: these are the radiated waves.)
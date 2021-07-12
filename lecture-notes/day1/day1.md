(my-label)=
# Day 1: How we got ultracold 


We discuss the origins and development of laser cooling techniques as well as the first creation of a Bose-Einstein condensates. These works provide the solid experimental tools for the study of complex many-body systems that we will study the next days. Most of the details can be found in the attached slides. Here we will simply go through a number of details that cannot be captured in slides quite as easily.

## The two-level system from an AMO perspective

To start out, we will consider two eigenstates \\(\ket{0}\\), \\(\ket{1}\\) of the Hamiltonian \\(\hat{H}_0\\) with
\begin{align}
 \hat{H}_0\ket{0}=E_0\ket{0}, \qquad \hat{H}_0\ket{1}=E_1\ket{1}.
\end{align}
Quite typically we might think of it as a two-level atom with states 1 and 2. The eigenstates can be expressed in matrix notation:
\begin{align}
 \ket{0}=\left( \begin{array}{c} 1 \\ 0 \end{array} \right), \qquad \ket{1}=\left( \begin{array}{c} 0 \\ 1 \end{array} \right),
\end{align}
so that \\(\hat{H}_0\\) be written as a diagonal matrix
\begin{align}
    \hat{H}_0 = \left(\begin{array}{cc} E_0 & 0 \\ 0 & E_1 \end{array}\right).
\end{align}
If we would only prepare eigenstates the system would be rather boring. However, we typically have the ability to change the Hamiltonian by switching on and off laser or microwave fields. We can then write the Hamiltonian in its most general form as:

```{math}
:label: Eq_TwoLevelGeneral
\hat{H} = \frac{\hbar}{2}\left( \begin{array}{cc} \Delta  & \Omega_x - i\Omega_y\\ \Omega_x +i\Omega_y & -\Delta \end{array} \right)
```
Sometimes we will also chose the definition:
\begin{align}
\Omega = |\Omega| e^{i\varphi}=\Omega_x + i\Omega_y
\end{align}
It is particularly useful for the case in which the coupling is created by a laser. Another useful way of thinking about the two-level system is as a spin in a magnetic field. Let us remind us of the definitions of the of the spin-1/2 matrices:
\begin{align}
s_x = \frac{\hbar}{2}\left(\begin{array}{cc}
0 & 1\\
1 &  0
\end{array}
\right)~
s_y = \frac{\hbar}{2}\left(\begin{array}{cc}
0 & -i\\
i &  0
\end{array}
\right)~s_z =\frac{\hbar}{2} \left(\begin{array}{cc}
1 & 0\\
0 &  -1
\end{array}
\right)
\end{align}
We then obtain:
```{math}
:label: Eq:HamSpin
\hat{H} = \mathbf{B}\cdot\hat{\mathbf{s}}\text{ with }\mathbf{B} = (\Omega_x, \Omega_y, \Delta)
```
You will go through this calculation in the excercise of this week.

### Case of no perturbation \\(\Omega = 0\\)

This is exactly the case of no applied laser fields that we discussed previously. We simply removed the energy offset \\(E_m = \frac{E_0+E_1}{2}\\) and pulled out the factor \\(\hbar\\), such that \\(\Delta\\) measures a frequency. So we have:
\begin{align}
E_0 = E_m+ \frac{\hbar}{2}\Delta\\
E_1 = E_m- \frac{\hbar}{2}\Delta
\end{align}
We typically call \\(\Delta\\) the energy difference between the levels or the _detuning_.

### Case of no detuning \\(\Delta = 0\\)

Let us suppose that the diagonal elements are exactly zero. And for simplicity we will also keep \\(\Omega_y =0\\) as it simply complicates the calculations without adding much to the discussion at this stage. The Hamiltonian reads then:
\begin{align}
\hat{H} = \frac{\hbar}{2}\left( \begin{array}{cc} 0  & \Omega\\ \Omega &0 \end{array} \right)
\end{align}

Quite clearly the states \\(\varphi_{1,2}\\) are not the eigenstates of the system anymore. How should the system be described now ? We can once again diagonalize the system and write
\begin{align}
\hat{H}\ket{\varphi_{\pm}} = E_{\pm}\ket{\varphi_\pm}\\
E_{\pm} = \pm\frac{\hbar}{2}\Omega\\
\ket{\varphi_\pm} = \frac{\ket{0}\pm\ket{1}}{\sqrt{2}}
\end{align}
Two important consequences can be understood from this result:

- The coupling of the two states shifts their energy by \\(\Omega\\). This is the idea of level repulsion.
- The coupled states are a superposition of the initial states.

This is also a motivation the formulation of the _'bare'_ system for \\(\Omega = 0\\) and the _'dressed'_ states for the coupled system.


### General case

Quite importantly we can solve the system completely even in the general case. By diagonalizing  Eq. {eq}`Eq_TwoLevelGeneral` we obtain:
\begin{align}\label{eq:Epm}
 E_\pm = \pm \frac{\hbar}{2} \sqrt{\Delta^2+|\Omega|^2}
\end{align}
The energies can be nicely summarized as in {numref}`avoided-crossing`

```{figure} AvoidedCrossing.png
---
height: 250px
name: avoided-crossing
---
The presentation of the eigenstate on the Bloch sphere.
```

The Eigenstates then read:
```{math}
:label: eq:staticpsiplus
\ket{\psi_+}=\cos\left(\frac{\theta}{2}\right) e^{-i{\varphi}/{2}}\ket{0}+\sin\left(\frac{\theta}{2}\right) e^{i{\varphi}/{2}}\ket{1}
```

```{math}
:label: eq:staticpsiminus
\ket{\psi_-}=-\sin\left(\frac{\theta}{2}\right) e^{-i{\varphi}/{2}}\ket{0}+\cos\left(\frac{\theta}{2}\right) e^{i{\varphi}/{2}}\ket{1}
```
where
\begin{align} \label{eq:parameters}
	\tan(\theta) = \frac{|\Omega|}{\Delta}
\end{align}

## The Bloch sphere

While we could just discuss the details of the above state in the abstract, it is extremely helpful to visualize the problem on the Bloch sphere. The idea of the Bloch sphere is that the we have a complex wave function of well defined norm and two free parameters. So it seems quite natural to look for a good representation of it. And this is the Bloch sphere as drawn in {numref}`bloch-sphere`.

```{figure} BlochSphereWithVectorForLecture.png
---
height: 250px
name: bloch-sphere
---
The presentation of the eigenstate on the Bloch sphere.
```

We will see especially its usefulness especially as we discuss the dynamics of the two-state system.

## Dynamical Aspects

### Time Evolution of \\(\ket{\psi(t)}\\)

After the static case we now want to investigate the dynamical properties of the two-state system. We calculate the time evolution of \\(\ket{\psi(t)} = c_0(t)\ket{0} + c_1(t)\ket{1}\\) with the Schrödinger equation and the perturbed Hamiltonian {eq}`Eq_TwoLevelGeneral`:
\begin{align}
i\hbar \frac{d}{dt}\ket{\psi(t)}&=\hat{H}\ket{\psi(t)},\\
i \frac{d}{dt}\left(\begin{array}{c} c_0(t) \\ c_1(t) \end{array}\right) &= \frac{1}{2}\left( \begin{array}{cc} \Delta & \Omega \\ \Omega^* & -\Delta \end{array} \right) \left(\begin{array}{c} c_0(t) \\ c_1(t) \end{array} \right).
\end{align}

We have two coupled differential equations and we luckily already know how to solve them as we have calculated the two eigenenergies in the previous section. For the state \\(\ket{\psi(t)}\\) we get
```{math}
:label: eq:psitimeevolution
\ket{\psi(t)}=\lambda e^{-i{E_+}t/{\hbar}} \ket{\psi_+} + \mu e^{-i{E_-}t/{\hbar}} \ket{\psi_-}
```

with the factors \\(\lambda\\) and \\(\mu\\), which are defined by the initial state. The most common question is then what happens to the system if we start out in the bare state \\(\ket{0}\\) and then let it evolve under coupling with a laser ? So what is the probability to find it in the other state \\(\ket{1}\\):
\begin{align}
	P_1(t)=\left|\braket{1|\psi(t)}\right|^2.
\end{align}
 As a first step, we have to apply the initial condition to {eq}`eq:psitimeevolution` and express \\(\ket{\varphi}\\) in terms of {eq}`eq:staticpsiplus` and {eq}`eq:staticpsiminus`:
\begin{align}
					\ket{\psi(0)} \overset{!}{=}& \ket{0}\\
											  = & e^{i{\varphi}/{2}} \left[ \cos\left( \frac{\theta}{2}\right) \ket{\psi_+}-\sin\left(\frac{\theta}{2}\right)\ket{\psi_-}\right]
				\end{align}

By equating the coefficients we get for \\(\lambda\\) and \\(\mu\\):
\begin{align}
  \lambda = e^{i{\varphi}/{2}}\cos\left(\frac{\theta}{2}\right), \qquad  \mu = -e^{i{\varphi}/{2}}\sin\left(\frac{\theta}{2}\right).
\end{align}

One thus gets:
\begin{align}
\hspace{-2mm} P_1(t)	=&\left|\braket{1|\psi(t)}\right|^2 \\
=& \left|e^{i\varphi} \sin\left(\frac{\theta}{2}\right)\cos\left(\frac{\theta}{2}\right)\left[e^{-i{E_+}t/{\hbar}} - e^{-i{E_-}t/{\hbar}}\right]\right|^2\\
=& \sin^2(\theta)\sin^2\left(\frac{E_+-E_-}{2\hbar}t\right)
\end{align}
\\(P_1(t)\\) can be expressed with \\(\Delta\\) and \\(\Omega\\) alone. The obtained relation is called Rabi's formula:
\begin{align}
 P_1(t)=\frac{1}{1+\left(\frac{\Delta}{|\Omega|}\right)^2}\sin^2\left(\sqrt{|\Omega|^2+\Delta^2}\frac{t}{2}\right)
\end{align}

```{figure} RabiOscillation.png
---
height: 250px
name: rabi-oscillation
---
Rabi oscillations
```

### Visualization of the dynamics in the spin picture

While the previous derivation might be the standard one, which certainly leads to the right results it might not be the most intuitive way of thinking about the dynamics. They become actually quite transparent in the spin language and on the Bloch sphere. So let us go back to the formulation of the Hamiltonian in terms of spins as in Eq. {eq}`Eq:HamSpin`.

How would the question of the time evolution from 0 to 1 and back go now ? Basically, we would assume that the spin has been initialize into one of the eigenstates of the $z$-basis and now starts to rotate in some magnetic field. How ? This can be nicely studied in the Heisenberg picture, where operators have a time evolution. In the Heisenberg picture we have:
\begin{align}
\frac{d}{dt} \hat{s}_i &= \frac{i}{\hbar}\left[\hat{H},\hat{s}_i\right]\\
\frac{d}{dt} \hat{s}_i &= \frac{i}{\hbar}\sum_j B_j \left[\hat{s}_j,\hat{s}_i\right]\\
 \end{align}
So to understand we time evolution, we only need to employ the commutator relationships between the spins:
\begin{align}
[ s_x, s_y] = \hbar is_z~~[ s_y, s_z] = \hbar is_x~~[ s_z, s_x] = \hbar is_y
\end{align}
For the specific case of \\(B_x=\Omega\\), \\(B_y = B_z = 0\\), we have then:
\begin{align}
\frac{d}{dt} \hat{s}_x &= 0\\
\frac{d}{dt} \hat{s}_y &= -\Omega \hat{s}_z\\
\frac{d}{dt} \hat{s}_z &= \Omega \hat{s}_y
 \end{align}

 So applying a field in x-direction leads to a rotation of the spin around the x axis with velocity \\(\Omega\\). We can now use this general picture to understand the dynamics as rotations around an axis, which is defined by the different components of the magnetic field.

 ## A few words on the quantum information notation

The qubit is THE basic ingredient of quantum computers. A nice way to play around with them is actually the [IBM Quantum experience](https://quantum-computing.ibm.com/). However, you will typically not find Pauli matrices etc within these systems. The typical notation there is:

-  \\(R_x(\phi)\\) is a rotation around the x-axis for an angle \\(\phi\\).
- Same holds for \\(R_y\\) and \\(R_z\\).
- _X_ denotes the rotation around the x axis for an angle \\(\pi\\). So it transforms \\(\ket{1}\\) into  \\(\ket{0}\\) and vise versa.
- _Z_ denotes the rotation around the x axis for an angle \\(\pi\\). So it transforms \\(\ket{+}\\) into  \\(\ket{-}\\) and vise versa.

The most commonly used gate is actually one that we did not talk about at all, it is the _Hadamard_ gate, which transforms \\(\ket{1}\\) into  \\(\ket{-}\\) and \\(\ket{0}\\) into  \\(\ket{+}\\):
\begin{align}
\hat{H}\ket{1} &= \ket{-}  ~   \hat{H}\ket{0} &= \ket{+}\\
\hat{H}\ket{-} &= \ket{1}  ~   \hat{H}\ket{+} &= \ket{0}
\end{align}


## Rotating frame

Until now, we discussed the properties of two coupled levels. However, we did not elaborate at any stage how such a system might emerge in a true atom. Two fundamental questions come to mind:

- How is it that a laser allows to treat two atomic levels of very different energies as if they were degenerate ?
- An atom has many energy levels $E_n$ and most of them are not degenerate. How can we reduce this complicated structure to a two-level system?

The solution is to resonantly couple two of the atom's levels by applying an external, oscillatory field, which is very nicely discussed in chapter 12 of Ref. {cite}`cohen1998atom`. We will discuss important and fundamental properties of systems with a time-dependent Hamiltonian.

We will discuss a simple model for  the atom in the oscillatory field. We can write down the Hamiltonian:

\begin{align}
 \hat{H} = \hat{H}_0 + \hat{V}(t).
\end{align}
Here, \\( \hat{H}\_0 \\) belongs to the atom and V(t) describes the time-dependent field and its interaction with the atom. We assume that \\(\ket{n}\\) is an eigenstate of \\(\hat{H}\_0\\) and write:
			\begin{align}
				\hat{H}_0\ket{n} = E_n \ket{n}.
			\end{align}

If the system is initially prepared in the state \\(\ket{i}\\), so that
\begin{align}
	\ket{\psi(t=0)} = \ket{i},
\end{align}
what is the probability
\begin{align}
	P_m(t) = \left|\braket{m|\psi(t)}\right|^2
\end{align}
to find the system in the state \\(\ket{m}\\) at the time t?

### Evolution Equation

The system \\(\ket{\psi(t)}\\) can be expressed as follows:
\begin{align}
	\ket{\psi(t)} = \sum_n \gamma_n(t) e^{-i{E_n}t/{\hbar}} \ket{n},
\end{align}
where the exponential is the time evolution for \\(\hat{H}_1 =~0\\). We plug this equation in the Schrödinger equation and get:
```{math}
:label: eq:timeev
i\hbar \sum_n\left(\dot{\gamma}_n(t)-i\frac{E_n}{\hbar}\gamma_n(t)\right)e^{-i{E_n}t/{\hbar}}\ket{n} = \sum_n \gamma_n(t) e^{-i{E_n}t/{\hbar}}\left(\hat{H}_0 + \hat{V}\right) \ket{n}
```

\begin{align}
\Longleftrightarrow i\hbar\sum_n \dot{\gamma}_n(t) e^{-i{E_n}t/{\hbar}} \ket{n}
 = \sum_n \gamma_n(t) e^{-i{E_n}t/{\hbar}} \hat{V} \ket{n}
\end{align}

If we multiply {eq}`eq:timeev` with \\(\bra{k}\\) we obtain a set of coupled differential equations
				\begin{align}
					i\hbar \dot{\gamma}_k e^{-i{E_k}t/{\hbar}} &= \sum_n \gamma_n e^{-{E_n}t/{\hbar}}\bra{k}\hat{V}\ket{n},\\
					i\hbar \dot{\gamma}_k &= \sum_n \gamma_n e^{-i {(E_n-E_k)}t/{\hbar}} \bra{k} \hat{V}\ket{n}
				\end{align}
				with initial conditions \\(\ket{\psi(t=0)}\\). They determine the full time evolution.

The solution of this set of equations depends on the details of the system. However, there are a few important points:


- For short enough times, the dynamics are driving by the coupling strength \\(\bra{k}\hat{V} \ket{n}\\).
- The right-hand sight will oscillate on time scales of \\(E_n-E_k\\) and typically average to zero for long times.
- If the coupling element is an oscillating field \\(\propto e^{i\omega_L t}\\), it might put certain times on resonance and allow us to avoid the averaging effect. It is exactly this effect, which allows us to isolate specific transitions to a very high degree. This is the idea behind atomic and optical clocks, which work nowadays at \\(10^{-18}\\).


We will now see how the two-state system emerges from these approximations and then set-up the perturbative treatment step-by-step.

### Rotating wave approximation
We will now assume that the coupling term in indeed an oscillating field with frequency \\(\omega_L\\), so it reads:
\begin{align}
\hat{V} = \hat{V}_0 \cos(\omega_Lt) = \frac{\hat{V}_0}{2} \left(e^{i\omega_lt}+e^{-i\omega_lt}\right)  
\end{align}
We will further assume the we would like use it to isolate the transition \\(i\rightarrow f\\), which is of frequency \\(\hbar \omega_0 = E_f - E_i\\). The relevant quantity is then the detuning \\(\delta = \omega_0 - \omega_L\\). If it is much smaller than any other energy difference \\(E_n-E_i\\), we directly reduce the system to the following closed system:

\begin{align}
i\dot{\gamma}_i &= \gamma_f e^{-i \delta t} \Omega\\
i\dot{\gamma}_f &= \gamma_i e^{i \delta t}\Omega^*
\end{align}
Here we defined \\(\Omega = \bra{i} \frac{\hat{V_0}}{2\hbar}\ket{f}\\). And to make it really a time-of the same form as the two-level system from the last lecture, we perform the transformation \\(\gamma_f = \tilde{\gamma}_f e^{i\delta t}\\), which reduces the system too:
\begin{align}
i \dot{\gamma}_i &= \Omega \tilde{\gamma}_f \\
i\dot{\tilde{\gamma}}_f &= \delta \tilde{\gamma}_f + \Omega^* \gamma_i
\end{align}
This has exactly the form of the two-level system that we studied previously.

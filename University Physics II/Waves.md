There are two types of waves:
* **Mechanical Waves**
	* Disturbance that travels through medium
	* Medium goes through displacement as wave travels
	* Examples: ripples in water, sound
* **Electromagnetic Waves**
	* Disturbance in electromagnetic field that can travel without a medium (in a vacuum)
	* Travels through a VACUUM at the speed of light, v = c = 2.99792458 × 108 m/s
	* Examples: light, x-ray, microwave
---
Types of **Mechanical Waves**:
* **Transverse Waves**
	* Displacement of particles is perpendicular (**transverse**) in respect to the direction of propagation
* **Longitudinal Waves** 
	* Displacement of particles is along the direction of (**longitudinal**) of propagation
---
**Periodic Wave** - each particle of the medium undergoes a periodic motion and is characterized by the following parameters:
* **Wavelength (λ)** - length of one complete cycle (trough to trough or peak to peak) (unit of meters)
* **Frequency (f)** - number of complete cycles in one second (inverse of time) (unit of hertz)
* **Time (T)** - time it takes for one cycle to be completed (inverse of frequency) (unit of hertz)
* **Amplitude (A)** - Maximum displacement of wave from equilibrium position
* **Speed** of any *periodic wave* is shown as ===*v = λf*=== (m/s)
---
### Practice Exercises: Speed of Waves 
What is the wavelength of an earthquake that shakes you with a frequency of 10.0 Hz and gets to another city 84.0 km away in 12.0 s?
![[Drawing 2023-08-21 11.27.54.excalidraw]]

A Girl Scout is taking a 10.00-km hike to earn a merit badge. While on the hike,  she sees a cliff some distance away. She wishes to estimate the time required to walk to the cliff. She knows that the speed of sound is approximately 343 meters per second. She yells and finds that the echo returns after approximately 2.00 seconds. If she can hike 1.00 km in 10 minutes, how long would it take her to reach the cliff?
![[Drawing 2023-08-21 11.34.49.excalidraw]]
___
**Simple Harmonic Motion**
$$y(x,t) = A*sin(kx \pm \omega * t + \phi)$$
* With – sign if wave moves toward positive x, and + sign if wave moves toward negative x.
* y is displacement of particle at time t and position x about equilibrium position
* A is the amplitude of the wave
* The quantity k is called the wave number, and is defined as ===k = 2π/λ===  
* The quantity ω is called the angular frequency, and is defined as ===ω = 2πf = 2π/T===
* The quantity Φ is called the initial phase (or phase shift)
___
Any wave function satisfies the **wave equation**: $\frac{\delta ^2 y}{\delta x^2} = \frac{\delta^2y}{v^2\delta t^2}$
___
### Practice Exercises: Simple Harmonic Motion and Wave Equation 
A wave is modeled by the wave function $y(x,t)=(0.30)sin([\frac{2\pi}{4.5}(x-18.00\frac{m}{s}t)]$. What are the amplitude, wavelength, wave speed, period, and frequency of t he wave? What is the propagation of this wave?
	![[Drawing 2023-08-21 13.27.44.excalidraw]]

A swimmer in the ocean observes one day that the ocean surface waves are  
periodic and resemble a sine wave. The swimmer estimates that the vertical distance  
between the crest and the trough of each wave is approximately 0.45 m, and the  
distance between each crest is approximately 1.8 m. The swimmer counts that 12  
waves pass every two minutes. Determine the simple harmonic wave function that  
would describe these waves.
![[Drawing 2023-08-21 13.35.42.excalidraw]]

---
**Stretched String** can be characterized by its linear mass density $\mu$ $$\mu = \frac{mass\ of\ string}{length\ of\ string} = \frac{m}{l}$$
**Speed of a stretched string** $$|v| = \sqrt{\frac{F_T}{\mu}}$$Waves carry energy and the energy carried by a wave on a stretched string is 
$$K_\lambda = \frac{1}{4}\mu A^2\omega ^2\lambda$$
$$U_\lambda = \frac{1}{4}\mu A^2\omega^2\lambda$$
$$E_\lambda = \frac{1}{2}\lambda A^2 \omega^2 \lambda$$
**Wave Intensity**, I, is the average power it carries per unit area: $I=P/A$
**Inverse square-law for intensity**: if waves are spread out in all directions and no energy is absorbed then this is considered a *spherical wave* and the intensity I at any distance *r* from a wave source is inversely proportional to $r^2$ so the inverse square law can be expressed as:
$$\frac{I_1}{I_2} = \frac{r^2_2}{r^2_1}$$
**Averaged power of a sinusoidal mechanical wave** $$P_{ave}=\frac{1}{2}\mu A ^2\omega ^2 v$$
___
#### **Reflection**
* Fixed end:
	* Wave acts on support and the support acts on the material producing the initial wave to create a reversed opposite wave (going back the way it came but on the opposite side of the axis it was originally traveling)![[Pasted image 20230822144140.png]]
* Free end:
	* Travels on the same side back towards the source![[Pasted image 20230822144116.png]]
The possible **frequencies of a vibrating string in a musical instrument** are given by $$f_n=\frac{n}{2L}\sqrt{\frac{F_T}{\mu}}$$




#### Base Case
Base case for 0 and 1:
$$1: 1 = (-1)^2 \cdot1 \checkmark \ \ \ 2: -1 = (-1)^3 \cdot1 \checkmark$$
#### Inductive Hypothesis
We assume the following to be true:
$$F_k=(-1)^{k+1}F_k$$
#### Inductive Step
We need to prove the following:
$$F_{k+1}=(-1)^{k+2}F_{k+1}$$
We can do the following conversion:
$$F_{k+1} = (-1)^{k+2}(F_{k} + F_{k-1})$$
Plug in and simplify:
$$(-1)^{k+2}(F_{k} + F_{k-1}) = (-1)^{k+2}F_{k+1}$$
We're left with: $$(F_{k} + F_{k-1}) = F_{k+1}$$
Which we know to be true because this is the definition of the Fibonacci sequence
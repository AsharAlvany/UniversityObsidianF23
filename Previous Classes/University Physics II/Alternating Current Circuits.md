**AC Source** - a device that supplies a sinusoidal varying voltage
$$v = V_0\sin\omega t$$
$$i = I_0\sin\omega t$$
Phasors - to represent sinusoidal varying voltages and currents. Where the magnitude of the phasor is the amplitude of the current. The projection on the vertical axis is the instantaneous current
The RMS values allow dc formulas to be applied to ac circuits
$$I_{RMS}=\frac{I_0}{\sqrt{2}}$$
	The same is applicable for voltage
When a resistor is connected with an ac source, the voltage and current are related by Ohm's law
$$V_R(t) = V_0\sin\omega t$$
The resistance does not depend on the frequency of the ac source
Current is in phase with voltage and $V_R=IR$
When an inductor is connected with an ac source the voltage and current amplitudes are related by
$$\frac{V_L}{I} = \omega L = X_L$$
	where X is the **reactance** in ohms and $\omega = 2\pi f$
Amplitudes are related by $V_L = IX_L$ Voltage curve leads current curve by a quarter cycle
When a capacitor is connected with an ac source the voltage and current are related by
$$\frac{V_C}{I} = \frac{1}{\omega C} = X_C$$
Amplitudes are related by $V_C = IX_C$ Voltage curve lags current curve by a quarter cycle
In an RLC circuit in series the voltage and the current are related as the following
![[Pasted image 20231129234227.png]]
The impedance of the circuit is given by
![[Pasted image 20231129234319.png]]
The voltage can either lag or lead the current given by
![[Pasted image 20231129234450.png]]
**Power**
Resistor
- voltage and current are in phase
- instantaneous power $p = vi$
Inductor
- voltage leads the current by 90
- the power is negative when v and i have opposite signs
- the average power is zero
Capacitor
- voltage lags the current by 90
- the power is negative when v and i have opposite signs
- the average power is zero
___
For an arbitrary combination of resistors, inductors, and capacitors, the average **power** is positive, and is given by
$$P = \frac{V^2_{RMS}}{R}$$
![[Pasted image 20231130001620.png]]
The average **power** associated with a circuit element in any AC circuit is given by
![[Pasted image 20231130001723.png]]
The factor cos $\phi$ is called the **power factor** of the circuit. When the phase angle is 0 the average power dissipated is
![[Pasted image 20231130001932.png]]
Resonance is the point at which $X_L$ and $X_C$ are equal. At this frequency the impedance Z has its smallest value equal simply to the resistance R and the current reaches its maximum possible value
The angular frequency at which the resonance peak occurs is called the **resonance angular frequency**
![[Pasted image 20231130003023.png]]
The sharpness of the peak is known as the **quality factor** of the circuit
![[Pasted image 20231130003227.png]]
In a transformer, the ratio of the voltages across the primary and secondary coils is equal to the ratioof the number of turns in the coils
![[Pasted image 20231130004348.png]]
The secondary coil is the input while the primary coil is the output

### Types of electronic devices: 

#### Passive devices: 

1. Resistors: 
	1. introduces resistance to the flow of electric current in an electrical current, which therein limits the current. 
	2. magnitude of the opposition to flow is called resistance
	3. resistance is measured in $\Omega$ , Ohms.
		1. R = V/I -> Ohm's Law
	4. Resistors dissipate electrical energy given $P = I^{2}R$ Watts or J/s
	5. made from a variety of materials, such as carbon film, metal film, etc
	6. values vary from milliohms to mega ohms and the tolerance of typical resistors varies from 1% to 5%, but there are more expensive kinds that vary from 0.1% to 0.001%.
	7. different types of resistors by size & form: 
		1. through -hole resistors
		2. surface-mount resistors SMD/SMT
	8. different resistors by application: 
		1. common resistor: used in current limiter, setting biases, voltage dividers, pull up, filtering, termination resistors, load resistors, etc.
		2. precision resistor for voltage feedback circuits, voltage references
		3. current sense resistors
		4. power resistors
2. Capacitors: 
	1. meant to store electrical energy and deliver it to the circuit when needed
	2. capacity of the capacitor to store charge is known as the capacitance of that capacitor, C, measured in Farads, F.
	3. various uses include: 
		1. blocking the flow of DC voltage and permits the flow of AC hence used for circuit coupling
		2. bypasses the unwanted signal frequencies to ground
		3. used for phase shifting or creating time delays
		4. can be used for filtration, such a removing ripples from the rectified waveform
		5. to get a tuned frequency
		6. as a motor starter
	4. Capacitance equation : $C=\frac{Q}{V}$ , where Q= charge, and V= Voltage
	5. if voltage across a capacitor is constant, there will be no current flow through the capacitor
	6. current will only flow across a capacitor if the voltage across it is changing with time, for ex: AC current
		1. this is why capacitors block DC 
		2. and allow AC signals to pass through when used in time series of the path of the signal
	7. $E= \frac{1}{2}V^{2}$ , is the equation for energy stored in a capacitor
	8. A capacitor consists of two parallel plates separated by a non conductive region
	9. $C=\epsilon \frac{A}{d}$ , A = plate area, d = distance between plates, and $\epsilon$ = dielectric permittivity
	10. capacitors fall into 2 main categories: 
		1. Polarized Capacitors: 
			1. can be given positive voltage in only one direction and placed on board in only one direction
			2. are electrolytic and tantalum capacitors
		2. Non-Polarized Capacitors:
			1. the ceramic capacitor, polyester capacitor, paper capacitor, and does not have polarity and can be placed in any direction
3. Inductors:
	1. aka coil or choke
	2. a passive, two terminal electric component that stores magnetic energy when an electric current is passed through it
	3. insulated wire wound into a coil around the core of some material
	4. denoted by inductance L, measured in Henry H
	5. when time varying current flows through an inductor, the magnetic field is created which induces an electromotive force in the inductor
	6. $V=L\frac{di}{dt}$
		1. there is a voltage across the inductor only if the current through it is changing
		2. DC produces no voltage, and in general, an inductor blocks the AC and passes the DC
4. Diodes: 
	1. a two terminal semiconductor device that allows an electric current to pass in one direction while blocking it in the reverse direction
	2. made up of one semiconductor of P-type material and another of N-type material, which are typically sillicone and germanium
	3. they conduct when a minimum forward voltage is applied across it and remain off during reverse bias condition
	4. applications include:
		1. power conversion (AC to DC)
		2. clamping the voltage
		3. demodulation of signals
	5. types of diodes:
		1. rectifier, switching, light-emitting, zener, schottky, ESD, tunnel, varicap, photodiode, laser diode 
5. Crystals:
	1. quartz crystal is made from a thin piece of quartz wafer. This wafer is made from silicone material, and is tightly fitted and controlled between two parallel metalized surfaces, which make an electrical connection
	2. When a voltage is applied, the crystal vibrates with a certain fundamental frequency which creates alternating waveform which swings between high and low levels, aka Piezoelectric effect. 
		1. this property is why they are used in electronic circuits along with active components to create a stable clock input to the processor
6. Relays:
	1. an electromagnetic switch that opens and closes potential-free contacts. 
	2. consists of armature, coil, spring, and contacts
	3. when voltage is applied to the coil, it creates a magnetic field which then attracts the armature and causes a change in the state of the circuit to change between open or closed. 
	4. this is usually used to control a high-power circuit while using a low-power signal
	5. two main types:
		1. electromechanical relay (EMR)
		2. solid-state relay (SSR)
			1. has a photodiode at its input side and a switch device at the output side
			2. when a specific voltage is applied to the inpus, the photodiode conducts and triggers the base of the transistor to cause the switching. 
			3. more widely used than EMR


#### Active Devices

1. Transistors:
	1. a nonlinear semiconductor three-terminal device. 
	2. considered to be one of the most important devices in electronics
	3. two main functions:
		1. to amplify input signals
			1. when used in the active region
		2. act as solid-state switches
			1. when operated either in saturation or a cut-off region
	4. offers very high input resistance and very low output resistance
	5. types of transistors:
		1. BJT: NPN and PNP
		2. FET: JFET, P-MOSFET, N-MOSFET
2. MOSFET:
	1. aka metal oxide semiconductor field-effect transistor
	2. a semiconductor device that is different than bipolar junction transistor due to its construction
	3. the applications remain the same as a regular transistor
	4. has four terminals such as drain, gate, source, and body
		1. body is shorted with a source terminal
		2. gate is insulated from the channel
	5. offers a high resistance as compared to BJT
3. Integrated Circuits:
	1. an electronic device built on a semiconductor wafer, usually made of sillicon
	2. contains millions of mini transistors, resistors, and capacitors
	3. powered by external power supply for their operations
	4. perform data or signal processing tasks
	5. types of ICs:
		1. digital, analog, mixed-signal
		2. 


helpful webpages: 
https://www.electrosmash.com/fuzz-face
https://www.experimentalistsanonymous.com/diy/index.php?dir=Schematics/
https://www.diystompboxes.com/smfforum/index.php?topic=118272.0

![[Pasted image 20241102004832.png]]


side note: what actually is the difference between trs and ts? 

**TS** = tip, sleeve
**TRS** = tip, ring, sleeve

trs and ts describe the connection types. TRS has three connection points, whereas TS only has two. Although TS is usually seen in guitar/ instrument cables, and TRS is seen with speakers, the main differences between cable functionality lie in the cables themselves, not the connectors. 

Guitar/ instrument cables are basically one wire wrapped with another wire (shielding), to prevent interference. Speaker or interconnect cables are two heavy copper wires running side by side like a power cord, and are heavier in gauge to be able to handle higher currents. Using an instrument grade cable for speakers can fry your cable, and also damage your equipment. Using a speaker cable for a guitar would be very noisy, as it has no shielding. 


### Fuzz investigation: 

1. How do fuzz pedals work? How do transistors create overdrive and the characteristic clipping effect heard in stuff like fuzz face?
	1. fuzz is distortion, clipping the top or bottom of a signal 
	2. to create clipping effects, we need to drive a circuit with a signal bigger than it can linearly respond to 
	3. for diode clipping, we need to drive a diode with a signal bigger than the diode turn-on voltage
		1. 0.6V for sillicone
		2. 0.2-0.3 for germanium 
	4. for transistor distortion, we need to drive the circuit with a signal that, when multiplied by the transistor gain, is bigger than the transistor-circuit's output can swing
	5. distortion can have different "timbres" depending on amplitude of added harmonic frequencies
		1. for ex, asymmetric clipping sounds different than symmetric clipping, and soft sounds different than hard clipping
	6. modern hi-gain tones are created by radically hi-pass filtering the signal around 1kHz. this reduces intermodulation distortion(IMD) effect from lower frequencies and produces a "tighter" and more "pronounced" tone
	7. overdrive, distortion, and fuzz can be differentiated based on how long the harmonic content lasts
		1. a guitar generates most of its harmonic content and greatest amplitude in the first fraction of a second, and then declines: 
			1. ![[Pasted image 20241102144932.png]]
		2. the main thing that differentiates the sound of a pedal, and what it's labeled as, is whether the clipping threshold and added harmonic content remains above the average input signal level, or whether the gain that the circuit applies to the input signal pushes it up high enough such that, even after the string has settled, it still remains near that threshold
	8. a fuzz circuit is usually a 2 or 3 stage amplifier. they typically use transistors. 
	9. a fuzz pedal follows the same guidelines as an overdrive, input, amplification, clipping, but on a more extreme level. hard clipping turns an input sine wave into a rigid square wave
		1. ![[Pasted image 20241102145837.png]]

to better understand different schematics, we will also need a basic understanding of [[Circuits]].
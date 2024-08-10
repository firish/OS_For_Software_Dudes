## Physical Structure of Memory
At the most fundamental level, memory in modern computers is primarily made up of transistors and capacitors. 

The significant parts of memory are,

- 1) capacitor:
A capacitor is an electric component that temporarily stores electricity.
It typically comprises two conductive plates separated by a dielectric (insulating) material.
The plates are typically metal (the most common is aluminum) and the dielectric is a high-potassium material like hafnium oxide.

The capacitor stores charge by accumulating electrons on the plates.
When a voltage is applied, electrons accumulate on one plate, creating a negative charge, while the other plate develops a corresponding positive charge due to the absence of electrons.
The dielectric material between the plates prevents the charges from crossing over, allowing the capacitor to hold the charge.
This charged state is interpreted as a binary '1'.
When there is no significant difference between the two plates, it is interpreted as a binary '0'.

Advanced Photolithography, stacking capacitors vertically, and a high-k dielectric (allowing high capacitance) allow the capacitors to be extremely small.


A regular capacitor used in circuits.

![Regular Capacitor](https://theengineeringmindset.com/wp-content/uploads/2019/10/inside-a-capacitor.png)

A paper capacitor, that takes less space.

![Paper capacitor](https://www.tdk.com/en/tech-mag/sites/default/files/2019-06/img_electronics_files_primer_vol1_1_3.gif)


- transistor
- word line
- bit line
- Sensor and Amplifier
- Memory Controller

### Understanding the components of memory 
The first major type of memory is DRAM (Dynamic RAM).
The major memory of phones and laptops is generally of this type.


- Capacitor: Stores charge to represent data (1 or 0).
- Transistor: Acts as a switch to control whether the capacitor is connected to the read/write circuitry.
- Data Storage: Each memory cell in DRAM consists of one capacitor and one transistor. The capacitor holds an electric charge (representing a binary 1) or no charge (representing a binary 0).
- Refresh Cycle: Because capacitors leak charge over time, the data needs to be refreshed periodically by reading and then rewriting it, which is why it's called "dynamic."

memory is slow. trip is slow. getting memory closer to cpu physically.








when we fetch from memory, how do we give address to the actual data? 
how is this different type of data actually stored in memory?

DDRM?

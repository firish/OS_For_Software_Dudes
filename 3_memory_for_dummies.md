## Physical Structure of Memory
At the most fundamental level, memory in modern computers is primarily made up of transistors and capacitors. 

The significant parts of memory are,

1) Capacitor:

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
capacitance = e0 (of dielectric) *  S (surface area of capacitor) / d (thickness of dielectric)

![Paper capacitor](https://github.com/user-attachments/assets/bc83e4c8-d47f-4efc-a2c8-1fce0b5f341c)


2) Transistor

Transistors are fundamental components in memory cells, particularly in DRAM and SRAM. 
They act as switches that control whether a capacitor (in DRAM) or a set of cross-coupled inverters (in SRAM) can be read from/written to.

Transistors in memory are tiny, flat, and rectangular structures embedded within the silicon wafer. 
They consist of three primary regions: the source, drain, and gate.
The gate is separated from the channel (the area between the source and drain) by a thin insulating layer, usually made of silicon dioxide or a high-k material.

Source and Drain: These are heavily doped regions of the semiconductor material (usually silicon) that allow current to flow when the transistor is turned on.
Channel: The region between the source and drain where current flows when the transistor is on.
Gate: This is the control electrode placed above the channel. The gate controls whether the current can flow from the source to the drain by applying a voltage.

The most common type of transistor used in memory is a MOSFET (Metal-Oxide-Semiconductor Field-Effect Transistor)
nMOS (n-type MOSFET): Conducts when a positive voltage is applied to the gate.
pMOS (p-type MOSFET): Conducts when a negative voltage is applied to the gate.
IMP: In memory cells, nMOS transistors are more common due to their higher electron mobility.

Advanced Lithography, scaling down the channel, High-k Dielectrics, 3D stackable structures like FinFET allow for extremely small transistors.

A regular transistor.

![Transistor](https://www.electronicshub.org/wp-content/uploads/2015/01/Introduction-to-Transistors-Featured-Image.jpg)

A MOSFET.

![MOSFET](https://github.com/user-attachments/assets/d825e63f-fa3d-487b-9652-e2d70c29c41b)



## DRAM
The first major type of memory is DRAM (Dynamic RAM).



- Capacitor: Stores charge to represent data (1 or 0).
- Transistor: Acts as a switch to control whether the capacitor is connected to the read/write circuitry.
- Data Storage: Each memory cell in DRAM consists of one capacitor and one transistor. The capacitor holds an electric charge (representing a binary 1) or no charge (representing a binary 0).
- Refresh Cycle: Because capacitors leak charge over time, the data needs to be refreshed periodically by reading and then rewriting it, which is why it's called "dynamic."

memory is slow. trip is slow. getting memory closer to cpu physically.








when we fetch from memory, how do we give address to the actual data? 
how is this different type of data actually stored in memory?

DDRM?

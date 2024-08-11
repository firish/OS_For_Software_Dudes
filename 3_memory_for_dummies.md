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

NOTE: 
BJT: Operates using both electrons and holes (bipolar operation) and is current-controlled.
MOSFET: Operates using only one type of charge carrier (unipolar) and is voltage-controlled.
MOSFETs are preferred in memory cells because of their high switching speed, noise immunity, and low power consumption.


## DRAM
The first major type of memory is DRAM (Dynamic RAM).
DRAM is the RAM of a computer. When a device spec says that it has 8GB RAM, most of it is DRAM.
This is volatile memory and is reset once the device is turned off. 

Structure:
DRAM is a grid.
The grid is made by the word line and bit line.
At each intersection of the two lines is a memory cell that has a capacitor and a transistor and holds 1 bit.

Capacitor:
In DRAM, each bit of data is stored in a tiny capacitor. The capacitor can either be charged (storing a '1') or discharged (storing a '0'). However, capacitors naturally lose their charge over time, which is why DRAM is called "dynamic" – it requires periodic refreshing to maintain the data.

Transistor:
Each capacitor is paired with a transistor to form a DRAM memory cell. The transistor acts as a switch that controls access to the capacitor. The capacitor can be charged or discharged when the transistor is on (activated by a voltage on the gate). The transistor allows the stored charge in the capacitor to be read or modified.

Word Line:
The word line is a control line that runs across a row of memory cells. It connects to the gates of the transistors in that row. When the memory controller activates a specific word line, it turns on all the transistors in that row, allowing data to be read from or written to the capacitors in that row.

Bit Line:
The bit line is a conductive line that runs vertically, connecting to the drain terminals of the transistors in a column of memory cells. When a word line is activated, the charge stored in the capacitor of the selected memory cell is transferred to the bit line, where it can be detected and read as a '0' or '1'. The bit line is also used during the write operation to set the charge in the capacitor.

Memory Controller:
The memory controller is a crucial part of the DRAM operation. It manages all communication between the CPU and the DRAM modules. The memory controller is responsible for:
Addressing: It decodes the memory address sent by the CPU and selects the appropriate row (via the word line) and column (via the bit line) in the DRAM array.
Data Read/Write: It controls the flow of data to and from the DRAM cells during read and write operations.
Refreshing: Since DRAM cells lose charge over time, the memory controller regularly refreshes the data by reading and rewriting it back to the same cells to maintain the stored information.

Row Address Strobe (RAS) and Column Address Strobe (CAS):
These signals are used by the memory controller to select the specific row and column of memory cells in the DRAM array. RAS activates the word line to select a row, and CAS activates the appropriate bit line to select a column. Together, they enable access to a specific memory cell.

Sense Amplifier (Sensor):
The sense amplifier plays a critical role in reading data from DRAM. When a word line is activated, the charge from the capacitor is transferred to the bit line, causing a small voltage change. If the capacitor is charged, the charge of the bit line increases slightly. If the capacitor was uncharged, the charge of the bit line was reduced slightly. The sense amplifier detects this tiny voltage difference and amplifies it to a level that can be interpreted as a '0' or '1'. It then sends the amplified signal to the memory controller for processing.


Precharge Circuit:
After a read or write operation, the bit lines need to be reset to a precharge voltage level to prepare for the next operation. The precharge circuit ensures that the bit lines are at the correct voltage before the next access, ensuring accurate read and write operations.
Refresh Logic:

Refresh circuit:
DRAM cells need to be periodically refreshed to maintain data integrity because the charge in the capacitors dissipates over time. The refresh logic in the memory controller ensures that each row of DRAM cells is refreshed within a specified time interval (typically every few milliseconds). The refresh operation reads the data from the cells and writes it back to restore the charge.

DRAM Operation: Step-by-Step
Addressing:
The CPU sends a memory address to the memory controller, which decodes it into row and column addresses.
The memory controller activates the appropriate word line (via RAS) to select the desired row of memory cells.

Reading Data:
When the word line is activated, the transistors in the selected row turn on, allowing the charge stored in each capacitor to transfer to the corresponding bit lines.
The sense amplifiers connected to the bit lines detect the small voltage change caused by the charge and amplify it to a recognizable '0' or '1'.
The amplified data is then sent to the memory controller and ultimately to the CPU.

Writing Data:
To write data, the memory controller activates the appropriate word line and bit line.
The desired data (either a '0' or '1') is driven onto the bit line, and the transistor allows this data to charge or discharge the capacitor in the selected memory cell.
The word line is then deactivated, storing the data in the capacitor.

Refreshing Data:
The memory controller periodically initiates a refresh cycle to prevent data loss. During a refresh, each row of memory cells is read and rewritten to restore the charge in the capacitors.
The refresh operation is managed automatically by the memory controller and happens in the background without disrupting normal read/write operations.

Simplified DRAM Architecture.

![DRAM ARCH](https://i.ytimg.com/vi/x3jGqOrXXc8/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDfvK_a5tHTAqVZQsp-j9SrYaCprw)

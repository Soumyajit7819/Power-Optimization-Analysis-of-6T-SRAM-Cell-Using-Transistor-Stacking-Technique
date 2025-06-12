# Power Optimization Analysis of 6T SRAM Cell Using Transistor Stacking Technique
## Using Cadence Virtuoso

> [!NOTE]
> **Abstract**-Efficient power utilization is a paramount concern in the VLSI industry, particularly with the increasing density of memory systems. The SRAM cell stands as a cornerstone component in various memory devices, including cache memories and CPU registers. However, the power consumption escalation is largely attributed to transistor leakage current. Hence, there arises a critical necessity to curtail power consumption in each memory cell. This project undertakes a meticulous examination of power optimization in the 6T SRAM cell through the application of the transistor stacking technique. This technique entails the use of two half-size transistors instead of a single full-size transistor, interconnected in series and maintained in an off state. This configuration effectively mitigates leakage current, consequently diminishing the power consumption of the SRAM cell. The project encompasses a comprehensive power consumption analysis of 6T SRAM cells, both with and without the stacking technique, conducted at varying voltages using the Cadence Virtuoso tool.

## 6T SRAM Cell

A 6T SRAM (Static Random Access Memory) cell is a basic building block of SRAM memory arrays commonly used in digital integrated circuits. It consists of six transistors organized in a specific configuration to store a single bit of data. The 6T SRAM cell comprises:

1.	Two cross-coupled inverters: These are formed by four transistors (two n-type and two p-type) connected in a feedback loop. They store the bit of data (0 or 1) in a latch-like structure.
2.	Access transistors: These are two additional transistors used for reading from and writing to the cell. They control the access to the cross-coupled inverters.

The 6T SRAM cell is known for its high speed and stability, making it suitable for use in cache memories and other applications where fast, reliable access to data is critical. 

### Working of 6T SRAM Cell

The 6T SRAM cell operates as a bistable latch, storing a single bit of data (0 or 1) in a stable state. Here's a brief overview of its operation:

1.	**Storage Operation (Write)**:
- Initially, both bitlines (BL and BLB) are pre-charged to a pre-set voltage, typically VDD/2.
- To write a '0' into the cell, the wordline (WL) is activated, turning on the access transistors and connecting the storage nodes (nodes between the inverters) to the bitlines.
- The cross-coupled inverters are then driven to the desired state by the bitlines, with one inverter storing a '0' and the other a '1'.
2.	**Reading Operation**:
- To read the stored value, the wordline is again activated, connecting the inverters to the bitlines.
- The voltage on the bitlines affects the inverters' state, causing one inverter to dominate and reinforcing its stored value.
- Sense amplifiers detect this dominant voltage level, determining the stored bit.
3.	**Operation Stability**:
- The stability of the stored data is maintained by the feedback loop between the inverters, ensuring that once set, the stored value remains until changed by a write operation.
4.	**Power Consumption**:
- SRAM cells consume power primarily during read and write operations, as well as through leakage currents in the transistors. Techniques like transistor stacking can be used to reduce leakage and overall power consumption.


## Transistor stacking in 6T SRAM cell

Transistor stacking for low-power design in a 6T SRAM cell can be implemented by using multiple smaller transistors in series for each access or pull-up/pull-down function. Here's how it can be applied to different parts of a 6T SRAM cell:

1. **Access Transistor Stacking**: In a 6T SRAM cell, access transistors connect the storage nodes to the bitlines during read and write operations. By stacking multiple smaller transistors in series for each access transistor, the overall leakage current can be reduced while maintaining the desired drive strength.
2. **Pull-up and Pull-down Transistor Stacking**: The pull-up and pull-down transistors in the cross-coupled inverters of the 6T SRAM cell can also be stacked to reduce leakage current. Stacking these transistors helps in maintaining the desired drive strength while reducing the individual transistor widths.
3. **Wordline Driver Transistor Stacking**: The wordline driver transistors, which control the activation of the access transistors, can also be stacked to reduce leakage current. By using multiple smaller transistors in series for the wordline driver, the drive strength can be maintained while reducing power consumption.

Overall, transistor stacking in a 6T SRAM cell involves using multiple smaller transistors in series to reduce leakage current and power consumption while maintaining the required performance characteristics.

In this project we used transistor stacking at the pull-up and pull-down network to  reduce the static power dissipation due to various leakage currents. The fig.2.4 shows the 6T SRAM with stacking effect of the transistors. The M3, M4, M5, M6, M9, M10 are the 6T SRAM cell. Stacking to the transistors M7 and M8 are applied as NMOS pull down transistors. Stacking to the transistors M1 and M2 are applied as PMOS pull up transistors.

During the cell not active state, the input point with the value zero attached to ground to the both transistors are connected series that are turned off. Due to the stacking the leakage current decreases. Due to stacking, leakage current passing by the way of the turned off transistors in PMOS pull up path decreased. The node having the value high it gets charged by large resistance that decreases present current and consumption of power.



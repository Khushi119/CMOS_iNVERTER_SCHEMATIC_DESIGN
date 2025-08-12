# ANALYSIS OF CMOS INVERTER WITH SCEMATIC DESIGN

CMOS Inverter – Schematic & Characteristics Analysis
Overview
This project focuses on the design, schematic implementation, and analysis of the characteristics of a CMOS inverter. A CMOS inverter is a fundamental digital logic gate used in almost all modern integrated circuits due to its low static power consumption, high noise margins, and full voltage swing.<br>
A CMOS inverter is built using one NMOS transistor and one PMOS transistor connected in a complementary fashion:
- PMOS is connected to VDD (positive supply) because it conducts well when the input is low (logic 0) and passes a strong logic 1.<br>
- NMOS is connected to GND because it conducts well when the input is high (logic 1) and passes a strong logic 0.<br>
This complementary arrangement ensures:
- When the input is 0, PMOS turns ON (output = 1), and NMOS turns OFF;<br>
- When the input is 1, NMOS turns ON (output = 0), and PMOS turns OFF.<br>
No direct path from VDD to GND exists in steady states, minimizing static power dissipation.

Key characteristics analyzed in this project include:
Voltage Transfer Characteristics (VTC);
Propagation Delay;
Power Dissipation

### Tools and Technologies ------->
---
Cadence Virtuoso 6.1.7-64b – Schematic Design <br>
GPDK 90 nm – Process Design Kit (PDK) used for technology-specific parameters and rules

### Steps to follow ------->
---
Steps to Design and Simulate CMOS Inverter in Cadence Virtuoso
1. Invoking the Tool

Open terminal and type: <br>
csh<br>
cd cds_working<br>
source cshrc.cadence<br>
virtuoso<br>

2. Create Library

    - Go to File → New → Library.<br>
    - Assign a name to the library.<br>
    - Attach the library to the technology library ts018_scl_prim.<br>
    - Click Apply → OK.<br>

3. Create Schematic<br>

    3.1 Create a Cell View<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Go to File → New → Cell View.<br>
           - Select the created library, enter the cell name, and click OK.<br>
           - Always select your own library while creating new cell views.<br>

    3.2 Draw the Schematic<br>
         Add instances:<br>
               - Use pmos_18 and nmos_18 from ts018_scl_prim.<br>
               - Use vdd and gnd from analogLib.<br>
               - Connect components using Create → Wire.<br>
         Add pins using Create → Pin:<br>
               - input for input pins.<br>
               - output for output pins.<br>
               - inputOutput type is for supply changes (only for layout).<br>
Check and save the schematic to ensure there are no errors.<br>

4. Running Spectre Simulation<br>

    4.1 Launch ADE: Go to Launch → ADEL.<br>
    4.2 Setup Model Libraries<br>
           -  Setup → Model Libraries → scl_pdk → design kit → models → hspice → ts18sl_scl_mat.lib.<br>
           -  Select tt_18 section.<br>

    4.3 Configure Stimuli<br>
    Setup → Stimuli, Enable configuration, define input signals, and click OK or Apply.<br>

    4.4 Select Analysis Type<br>
Choose Transient Analysis for switching behavior, Choose DC Analysis for voltage transfer characteristics.



# ANALYSIS OF CMOS INVERTER WITH SCEMATIC DESIGN

CMOS Inverter – Schematic & Characteristics Analysis
Overview
This project focuses on the design, schematic implementation, and analysis of the characteristics of a CMOS inverter. A CMOS inverter is a fundamental digital logic gate used in almost all modern integrated circuits due to its low static power consumption, high noise margins, and full voltage swing.<br>
A CMOS inverter is built using one NMOS transistor and one PMOS transistor connected in a complementary fashion:
- PMOS is connected to VDD (positive supply) because it conducts well when the input is low (logic 0) and passes a strong logic 1.<br>
- NMOS is connected to GND because it conducts well when the input is high (logic 1) and passes a strong logic 0.<br>
This complementary arrangement ensures:
- When the input is 0, PMOS turns ON (output = 1), and NMOS turns OFF.<br>
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
Steps to Design and Simulate CMOS Inverter in Cadence Virtuoso<br>

**Step 1.** Invoking the Tool<br>

Open terminal and type:<br>
- csh<br>
- cd cds_working<br>
- source cshrc.cadence<br>
- virtuoso<br>

**Step 2.** Create Library<br>
<br>
- Go to File → New → Library.<br>
- Assign a name to the library.<br>
- Attach the library to the technology library ts018_scl_prim.<br>
- Click Apply → OK.<br>

**Step 3.** Create Schematic<br>
<br>
- **3.1** Create a Cell View<br>
    - Go to File → New → Cell View.<br>
    - Select the created library, enter the cell name, and click OK.<br>
    - Always select your own library while creating new cell views.<br>
- **3.2** Draw the Schematic<br>
    - Add instances:<br>
        - Use pmos_18 and nmos_18 from ts018_scl_prim.<br>
        - Use vdd and gnd from analogLib.<br>
        - Connect components using Create → Wire.<br>
    - Add pins using Create → Pin:<br>
        - input for input pins.<br>
        - output for output pins.<br>
        - inputOutput type is for supply changes (only for layout).<br>
Check and save the schematic to ensure there are no errors.<br>

**Step 4.** Running Spectre Simulation<br>
- **4.1** Launch ADE: Go to Launch → ADEL.<br>
- **4.2** Setup Model Libraries<br>
    -  Setup → Model Libraries → scl_pdk → design kit → models → hspice → ts18sl_scl_mat.lib.<br>
    -  Select tt_18 section.<br>

- **4.3** Configure Stimuli<br>
    Setup → Stimuli, Enable configuration, define input signals, and click OK or Apply.<br>

- **4.4** Select Analysis Type<br>
Choose Transient Analysis for switching behavior, Choose DC Analysis for voltage transfer characteristics.<br>
- **4.5** Select signlas to plot: select a node for current and net for voltage<br>
    - Outputs -> To Be Plotted -> Select on Schematic<br>
- **4.6** Run Simulation : Simulation -> Netlist and Run<br>

**Step 5.** Adding Design Variables<br>
- **5.1** Add a design variable in the circuit, for example: Vin <br>
- **5.2** Launch ADE L -> Variables -> Edit<br>
    - In place of name give variable name (i.e Vin in this case) and give a default value to it and then apply OK.<br>

**Step 6.** Creating a symbol for schematic<br>
- 6.1 Apply input/output/inout pins in schematic to inputs and outputs which are required as pins in symbol. For example: an inverter having top pin as vdd, left pin as in, right pin as out and bottom pin as gnd.
- 6.2<br>
    - Create -> Cellview -> From Cellview<br>
    - Select library name and give cell name<br>
    - From View Name: schematic<br>
    - To View Name: symbol<br>
    - Apply -> OK<br>
- 6.3 select top pin as Vdd, left pin as in, right pin as out and bottom pin as gnd. Apply -> OK<br>
- 6.4 A rectangular box appears with all pins. Give name to [@partname] for example inverter<br>
- 6.5 Modify this rectangular box as per requirement (use shapes from toolbar)<br>

![DRC Report Screenshot]()

### Transient Analysis of CMOS Inverter ------->
----
Transient analysis examines the behavior of signals as a function of time, focusing on the dynamic response of a circuit to changing inputs. In the transient analysis of a CMOS inverter, both the input and output waveforms are observed and plotted to study parameters such as **propagation delay**, **rise time**, and **fall time**.

### Key Parameters:
- **Rise Time (tr):**  
  The time taken by the output to transition from 10% to 90% of its steady-state value.<br>

- **Fall Time (tf):**  
  The time taken by the output to transition from 90% to 10% of its steady-state value.<br>

- **Propagation Delay (tp):**  
  The average time taken for a change at the input to cause a corresponding change at the output, measured at the 50% voltage level of both input and output signals.<br>

#### Types of Propagation Delay:
- **High-to-Low Delay (tphl):**  
  Time between the 50% point of the input rising edge and the 50% point of the output falling edge.<br>
  
- **Low-to-High Delay (tplh):**  
  Time between the 50% point of the input falling edge and the 50% point of the output rising edge.

#### Propagation delay is calculated by Formula: <br> Tp = (tphl + tplh)/2


### Significance:
These parameters are critical in evaluating the speed performance of logic gates and play a significant role in determining the maximum operating frequency of digital circuits.




    
    
    
    
    
    
    
    
     

# ANALYSIS OF CMOS INVERTER WITH SCEMATIC DESIGN

CMOS Inverter – Schematic & Characteristics Analysis
Overview
This project focuses on the design, schematic implementation, and analysis of the characteristics of a CMOS inverter. A CMOS inverter is a fundamental digital logic gate used in almost all modern integrated circuits due to its low static power consumption, high noise margins, and full voltage swing.<br>
A CMOS inverter is built using one NMOS transistor and one PMOS transistor connected in a complementary fashion:
PMOS is connected to VDD (positive supply) because it conducts well when the input is low (logic 0) and passes a strong logic 1.
NMOS is connected to GND because it conducts well when the input is high (logic 1) and passes a strong logic 0.

This complementary arrangement ensures:
When the input is 0, PMOS turns ON (output = 1), and NMOS turns OFF;
When the input is 1, NMOS turns ON (output = 0), and PMOS turns OFF.

No direct path from VDD to GND exists in steady states, minimizing static power dissipation.

Key characteristics analyzed in this project include:
Voltage Transfer Characteristics (VTC);
Propagation Delay;
Power Dissipation

### Tools and Technologies ------->
---
Cadence Virtuoso 6.1.7-64b – Schematic and Layout Design <br>
GPDK 90 nm – Process Design Kit (PDK) used for technology-specific parameters and rules

### Steps 

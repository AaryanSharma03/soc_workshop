
# Digital VLSI SoC Desgin and Planning

Section 1: SKy130 Day1- Inception of open-source EDA, OpenLANE and Sky130 PDK SoC Design and OpenLANE



## Section 1: SKy130 Day1- Inception of open-source EDA, OpenLANE and Sky130 PDK SoC Design and OpenLANE

1. Introduction to All Components of Open-Source Digital ASIC Design

Open-source ASIC (Application-Specific Integrated Circuit) design refers to the process of creating integrated circuits using publicly available design tools and intellectual property (IP). Open-source ASIC design enables wider participation, reduces costs, and provides flexibility to engineers, researchers, and hobbyists.

Here are the primary components of open-source digital ASIC design: a. RTL (Register Transfer Level) Design

Description: RTL is the abstraction level at which the behavior of digital circuits is described in terms of data flows and operations between registers and combinational logic. Tools: Commonly used RTL design languages include VHDL, Verilog, and SystemVerilog. Tools like Yosys are used for synthesizing RTL designs into gate-level representations.

b. Logic Synthesis

Description: The process of converting RTL designs into a gate-level netlist. Synthesis tools map the high-level RTL description to a target technology (e.g., specific cells in a particular CMOS process). Tools: Open-source synthesis tools like Yosys perform RTL-to-gate synthesis. They convert RTL into a netlist in a format compatible with physical design tools.

c. Placement and Routing

Description: Placement refers to determining the positions of cells in the physical design. Routing refers to connecting the cells using metal layers. Tools: Open-source tools like OpenROAD are used for placement and routing, automating the flow from a gate-level netlist to a physical layout.

d. Floorplanning and Physical Design

Description: Floorplanning involves determining the locations of macros (like memories, standard cells, and I/O pads) on a chip. Physical design also includes the layout, power delivery, and clock distribution. Tools: OpenROAD and Magic are common open-source tools used for floorplanning and layout design.

e. Verification

Description: Verification ensures that the design meets the specified requirements. This involves both functional verification and physical verification (e.g., DRC, LVS checks). Tools: Tools like Verilator, ModelSim, and QFlow are used for simulation and verification of the design.

f. Physical Verification

Description: This step ensures that the physical design meets fabrication requirements, such as Design Rule Checks (DRC) and Layout Versus Schematic (LVS) checks. Tools: Open-source tools like KLayout and OpenROAD can be used for physical verification tasks.

g. GDSII File Generation

Description: The final layout is exported as a GDSII file, which is the industry-standard format for chip manufacturing. Tools: Magic and OpenROAD can generate the GDSII file from the final layout.

2. Simplified RTL-to-GDS Flow

The RTL-to-GDS flow is the process of converting a high-level RTL description into a GDSII file, which can be used for manufacturing an ASIC. Here's a simplified flow:

RTL Design (Verilog/VHDL): Engineers design the functionality of the chip using RTL code (e.g., Verilog or VHDL).

Synthesis (RTL to Gate-Level Netlist): The RTL code is passed through a synthesis tool (e.g., Yosys), which converts it into a gate-level netlist (usually in standard formats like EDIF or Verilog).

Placement and Routing: The gate-level netlist is then placed on the chip using placement tools (e.g., OpenROAD), which optimize the positioning of cells. Routing tools connect these cells and optimize the layout of the metal layers.

Physical Design: Floorplanning, power planning, and clock tree synthesis are done during physical design to ensure that the chip functions as expected in the real world.

Physical Verification: DRC (Design Rule Check), LVS (Layout Versus Schematic), and other verification steps are carried out to ensure the layout conforms to design rules and that the physical design matches the logical design.

GDSII Export: After the layout passes all verification checks, the final design is exported as a GDSII file, which is used by semiconductor manufacturers to fabricate the chip.

3. Introduction to OpenLANE and Strive Chipsets a. OpenLANE

OpenLANE is an open-source digital ASIC flow that integrates various existing open-source tools into a single streamlined design flow, simplifying the process of designing an ASIC from RTL to GDSII.

Key Features: RTL to GDS Flow: OpenLANE automates the RTL-to-GDS flow, integrating various tools for synthesis, placement, routing, and physical verification. Open-Source Integration: OpenLANE integrates with tools such as Yosys (synthesis), OpenROAD (placement & routing), KLayout (physical verification), and others. Customization: It allows designers to customize the flow according to their needs, enabling experimentation and optimization.

Key Components: Yosys: For RTL synthesis. OpenROAD: For placement and routing. Magic: For DRC/LVS checks and GDSII generation. KLayout: For viewing and debugging the final layout.

OpenLANE's goal is to provide a fully automated, open-source ASIC design flow, from RTL to GDSII, without requiring proprietary tools. It has gained popularity in the academic and open-source hardware communities. b. Strive Chipsets

Strive is a platform for creating low-power and high-performance digital chips, built using OpenLANE's design flow. Strive aims to make the chip design process more accessible by leveraging the OpenLANE framework and enabling fast prototyping of custom SoCs.

Key Features: Low Power: Strive chipsets are optimized for low-power operation, which is crucial in modern IoT, mobile, and embedded systems. Customizability: The platform allows for flexible design modifications, making it suitable for a variety of applications, from small IoT devices to more complex chips. Integration with OpenLANE: Strive chipsets use OpenLANE to automate the ASIC design flow, providing a simple and efficient way to generate custom silicon.

4. Introduction to OpenLANE Detailed ASIC Design Flow

The OpenLANE flow provides a comprehensive, end-to-end solution for ASIC design. Here's a detailed look at the main steps in the OpenLANE flow: a. Setup and Preparation

Install the OpenLANE environment, including necessary dependencies (Docker, Linux tools, etc.). Prepare the RTL design files (Verilog/VHDL) and configuration files.

b. Synthesis (Yosys)

Synthesis: The RTL design is synthesized into a gate-level netlist using Yosys. This process also involves optimization of the design for area, speed, and power consumption.

c. Placement (OpenROAD)

Placement: The synthesized netlist is placed on the chip floor using OpenROAD’s placement tools. This step ensures that the components are optimally positioned to minimize routing complexity.

d. Clock Tree Synthesis (CTS)

Clock Tree Synthesis: The clock network is designed to ensure that the clock signal reaches all parts of the chip simultaneously, with minimal skew.

e. Routing (OpenROAD)

Routing: The routing step connects the placed cells with metal wires, ensuring that signals flow between logic gates, memory cells, and I/O pads.

f. Signoff (DRC, LVS, and PAR)

Design Rule Checks (DRC): Ensure that the layout adheres to the foundry's manufacturing constraints. Layout vs Schematic (LVS): Ensure that the layout corresponds to the original schematic (netlist). Physical Aware Routing (PAR): Ensure that the routing is physically feasible and optimized for performance.

g. GDSII Export

Once the design is complete and verified, the final layout is exported as a GDSII file for manufacturing


[Documentation here [soon]](https://linktodocumentation)


## Implementation Day 1

 1. Run 'picorv32a' and its analsys
 2. Calculate Flop Ratio 
        
        FLop ratio=No. of D flip-flops/Total no. of Cells



## Step by step Procedure 
1. Open command terminal
2. Open the working directory file you are working on in my case it is
```bash
  cd Desktop/work/tools/openlane_working_dir/openlane
```
3. Type and hit enter
```bash 
  docker
```
```bash 
  ./flow.tcl -interactive
```
Note: dont miss to write interactive

![Screenshot from 2024-12-30 16-42-38](https://github.com/user-attachments/assets/4f2bc01d-d191-494d-8c78-2875131100ab)
You can see as above picture now promt starts form %

4. Run this command (it has to be run every time when you enter openlane)
package require openlane 0.9  


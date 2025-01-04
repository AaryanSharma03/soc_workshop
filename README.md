# Digital VLSI SoC Desgin and Planning
![Static Badge](https://img.shields.io/badge/OS-linux%2C_Windows-orange)
![Static Badge](https://img.shields.io/badge/EDA%20Tools-OpenLANE--Flow%2C_Yosys%2C_abc%2C_OpenROAD%2C_TritonRoute%2C_OpenSTA%2C_magic%2C_netgen%2C_GUNA-purple)
![Static Badge](https://img.shields.io/badge/languages-verilog%2C_bash%2C_TCL-blue)

> 2 Week digital VLSI SoC design and planning workshop with complete RTL2GDSII flow
## Section 1: SKy130 Day1- Inception of open-source EDA, OpenLANE and Sky130 PDK SoC Design and OpenLANE

### Descriptions
<details>
  <summary>
Expand
  </summary>

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
</details>

## Implementation Day 1

 1. Run synthesis 'picorv32a' and its analsys
 2. Calculate Flop Ratio 
        
```math
Flop\ Ratio = \frac{Number\ of\ D\ Flip\ Flops}{Total\ Number\ of\ Cells}
```
## Procedure 
1. Open command terminal
2. Open the working directory file in downloaded folder you are working on in my case its location is `Desktop/work` by running the following command in terminal
```bash
  cd Desktop/work/tools/openlane_working_dir/openlane
```
3. Simply type in the following in your terminal`docker` and hit enter, run the command
```bash 
  ./flow.tcl -interactive
```
Note: Dont miss to write Interactive if you don't use the `-interactive` flag, OpenLane will run the flow automatically, without pausing. It will perform all the steps in the flow without waiting for user inputs, which is useful for automated runs, such as in a CI/CD pipeline or when you are confident that all the parameters and settings are correctly configured in other words process will be `autonomous`

![Screenshot from 2024-12-30 16-42-38](https://github.com/user-attachments/assets/4f2bc01d-d191-494d-8c78-2875131100ab)

You can see as above picture now promt starts form %

4. Run this command (it has to be run every time when you enter openlane)
```bash 
  package require openlane 0.9
```
Sideways you can look into `picorv32a` you can also look upto various designs present in `OpenLANE` in other new terminal tab
```bash
cd Desktop/work/tools/openlane_working_dir/openlane/designs
```
```bash
ls -ltr
```
```bash
cd picorv32a
```
```bash
ls -ltr
```
This will navigate you to the config files there are two types config files `sky130A_sky130_fd_sc_<variant>_config.tcl` and `config.tcl` do not close this tab yet.

4. To run synthesis we first have to setup file system for layout and chip information that can be done as (prep -design <design_name>)
```bash
prep -design picorv32a
```
![Screenshot from 2024-12-30 17-08-57](https://github.com/user-attachments/assets/c9fa1656-e9f4-453f-a8de-92045370c5ff)
Confirmation will appear as Preparation Complete

5. Back to your other terminal new tab look for new file generated with name ```runs``` and open runs content and list its parts in contaganious manner using cd and ls -ltr same as Step 4
![Screenshot from 2024-12-30 17-14-08](https://github.com/user-attachments/assets/c2ee83ca-8a83-4f6f-90f4-7f9468436a86)
 In this runs file you can find various sections of processes involved
![Screenshot from 2024-12-30 17-27-57](https://github.com/user-attachments/assets/7149b2d5-da5a-407f-87c1-e605cde05344)
 similarly you can view these sections which have alll the information of layout, wire ,chip ,macros etc

6. Now we are ready to run the synthesis which involves `Yosys` and `ABC`,run the command
```bash
run_synthesis
```
 It will take 2-3 minutes
![Screenshot from 2024-12-30 17-40-08](https://github.com/user-attachments/assets/be2784a2-ac36-4890-9008-619c8174efb4)

7. This completes the synthesis run, Now we will calculate the flop ratio in the final synthesis statistical report you can find the count of D flip flop as `dfxtp_4` and cells as `cells`
![Screenshot from 2024-12-30 17-41-09](https://github.com/user-attachments/assets/98fded2b-69cb-4c81-9ab2-efb0aec08688)

 The no. of cells are 14876 and d flip flop are 1613
 ```math
Flop\ Ratio = \frac{1613}{14876} = 0.1084296854
```
 So, the result for FLop ratio is 0.1084296854
 Note: You also can view this stat report in reports created by runs file we discussed earlier and various reports
 ```bash
 reports/synthesis/
```
``` bash
less yosys_2.stat.rpt
```
## Section 2: SKy130 Day2- Good floorplan vs bad floorplan and introduction to library cells

### Descriptions
<details>
  <summary>
Expand
  </summary>

Good Floor Planning Considerations

Floor planning is an essential step in the ASIC design process that impacts the chip’s performance, area, and power efficiency. Proper floor planning involves careful consideration of various factors to optimize the placement of cells and other components. Here are key considerations for good floor planning:
1. Utilization Factors and Aspect Ratio

    Utilization Factor:
        The utilization factor represents the proportion of the chip’s area occupied by standard cells (logic cells) relative to the total available area. A high utilization factor implies better area efficiency, but too high a value can lead to congestion, making it harder to route connections. A lower factor may waste chip area, leading to higher manufacturing costs.
        Optimal utilization should strike a balance: typically around 60-80% to allow room for efficient routing while minimizing wasted space.

    Aspect Ratio:
        The aspect ratio is the ratio of the chip’s height to its width. A square or near-square aspect ratio is often preferred as it simplifies the routing and reduces wire lengths, enhancing performance. However, in certain designs, the aspect ratio might be stretched or adjusted based on specific design constraints like I/O requirements or power distribution needs.

2. Concept of Pre-Placed Cells

    Pre-Placed Cells:
        Pre-placed cells refer to critical components like power pads, clock trees, and macros (e.g., memories, PLLs, or analog blocks) that are placed manually or in fixed positions before the automatic placement of standard cells. This helps in ensuring that these components are optimally placed early in the design flow, reducing congestion and improving routing.
        Pre-placing ensures that important structures are placed in the right locations to minimize interference with logic cells and to meet timing and power requirements.

3. Decoupling Capacitors

    Decoupling Capacitors:
        Decoupling capacitors are used to smooth out power supply fluctuations and to reduce noise within the chip. These capacitors are strategically placed near the power pins of cells to mitigate voltage drops and ensure stable power delivery.
        In floor planning, their placement is critical to maintaining signal integrity and improving overall chip reliability, particularly for high-speed designs where power supply noise can significantly impact performance.

4. Power Planning

    Power Planning:
        Power planning involves determining how power will be distributed across the chip, ensuring that every component receives stable and sufficient power while minimizing power losses.
        This involves designing power grids and power straps (metal traces for power distribution) and ensuring that there is enough decoupling capacitance for noise mitigation.
        Effective power planning also includes managing power gating techniques to reduce leakage power during idle periods, which is crucial for low-power designs.

5. Pin Placement and Logical Cell Placement Blockage

    Pin Placement:
        Proper placement of pins (input/output terminals) is essential to minimize signal delays and routing congestion. Pin placement should be aligned with the logical design to minimize wire length and optimize timing. Inputs and outputs should be placed close to their associated logic to reduce the need for long, slow signal paths.
    Logical Cell Placement Blockage:
        Placement blockage refers to areas on the chip where certain cells or components (such as large macros or pads) should not be placed. This ensures that critical regions, like those for power delivery or critical signal paths, are left clear for routing.
        Careful management of placement blockages prevents congestion, enhances routing efficiency, and ensures the integrity of power grids and signal paths.
</details>
## Implementation Day 2

1. Run picorv32a design floorplan using OpenLANE flow and generate necessary outputs.
 
2. Calculate the die area in microns from the values in floorplan def

3. Load generated floorplan def in magic tool and explore the floorplan

4. Run picorv32a design congestion aware placement using OpenLANE flow and generate necessary outputs

5. Load generated placement def in magic tool and explore the placement

```math
Area\ of\ die\ in\ microns = Die\ width\ in\ microns \ x \ Die\ height\ in\ microns
```

## Switches(Optional)

1. Open new tab in terminal and got to `Desktop/work/tools/openlane_working_dir/openlane/configuration` and simply type
```bash
pwd
```
![Screenshot from 2024-12-30 20-50-49](https://github.com/user-attachments/assets/8a5912ff-10dd-4167-be67-303585931cd5)

2. List its components `ls -ltr` it will have `README.md` file ,open this file by simplying typing 
```bash
less
```
and hit enter, this will open all the variables in each stage i.e `SYNTH_CAP_LOAD`, `SYNTH_DRIVING_CELL`, `SYNTH_MAX_FANOUT`, `SYNTH_MAX_TRANS` etc in synthesis there are also global variables i.e. `DESIGN_NAME`, `VERILOG_FILES`, `CLOCK_PERIOD`, `CLOCK_NET`, `CLOCK_PORT` etc. Similarly in `Floorplanning` we have same setup of switches i.e.  `FP_CORE_UTIL` The core utilization percentage, `FP_ASPECT_RATIO` The core's aspect ratio (height / width), `FP_SIZING` Whether to use relative sizing by making use of `FP_CORE_UTIL` or absolute one using `DIE_AREA`, `DIE_AREA` Specific die area to be used in floorplanning. Specified as a 4-corner rectangle etc. Similarly for `Placement`, `CTS`, `ROUTING`there are switches we need to setup
![Screenshot from 2024-12-30 20-45-49](https://github.com/user-attachments/assets/dce3ed9d-7b23-47ae-b50b-2bf7d03f1545)

3. Using step 2 open `floorplan.tcl` in `configuration`
![Screenshot from 2024-12-30 20-52-53](https://github.com/user-attachments/assets/34355ade-76f6-452c-bcc1-7b6cd7bd8175)
![Screenshot from 2024-12-30 20-53-11](https://github.com/user-attachments/assets/1863be3d-b757-4d4a-abaa-9b03281f98f0)
Here you can see how to set these switches/parameters otherwise they are set by default values

## Procedure
1. Run the command
```bash
run_floorplan
```
![Screenshot from 2024-12-30 21-05-54](https://github.com/user-attachments/assets/b8a0aee0-92df-4a54-85e9-7e82c9b297c9)
Need not to take the warning seriously as these values are not required at this time
2. Open new terminal tab and go to `Desktop/work/tools/openlane_working_dir/designs/picorv32a/runs` and open the file you are working on in my case it is `30-12_11-38` go to `results/floorplan` and simply type the following command
```bash
less picorv32a.floorplan.def
```
![Screenshot from 2024-12-30 21-51-52](https://github.com/user-attachments/assets/6bf697e7-45a1-45df-9b17-ac33b93ef3a9)
![Screenshot from 2024-12-30 21-55-37](https://github.com/user-attachments/assets/9ee6951f-ad43-4254-80fb-632a9b49a6a4)
3. You can see `DIEAREA ( 0 0 ) ( 660685 671405 )` `first 0` is lower left x-value and `second 0` is lower right y-value , `660685` is upper right x-value and `671405` is the upper left y-value this data can be used to calculate the die area. Unit will be the `UNITS DISTANCE MICRONS` it is data base unit per micron meaning i micron equals to `1000`. Such that you can divide `660685` `671405` by `1000` to get dimensions in microns that will be
```math
Width= \frac{660685}{1000} = 660.685 microns
```
```math
Height= \frac{671405}{1000} = 671.405 microns
```
```math
Die AREA =Height x Width
```
```math
Die Area = 443587.2124 micron square
```

4. Press `Q` to return to shell and run the command 
```bash
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```
![Screenshot from 2024-12-31 00-53-03](https://github.com/user-attachments/assets/c02ba127-9bb9-4f13-8b49-1729c0953c87)
  This is the path location for sky130A.tech, we need `picorv32a.floorplan.def` and `merged.lef` file which is two level up/behind meaning inside the `<date>` file this is done to see the actual layout of the floorplan through `Magic VLSI layout tool`
![Screenshot from 2024-12-31 00-53-18](https://github.com/user-attachments/assets/1d1b7715-06f9-4708-ac5a-0ea309cbf15e)

5. Select the layout by pressing `S` on your keyboard and then pressing `V` on your keyboard now your chip is centralised
![Screenshot from 2024-12-31 00-53-39](https://github.com/user-attachments/assets/ef1acfab-e075-409e-9097-a8225a43d60b)

6. To zoom draw the rectangle around the area you want to zoom in by pressing left click, right click  and moving mouse accordingly and finally pressing `Z` on your keyboard
![Screenshot from 2024-12-31 00-54-05](https://github.com/user-attachments/assets/ac805188-dda8-4a0b-b0de-c5c9aa830582)
  To select a particular object you can move your mouse toward the desired object and press `S` on your keyboard which will make it highlight
  For more controls you can visit this link here  - [Magic TUTORIAL](http://opencircuitdesign.com/magic/tutorials/tut1.html)
  There is also on more window with title `tkcon 2.3 Main` to know the selected pin is in which layer you can write in tkcon.tcl window
```bash
what
```
![Screenshot from 2024-12-31 00-54-26](https://github.com/user-attachments/assets/ea1a9779-be18-4b31-9d56-005fd202d214)
![Screenshot from 2024-12-31 00-55-19](https://github.com/user-attachments/assets/3e2fbc14-b9ee-405c-bcb3-fa8a04c634f6)

7. Next step is run placement simply type and run
```bash
run_placement
```
in the main terminal where you had run your floorplan, first of all global placement whose main focus is reduction of wire length.
You will see the half wire length below which is `overflow` and our objective reduce the overflows values which means our design converges. After the script is run placement is done.
![Screenshot from 2024-12-31 00-45-02](https://github.com/user-attachments/assets/29083a33-c169-4cba-ae69-1a867e39fbac)

8. Open new terminal tab and go to `/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/30-12_11-38/results/placement` and run the command as earlier
```bash
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```
![Screenshot from 2024-12-31 01-05-21](https://github.com/user-attachments/assets/a6ef917c-f738-459c-b4d2-22ce3f9c2ba1)
This will open a new window by `Magic VLSI layout tool` one with name `Toplevel` and `tkcon.tcl`
![Screenshot from 2024-12-31 01-05-57](https://github.com/user-attachments/assets/b0e0f477-584f-43eb-82db-b21d75ef6455)

9. Zoom in by pressin `Z` on your keyboard to see the standard cell and rows.
![Screenshot from 2024-12-31 01-06-42](https://github.com/user-attachments/assets/e09c62f5-15e2-45bc-ae20-d846eb25c24d)
From this you can see how the all cells are placed
This is all about placement
Note: Open source floorplan doesnot create power distribution it is done post `Floorplan` and `Placement`.

## Section 3: SKy130 Day3- Design library cell using Magic layout and ngspice characterization

### Descriptions
<details>
  <summary>
Expand
  </summary>


  </details>

## Implementation
1. Doing layout simulation from the magic file in ngspice
2. Charactersizing our sample cell
3. We will plugin the sample cell in OpenLANE
## Procedure
Note: Say you want to make changes on fly in the configuration i.e. how the pins are alligned along the core before these were placed randomly equidistant to each other so there are four strategies supported by the `IO Placer` which is a opensource EDA tool.
Say we have done synthesis stage and floorplan stage you can open the `/home/work/tools/openlane_working_dir/configuration` than simply run the command 
```bash
pwd
```
now open the `floorplan.tcl` file by running the command 
```bash
less floorplan.tcl
```
![Screenshot from 2024-12-31 23-09-01](https://github.com/user-attachments/assets/f81e5436-512a-4055-859a-4185cebebabf)
From running above commands you will get to new window where you can see various variables you can change accordingly let us say we want to change the IO pin mode so there is a line `set ::env(FP_IO_MODE) 1; # 0 matching mode - 1 random equidistant mode` it mentions `0 matching mode` - `1 random equidistant mode` do not worry there is 2 mode also that is not visible. Come back to your original terminal window and run the following command
```bash
set ::env(FP_IO_MODE) 2
```
![Screenshot from 2024-12-31 23-08-56](https://github.com/user-attachments/assets/973de9e2-7d2d-4927-abb0-1a2ecfc1ce5b)
Now run the floorplan again in the same terminal
```bash
run_floorplan
```
You can view the changes by `Magic Layout Tool` by running the command in `step 4` of `section-2`  in directory 
```bash
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/<date>/results/floorplan
```
```bash
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```
Magic VLSI Layout Tool will open and you can view the changes there now ins will be stacked over each other. 
You can just reset the changes by running the following commands
```bash
set ::env(FP_IO_MODE) 1
```
```bash
run_floorplan
```
in the original terminal window.gg 

### NGSPICE

1. First of all you have to download ngspice on your windows desktop, you can simply download it by searching ngspice on google
![Screenshot (482)](https://github.com/user-attachments/assets/6bcf5c4a-1d92-47ed-b4b3-a49fd8f0870f).
![Screenshot (483)](https://github.com/user-attachments/assets/0f33ab9f-b5d9-4997-b88f-21a6f361a7e8).
![Screenshot (484)](https://github.com/user-attachments/assets/9f515eb4-115b-4985-815c-25e9d0aa2655).
![Screenshot (485)](https://github.com/user-attachments/assets/685f0919-00dc-43d0-9ed9-36b822ec5c9d).
2. After the download is complete extract the downloaded zip file into a location of your choice
3. Create a circuit i.e. 
  First create component connectivity

![Inverter](https://github.com/user-attachments/assets/4ef82ff6-9144-4796-a13e-63f34f888037).

  Appoint components value
  
![Inverter (1)](https://github.com/user-attachments/assets/de55ac2b-6d24-4d85-a8bc-3cd46062b2d2).

  Identify the nodes and name them (nodes are basically points which defines a component between them)
  
![Inverter (2)](https://github.com/user-attachments/assets/8ead1d81-507d-4460-841e-2890c32b4db7).

5. Now you can create your `.cir` file using this reference `MODEL Decriptions` `NETLIST Description` can be generated and appropriate `SIMULATION Commands` can be issued this whole process can be done on notepad.
```javascript
  *** MODEL Descriptions ***
  *** NETLIST Description ***
  M1 out in vdd vdd pmos W=0.375u L=0.25u
  M2 out in 0 0 nmos W=0.375u L=0.25u
  cload out 0 10f
  Vdd vdd 0 2.5
  Vin in 0 2.5
  *** SIMULATION Commands ***
  .op
  .dc Vin 0 2.5 0.05
  *** .include tsmc_025um_model.mod ***
  .LIB "tsmc_025um_model.mod" CMOS_MODELS
  .end
```
NOTE: When saving your file make sure `save as type` is selected as `All files (*.*)` in my case i saved my file in same folder as ngspice
 ![Screenshot (486)](https://github.com/user-attachments/assets/6c7c867a-0ad3-4e4a-b73a-a883f6d4a33b).
5. Do same for the model file save it as `.mod` file type in notepad
```bash
  * SPICE 3f5 Level 8, Star-HSPICE Level 49, UTMOST Level 8

.lib cmos_models

* DATE: Feb 23/01

* LOT: T0BM WAF: 07

* Temperature_parameters=Default

.MODEL nmos NMOS ( LEVEL = 49

+VERSION = 3.1 TNOM = 27 TOX = 5.8E-9

+XJ = 1E-7 NCH = 2.3549E17 VTH0 = 0.3907535

+K1 = 0.4376003 K2 = 8.265151E-3 K3 = 4.214601E-3

+K3B = -3.7220937 W0 = 2.517345E-6 NLX = 2.310668E-7

+DVT0W = 0 DVT1W = 0 DVT2W = 0

+DVT0 = 0.2411602 DVT1 = 0.3707226 DVT2 = -0.5

+U0 = 316.5922683 UA = -9.89493E-10 UB = 2.154013E-18

+UC = 2.474632E-11 VSAT = 1.254499E5 A0 = 1.2735648

+AGS = 0.2428704 B0 = 2.579719E-8 B1 = -1E-7

+KETA = 4.87168E-4 A1 = 0 A2 = 0.5196633

+RDSW = 120 PRWG = 0.5 PRWB = -0.2

+WR = 1 WINT = 2.357855E-8 LINT = 1.210018E-9

+DWG = 2.292632E-9

+DWB = -9.94921E-10 VOFF = -0.1039771 NFACTOR = 1.3905578

+CIT = 0 CDSC = 2.4E-4 CDSCD = 0

+CDSCB = 0 ETA0 = 3.894977E-3 ETAB = 7.800632E-4

+DSUB = 0.0307944 PCLM = 1.7312397 PDIBLC1 = 0.999135

+PDIBLC2 = 4.850036E-3 PDIBLCB = -0.0866866 DROUT = 0.8612131

+PSCBE1 = 7.995844E10 PSCBE2 = 1.457011E-8 PVAG = 0.0099984

+DELTA = 0.01 RSH = 5 MOBMOD = 1

+PRT = 0 UTE = -1.5 KT1 = -0.11

+KT1L = 0 KT2 = 0.022 UA1 = 4.31E-9

+UB1 = -7.61E-18 UC1 = -5.6E-11 AT = 3.3E4

+WL = 0 WLN = 1 WW = -1.22182E-16

+WWN = 1.2127 WWL = 0 LL = 0

+LLN = 1 LW = 0 LWN = 1

+LWL = 0 CAPMOD = 2 XPART = 0.4

+CGDO = 3.11E-10 CGSO = 3.11E-10 CGBO = 1E-12

+CJ = 1.741905E-3 PB = 0.9876681 MJ = 0.4679558

+CJSW = 3.653429E-10 PBSW = 0.99 MJSW = 0.2943558

+CF = 0 PVTH0 = -0.01 PRDSW = 0

+PK2 = 2.589681E-3 WKETA = -1.866069E-3 LKETA = -0.0166961 )

*

.MODEL pmos PMOS ( LEVEL = 49

+VERSION = 3.1 TNOM = 27 TOX = 5.8E-9

+XJ = 1E-7 NCH = 4.1589E17 VTH0 = -0.583228

+K1 = 0.5999865 K2 = 6.150203E-3 K3 = 0

+K3B = 3.6314079 W0 = 1E-6 NLX = 1E-9

+DVT0W = 0 DVT1W = 0 DVT2W = 0

+DVT0 = 2.8749516 DVT1 = 0.7488605 DVT2 = -0.0917408

+U0 = 136.076212 UA = 2.023988E-9 UB = 1E-21

+UC = -9.26638E-11 VSAT = 2E5 A0 = 0.951197

+AGS = 0.20963 B0 = 1.345599E-6 B1 = 5E-6

+KETA = 0.0114727 A1 = 3.851541E-4 A2 = 0.614676

+RDSW = 1.496983E3 PRWG = -0.0440632 PRWB = -0.2945454

+WR = 1 WINT = 7.879211E-9 LINT = 2.894523E-8

+DWG = -1.112097E-8

+DWB = 9.815716E-9 VOFF = -0.1204623 NFACTOR = 1.2259401

+CIT = 0 CDSC = 2.4E-4 CDSCD = 0

+CDSCB = 0 ETA0 = 0.3325261 ETAB = -0.0623452

+DSUB = 0.9206875 PCLM = 0.833903 PDIBLC1 = 9.948506E-4

+PDIBLC2 = 0.0191187 PDIBLCB = -1E-3 DROUT = 0.9938581

+PSCBE1 = 2.887413E10 PSCBE2 = 8.325891E-9 PVAG = 0.8478443

+DELTA = 0.01 RSH = 3.6 MOBMOD = 1

+PRT = 0 UTE = -1.5 KT1 = -0.11

+KT1L = 0 KT2 = 0.022 UA1 = 4.31E-9

+UB1 = -7.61E-18 UC1 = -5.6E-11 AT = 3.3E4

+WL = 0 WLN = 1 WW = 0

+WWN = 1 WWL = 0 LL = 0

+LLN = 1 LW = 0 LWN = 1

+LWL = 0 CAPMOD = 2 XPART = 0.4

+CGDO = 2.68E-10 CGSO = 2.68E-10 CGBO = 1E-12

+CJ = 1.864957E-3 PB = 0.976468 MJ = 0.4614408

+CJSW = 3.118281E-10 PBSW = 0.6870843 MJSW = 0.3021929

+CF = 0 PVTH0 = 6.397941E-3 PRDSW = 30.410214

+PK2 = 2.100359E-3 WKETA = 5.428923E-3 LKETA = -0.0111599 )

*

.endl
```
 ![Screenshot (487)](https://github.com/user-attachments/assets/07694889-eac0-4c3d-9183-53889134e184)
 
6. Everything is ready now open the  `ngspice.exe` file in `Spice64\bin`
![Screenshot (488)](https://github.com/user-attachments/assets/76cc0221-af15-4dd8-970a-a98aa4e6ee7d)
![Screenshot (489)](https://github.com/user-attachments/assets/ce5d9b1a-209a-4176-842d-9471174734d1)
7. Now open the current directory where you saved your  `.cir` and  `.mod` file using  `cd` command
8. Source your `.cir` file in my case i have named it as `cmosVTS_PMOSwidth_NMOSwidth.cir` file
```bash
source cmosVTS_PMOSwidth_NMOSwidth.cir
```
![Screenshot (491)](https://github.com/user-attachments/assets/6a73b767-1ffd-421e-b3e9-a0b58376419a)
![Screenshot (492)](https://github.com/user-attachments/assets/d01d7809-0bb6-4814-bd1a-c5c4293ad3df)
9. Now execute the circuit by simply typing
```bash
run
```
![Screenshot (492)](https://github.com/user-attachments/assets/d2a21955-273a-4af2-acf7-006d74fc2d43)
```bash
set plot
```
![Screenshot (493)](https://github.com/user-attachments/assets/da6d15bb-9a0a-4582-a907-170f75f0c4fc)
![Screenshot (494)](https://github.com/user-attachments/assets/f1df147e-7173-440a-b843-748d61531667)
this will give you the variables for which you can plot graphs, in our case we will be working on `dc level` for DC Transfer Characterstics so run the command
```bash
set plot dc1
```
```bash
display
```
![Screenshot (495)](https://github.com/user-attachments/assets/e8a2188a-2aa7-4d77-afa2-ac1b9be56ec3)

10. Finally run the command
```bash
plot out vs in
```
![Screenshot (496)](https://github.com/user-attachments/assets/63ffb1ef-5b31-4eef-8d00-e09cde5de530)
This waveform will be generated which represents the `DC Transfer Characterstics` for `output` versus `input` v
![Screenshot (497)](https://github.com/user-attachments/assets/153fed95-b633-4acb-b966-64ffbc7e7f62)
NOTE: That the waveform is shifted in left, ideally it should be symmetrical this is because same size of nmos and pmos for our circuit now let us increase the pmos `W/L` to `2.5` means previously for both pmos and nmos `W/L` was `1.5` now it has been increased in pmos. 
11. Create new `.cir` file with pmos having  `W=0.9375u` 
```javascript
*** MODEL Descriptions ***
*** NETLIST Description ***
M1 out in vdd vdd pmos W=0.9375u L=0.25u
M2 out in 0 0 nmos W=0.375u L=0.25u

cload out 0 10f

Vdd vdd 0 2.5
Vin in 0 2.5
*** SIMULATION Commands ***
.op
.dc Vin 0 2.5 0.05
*** .include tsmc_025um_model.mod ***
.LIB "tsmc_025um_model.mod" CMOS_MODELS
.end
```
12. Open the same `NGSPICE` Interface hit `ENTER` and source this new `.cir` file, in my case i have named it as `cmosVTS_PMOSwidth_2.5NMOSwidth.cir`
```bash
source cmosVTS_PMOSwidth_2.5NMOSwidth.cir
```
![Screenshot (498)](https://github.com/user-attachments/assets/0d919e01-57c6-47f4-a8e3-4ad0a8d4e3a0)
13. Repeat the same procedure by running the command 
```bash
run
```
```bash
setplot
```
```bash
setplot dc2
```
NOTE: This time we are setting plot for new `dc2` not previous `dc1` characterstics
```bash
display
```
![Screenshot (499)](https://github.com/user-attachments/assets/c088a176-41cf-475d-9e3a-52ab084b96ce)
```bash
plot out vs in
```

![Screenshot (500)](https://github.com/user-attachments/assets/c14d6096-6b44-4a03-ad42-99bb687de44f)
The difference is clear as day now the `DC Transfer Characterstics` are more symmetrical and centralised

## Static Behaviour: CMOS Inverter Robustness
# Switching Threshold, Vm
Vm is point where Vin=Vout
The graphs we earlier plotted represented switching
![Screenshot 2025-01-01 171856](https://github.com/user-attachments/assets/469187a2-883a-4116-8195-055e08b03079)
We can conclude a lot of current leaks to the ground during switch from rise to fall, we shall derive this switching threshold. It is a great oppurtunity to calculate the Rise and Fall `delay` with different switching threshold, `Vm`
```math
Vm = R.Vdd/(1+R)
```
where
```math
R=\frac{Kp.Vdsatp}{Kn.Vdsatn} = \frac{\frac{Wp}{Lp}.Kp'.Vdsatp}{\frac{Wn}{Ln}.Kn'.Vdsatn}
```
```math
\frac{\frac{Wp}{Lp}}{\frac{Wp}{Lp}} = \frac{Kn'.Vdsatn([Vm-Vt])\ - \frac{Vdsatn}{2}}{Kp'.Vdsatp([-Vm+Vdd+Vt])\ + \frac{Vdsatp}{2}}
```
1. Keeping the configuration as same before 'cmosVTS_PMOSwidth_NMOSwidth.cir` Except this time input will be impulse and we will be running transit time analysis
  ```bash
*** MODEL Descriptions ***
*** NETLIST Description ***
M1 out in vdd vdd pmos W=0.375u L=0.25u
M2 out in 0 0 nmos W=0.375u L=0.25u

cload out 0 10f

Vdd vdd 0 2.5
Vin in 0 0 pulse 0 2.5 0 10p 10p 1n 2n

*** SIMULATION Commands ***
.op
.trans 10p 4n 
*** .include tsmc_025um_model.mod ***
.LIB "tsmc_025um_model.mod" CMOS_MODELS
.end
```
where Vin is now given as an impulse and we know the impulse is function of time
2. Save it as `.cir` file with different name in my case it is `cmosVTS_PMOSwidth_NMOSwidthTranAnalysis.cir` and keep the location same as previous files

![Impulse](https://github.com/user-attachments/assets/b2b5f909-4741-4748-a051-ade0d390ddce)

3. Now run the file 'cmosVTS_PMOSwidth_NMOSwidth.cir` as `step 8` to `step 9`.
4. Finally run the command
```bash
plot out vs in in
```
![Screenshot (503)](https://github.com/user-attachments/assets/57bfb8df-219b-4fc7-a50b-b857e268f9fa)
Open the plot window now zoom into the plot, hold right click and draw rectangle around the desired region two to three times for increased accuracy
![Screenshot (504)](https://github.com/user-attachments/assets/d912c82b-59f8-42d7-8dcb-13afc4092a44)
![Screenshot (505)](https://github.com/user-attachments/assets/c18f8053-9e39-4683-9942-2267584f2859)
5. Select thee point at which `Vin` and `Vout` interacts and open the ngspice terminal there will be coordinates of the selected point
![Screenshot 2025-01-02 184938](https://github.com/user-attachments/assets/c73dca51-cf3c-4e73-93a4-a56999d99fea)
As discussed this point is where `Vin` and `Vout` is equal which also means it is the switching threshold voltage `Vm`
```math
Vm = 0.9912
```
6. Now run the `cmosVTS_PMOSwidth_NMOSwidthTranAnalysis.cir` file
```bash
source cmosVTS_PMOSwidth_NMOSwidthTranAnalysis.cir
```
![Screenshot (507)](https://github.com/user-attachments/assets/8b941c9c-65c9-4c28-98d2-d472d5932f57)
```bash
run```
```bash
setplot
```
![Screenshot (508)](https://github.com/user-attachments/assets/2e0cd60c-739b-4eea-a209-860defcb5daa)
![Screenshot (509)](https://github.com/user-attachments/assets/30f3ae7f-a54a-4367-8d9b-eb06def96951)
it will represent the available plots and you can see there is transient time plot which you need to run.
```bash
setplot tran2
```
```bash
display
```
![Screenshot (510)](https://github.com/user-attachments/assets/76191538-1800-48b0-b7bc-af0c1c921027)
7. Finally run the command
```bash
plot out vs time in
```
![Screenshot (511)](https://github.com/user-attachments/assets/b381bae7-2302-4476-b22a-64a725dbc8b8)
![Screenshot (512)](https://github.com/user-attachments/assets/6d32e24e-b0f8-4a50-a4cb-a1a6290596ad)
8. Maximize the plot window and now to calculate the rise delay and fall delay we will choose half voltage values of each plot `Vin` and inverter output `Vout`
![Screenshot (513)](https://github.com/user-attachments/assets/646e29e6-f249-4e51-a5e6-bc31f10e55a4)
9. Zoom into the first region near `1.25V` axis and find out the coordinates of `Vin` and `Vout` at this `1.25V` axis. To zoom just click right mouse button, hold and draw.
![Screenshot (514)](https://github.com/user-attachments/assets/38e1a3bf-cc0c-4d05-ba61-109b37da0dda)
![Screenshot (515)](https://github.com/user-attachments/assets/2d5ee794-b840-48ad-a389-5f0474661322)
To know the coordinates of the location just click that point and view the ngspice window with latest output. Select the point of Vin=1.25V and view the coordinates in ngspice window.
![Screenshot 2025-01-02 190132](https://github.com/user-attachments/assets/375c71b6-2244-40a0-ae94-1c0e38a36e8c)
So on viewing the ngspice we come to know that Vin=1.25V at time = 1.01474e^-09,
next by selecting at Vout=1.25V. 
![Screenshot (517)](https://github.com/user-attachments/assets/9d8c12c9-e582-4127-bff5-ec0390773744)
![Screenshot 2025-01-02 190307](https://github.com/user-attachments/assets/f4499625-ca0d-4997-8613-49c6d86d66f5)
So on viewing the ngspice we come to know that Vout=1.25V at time = 1.16295e^-09 AND Vin=1.25 at time = 1.01474e^-09, knowing the time at rising Vout with respect to Vin we calculate the `rise delay` as below:
```math
Rise Delay = 1.16295ns - 1.01474ns = 0.14821ns
```
```math
Rise Delay = 148.21ps
```
10. Similarly zoom into the next region and find out the coordinates of `Vin` and `Vout`of time at `1.25V` axis.
![Screenshot (518)](https://github.com/user-attachments/assets/1084f945-5444-4148-b643-d042d90ee3a4)
Select the point of Vin=1.25V and view the coordinates in ngspice window.
![Screenshot (519)](https://github.com/user-attachments/assets/381257f9-36ab-4ed9-a57c-d712708ecb4a)
![Screenshot 2025-01-02 190838](https://github.com/user-attachments/assets/2d777da4-7669-4e3a-b68a-d9a0014c1be5)
So on viewing the ngspice we come to know that Vout=1.25V at time = 2.005e^-09,
next by selecting at Vin=1.25V time is 2.07665e^-09 
![Screenshot (520)](https://github.com/user-attachments/assets/d288f9a4-2572-40cd-8ec4-f64bb8498011)
![Screenshot 2025-01-02 190956](https://github.com/user-attachments/assets/f512c43a-b9d4-4867-a171-f15db50ae948)
So on viewing the ngspice we come to know that Vout=1.25V at time = 2.07665e^-09, knowing the time at rising Vout with respect to Vin we calculate the `fall delay` as below:
```math
Fall Delay = 2.07665ns - 2.005ns = 0.07165ns
```
```math
Fall Delay = 71.65ps
```
This all was done for the values of `Wp=Wn=0.375` and `Lp=Ln=0.25` or you can say `Wp/Lp=Wn/Ln=1.5` now let us vary the pmos channel width and recalculate the `Switching Threshold` `Rise Delay` and `Fall Delay`
Wp | Lp | Wn | Ln | Wp/Lp | xWn/Ln |
--- | --- | --- | --- | --- | --- |
0.375 | 0.25 | 0.375 | 0.25 | 1.5 | 1.5 | 
0.750 | 0.25 | 0.375 | 0.25 | 3.0 | 1.5 |  
1.125 | 0.25 | 0.375 | 0.25 | 4.5 | 1.5 |  
1.500 | 0.25 | 0.375 | 0.25 | 6.0 | 1.5 | 
1.875 | 0.25 | 0.375 | 0.25 | 7.5 | 1.5 | 

To calculate the values again we would have to repeat the above procedures again the difference is only that we have to change `W (width)` of pmos channel in the `.cir` file and run the SPICE simulation here are the log files and `Vout` vs `Vin` plot of each node. First let us calculate switching threshold for each node.

I. Node `Wp/Lp=3.0` and `Wn/Ln=1.5`
![Screenshot (521)](https://github.com/user-attachments/assets/23b5697a-61e7-4c50-be72-bafc5c316c9f)
![Screenshot (522)](https://github.com/user-attachments/assets/4ffa20c9-e528-49b3-b4f4-def0fefa3c6d)
![Screenshot 2025-01-02 225656](https://github.com/user-attachments/assets/34614c08-b5f5-4597-8ecb-0bd17d39ecb8)
  Vout versus Vin plot (above)
![Screenshot 2025-01-02 223826](https://github.com/user-attachments/assets/fe6e82a2-64bf-49d0-a86f-58a7d79f07a0)
![Screenshot 2025-01-02 224122](https://github.com/user-attachments/assets/497d850e-5129-43f5-9e6b-45b4db9b3a04)
  where `Vin` = `Vout` is the switching threshold voltage `Vm`
```math
Vm = 1.15182
```
II. Node `Wp/Lp=4.5` and `Wn/Ln=1.5`
![Screenshot (523)](https://github.com/user-attachments/assets/d12b6c75-e7b3-447f-9387-6293ea8a7cf2)
![Screenshot (524)](https://github.com/user-attachments/assets/c88cef18-8e58-40cb-a6e3-13ab045c1659)
![Screenshot 2025-01-02 225808](https://github.com/user-attachments/assets/46a44b50-9f3f-4e77-811e-24702d5adceb)
  Vout versus Vin plot (above)
![Screenshot 2025-01-02 224425](https://github.com/user-attachments/assets/89216c5d-a54b-4019-a449-bf62e729b172)
![Screenshot 2025-01-02 224537](https://github.com/user-attachments/assets/57a8678c-b087-41b5-9884-4f5c085500c8)
  where `Vin` = `Vout` is the switching threshold voltage `Vm`
```math
Vm = 1.25109
```
III. Node `Wp/Lp=6.0` and `Wn/Ln=1.5`
![Screenshot (526)](https://github.com/user-attachments/assets/e28ef0cb-561c-45d5-a154-d04856d18860)
  Vout versus Vin plot (above)
![Screenshot 2025-01-02 225037](https://github.com/user-attachments/assets/1f786633-6fb4-4c20-b9e2-83b5422bec47)
  where `Vin` = `Vout` is the switching threshold voltage `Vm`
```math
Vm = 1.32053
```
IV. Node `Wp/Lp=7.5` and `Wn/Ln=1.5`
![Screenshot (528)](https://github.com/user-attachments/assets/8f3fbb59-482c-4b57-beef-05542b3d51bc)
  Vout versus Vin plot (above)
![Screenshot 2025-01-02 225331](https://github.com/user-attachments/assets/12a3ca45-0f6f-4f2c-8e9f-693390042d99)
  where `Vin` = `Vout` is the switching threshold voltage `Vm`
```math
Vm = 1.37326
```
  Now let us calculate the `Rise Delay` and `Fall Delay` for each node 

I. Node `Wp/Lp=3.0` and `Wn/Ln=1.5`
![Screenshot (529)](https://github.com/user-attachments/assets/1cb6b73e-e06c-485b-a5f3-5a0fd8cf349f)
  Values are 1.01494e-09, 1.09526e-09, 2.00493e-09, 2.08101e-09
```math
Rise Delay = 1.09526ns - 1.01494ns = 0.08032ns
```
```math
Rise Delay = 80.32ps
```
```math
Fall Delay = 2.08101ns - 2.00493ns = 0.07608ns
```
```math
Fall Delay = 76.08ps
```
![Screenshot 2025-01-02 233017](https://github.com/user-attachments/assets/d835d970-6629-419c-8304-9b646c118c4c)
![Screenshot 2025-01-02 234325](https://github.com/user-attachments/assets/87dbfcc9-a98b-400c-a09f-b9cbaefbdb86)

II. Node `Wp/Lp=4.5` and `Wn/Ln=1.5`
![Screenshot (530)](https://github.com/user-attachments/assets/d703c486-e72d-43f4-977a-d07e0548e1fb)
  Values are 1.01483e-09, 1.07169e-09, 2.00478e-09, 2.08507e-09
```math
Rise Delay = 1.07169ns - 1.01483ns = 0.05685ns
```
```math
Rise Delay = 56.85ps
```
```math
Fall Delay = 2.08507ns - 2.00478ns = 0.08029ns
```
```math
Fall Delay = 80.29ps
```
![Screenshot 2025-01-02 233906](https://github.com/user-attachments/assets/a4a46469-dd8a-4796-8673-2b2e8cf8e875)
![Screenshot 2025-01-02 234128](https://github.com/user-attachments/assets/e3b73048-7e52-4994-a546-841e44431bab)

III. Node `Wp/Lp=6.0` and `Wn/Ln=1.5`
![Screenshot (531)](https://github.com/user-attachments/assets/4190745d-11fb-46e8-8cc2-eb19b3043870)
  Values are 1.01481e-09, 1.0599e-09, 2.00484e-09, 2.08903e-09
```math
Rise Delay = 1.0599ns - 1.01481ns = 0.04509ns
```
```math
Rise Delay = 45.09ps
```
```math
Fall Delay = 2.08903ns - 2.00484ns = 0.08419ns
```
```math
Fall Delay = 84.19ps
```
![Screenshot 2025-01-02 234808](https://github.com/user-attachments/assets/1cfa5d08-4931-46bf-a73a-1ba0796a41ac)
![Screenshot 2025-01-02 235008](https://github.com/user-attachments/assets/d10d7060-7e2b-4e24-88c7-fd8a2345c42c)

IV. Node `Wp/Lp=7.5` and `Wn/Ln=1.5`
![Screenshot (532)](https://github.com/user-attachments/assets/e1131769-68b3-45c1-89c5-c153abfbf9ec)
  Values are 1.015e-09, 1.05275e-09, 2.00484e-09, 2.09339e-09
```math
Rise Delay = 1.015ns - 1.05275ns = 0.03775ns
```
```math
Rise Delay = 37.75ps
```
```math
Fall Delay = 2.09339ns - 2.00484ns = 0.08855ns
```
```math
Fall Delay = 88.55ps
```
![Screenshot 2025-01-02 235248](https://github.com/user-attachments/assets/1336a9d6-b574-4dff-902c-f351e471bbfb)
![Screenshot 2025-01-02 235420](https://github.com/user-attachments/assets/7a43ec26-30a8-4bc3-95f2-a19e11c31939)


Wp | Lp | Wn | Ln | Wp/Lp | xWn/Ln | Vm(Switching Threshold in Volts) | Rise Delay (ps) | Fall Delay (ps) |
--- | --- | --- | --- | --- | --- | --- | --- | --- |
0.375 | 0.25 | 0.375 | 0.25 | 1.5 | 1.5 | 0.9912 | 148.21 | 71.65 |
0.750 | 0.25 | 0.375 | 0.25 | 3.0 | 1.5 | 1.15182 | 80.32 | 76.08 | 
1.125 | 0.25 | 0.375 | 0.25 | 4.5 | 1.5 | 1.25109 | 56.85 | 80.29 | 
1.500 | 0.25 | 0.375 | 0.25 | 6.0 | 1.5 | 1.32053 | 45.09 | 84.19 |
1.875 | 0.25 | 0.375 | 0.25 | 7.5 | 1.5 | 1.37326 | 37.75 | 88.55 |

## 
 
1. First you are going to download .magfile this file is available at
```bash
https://github.com/nickson-jose/vsdstdcelldesign.git
```
copy the link
2. Open the command terminal and open the openlane directory, run
```bash
git clone https://github.com/nickson-jose/vsdstdcelldesign.git
```
this will download the neseccary files for our next stage
3. Ensure everything is downloaded by running command
``bash
ls -ltr
```
```bash
pwd
```
![Screenshot from 2025-01-03 04-03-55](https://github.com/user-attachments/assets/75469c08-1477-4154-bb45-cf976e92f000)

copy the location as we now need to copy the `.tech` file to this new file
4. Open the `skywater130A.tech` file present in pdks folder
![Screenshot from 2025-01-03 04-05-46](https://github.com/user-attachments/assets/c4044170-3cb9-45ac-844a-518769bc1bcb)
5. Run the `.mag` file with the command 
```bash
magic -T sky130A.tech sky130_inv.mag &
```
![Screenshot from 2025-01-03 04-10-05](https://github.com/user-attachments/assets/0804b678-6068-42ef-9324-71a248e8560b)
This will open the `Magic Tool`
![Screenshot from 2025-01-03 04-10-12](https://github.com/user-attachments/assets/e00cfcb9-a06b-4be8-84be-b1ae22b0c92a)

  Red strip -> Polysilcon
  Source of `PMOS` is connected to the Vdd the source of the `NMOS` is connected to the `ground` and `drain` of `PMOS` and `NMOS` is connected to the `output` also `gate` of nmos and pmos are connected to `input`
  There are different layers present at right side by hovering over any layer you can read its description on the toolbar
  ![Screenshot from 2025-01-04 12-03-37](https://github.com/user-attachments/assets/3ee626f5-3ad9-4ed4-9956-69cd80b9bbf3)
  Select the region you want know about by just pressing `S` on your keyboard and run the command `what` in tkcon window, in my case
  ![Screenshot from 2025-01-04 12-11-59](https://github.com/user-attachments/assets/9ab9803b-a1c2-4d66-aec1-6f48e5cea87a)
  ![Screenshot from 2025-01-04 12-14-40](https://github.com/user-attachments/assets/f137d67e-75aa-488d-bf81-458f852da017)
  For checking the interconnection you can click `S` thrice on your keyboard
  ![Screenshot from 2025-01-04 12-19-08](https://github.com/user-attachments/assets/be95642d-efd8-454a-8a09-11d16fee0209)
  ![Screenshot from 2025-01-04 12-19-08](https://github.com/user-attachments/assets/de75bd57-985d-4f00-89cd-0f6fcd80ccab)
  You can see that port `Y` is connected to `drain` of both `PMOS` and `NMOS`
  From above you can see that Drain of both nmos and pmos are connected, similarly you can verify the connections
  ![Screenshot from 2025-01-04 12-22-58](https://github.com/user-attachments/assets/ffa37128-c750-461a-a70a-917932139584)
  Here you can see that `nmos` source is connected to the `GND`
  You can know more about the layer by simply typing 
  ```bash
property
```
```bash
box
```
  ![Screenshot from 2025-01-04 12-26-20](https://github.com/user-attachments/assets/13c276c0-7533-4550-8728-99cac83d5452)
  This will provide you with the dimensions of the inverter cell
  You can also check for errors if `DRC=0` than it is fine if you see `DRC` non zero you can get more info on `tkcon` console by clicking `DRC` in toolbar and then selecting `DRC find next error`
  For more information [Documentation Here](https://github.com/nickson-jose/vsdstdcelldesign/blob/master/README.md)
  To simulate this framework in `NGSpice` we need to extract the layer
6. Run the command, before we have to know the location of the exracted file so first run the command
```bash
pwd
```
and then
``` bash
extract all
```
![Screenshot from 2025-01-04 12-47-07](https://github.com/user-attachments/assets/4cb7176d-d1b6-4113-b75c-b631a513d6bc)

7. Verify that file was created in the location
![Screenshot from 2025-01-04 12-50-42](https://github.com/user-attachments/assets/117732eb-3e2f-422f-a554-23cd5efe1bcc)

8. To be used by `NGSpice` we have to create `.spice` file so type the commands
```bash
ext2spice cthresh 0 rthresh 0
```
![Screenshot from 2025-01-04 12-53-10](https://github.com/user-attachments/assets/6d5ad0b8-b06a-48c3-a873-da608df0ce2b)

This will kill the parasatic capacitance
9. Run the command
```bash
ext2spice
```
![Screenshot from 2025-01-04 12-58-08](https://github.com/user-attachments/assets/e6fea847-8cc7-41b5-947d-514614f49c27)
10. Verify the file with `.spice` type was created 
![Screenshot from 2025-01-04 12-58-17](https://github.com/user-attachments/assets/dff22ddf-d73b-44c3-be12-ab601931355c)

11. open the file by simply typing
```bash
vim skywater130_inv.spice
```
![Screenshot from 2025-01-04 13-04-03](https://github.com/user-attachments/assets/6f2c9aa7-6c7d-45f4-a5cf-d3c3188e94b6)

12. To start with simmulation we will have to do correct scaling in `.spice` file back to your magic tool zoom into the layer till you can select the smallest grid block on the layout, if grid is not visible you can turn it on from the windows option in the toolbar
and run the command 
```bash
box
```
  This will provide you with the dimensions in my case it is `0.010` microns
  ![Screenshot from 2025-01-04 14-46-14](https://github.com/user-attachments/assets/0328749f-9900-4316-a897-e14127f85f0c)

13. Edit the `.spice` file with correct scaling values
14. Now we have to include the `.lib` files that can be found in the same directory of `/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign` that can be found in the same directory within `libs` 
![Screenshot from 2025-01-04 15-18-49](https://github.com/user-attachments/assets/d0ea4035-00f9-4dfd-a579-b61a799b87af)
15. Now back to the `.spice` file type
```bash
.include ./libs/pshort.lib
.include ./libs/nshort.lib
```
One more thing to notice is that in this `.spice` file `Vgnd` and `Vpwr` are not defined 
16. Comment out the lines and, define the power and ground as shown
![Screenshot from 2025-01-04 15-23-04](https://github.com/user-attachments/assets/bc928b20-9b55-4cf1-83c1-2233d6b1d619)

Or simply copy paste the below file
```bash
.option scale=0.010u
.include ./libs/pshort.lib
.include ./libs/nshort.lib

//.subckt sky130_inv A Y VPWR VGND
X0 Y A VGND VGND nshort_model.0 ad=1.44n pd=0.152m as=1.37n ps=0.148m w=35 l=23
X1 Y A VPWR VPWR pshort_model.0 ad=1.44n pd=0.152m as=1.52n ps=0.156m w=37 l=23
VDD VPwR 0 3.3V
VSS VGND 0 0V
Va A VGND PULSE(0V 3.3V 0 0.1ns 0.1ns 2ns 4ns)
C0 VPWR A 0.0774f
C1 Y A 0.0754f
C2 VPWR Y 0.117f
C3 Y VGND 0.279f
C4 A VGND 0.45f
C5 VPWR VGND 0.781f
.tran 1n 20n
.control
.endc
.end
//.ends
```
17. Now run the command and pass the `.spice` file into it
    ```bash
    ngspice skywater130_inv.spice
    ```

# Magic VLSI
Before starting simulation first let us know about magic by a lab [Click Here](http://opencircuitdesign.com/magic/)


1. Run the command to download a file
   ```bash
   wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
   ```
   This will download the required file.
![Screenshot from 2025-01-04 18-20-31](https://github.com/user-attachments/assets/bb14799e-aabf-4c78-8a2e-23776ae6b97c)

2. Now type the following command
```bash
  tar xfz drc_tests.tgz
```
3. Open the `drc_tests` and view its content by running
   ```bash
   ls -ltr
   ```
   ![Screenshot from 2025-01-04 19-10-30](https://github.com/user-attachments/assets/2d56df23-d994-4323-a6fe-9724ee7a5f86)

4. To view the .tech file locally you can run the command
   ```bash
   vi .magicrc
   ```
5. To start magic you just type (for better graphics `XR` is chosen)
  ```bash
  magic -d XR
  ```
6. In the layout view open any file
![Screenshot from 2025-01-04 19-19-14](https://github.com/user-attachments/assets/abcc0919-80c1-4688-ba2f-de0c92fdf2d1)
![Screenshot from 2025-01-04 19-19-55](https://github.com/user-attachments/assets/dc013fc6-b355-414e-8742-293e45c11e8e)
In my case `Met3 (m3)
![Screenshot from 2025-01-04 19-20-08](https://github.com/user-attachments/assets/8a398f86-35fc-48e6-8559-9553937f9e1f)
Each of these examples have a unique name which calls for its rule no. and description in skywater130 documentation, to view the rules you can navigate to the site and open the `periphereal rules` for `met3`
You can verify all the errors by selecting the desired block and running the command
[Rules](https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html)
```bash
drc why
```
![Screenshot from 2025-01-04 19-36-51](https://github.com/user-attachments/assets/4163f3f7-d118-4e1d-8c24-b30b2c23e2b9)
7. Select any region in m3contact, to do this select a region, hover to the side bar palette and choose the `m3contact` layer by pressing the `scrollbar` on your mouse and you can clearly see DRC is non-zero value
![Screenshot from 2025-01-04 19-47-13](https://github.com/user-attachments/assets/8f5da1cf-d3a6-411e-95fe-5f2e49ecd159)

8. Run the command
```bash
cif see VIA2
```
From the rules the `via2` distance enclosed by `met3` 
![Screenshot from 2025-01-04 21-01-16](https://github.com/user-attachments/assets/101ad028-1012-4adc-80dc-0b4e1189f020)

![Screenshot from 2025-01-04 19-47-59](https://github.com/user-attachments/assets/a7913aa0-b07f-46b6-8f11-b7d903813365)
Actualy these contact cuts are the mask for VIA2 these are defined by certain rules

9. Type the command
    ```bash
    box
    ```
   this will you provide you with the width between VIA2 and contact cut
   ![Screenshot from 2025-01-04 20-52-06](https://github.com/user-attachments/assets/f5aa0ff0-a858-4c2c-abc7-404fb830cee3)
  You can see that distance is never less than 0.065um
   ```bash
   feed clear
   ```
   To clear the changes
10. Now we will find the error ourselve and try to resolve it run the command
    ```bash
    load poly
    ```
    ![Screenshot from 2025-01-04 22-20-28](https://github.com/user-attachments/assets/d4f40704-eb20-41aa-9f4a-609aedcffdd3)

11. djafk, as the name suggests the poly.9 represents the distance between polysilicon and polyresistor which should be obeying the rule
    ![Screenshot from 2025-01-04 22-26-16](https://github.com/user-attachments/assets/41fc1d95-be66-4293-a6fd-b960c59c6c20)
    ![Screenshot from 2025-01-04 22-27-09](https://github.com/user-attachments/assets/58382325-235e-4105-949f-14012b877086)
12. `*poly` poly and all types containing poly
    ![Screenshot from 2025-01-04 22-41-10](https://github.com/user-attachments/assets/1a2decba-7659-426e-b637-27d9547cb49d)

13. Run the command
    ```bash
    drc check
    ```
    now you can see that all these spacing rules has been fixed
    

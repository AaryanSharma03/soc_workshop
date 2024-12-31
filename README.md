
# Digital VLSI SoC Desgin and Planning

Section 1: SKy130 Day1- Inception of open-source EDA, OpenLANE and Sky130 PDK SoC Design and OpenLANE

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
  For more controls you can visit this link here  - [Magic TUTORIAL](https://awesomeopensource.com/project/elangosundar/awesome-README-templates](http://opencircuitdesign.com/magic/tutorials/tut1.html)
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
3. We will feeding the sample cell in OpenLANE
## Procedure
Note: Say you want to make changes on fly in the configuration i.e. how the pins are alligned along the core before these were placed randomly equidistant to each other so there are four strategies to this.
Say we have done synthesis stage and floorplan stage you can open the `/home/work/tools/openlane_working_dir/configuration` than simply run the command 
```bash
pwd
```
now open the `floorplan.tcl` file by running the command 
```bash
less floorplan.tcl
```

1. First you are going to download mat file .magfile

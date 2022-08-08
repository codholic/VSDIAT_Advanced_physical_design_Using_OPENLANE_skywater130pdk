# VSDIAT_Advanced_physical_design_Using_OPENLANE_skywater130pdk
This repo is a part of the partial fulfilment of the 5-days "Advanced Physical Design Workshop using OpenLANE using SKY130" workshop, powered by VLSI System Design and sponsored by Efabless Corporation

#Tools Used in the workshop
All the tools used in this workshop, were open source:
* Yosys and ABC: For Synthesis
* Magic : For Layout
* Ngspice : For Circuit Design and Simulation
* OpenSTA: For Static Timing Analysis(STA)
All of these were integrated in the OpenLane flow which is why OpenLane is used in this workshop, OpenLane flow is in the following: Image Courtesy: ([OpenLane/Efabless](https://github.com/efabless/openlane/blob/master/doc/openlane.flow.1.png))
![image](https://user-images.githubusercontent.com/46148300/183437184-febf53bc-7266-4e1f-9e79-e21f73bb50b3.png)

# 5 Days’ workflow:
# Day 1:  Inception of Open-Source EDA, OpenLane and Sky130 pdk
Learnings of the day:
A brief introduction RTL to GDS Flow, SOC design and RISCV architecture was given at first as later we have worked using picorv32a which is based on RISCV
Then OpenLane Flow was introduced, Let’s see what I did using OpenLane!!!
 
# Invoking OpenLane and Preparing Design
![image](https://user-images.githubusercontent.com/46148300/183443947-9eee4e29-614f-47c3-9a81-892991e533ef.png)
* Then we edited the cofig.tcl file before running synthesis, Edited config.tcl is in the following, Changes I made are :
   * setting Core utilization, IO vertical and horizontal metal, Clock Period 
![image](https://user-images.githubusercontent.com/46148300/183444998-92b8b354-6723-453c-8f96-989216050e6e.png)
# Synthesis
* After that, ran synthesis from openlane interactive terminal
![image](https://user-images.githubusercontent.com/46148300/183445411-ecff8b83-2587-4774-b9b7-e14ad0d32086.png)
![image](https://user-images.githubusercontent.com/46148300/183445680-b6fb60b1-e54d-464a-ac79-6b1ea5968289.png)
* We were asked to calculate the flop ratio which is :
  * Flop Ratio= (Total no.of Flops )/(Total no.of cells)=1613/14876=.108=10.8%
![image](https://user-images.githubusercontent.com/46148300/183447701-63f08942-251f-430b-beb3-7ccf82f10789.png)
![image](https://user-images.githubusercontent.com/46148300/183447787-92e36f9c-f894-45d0-970a-2175079c79ad.png)

# Day 2:   Good FloorPlan, Bad FloorPlan and Introduction to Library Cells
# Floor Plan
![image](https://user-images.githubusercontent.com/46148300/183449816-d9aa4166-bda4-4adb-81a5-a2b40c5e301d.png)
* Visualize Floorplan by magic 
![image](https://user-images.githubusercontent.com/46148300/183451672-4e8b0200-74a5-49af-a774-0939e52a7118.png)
![image](https://user-images.githubusercontent.com/46148300/183451707-68bf16b9-b371-4fb5-86c3-5b7482aa5da6.png)
![image](https://user-images.githubusercontent.com/46148300/183451754-60081f82-4d40-49a0-81e7-9818ed478841.png)
* I also tried out some commands on tkcon like %what to see the selection info and etc.
![image](https://user-images.githubusercontent.com/46148300/183451989-e6869862-449d-4a55-bd10-ec6f6c683b01.png)

# Placement 
![image](https://user-images.githubusercontent.com/46148300/183452847-af35d889-559f-4165-a1da-d49b6bc9ca92.png)
![image](https://user-images.githubusercontent.com/46148300/183452884-68a412b1-debc-4511-8e0e-5982242f03f8.png)
* Visualizing in magic 
![image](https://user-images.githubusercontent.com/46148300/183452964-8d5c9a73-08f4-4371-82eb-3b7ff594b768.png)
![image](https://user-images.githubusercontent.com/46148300/183453002-a5533860-4530-42fd-8fc9-ba46578bcd27.png)
![image](https://user-images.githubusercontent.com/46148300/183453116-7914edc4-308c-4c05-be8f-e8cd3fd8ea1a.png)

# Day 3:  Design library cell using magic layout and NgSpice characterization
* A inverter cell layout was given
![image](https://user-images.githubusercontent.com/46148300/183455221-94a5f474-b66a-4736-9370-15ed12730791.png)
* Then extracted to spice and simulated the edited netlist
![image](https://user-images.githubusercontent.com/46148300/183455577-e6930620-50b8-4276-833a-e93d82be07d5.png)













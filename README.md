![image](https://user-images.githubusercontent.com/46148300/183461134-dd7c07ff-ada9-4d6a-bad2-c72d6342aca8.png)
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
* Then we inserted the given inverter into picorv32a 
![image](https://user-images.githubusercontent.com/46148300/183457903-90808123-7db0-4d4e-b2eb-d742426c569b.png)

# Day 4: Pre-layout timing analysis and  Importance of good clock tree
![image](https://user-images.githubusercontent.com/46148300/183456760-bae40703-0579-4feb-954b-f1ee19dd81b9.png)
![image](https://user-images.githubusercontent.com/46148300/183458038-72375f92-8f06-4b64-bfe3-14d16c2d30aa.png)
![image](https://user-images.githubusercontent.com/46148300/183458058-9615a501-3179-4375-9afd-8de5627ff27c.png)
![image](https://user-images.githubusercontent.com/46148300/183458078-a84eff76-d18e-4202-8af6-0e3f32d937fb.png)

* Improving slack by increasing area 
* by OpenSTA outside OpenLane flow
![image](https://user-images.githubusercontent.com/46148300/183457865-ace5ef71-9702-400f-96eb-e7bdd9b8a37b.png)
* From OpenLane flow
![image](https://user-images.githubusercontent.com/46148300/183458360-b5500f95-8b88-4952-a321-aada175ebd63.png)
![image](https://user-images.githubusercontent.com/46148300/183457826-2a3bf1e0-90b8-4f5c-9fdb-d7c481c19f58.png)
![image](https://user-images.githubusercontent.com/46148300/183458522-90f3f06c-e801-4a71-aa95-dbd7a37243d5.png)
![image](https://user-images.githubusercontent.com/46148300/183458598-7fec59c2-d14e-4c74-b0b9-7057927523f9.png)
![image](https://user-images.githubusercontent.com/46148300/183458621-ea0b2bfb-8411-482b-8679-f8f870fe7d32.png)

# Day 5: Final Steps for RTL2GDS using tritonroute and openSTA
![image](https://user-images.githubusercontent.com/46148300/183459380-0d5ee6d1-9849-4565-93bc-ef39e169aa9c.png)
![image](https://user-images.githubusercontent.com/46148300/183459456-4b09bdc6-d765-4ebe-8b2c-cd78d63ad488.png)
![image](https://user-images.githubusercontent.com/46148300/183459484-e3f3e949-931a-4c04-a031-3b9c5000648d.png)

# Acknowledgement
* [Kunal Ghosh](https://github.com/kunalg123)
* [Nickson Jose](https://github.com/nickson-jose)







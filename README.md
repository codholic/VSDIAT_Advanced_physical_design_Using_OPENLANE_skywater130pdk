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
 
* Invoking OpenLane and Preparing Design
![image](https://user-images.githubusercontent.com/46148300/183443947-9eee4e29-614f-47c3-9a81-892991e533ef.png)
* Then we edited the cofig.tcl file before running synthesis, Edited config.tcl is in the following, Changes I made are :
   * setting Core utilization, IO vertical and horizontal metal, Clock Period 
![image](https://user-images.githubusercontent.com/46148300/183444998-92b8b354-6723-453c-8f96-989216050e6e.png)
* After that, ran synthesis from openlane interactive terminal
![image](https://user-images.githubusercontent.com/46148300/183445411-ecff8b83-2587-4774-b9b7-e14ad0d32086.png)
![image](https://user-images.githubusercontent.com/46148300/183445680-b6fb60b1-e54d-464a-ac79-6b1ea5968289.png)
* We were asked to calculate the flop ratio which is :
  * Flop Ratio= (Total no.of Flops )/(Total no.of cells)=1613/14876=.108=10.8%
![image](https://user-images.githubusercontent.com/46148300/183447701-63f08942-251f-430b-beb3-7ccf82f10789.png)
![image](https://user-images.githubusercontent.com/46148300/183447787-92e36f9c-f894-45d0-970a-2175079c79ad.png)
* Then comes Floor Plan
![image](https://user-images.githubusercontent.com/46148300/183449816-d9aa4166-bda4-4adb-81a5-a2b40c5e301d.png)







# pes_pd
# Day-1 Inception of open source EDA ,openLANE and Sky130 PDK


</details>	
	
 <details>
 <summary> How to talk to computers  </summary>

### Introduction to QFN-48 package,chip,pads,core,die and IPs

 
 ![pd1](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/7da74702-9420-4872-960e-81339d4c0f8e)

 
 Block diagram of Arduino board


 ![pd2](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/c87f0870-8bba-4e3f-b347-d7e33db6a4e2)

 IC in board (Package : QFN -48 Quad flat No-leads)
 
 

![pd3](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/16bd0abf-d166-416b-bcb4-5539bab55247)

example:

![pd4](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/5b85bbf4-ab29-49d3-a71d-2b7c22dd01c8)

> chip is at the centre of the package


> the way the chip is connected to package is by **wirebounce**


> through **wirebounce** ,able to transfer all the signal from outside world


chip:

![pd5](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/4c47281f-2f94-4289-9a0a-b9da48318f34)

components:

1. **PADS** :through which, can send signal inside the chip and viceverse
2. **core** : where all digital logic sits

3. **Die** : size of the entire chip,manufactured on the silicon 

RISC SoC:


![pd7](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/90631909-0ff7-45ba-8ea5-073f0d41694d)


Foundary Ips(intellectual properties) 

Macros : pure digital logic


### Introduction to RISC-V


![pd8](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/5b59a5bc-328d-464d-b3ca-56bc98a9dac8)


### From software Application to hardware

![Screenshot (182)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/e26f7e75-d474-40ac-9198-7e1f7bb8582b)


> c or any other language converted in to assembly level language by complier then assembly in turn converted in to binary code which hardware can understand


> there are two main interface


1. instructions (also called architecture of computer)

2.assembler,which converts assembly level to binary code





**Example:clock**

![Screenshot (181)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/d5d9eeac-e267-49fa-a5a2-ba479e3730ce)



</details>	
	
 <details>
 <summary> SoC Design and OpenLANE  </summary


### Introduction to all components of open-source digital asic design

**open source digital asic design**


![Screenshot (185)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/dbdd9025-835f-4ca5-8c54-b08c3c323585)



**Process Design Kit(PDK)**: 

> In the field of semiconductor manufacturing, a PDK is a set of files and data used by semiconductor designers to create and verify the physical layout of an integrated circuit (IC) on a silicon wafer.
> It includes information about the fabrication process, device models, and design rules


> PDK is the interface between fabrication and the designer


> google worked out an agreement with sky water the open source PDK for the 130nm process by skywater

> june 30 2020 google relewased first ever PDK open source

![Screenshot (186)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/b1174e08-aa59-4b6d-99e8-4e7b01beb6e9)


is 130nm fast?
yes it is ,
here are two examples:

![Screenshot (187)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/c1849600-fda9-4a21-947f-45e0bc84ae4c)


### simplified ASIC design flow:

![Screenshot (188)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/ed8c20fc-a6ac-4685-b23c-d92cd12742d0)

1. **synthesis**:
> coverts RTL to a circuit out of components from the standard cell library(SCL)

![Screenshot (190)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/767567d2-fcae-4695-b640-e8a096ca7893)

> standard cells,each cell has different views/models

--> Electrical, HDL,SPICE

--> Layout (Abstract and Detailed)


2. **floor /power planning**:


it depends on whether we are implementing the single component (MacroFloor planning)or whole chip(chip Floor planning)

macro Floor planning : Dimensions, pin locations,rows definition

![Screenshot (192)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/9917b9e9-f970-4233-b6ea-7462d67d0882)



chip Floor planning: partition the chip die between different system building blocks and place the I/O pads

![Screenshot (193)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/0cf29d23-1247-4fbf-9223-ea32c1d6fd4c)



3.**placement**

placements are done in tw steps:


--> global placemnts find optimal positions for old cells,cells may overlap

--> Detailed placements


4.**clocl tree synthesis**:

--> To deliver the clock to all sequential elements (e.g., FF) with minimum skew And in agood shape

-->Tree(H,X,...)


5. **routing**

--> implement the interconnect using the available metal layers

--> Metal tracks form a routing grid

--> Routing grid is huge 

--> Divide and Conquer


-- **Global Routin**g:Generates routing guides 


-- **Detailed Routing** : Uses the Routing guides to implement the actual wiring


6. **sign off**


--> **physical Verifications**

--Design rules Checking(DRC)


--Layout vs.Schematic(LVS)


-->**Timimg Verification**


--Static Timing Analysis



### Intoduction to openLANE and Strives chipsets

The problem is tougher when using Open source EDA


> Tools Qualificationa

> Tools Calibration

> Missing tools




**OpenLANE**

> Started as an Open Source Flow for a True Open Source Tape-out Experiment

> striVe is a family of Open everything SoCs

-- Open PDK, Open EDA,Open RTL


striVes has different members :

1. striVe : Sky 130 SCL + Synthesized 1Kbytes SRAM

2. striVe 2 : Sky 130 SCL +  1Kbytes Open RAM block

3. striVe 2a : striVe 2 with a single chip core module

4. strive 3 : OSU SCL + Synthesized 1Kbytes SRAM

5. striVe 5 : Sky 130 SCL + 8 x 1 Kbytes openRAM banks

6. striVe 6 : striVe 2 with DFT


![Screenshot (195)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/2860f943-a999-467e-9d83-35c8c37ebb62)



> The main goal of OpenLANE is to produce NO LVS violations , NO DRC violations and timing violations



> OpenLANE Tuned for SkyWater 130n Open PDK

OpenLANE has two modes of operation:

-- Autonomous or interactive

-- DesignSpace Exploration: find the best set of flow configuration



> OpenLANE has more number of design examples there are 43 design with their best configuration


### Introduction to OpenLANE detailed ASIC design flow

![Screenshot (196)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/e3d53506-ef0e-4020-a950-33ae9aff0e95)


![Screenshot (197)](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/ac9d7579-40e5-4c39-9efd-64748a9f175b)



**Design For Test(DFT)**

> Scan Insertion

> Automatic Test Pattern Generation(ATPG)

> Test Patterns Compaction

> Fault Coverage

> Fault Simultion



**Logic Equivalence Check(LEC)**:

This is done by using **yosys**



>  Every time the netlist is modified ,verification must be performed

- CTS modifies the netlist

- post placement  optimizations modifies the netlist



> LEC is ude3s to formally confirm that the function did not change after modifying the netlist



**Dealing with Antenna Rules Violations:**

>  When ametal wire segment is fabricated ,it can act as an antenna.

- Reactive ion etching causes charge to accumulate on the wire

- Transistore gates can be damaged during fabrication

so for this problem we have two solutions :



1.Bridging attaches ahigher layer intermediary (requires Router awareness)


2. Add antenna diode cell to leak away charges (Antenna diodes are provides by the SCL)

- Add a fake Antenna Diode next to every cell input after placement


- Run the Antenna checker (Magic) in the routed layout

- if the checker reports a Violation on tthe cell input pin,replace the Fake Diode cell bu a real one




**Static Timing Analysis :**

> RC Extraction : DEF2SPEF

> STA: openSTA (openROAD)

</details>	
	
 <details>
 <summary> Get familiar to Open-source EDA tools  </summary>

 ### openlane Directory structure 

Sky 130A is pdk variant
which has two sub directries 

1. lib.ref : all the processor specific files

we will be working on pdk variant called sky130_fd_sc_hd

- sky130  : is the process name 

- fd : skywater foundary

- sc : standard cell

- hd(high density) : variant of pdk

2. lib.tech :specific to the tool



 ![Screenshot from 2023-09-09 15-55-07](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/6bcaf760-d917-4601-9aca-3872e9dc8024)


![Screenshot from 2023-09-09 16-02-27](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/cf9c5c18-c378-48ca-b00a-d941e9db811e)


### Design Preperation step



 after installing the openlane flow

 go to the terminal and run following command for access the openlane:

 > cd/desktop/works/tools/openlane_workshop__dir/openlane

> docker

> ./flow.tcl -interactive

> package require openlane 0.9



![Screenshot from 2023-09-09 16-30-35](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/cc22233d-3a1b-4a79-8860-365f30f16333)





![Screenshot from 2023-09-09 22-14-04](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/8113bfae-c09e-4e24-ac7a-0f7825e02d05)




![Screenshot from 2023-09-09 22-14-35](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/73b39a21-749b-48b2-a612-a2f70cae03cf)

### review files after design and run synthesis


![Screenshot from 2023-09-09 22-15-40](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/54068f86-6344-4a54-8e80-46ba7f3a6c06)



![Screenshot from 2023-09-10 15-59-02](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/6b132569-9151-4b67-8b6c-59c6565f7971)


![Screenshot from 2023-09-10 15-59-59](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/c2457dc5-a570-49a0-94c3-fcc1b6d3e68c)


![Screenshot from 2023-09-10 16-18-50](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/fcfc0075-200f-4d4c-8264-4a7ca123bd5c)


![Screenshot from 2023-09-10 16-20-34](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/bf37658d-f413-4f51-b630-2d58bd594e10)



![Screenshot from 2023-09-10 16-40-56](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/e49811bd-91ce-43dd-99d0-394689276fb2)


**we will calculate filflops ratio**


</details>

# Day-2 Good floorplan vs bad floorplan and introduction to library cells

 <details>
 <summary> Chip Floor planning considerations  </summary

 ### Utilization factor and aspect ratio

 **Define width and height of core and die**

 
 
![Untitled1](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/89e7c398-e484-48ed-9d72-3ca319762fcb)

minimum area requires for nelist given above

![Untitled2](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/792a84ef-1036-4cac-9c1a-f89f1ca53f79)


 calculating  area occupied by the above netlist on a silicon  wafer

 ![Untitled3](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/73dd995b-fe4a-4a24-aa1d-3cddcf8ee056)



utilization factor =(areaoccupied by netlist)/(Total area of the core)


for the above netlist there is 100 % utilization and utlization factor is 1
> if this  the case we cannot add extra components(for optimization) to the die since there is no spcae in die (i.e., utlization is 100%)


> so in many cases we will keep utilization factor approximately 0.5 or 0.6.



**aspect ratio**


aspect ratio=(height)/(width)


> here for above netlist aspect ratio is 1 whuch signifies that the chip is square shaped .id ratio is other than 1 then chip is rectangle shaped.


### pre-placed cells


![Untitled4](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/af7b7365-e798-4e33-a7da-7bb1de82ede3)



![Untitled5](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/dad5dcf7-c7c5-4571-92fb-8cb3578790c9)



similarly there are ither IP's available

- memory

- clock gating cell

- camparator

-mux


> the arrangement of these IP's  is reffered as floorplanning

> these IP's have user defined locations ,and hence are placed  in chip before automated placement -and-routing and are called **pre-placed cells**

>  Automated placement and routing tools places the remaining logical cells in the design onto chip


### de-coupling capacitor 


![Untitled1](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/2131e526-9a01-4529-9b6d-f8e3fe8a09f0)


- During switching operation, the circuit demands switching current  i.e., peak current

- due to the presence ofRdd and Ldd there will be a voltage drop across them and the voltage atnode'A' would be Vdd

  
Noise margin Graph


![Untitled1](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/24c9d75e-692d-442b-b8e9-6aab437bda58)

- any voltage lies between vOL to VIL ----logic 0


- any voltage lies between VOH to VIH ----logic 1

- in the undefined region any voltage can go either areas (0 or 1) which is danger(grey area).so in this we have problem of large physical distance ,here comes the concept of **De-coupling**

> De-coupling capacitors are huge capacitors filled with charge


> as name says decoupling it de couples circuit from main supply


**no switching activities are missed** by using decoupling capacitor



### power planning


after solving the problem current demand  using de-coupling 
now we have problem of signal power supply ,i.e.,

if a particular macro is repeated multiple times on chip then the current demand for each and every elemt of macro

![Untitled3](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/435a7f46-0568-4c5b-a2b8-a4f123ca1358)


- assume signal(0-1) has been sent from driver to load

- we should make sure that load is receiving the same signal from driver

![Untitled4](https://github.com/vishnupriyapesu/pes_pd/assets/142419649/d1fe97ee-2e23-4ae8-a185-e2b10d5f0a4d)









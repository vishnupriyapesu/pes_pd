
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

In the field of semiconductor manufacturing, a PDK is a set of files and data used by semiconductor designers to create and verify the physical layout of an integrated circuit (IC) on a silicon wafer.
It includes information about the fabrication process, device models, and design rules





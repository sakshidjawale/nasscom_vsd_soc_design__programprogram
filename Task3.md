# nasscom_vsd_soc_design_program
## Task 3: Design library cell using Magic Layout and ngspice characterization
### 1) Clone custom inverter standard cell design from github repository  

![VirtualBox_vsdworkshop_30_09_2024_00_42_54](https://github.com/user-attachments/assets/4f6ecdc2-f3fe-4d81-b2fe-58a448b64410)


### 2) Load the custom inverter layout in magic and explore.  

Screenshot of custom inverter layout in magic  

![VirtualBox_vsdworkshop_30_09_2024_00_44_28](https://github.com/user-attachments/assets/e909d9b2-d356-4aa3-a56e-76eb86ef5c85)

NMOS and PMOS identified  

![VirtualBox_vsdworkshop_30_09_2024_00_45_57](https://github.com/user-attachments/assets/0fac7335-b385-4d1b-bdf2-8566876b6208)
![VirtualBox_vsdworkshop_30_09_2024_00_45_24](https://github.com/user-attachments/assets/6a438541-e873-41eb-b141-d48609c43802)

Output Y connectivity to PMOS and NMOS drain verified  

![VirtualBox_vsdworkshop_30_09_2024_00_47_06](https://github.com/user-attachments/assets/308a922c-33f9-4f55-93b6-f999b4c3c60c)

PMOS source connectivity to VDD (here VPWR) verified  

![VirtualBox_vsdworkshop_30_09_2024_00_48_14](https://github.com/user-attachments/assets/0c52dc31-e113-4e1a-83c3-15d5c9c8fc65)

NMOS source connectivity to VSS (here VGND) verified  

![VirtualBox_vsdworkshop_30_09_2024_00_48_37](https://github.com/user-attachments/assets/39a723d7-6827-4d23-92bb-b82ff168fe57)


### 3) Spice extraction of inverter in magic.  

Screenshot of tkcon window after running commands  

![VirtualBox_vsdworkshop_30_09_2024_00_51_55](https://github.com/user-attachments/assets/c1218a7d-fec8-4960-abb1-54c3930c1549)
![VirtualBox_vsdworkshop_30_09_2024_00_52_35](https://github.com/user-attachments/assets/51729673-38ae-44fd-a9ab-d7ddb4d3e9cf)

Screenshot of created spice file  

![VirtualBox_vsdworkshop_30_09_2024_01_00_12](https://github.com/user-attachments/assets/3b5c4a5c-76f9-470c-984f-169446b40724)



### 4) Editing the spice model file for analysis through simulation.  

Measuring unit distance in layout grid  

![VirtualBox_vsdworkshop_30_09_2024_01_19_36](https://github.com/user-attachments/assets/08be0a0c-631a-46be-a3fd-cdc00e57c8cc)

Final edited spice file ready for ngspice simulation  

![VirtualBox_vsdworkshop_30_09_2024_01_28_36](https://github.com/user-attachments/assets/65f3888a-70b9-4086-a9fb-9ca26626d84b)


### 5) Post-layout ngspice simulations.  

Screenshots of ngspice run  

![VirtualBox_vsdworkshop_30_09_2024_01_34_29](https://github.com/user-attachments/assets/a20474e9-ff30-4c53-8e2a-df33035125a4)

Screenshot of generated plot  

![VirtualBox_vsdworkshop_30_09_2024_01_35_09](https://github.com/user-attachments/assets/d2c3977f-1fcb-4748-abe6-2571ec53523e)

**Rise transition time calculation**  

<div align="center">

*Rise transition time = Time taken for output to rise to 80% - Time taken for output to rise to 20%*

20% of output = 660 mV  
80% of output = 2.64 V

</div>

20% Screenshots  

![VirtualBox_vsdworkshop_30_09_2024_01_39_53](https://github.com/user-attachments/assets/9b9103c9-79b1-47f2-9db7-22ef773228d8)
![VirtualBox_vsdworkshop_30_09_2024_01_40_08](https://github.com/user-attachments/assets/c790d2a5-3ade-4827-8547-d5b6b26cf48b)

80% Screenshots  

![VirtualBox_vsdworkshop_30_09_2024_01_44_47](https://github.com/user-attachments/assets/7a66e981-2121-411a-a028-17d08b7c5897)
![VirtualBox_vsdworkshop_30_09_2024_01_45_00](https://github.com/user-attachments/assets/1505dad1-7106-4b4f-81b8-e57e788635c2)
<div align="center">

*Rise transition time = 2.24639 - 2.18241 = 0.06398ns = 63.98ps*

</div>


**Fall transition time calculation**

<div align="center">

*Fall transition time = Time taken for output to fall to 20% - Time taken for output to fall to 80%*

20% of output = 660 mV  
80% of output = 2.64 V

</div>

20% Screenshots  

![VirtualBox_vsdworkshop_30_09_2024_01_46_47](https://github.com/user-attachments/assets/727e3f57-ea7d-4ecd-9e11-f4237b42ab90)
![VirtualBox_vsdworkshop_30_09_2024_01_47_06](https://github.com/user-attachments/assets/f9225a6b-5bd5-4e2a-beba-f62e8205291d)

80% Screenshots  

![VirtualBox_vsdworkshop_30_09_2024_01_47_50](https://github.com/user-attachments/assets/07727d32-3162-4243-bd95-a07bb276ac11)
![VirtualBox_vsdworkshop_30_09_2024_01_48_02](https://github.com/user-attachments/assets/80ebfb35-fcc1-41bb-a4ac-25442abe5e04)

<div align="center">

*Fall transition time = 2.17998 - 2.11972 = 0.06026ns = 60.26ps*

</div>

**Rise Cell Delay Calculation** 

<div align="center">

*Rise Cell Delay = Time taken for output to rise to 50% - Time taken for input to fall to 50%*

50% of output = 1.65 V  

</div>

50% Screenshots 

![VirtualBox_vsdworkshop_30_09_2024_01_51_39](https://github.com/user-attachments/assets/bdaf1d8e-7a05-4990-a40b-6eaefa7665b5)
![VirtualBox_vsdworkshop_30_09_2024_01_51_54](https://github.com/user-attachments/assets/5650756b-028c-491d-ae67-41dcc891e6db)

<div align="center">

*Rise Cell Delay = 2.21093 - 2.1501 = 0.06083ns = 60.83ps*

</div>

**Fall Cell Delay Calculation**
<div align="center">

*Fall Cell Delay = Time taken for output to fall to 50% - Time taken for input to rise to 50%*

50% of output = 1.65 V  

</div>

50% Screenshots  

![VirtualBox_vsdworkshop_30_09_2024_01_53_51](https://github.com/user-attachments/assets/3e72a29c-54a3-44e7-a7fc-3a27f11e5c77)
![VirtualBox_vsdworkshop_30_09_2024_01_54_10](https://github.com/user-attachments/assets/d5f9a226-779e-44a8-97ff-c33d78675a1a)


<div align="center">

*Fall Cell Delay = 4.07787 - 4.04987 = 0.028ns = 28ps*

</div>

### 6) 



### 7) 


** ** 

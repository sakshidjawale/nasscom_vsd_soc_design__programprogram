# nasscom_vsd_soc_design_program
## Task 5: Final steps for RTL2GDS using tritonRoute and openSTA
### 1) Perform generation of Power Distribution Network (PDN) and explore the PDN layout.
Screenshots of power distribution network run

![VirtualBox_vsdworkshop_04_10_2024_21_48_43](https://github.com/user-attachments/assets/559f5750-d07b-41f1-bbe0-44417712e010)
![VirtualBox_vsdworkshop_04_10_2024_21_49_17](https://github.com/user-attachments/assets/e72eaed0-2198-4561-8970-d14a2c3bcd90)

Load PDN def in magic in another terminal

![VirtualBox_vsdworkshop_04_10_2024_21_52_08](https://github.com/user-attachments/assets/2c2a0f41-61da-4a65-b421-4696ac11449a)
![VirtualBox_vsdworkshop_04_10_2024_21_52_54](https://github.com/user-attachments/assets/2ce2f351-99d8-4fe4-8e37-e85555bab1de)
![VirtualBox_vsdworkshop_04_10_2024_21_53_12](https://github.com/user-attachments/assets/347bc9e7-d662-483f-a16c-f2298f56fd47)


### 2) Perfrom detailed routing using TritonRoute and explore the routed layout.
Screenshots of routing run

![VirtualBox_vsdworkshop_04_10_2024_21_55_27](https://github.com/user-attachments/assets/02f0e3ce-94c7-4731-9749-2c24e5bae29b)
![VirtualBox_vsdworkshop_04_10_2024_22_05_55](https://github.com/user-attachments/assets/b2e6284a-4ff8-49bb-86e4-51e86da0d1ed)
![VirtualBox_vsdworkshop_04_10_2024_22_06_11](https://github.com/user-attachments/assets/21235b19-9938-439f-a309-cd5274e5fed0)

Load routed def in magic in another terminal

![VirtualBox_vsdworkshop_04_10_2024_22_08_21](https://github.com/user-attachments/assets/069a4232-1a26-411f-9526-0f016e87efe4)
![VirtualBox_vsdworkshop_04_10_2024_22_08_38](https://github.com/user-attachments/assets/ad348a59-5704-47d4-8972-d378bb13cf8b)
![VirtualBox_vsdworkshop_04_10_2024_22_09_33](https://github.com/user-attachments/assets/58b24c05-86a4-45e3-b1a9-ab471436c177)
![VirtualBox_vsdworkshop_04_10_2024_23_01_40](https://github.com/user-attachments/assets/018f7a30-386f-4d2f-aeda-ad81f4a22be7)


Screenshot of fast route guide present in "openlane/designs/picorv32a/runs/04-10_16-08/tmp/routing" directory

![VirtualBox_vsdworkshop_04_10_2024_22_11_01](https://github.com/user-attachments/assets/5531fc7e-da87-4495-a969-3e7aac2e9bbd)

### 3) Post-Route parasitic extraction using SPEF extractor.

![VirtualBox_vsdworkshop_04_10_2024_22_44_17](https://github.com/user-attachments/assets/182f7aa6-01d3-4ad6-952c-7c025a5a4486)
![VirtualBox_vsdworkshop_04_10_2024_22_44_59](https://github.com/user-attachments/assets/a247ac61-c840-4d59-b6f6-927bfcb91eca)

### 4) Post-Route OpenSTA timing analysis with the extracted parasitics of the route.

To be run in OpenLANE flow to do OpenROAD timing analysis with integrated OpenSTA in OpenROAD

![VirtualBox_vsdworkshop_04_10_2024_22_49_01](https://github.com/user-attachments/assets/d35a3fd3-bce9-40d1-97d4-dfd2a788cb36)
![VirtualBox_vsdworkshop_04_10_2024_22_49_18](https://github.com/user-attachments/assets/39369ede-4c32-40a2-8454-7afd7769d7f4)
![VirtualBox_vsdworkshop_04_10_2024_22_49_36](https://github.com/user-attachments/assets/719fe792-d39d-4b43-8755-f765176422d4)
![VirtualBox_vsdworkshop_04_10_2024_22_49_47](https://github.com/user-attachments/assets/a53b05e0-8034-4922-b403-c5d7a022eec9)

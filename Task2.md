# nasscom_vsd_soc_design_program
## Task 2: Design floorplan'picorv32a'
### 1) Run picorv32a floorplan
![VirtualBox_vsdworkshop_23_09_2024_16_57_38](https://github.com/user-attachments/assets/090b3c30-5b8a-4b59-b9e2-65ac38c7a58b)
![VirtualBox_vsdworkshop_23_09_2024_16_58_11](https://github.com/user-attachments/assets/3daff1cd-b2b3-4e57-8b03-6e8fd81294d0)

### 2) Calculate die area in microns  
![VirtualBox_vsdworkshop_23_09_2024_17_02_32](https://github.com/user-attachments/assets/42966701-aeba-4599-80bc-1998d655a7e2)  
**According to floorplan def:**  
    Distance in microns = Value in unit distance / 1000  
    Die width in microns = (660685-0)/1000 = 660.685 microns  
    Die height in microns = (671405-0)/1000 = 671.405 microns  
    Area of die in microns = 660.685 x 671.405 = 443587.212425 square microns  

### 3) Load generated floorplan def in magic tool and explore the floorplan  
 **floorplan def in magic**  
![VirtualBox_vsdworkshop_23_09_2024_17_06_01](https://github.com/user-attachments/assets/59461f4a-4123-48d2-b9e2-81c4dd410836)
![VirtualBox_vsdworkshop_23_09_2024_17_06_37](https://github.com/user-attachments/assets/7d331556-375f-4db9-85c5-4b057b232841)

 **Equidistant placement of ports**  
![VirtualBox_vsdworkshop_23_09_2024_17_08_17](https://github.com/user-attachments/assets/9ce8bc6e-8c22-4924-aa61-cc8f028a6413)

 **Port layer as set through config.tcl**  
![VirtualBox_vsdworkshop_23_09_2024_17_08_53](https://github.com/user-attachments/assets/5f1e37fd-1a15-4bef-a378-4d4a8362f549)
![VirtualBox_vsdworkshop_23_09_2024_17_10_20](https://github.com/user-attachments/assets/3cc3cde6-febb-4801-9725-6e96f2be5cf4)


 **Decap Cells and Tap Cells (Diagonally equidistant Tap cells)**  
![VirtualBox_vsdworkshop_23_09_2024_17_11_14](https://github.com/user-attachments/assets/3bef197f-1700-4677-a348-5cb75b657e37)


 **Unplaced standard cells at the origin**  
![VirtualBox_vsdworkshop_23_09_2024_17_12_08](https://github.com/user-attachments/assets/7882c59c-2ad9-46b8-9488-c0f28179b0c1)


 ### 4) Run 'picorv32a' design congestion aware placement  
![VirtualBox_vsdworkshop_23_09_2024_17_13_19](https://github.com/user-attachments/assets/b5ab0001-3474-492b-a17b-cfd48ae71ee8)
![VirtualBox_vsdworkshop_23_09_2024_17_14_11](https://github.com/user-attachments/assets/e750bba1-14ec-491b-971b-93a6536666a3)


 ### 5) Load generated placement def in magic tool and explore the placement.  
![VirtualBox_vsdworkshop_23_09_2024_17_16_05](https://github.com/user-attachments/assets/83b3e7a7-6153-46bf-b72c-f1d4507df0d2)
![VirtualBox_vsdworkshop_23_09_2024_17_16_30](https://github.com/user-attachments/assets/33970f07-6a5d-4643-8182-66b364a57ee3)
![VirtualBox_vsdworkshop_23_09_2024_17_16_59](https://github.com/user-attachments/assets/0b16b6b6-3d71-4169-afa4-73b353e36028)


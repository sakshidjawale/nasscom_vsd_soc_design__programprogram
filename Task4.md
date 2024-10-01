# nasscom_vsd_soc_design_program
## Task 4: Pre-layout timing analysis and importance of good clock tree  

### 1) Fix up small DRC errors and verify the design is ready to be inserted into our flow.  

Conditions to be verified before moving forward with custom designed cell layout:

*Condition 1: The input and output ports of the standard cell should lie on the intersection of the vertical and horizontal tracks.  
*Condition 2: Width of the standard cell should be odd multiples of the horizontal track pitch.  
*Condition 3: Height of the standard cell should be even multiples of the vertical track pitch.  

![VirtualBox_vsdworkshop_30_09_2024_23_02_03](https://github.com/user-attachments/assets/a0846473-7dc1-415d-ab8e-1723cfa06330)

Screenshot of tracks.info of sky130_fd_sc_hd  

![VirtualBox_vsdworkshop_30_09_2024_23_03_54](https://github.com/user-attachments/assets/224719ca-bb71-4e9c-a08c-3c344590d401)

Commands for tkcon window to set grid as tracks of locali layer

![VirtualBox_vsdworkshop_30_09_2024_23_07_21](https://github.com/user-attachments/assets/bcfb9bf5-1343-4f6b-9c5a-1a65395db0a4)

Condition 1 verified

![VirtualBox_vsdworkshop_30_09_2024_23_07_55](https://github.com/user-attachments/assets/728ac85c-a8f9-4ac1-b140-17b7d0218db4)

Condition 2 verified  

<div align="center"> *Horizontal track pitch =0.46um* </div>

![VirtualBox_vsdworkshop_30_09_2024_23_14_49](https://github.com/user-attachments/assets/4e3ab76c-d7ca-418d-be99-65c461f1cce5)

<div align="center"> *Width of std cell =1.38um = 0.46 x 3* </div>

Condition 3 verified

<div align="center"> *Vertical track pitch =0.34um* </div>

![VirtualBox_vsdworkshop_30_09_2024_23_15_51](https://github.com/user-attachments/assets/520258e5-0b20-497d-8347-746ee8483b80)

<div align="center"> *Height of std cell =2.37um = 0.34 x 7* </div>

### 2) Save the finalized layout with custom name and open it.

![VirtualBox_vsdworkshop_30_09_2024_23_19_13](https://github.com/user-attachments/assets/9f27ec6a-f3ab-4c14-b88b-f37277684684)

Screenshot of newly saved layout

![VirtualBox_vsdworkshop_30_09_2024_23_19_43](https://github.com/user-attachments/assets/698c7198-e0bc-47ed-9e4a-841f3cf6549e)

### 3) Generate lef from the layout.  

 Screenshot of command run
 
![VirtualBox_vsdworkshop_30_09_2024_23_20_17](https://github.com/user-attachments/assets/a3dffc9b-55bc-42b9-96aa-c1c9911f583a)

 Screenshot of newly created lef file
 
 ![VirtualBox_vsdworkshop_30_09_2024_23_21_54](https://github.com/user-attachments/assets/a508dfd7-336c-4cbc-92b4-4dbc5a4f7e0d)

### 4) Copy the newly generated lef and associated required lib files to 'picorv32a' design 'src' directory.  

Screenshot of commands run 

![VirtualBox_vsdworkshop_30_09_2024_23_23_48](https://github.com/user-attachments/assets/11e1b7f4-9779-4787-a9ba-5503512aea46)


### 5) Edit 'config.tcl' to change lib file and add the new extra lef into the openlane flow.  

Edited config.tcl to include the added lef and change library to ones we added in src directory  

![VirtualBox_vsdworkshop_30_09_2024_23_27_29](https://github.com/user-attachments/assets/2f42161b-237e-4edb-a1cb-97ca8976c5d3)


### 6) Run openlane flow synthesis with newly inserted custom inverter cell.


![VirtualBox_vsdworkshop_30_09_2024_23_31_15](https://github.com/user-attachments/assets/35be1501-1ea4-4ed9-80b4-53780d0050a5)
![VirtualBox_vsdworkshop_30_09_2024_23_31_23](https://github.com/user-attachments/assets/e5ad07b0-3eba-4a8e-b37c-ce82acd9f401)
![VirtualBox_vsdworkshop_30_09_2024_23_32_39](https://github.com/user-attachments/assets/891d3313-dae7-4eb1-b387-1b5779fe6059)


### 7) Remove/reduce the newly introduced violations with the introduction of custom inverter cell by modifying design parameters.


Noting down current design values generated before modifying parameters to improve timing

![VirtualBox_vsdworkshop_30_09_2024_23_33_07](https://github.com/user-attachments/assets/3285dd16-85a7-4b55-bec8-8ffddc94fa8d)
![VirtualBox_vsdworkshop_30_09_2024_23_33_17](https://github.com/user-attachments/assets/02100596-3977-4fb6-89a9-d5c7f66e81fe)


Commands to view and change parameters to improve timing and run synthesis

![VirtualBox_vsdworkshop_30_09_2024_23_36_22](https://github.com/user-attachments/assets/82599181-ea1f-4185-8c56-687ee7412581)
![VirtualBox_vsdworkshop_30_09_2024_23_38_32](https://github.com/user-attachments/assets/a6e8a8f4-4381-42a4-8035-6f79fa2161b9)


Screenshot of merged.lef in tmp directory with our custom inverter as macro

![VirtualBox_vsdworkshop_30_09_2024_23_42_35](https://github.com/user-attachments/assets/bd700f0f-13e1-454e-8d84-b59ccf52c854)


Comparing to previously noted run values area has increased and worst negative slack has become 0

![VirtualBox_vsdworkshop_30_09_2024_23_43_21](https://github.com/user-attachments/assets/e0f61c48-9e3e-4bdf-b7ec-c4f106071dad)
![VirtualBox_vsdworkshop_30_09_2024_23_43_31](https://github.com/user-attachments/assets/bd3210ab-d408-4199-baa0-94c895e1247b)



### 8) Once synthesis has accepted our custom inverter we can now run floorplan and placement and verify the cell is accepted in PnR flow.

Now that our custom inverter is properly accepted in synthesis we can now run floorplan using following command

![VirtualBox_vsdworkshop_30_09_2024_23_44_01](https://github.com/user-attachments/assets/e31ae0d4-c46e-437a-ae53-33f6bd8da75c)
![VirtualBox_vsdworkshop_30_09_2024_23_44_37](https://github.com/user-attachments/assets/9f471de7-8b99-4833-867e-88cf999fc97d)


Since we are facing unexpected un-explainable error while using 'run_floorplan' command, we can instead use the following set of commands available based on information from "Desktop/work/tools/openlane_working_dir/openlane/scripts/tcl_commands/floorplan.tcl" and also based on 'Floorplan Commands' section in "Desktop/work/tools/openlane_working_dir/openlane/docs/source/OpenLANE_commands.md"

![VirtualBox_vsdworkshop_30_09_2024_23_46_00](https://github.com/user-attachments/assets/3d16a5a3-fac6-4792-aa6d-939d4e644403)
![VirtualBox_vsdworkshop_30_09_2024_23_46_24](https://github.com/user-attachments/assets/7f86a5d2-00f1-4002-a8fb-d077075da7db)
![VirtualBox_vsdworkshop_30_09_2024_23_46_42](https://github.com/user-attachments/assets/a54cd29d-68f6-446d-8b0c-1bf3d0dbdff9)



Now that floorplan is done we can do placement using following command

![VirtualBox_vsdworkshop_30_09_2024_23_47_29](https://github.com/user-attachments/assets/69c58a54-a81d-4c6e-be40-9f0190c04d02)
![VirtualBox_vsdworkshop_30_09_2024_23_48_17](https://github.com/user-attachments/assets/1e033dc3-af14-498f-86aa-05004d504edd)



Screenshot of placement def in magic

![VirtualBox_vsdworkshop_30_09_2024_23_50_27](https://github.com/user-attachments/assets/46152ef0-6aa8-4232-b5e0-06712016980a)

Screenshot of custom inverter inserted in placement def with proper abutment

![VirtualBox_vsdworkshop_30_09_2024_23_53_11](https://github.com/user-attachments/assets/facd4a16-3897-478c-928e-6a2ca259089a)

Command for tkcon window to view internal layers of cells. Abutment of power pins with other cell from library clearly visible

![VirtualBox_vsdworkshop_30_09_2024_23_53_46](https://github.com/user-attachments/assets/80b77642-6181-4749-9caf-12138af1128f)

### 9) Do Post-Synthesis timing analysis with OpenSTA tool.

Since we are having 0 wns after improved timing run we are going to do timing analysis on initial run of synthesis which has lots of violations and no parameters were added to improve timing

Commands to invoke the OpenLANE flow include new lef and perform synthesis  
{
cd Desktop/work/tools/openlane_working_dir/openlane  
docker  
./flow.tcl -interactive  
package require openlane 0.9  
prep -design picorv32a  
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]  
add_lefs -src $lefs  
set ::env(SYNTH_SIZING) 1  
run_synthesis
}

![VirtualBox_vsdworkshop_01_10_2024_00_02_03](https://github.com/user-attachments/assets/9d858693-36b3-4a59-98ed-8852c581a8c0)

Newly created "pre_sta.conf" for STA analysis in openlane directory

![VirtualBox_vsdworkshop_01_10_2024_00_04_59](https://github.com/user-attachments/assets/4feb9df6-538f-4a25-9051-bfae4c0322ee)

Newly created "my_base.sdc" for STA analysis in "openlane/designs/picorv32a/src directory" based on the file "openlane/scripts/base.sdc"

![VirtualBox_vsdworkshop_01_10_2024_00_08_22](https://github.com/user-attachments/assets/a490e2c7-55a9-4f65-b8e4-0404c5f42692)

Commands to run STA in another terminal

![VirtualBox_vsdworkshop_01_10_2024_00_14_32](https://github.com/user-attachments/assets/45964da3-99ad-48e3-8692-c7ed40dffc15)
![VirtualBox_vsdworkshop_01_10_2024_00_15_21](https://github.com/user-attachments/assets/e6614ee7-d7c3-4b8c-b4fe-f94a062a5936)
![VirtualBox_vsdworkshop_01_10_2024_00_14_43](https://github.com/user-attachments/assets/d10c51c1-f9bf-4fa2-9f28-1efadf6934ac)

Since more fanout is causing more delay we can add parameter to reduce fanout and do synthesis again
Commands to include new lef and perform synthesis

![VirtualBox_vsdworkshop_01_10_2024_00_17_46](https://github.com/user-attachments/assets/4262f7f8-692e-4c4b-bb49-06892b6fc27d)
![VirtualBox_vsdworkshop_01_10_2024_00_18_48](https://github.com/user-attachments/assets/f0c2162c-a062-4c62-85eb-b7f504b25bc8)

Commands to run STA in another terminal

![VirtualBox_vsdworkshop_01_10_2024_00_19_56](https://github.com/user-attachments/assets/a199a7e3-3993-49f6-bb1f-898b0cda324c)
![VirtualBox_vsdworkshop_01_10_2024_00_20_06](https://github.com/user-attachments/assets/817b5685-3ca8-4636-bfc2-964b1d005958)
![VirtualBox_vsdworkshop_01_10_2024_00_20_15](https://github.com/user-attachments/assets/2c2284fe-56b8-4aa6-b49e-d2b93d1f0b07)


### 10) Make timing ECO fixes to remove all violations.

OR gate of drive strength 2 is driving 4 fanouts

![VirtualBox_vsdworkshop_01_10_2024_00_23_51](https://github.com/user-attachments/assets/14b20fae-b841-442e-bc06-add9eb56fe00)

Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4 (slack gets reduced)

![VirtualBox_vsdworkshop_01_10_2024_00_27_35](https://github.com/user-attachments/assets/e7354235-09b2-44e0-bbba-8a5e2b68ef72)
![VirtualBox_vsdworkshop_01_10_2024_00_28_57](https://github.com/user-attachments/assets/c66f3adf-1f50-4705-b327-569305b63ed7)
![VirtualBox_vsdworkshop_01_10_2024_00_29_21](https://github.com/user-attachments/assets/f75f2270-2f2d-41a0-b3fe-6b1129138f58)

OR gate of drive strength 2 is driving 4 fanouts

![VirtualBox_vsdworkshop_01_10_2024_00_30_25](https://github.com/user-attachments/assets/ba6b5c4f-b360-4656-a11f-e9c6821ce478)

Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4 (slack gets reduced)

![VirtualBox_vsdworkshop_01_10_2024_00_31_30](https://github.com/user-attachments/assets/1ebcd537-1e60-4361-8e9a-1a4424ac2080)
![VirtualBox_vsdworkshop_01_10_2024_00_32_04](https://github.com/user-attachments/assets/a806d767-f5c5-4011-b994-ee8840a89435)
![VirtualBox_vsdworkshop_01_10_2024_00_32_18](https://github.com/user-attachments/assets/9006819b-08fb-4995-918b-61dd5491100e)


OR gate of drive strength 2 driving OA gate has more delay

![VirtualBox_vsdworkshop_01_10_2024_00_33_27](https://github.com/user-attachments/assets/6d486dd9-8160-4f4b-b7df-3e814796cddd)

Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4

![VirtualBox_vsdworkshop_01_10_2024_00_34_22](https://github.com/user-attachments/assets/34bf7aa4-3067-4e3f-9bd7-6c7832d4a58d)
![VirtualBox_vsdworkshop_01_10_2024_00_34_38](https://github.com/user-attachments/assets/965b4c77-996c-44e9-a0b4-d20b128c334f)


OR gate of drive strength 2 driving OA gate has more delay

![VirtualBox_vsdworkshop_01_10_2024_00_35_20](https://github.com/user-attachments/assets/a071b76a-f7a1-450c-9363-7bc9cbd34965)

Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4

![VirtualBox_vsdworkshop_01_10_2024_00_36_09](https://github.com/user-attachments/assets/8a44cfb4-f8e9-4127-86b0-7a3cce6388d9)
![VirtualBox_vsdworkshop_01_10_2024_00_36_29](https://github.com/user-attachments/assets/ca2c34bd-cc77-40c3-bcd1-fadc22fb9686)


Commands to verify instance "_14506_" is replaced with "sky130_fd_sc_hd__or4_4"

![VirtualBox_vsdworkshop_01_10_2024_00_37_19](https://github.com/user-attachments/assets/866a8ea5-9906-495a-bfdd-48efcb79a005)

*We started ECO fixes at wns -23.9000 and now we stand at wns -22.6173 we reduced around 1.2827 ns of violation*


### 11) Replace the old netlist with the new netlist generated after timing ECO fix and implement the floorplan, placement and cts.
Now to insert this updated netlist to PnR flow and we can use "write_verilog" and overwrite the synthesis netlist but before that we are going to make a copy of the old netlist

Commands to make copy of netlist

![VirtualBox_vsdworkshop_01_10_2024_00_39_54](https://github.com/user-attachments/assets/e49ed951-b7af-4694-bf61-70990babcf5e)


Commands to write verilog

![VirtualBox_vsdworkshop_01_10_2024_00_41_48](https://github.com/user-attachments/assets/ccbeb339-5007-4e1d-8373-078a085614d0)

Verified that the netlist is overwritten by checking that instance "_14506_" is replaced with "sky130_fd_sc_hd__or4_4"

![VirtualBox_vsdworkshop_01_10_2024_00_44_00](https://github.com/user-attachments/assets/149114f0-9776-4637-9273-c71c78e4db1e)


Since we confirmed that netlist is replaced and will be loaded in PnR but since we want to follow up on the earlier 0 violation design we are continuing with the clean design to further stages
Commands load the design and run necessary stages

![VirtualBox_vsdworkshop_01_10_2024_00_48_59](https://github.com/user-attachments/assets/5f2bfeb8-01a2-4bdd-8747-4b4c031ca690)
![VirtualBox_vsdworkshop_01_10_2024_00_50_11](https://github.com/user-attachments/assets/89163d90-b92a-4a29-8d05-6729a9214c56)
![VirtualBox_vsdworkshop_01_10_2024_00_52_02](https://github.com/user-attachments/assets/3f2707e9-2bea-4c5c-9422-6260f7a6898a)
![VirtualBox_vsdworkshop_01_10_2024_00_52_49](https://github.com/user-attachments/assets/2777bd17-769b-41ee-b837-1dc705cb38b1)
![VirtualBox_vsdworkshop_01_10_2024_00_54_15](https://github.com/user-attachments/assets/5c036e9b-e9ca-46b2-9d48-c53a6f1c6616)
![VirtualBox_vsdworkshop_01_10_2024_00_56_55](https://github.com/user-attachments/assets/d1dde77d-129e-4c0c-8556-d4f072a2be23)



### 12) Post-CTS OpenROAD timing analysis.

Commands to be run in OpenLANE flow to do OpenROAD timing analysis with integrated OpenSTA in OpenROAD

![VirtualBox_vsdworkshop_01_10_2024_01_03_04](https://github.com/user-attachments/assets/b900c85a-98e2-4d10-b552-1d4e9beb8126)
![VirtualBox_vsdworkshop_01_10_2024_01_04_00](https://github.com/user-attachments/assets/d354cc15-fbd0-4e91-a139-2f03526a24f0)
![VirtualBox_vsdworkshop_01_10_2024_01_04_15](https://github.com/user-attachments/assets/7e38dd84-9e50-4425-b26f-4e7e4f4bd759)
![VirtualBox_vsdworkshop_01_10_2024_01_04_42](https://github.com/user-attachments/assets/5f47b55a-3046-4fd5-9422-e973415e128d)



### 13) Explore post-CTS OpenROAD timing analysis by removing 'sky130_fd_sc_hd__clkbuf_1' cell from clock buffer list variable 'CTS_CLK_BUFFER_LIST'.

Commands to be run in OpenLANE flow to do OpenROAD timing analysis after changing 'CTS_CLK_BUFFER_LIST'

![VirtualBox_vsdworkshop_01_10_2024_01_10_36](https://github.com/user-attachments/assets/2e86e6aa-8e8b-49dd-9183-9b2786de53d4)
![VirtualBox_vsdworkshop_01_10_2024_01_13_06](https://github.com/user-attachments/assets/bdb608a8-bc26-419b-b7e4-776c7e10b310)
![VirtualBox_vsdworkshop_01_10_2024_01_13_30](https://github.com/user-attachments/assets/21ba06d1-2e63-46ab-8891-8d87e328ad1d)
![VirtualBox_vsdworkshop_01_10_2024_01_14_16](https://github.com/user-attachments/assets/8212ba23-e3c7-4985-8090-7ed57e2c9fae)
![VirtualBox_vsdworkshop_01_10_2024_01_14_26](https://github.com/user-attachments/assets/36b38806-3c7b-412f-a5f9-8d8b0197ff95)
![VirtualBox_vsdworkshop_01_10_2024_01_16_08](https://github.com/user-attachments/assets/a4b9afb2-7182-4628-b745-48650d69f471)





# nasscom_vsd_soc_design_program
## Task 4: Pre-layout timing analysis and importance of good clock tree  

### 1) Fix up small DRC errors and verify the design is ready to be inserted into our flow.  
Conditions to be verified before moving forward with custom designed cell layout:

Condition 1: The input and output ports of the standard cell should lie on the intersection of the vertical and horizontal tracks.  
Condition 2: Width of the standard cell should be odd multiples of the horizontal track pitch.  
Condition 3: Height of the standard cell should be even multiples of the vertical track pitch.  

Screenshot of tracks.info of sky130_fd_sc_hd  

Screenshot of commands run

Condition 1 verified

Condition 2 verified  
<div align="center"> *Horizontal track pitch =0.46um* </div>

<div align="center"> *Width of std cell =1.38um = 0.46 x 3* </div>

Condition 3 verified
<div align="center"> *Vertical track pitch =0.34um* </div>

<div align="center"> *Height of std cell =2.37um = 0.34 x 7* </div>

 ### 2) Save the finalized layout with custom name and open it.

 ### 3) Generate lef from the layout.  
 Screenshot of command run

 Screenshot of newly created lef file
 

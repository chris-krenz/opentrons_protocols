> [!WARNING]
> Validated in food coloring test, not with actual reagents

# Pierce Dilution-Free Rapid Gold BCA Protein Assay Kit (OT-Flex)

## Overview
This protocol performs automated Pierce Gold BCA assay kit from a 96 wellplate using the Opentrons Flex robot with an 1000uL 8-channel and 50 uL 1-channel  pipette. The protocol is flexible, allowing inputs for different numbers of BSA unknowns and different numbers of replicates. 
This kit has a working range of BSA for 20 to 10,000 μg/mL

The code can accept up to 24 unknowns samples and up to 3 replicates

<details>
<summary>Click here for Pierce Gold BCA Assay Kit Information</summary>
  
  The Pierce Gold BCA Assay kit itself is for quantification of proteins in an unknown sample. The kit provides 8 standards with known protein concentrations. 
  
  The unknowns and standards will then be mixed with a working reagent created by mixing reagent A and reagent B provided by the kit. 
  
  The mixture will be left to incubate for 5 minutes at room temperature, and afterwards read in a plate reader at wavelength 480 nm. 

  Protein concentration and absorbance relationship is nearly linear. 
  </details>


## Protocol Hardwares
> [!NOTE]
> Standards and unknowns are transferred to 1.5 mL snapcap tubes to make automation smoother
- Robot: Opentrons Flex
- Hardware: Heater shaker with the universal flat plate
- Pipette: Flex 8-Channel 1000 µL and 1-Channel 50 µL

All labwares and consumable materials are listed [here](https://www.protocols.io/private/3A61A2A67AEF11F19BE90A58A9FEAC02)

<details>
<summary>Click here for materials reference image</summary>

  Heater-Shaker universal flat plate

  <img width="386" height="217" alt="image" src="https://github.com/user-attachments/assets/6d3ab0c3-4660-4dc9-8cd2-24c47ffe4edb" />

</details>

## Automated Protocol Summary
### Setup
Before automation, download the pierce_gold_bca_assay.py file, edit the parameter to fit your needs, and import it into the Opentrons software.\
Set up the Flex accordingly to what the software shows. 
>[!IMPORTANT]
>The liquid volume displayed is the minimum, perfect liquid dispersion may not always be guaranteed, it is suggested to add an extra reagent to prevent bubbles everytime.

<details>
<summary>Click here for further information about how to set-up for your first time</summary>
  What the screen should look like when loaded. 
  <img width="1531" height="299" alt="image" src="https://github.com/user-attachments/assets/5f80b3b5-0a5f-4a53-b624-a169e2c26481" />
  
  To see robot set-up on the software, press on the your chosen protocol. 
  <img width="800" height="405" alt="image" src="https://github.com/user-attachments/assets/1ca5895e-dd85-4b84-956a-730e730ac0ec" />
  
  Click on the 'Visualize' button
  In this window, you can view all the specific labware name when hovering over it, along with the steps with well view, pick tip usage, etc
  >Make sure to see step 1 or 2 to make sure all liquid has been loaded before moving on to the next step.
  <img width="800" height="484" alt="image" src="https://github.com/user-attachments/assets/be943cf2-f015-4152-ac51-b64af2421700" />
  
  When clicking on labwares, specifics like liquid type and liquid volume are shown.\
  <img width="478" height="374" alt="image" src="https://github.com/user-attachments/assets/fe6c7f59-05e1-4fc0-b8c8-14c592bba52e" />
</details>

Example Set Up for 4 unknowns: <img width="399" height="316" alt="image" src="https://github.com/user-attachments/assets/6aa10b0c-dbd5-4398-a208-318e86ddb5c3" />


### Procedure
For automation prep and protocol procedures follow the instructions [here](https://www.protocols.io/private/3A61A2A67AEF11F19BE90A58A9FEAC02)

## Labware Required
This protocol requires the following custom labware:

[custom_labware/nunc_96_wellplate_optical_bottom_400ul.json](https://github.com/bingling-w/opentrons_protocols/blob/4070e261d453abb1e0a81ed08c07d66fa3a36a12/custom_labware/nunc_96_wellplate_optical_bottom_400ul.json)

## Protocol Validations
- $R^2$ value close to 1, signaling strong correlation between absorbance and concentration values.
- Food coloring validation:
  - Using 10% glycerol, do serial dilution with red food coloring as standards.
  - Add red coloring in reagent B, and use 10% glycerol as reagent A.
  - Do an automated and manual run of the protocol.
  - Compare the standard curve of the two, the slopes of both should be close when using the same standards.

Calculator for BCA assay is in protocols.io.
  </details>


## Protocol Updates
- Ver. 13: Increased the amount of unknown samples allowed for 3 replicates, and added an extra rack of 200 uL tips for when unknown number exceeds 16 and when replicates equals 3 to prevent running out of tips. When reagent B volume exceeds 150 uL, switches to a 200 uL tip using the 8-channel pipette for quicker transfer (wastes 8 more tips, but much more efficient when reagent B volume is high). 
- Ver. 12: Includes flexible input for changing module locations, and changing pipette locations (left or right mount) to further simplify the process especially for new users. 
- Ver. 11: Includes flexible input for v-bottom well or diamond-bottom wells, accessible for users with different labwares. 
- Ver. 10: Changed flow rate to be even slower, and added correct dead volume for working reagent. Slower flow rate results in more accurate pipetting, and the correct dead volume reduces liquid waste.
- Ver. 9: Code is made to blow out, touch tip, and blow out again to account for viscousity of unknowns and standards to prevent droplets. 
- Ver. 8: Code is optimized to dispense and aspirate slower for more accurate pipetting. 
- Ver. 7: Code is optimized to use small volume pipette arms and tips to minimize % error of the machine.
- Ver. 6: Code is optimized to use partial nozzle set up for the 8-channel pipette when there is not a full column to reduce WR and tip waste.
- Ver. 5: Code is made so pipette goes to the very bottom of the reservoir to reduce dead volume. 
- Ver. 4: Code is optimized to distribute reagent B uniformly across the reservoir, and mixed with reagent A at different heights for a more uniform mixture. 
- Ver. 2: Code contains mixing and blow out steps, though does not mix as well because the tip can mix max 50 uL volumes. 
- Ver. 1: Code is optimized for flexibility for user to change the protocol base on how many replicates and unknowns is neccessary.

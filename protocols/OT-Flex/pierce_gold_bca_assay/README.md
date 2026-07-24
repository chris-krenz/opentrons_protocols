> [!WARNING]
> Not validated.

# Pierce Dilution-Free Rapid Gold BCA Protein Assay Kit (OT-Flex)

## Overview
This protocol performs an automated Pierce Gold BCA assay kit run from a 96-well plate using the Opentrons Flex robot with a 1000 uL 8-channel and 50 uL 1-channel pipette. The protocol is flexible, allowing inputs for different numbers of BSA unknowns and different numbers of replicates. 
This kit has a working range of BSA from 20 to 10,000 μg/mL.

The code can accept up to 24 unknown samples and up to 3 replicates.

<details>
<summary>Click here for Pierce Gold BCA Assay Kit Information</summary>
  
  The Pierce Gold BCA Assay kit itself is for quantification of proteins in an unknown sample. The kit provides 8 standards with known protein concentrations. 
  
  The unknowns and standards will then be mixed with a working reagent created by mixing reagent A and reagent B provided by the kit. 
  
  The mixture will be left to incubate for 5 minutes at room temperature, and afterwards read in a plate reader at a wavelength of 480 nm. 

  The relationship between protein concentration and absorbance is nearly linear. 
  </details>


## Protocol Hardwares
> [!NOTE]
> Standards and unknowns are transferred to 1.5 mL snapcap tubes to make automation smoother
- Robot: Opentrons Flex
- Hardware: Heater shaker with the universal flat plate
- Pipette: Flex 8-Channel 1000 µL and 1-Channel 50 µL

All labware and consumable materials are listed [here](https://www.protocols.io/private/3A61A2A67AEF11F19BE90A58A9FEAC02)

<details>
<summary>Click here for materials reference image</summary>

  Heater-Shaker universal flat plate

  <img width="386" height="217" alt="image" src="https://github.com/user-attachments/assets/6d3ab0c3-4660-4dc9-8cd2-24c47ffe4edb" />

</details>

## Automated Protocol Summary
### Setup
Before automation, download the pierce_gold_bca_assay.py file, edit the parameters to fit your needs, and import it into the Opentrons software.\
Set up the Flex according to what the software shows. 
>[!IMPORTANT]
>The liquid volume displayed is the minimum; perfect liquid dispersion may not always be guaranteed, so it is suggested to add extra reagent to prevent bubbles every time.

<details>
<summary>Click here for further information about how to set-up for your first time</summary>
  What the screen should look like when loaded. 
  <img width="1531" height="299" alt="image" src="https://github.com/user-attachments/assets/5f80b3b5-0a5f-4a53-b624-a169e2c26481" />
  
  To see robot set-up on the software, press on your chosen protocol. 
  <img width="800" height="405" alt="image" src="https://github.com/user-attachments/assets/1ca5895e-dd85-4b84-956a-730e730ac0ec" />
  
  Click on the 'Visualize' button
  In this window, you can view the specific labware name when hovering over it, along with the steps with well view, tip pickup usage, etc.
  >Make sure to see step 1 or 2 to make sure all liquid has been loaded before moving on to the next step.
  <img width="800" height="484" alt="image" src="https://github.com/user-attachments/assets/be943cf2-f015-4152-ac51-b64af2421700" />
  
  When clicking on labware, specifics like liquid type and liquid volume are shown.\
  <img width="478" height="374" alt="image" src="https://github.com/user-attachments/assets/fe6c7f59-05e1-4fc0-b8c8-14c592bba52e" />
</details>

Example Setup for 4 unknowns: <img width="399" height="316" alt="image" src="https://github.com/user-attachments/assets/6aa10b0c-dbd5-4398-a208-318e86ddb5c3" />


### Procedure
For automation prep and protocol procedures follow the instructions [here](link here)

## Labware Required
This protocol requires the following custom labware:

[custom_labware/nunc_96_wellplate_optical_bottom_400ul.json](https://github.com/bingling-w/opentrons_protocols/blob/4070e261d453abb1e0a81ed08c07d66fa3a36a12/custom_labware/nunc_96_wellplate_optical_bottom_400ul.json)

## Protocol Validations
- $R^2$ value close to 1, signaling strong correlation between absorbance and concentration values.
- Food coloring validation:
  - Using 10% glycerol, do a serial dilution with red food coloring as standards.
  - Add red coloring to reagent B, and use 10% glycerol as reagent A.
  - Do an automated and manual run of the protocol.
  - Compare the standard curves of the two; the slopes of both should be close when using the same standards.

Calculator for BCA assay is in protocols.io.
  </details>


## Protocol Updates
- Ver. 2: Added ability to pick up wellplate lid to place it on the wellplate. 
- Ver. 1: Adapted from the Pierce Gold BCA assay protocol. 

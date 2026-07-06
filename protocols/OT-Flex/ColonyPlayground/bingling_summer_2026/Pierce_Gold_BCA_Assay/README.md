# Pierce Dilution-Free Rapid Gold BCA Protein Assay Kit (OT-Flex)

## Overview
This protocol performs automated Pierce Gold BCA assay kit from a 96 wellplate using the Opentrons Flex robot with an 1000uL 8-channel and 50 uL 1-channel  pipette. The protocol is flexible, allowing inputs for different numbers of BSA unknowns and different numbers of replicates. 

The code can accept up to 24 unknowns samples of protein for 1 to 2 replicates or accept up to 18 unknowns for 3 replicates.

<details>
<summary>Click here for Pierce Gold BCA Assay Kit Information</summary>
  
  The Pierce Gold BCA Assay kit itself is for quantification of proteins in an unknown sample. The kit provides 8 standards with known protein concentrations. 
  
  The unknowns and standards will then be mixed with a working reagent created by mixing reagent A and reagent B provided by the kit. 
  
  The mixture will be left to incubate for 5 minutes at room temperature, and afterwards read in a plate reader at wavelength 480 nm. 
  
  <img width="1160" height="218" alt="image" src="https://github.com/user-attachments/assets/3210d5fc-5c4c-431f-bfea-8e2b65adba7d" />
  
  Above is a sample absorbance reading for 8 standards in column 1, and 4 unknowns in column 2. 
  
  The standard readings in column 1 will be turned into a linear regression graph shown below:
  
  <img width="370" height="270" alt="image" src="https://github.com/user-attachments/assets/ec320357-8061-4eb3-afae-40104f85c5c0" />
  
  The quadratic equation from the standard curve, y = 0.246x + 0.0249 (y = absorbance), will be used to calculate the unknown protein concentrations:

  Ex. If the equation is y = 0.246x + 0.0249, isolate x (x = concentration (mg/mL))

  x = ( y - 0.0249 ) / 0.246

  So an absorbance reading of 1.426 means the unknown sample has a protein concentation of 5.696 mg/mL

  [Standard curve and unknown concentration calculator](https://docs.google.com/spreadsheets/d/e/2PACX-1vQHjbm-x1kIOYTJoq81OzskibxwKUSKyZn81WVdUn8h-sNTi3uS-CjySMG9yDvNimtIrA33ofB6ztlT/pubhtml)
  </details>


## Protocol Materials
> [!NOTE]
> Standards and unknowns are placed in 1.5 mL snapcap tubes to make automation smoother
- Robot: Opentrons Flex
- Kit: Pierce Gold BCA Assay kit
- Hardware: Heater shaker with the universal flat plate
- Pipette: Flex 8-Channel 1000 µL and 1-Channel 50 µL
- Tips: One 200 uL tip rack and one 50 uL tip rack
- Plate: NUNC 96 wellplate optical bottom black (include picture)
- Reservoir: Opentrons Tough 22 mL 12 Well Reservoir
- Others: Two opentrons 24 tuberack holder

<details>
<summary>Click here for materials reference image</summary>

  Heater-Shaker universal flat plate

  <img width="386" height="217" alt="image" src="https://github.com/user-attachments/assets/6d3ab0c3-4660-4dc9-8cd2-24c47ffe4edb" />
  
  NUNC 96 wellplate optical bottom black:
  
  <img width="350" height="300" alt="image" src="https://github.com/user-attachments/assets/0b0bcbca-94de-4adb-859c-b1a4f9ebb61b" />
  
  Opentrons Tough 22 mL 12 Well Reservoir:
  
  <img width="350" height="260" alt="image" src="https://github.com/user-attachments/assets/a10b9586-7cb7-46e7-a837-904160e4ec50" />

  Opentrons 24 tuberack holder:

  <img width="350" height="280" alt="image" src="https://github.com/user-attachments/assets/c35fd4fa-19fd-442d-aad7-b45a3afa3f42" />

  Nest 1.5 mL snapcap:

  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/c30153fa-5061-484f-a0e8-510f70f14e0f" />

</details>

## Protocol Summary
### Setup
Before automation, place all labware in the correct deck spot accordance to the screen visualization set up in the Opentrons software

Example Set Up image for 4 unknowns: <img width="399" height="316" alt="image" src="https://github.com/user-attachments/assets/6ed72e8b-261a-4152-9853-1768faf6d961" />

- Liquid: Red = standards; yellow = unknowns; blue = reagent B; green = reagent A
- Tipracks: Purple = 50 uL; Yellow = 200 uL
### Procedure
1. Place standards' tubes in the tuberack in deck space D2 in columns (verticle) of preferred order. Place unknowns' tubes in the tuberack in deck space D3 in column(s) of preferred order.
2. Dispense the necessary amount of reagent A and B into the reservoir and tube respectively.
3. Start automation protocol.
4. Dispenses 10 µL of BSA standards into column 1 (and column 2-3 if there's replicates)
5. Dispenses 10 µL of BSA unknowns into the column next to the standards (replicates will be placed next to the first replicates row)
6. Combine reagent A and reagent B in a 50:1 ratio, then mix to create the working reagent.
7. Dispense 200 µL of working reagent with the 8-channel pipette into each row where there is standards and unknowns.
8. Heater-shaker will shake the well-plate at 825rpm for 25 seconds to mix well.
9. Protocol will set a timer for 5 minutes.
10. When timer is up, protocol will display completion so user can bring the wellplate to the plate reader for absorbance reading. 

## Labware Required
This protocol requires the following custom labware:

[custom_labware/nunc_96_wellplate_optical_bottom_400ul.json](https://github.com/bingling-w/opentrons_protocols/blob/4070e261d453abb1e0a81ed08c07d66fa3a36a12/custom_labware/nunc_96_wellplate_optical_bottom_400ul.json)

## Protocol Validations
- $R^2$ value close to 1, signaling strong correlation between absorbance and concentration values. 

## Protocol Updates
- Ver. 10: Changed flow rate to be even slower for accurate pipetting, and added correct dead volume for working reagent.
- Ver. 9: Code is made to blow out, touch tip, and blow out again to account for viscousity of unknowns and standards to prevent droplets. 
- Ver. 8: Code is optimized to dispense and aspirate slower for more accurate 
- Ver. 7: Code is optimized to use small volume pipette arms and tips to minimize % error of the machine.
- Ver. 6: Code is optimized to use partial nozzle set up for the 8-channel pipette when there is not a full column to reduce WR and tip waste.
- Ver. 5: Code is made so pipette goes to the very bottom of the reservoir to reduce dead volume. 
- Ver. 4: Code is optimized to distribute reagent B uniformly across the reservoir, and mixed with reagent A at different heights for a more uniform mixture. 
- Ver. 2: Code contains mixing and blow out steps, though does not mix as well because the tip can mix max 50 uL volumes. 
- Ver. 1: Code is optimized for flexibility for user to change the protocol base on how many replicates and unknowns is neccessary.

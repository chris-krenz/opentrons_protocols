# Pierce Dilution-Free Rapid Gold BCA Protein Assay Kit (OT-Flex)

## Overview
For full overview see: [protocols/OT-Flex/Pierce_Gold_BCA_Assay/README.md](https://github.com/bingling-w/opentrons_protocols/blob/b93ca273f6ca3675e3d4cf0b563ff5fef0383b0d/protocols/OT-Flex/Pierce_Gold_BCA_Assay/README.md)

This protocol version performs automated Pierce Gold BCA assay kit from a 96 well plate using the Opentrons Flex robot with an 1000uL 8-channel and 50 uL 1-channel  pipette. The protocol is flexible, allowing inputs for different numbers of BSA unknowns and different numbers of replicates. 

The code can accept up to 12 unknowns in tube rack columns 3-5 starting in row A and working down (A3, B3 ,... ,D5), and up to 4 repititions. 

## Protocol Materials
- Robot: Opentrons Flex
- Hardware: Heater shaker with the universal flat plate
- Pipette: Flex 8-Channel 1000 µL and 1-Channel 50 µL
- Tips: One 200 uL tip rack and one 50 uL tip rack
- Plate: NUNC 96 wellplate optical bottom black
- Reservoir: Opentrons Tough 22 mL 12 Well Reservoir
- Others: Two opentrons 24 tuberack holder

## Protocol Summary
### Setup
Before automation, place all labware accordance to the screen visualization set up

Example Set Up image for 4 unknowns: <img width="809" height="587" alt="image" src="https://github.com/user-attachments/assets/7e9c8b7e-0ef1-4fc4-bbc4-8f5605bd0269" />

- Liquid: Red = standards; yellow = unknowns; blue = reagent B; green = reagent A
- Tipracks: Blue = 1000 uL; Yellow = 200 uL
### Procedure
1. Place unknowns and standards tubes in preferred order in columns, and dispense the necessary amount of reagent A and B into the reservoir and tube respectively.
2. Start automation protocol.
3. Dispenses 10 µL of BSA standards into column 1 (and column 2-3 if there's replicates)
4. Dispenses 10 µL of BSA unknowns into the column next to the standards (replicates will be placed next to the first replicates row)
5. Combine reagent A and reagent B in a 50:1 ratio, then mix to create the working reagent.
6. Dispense 200 µL of working reagent with the 8-channel pipette into each row where there is standards and unknowns. Rows with less than 8 rows will have WR dispensed with the 1-channel pipette
7. Heater-shaker will shake the well-plate at 1500rpm for 30 seconds to mix well.
8. Protocol will set a timer for 5 minutes.
9. When timer is up, protocol will display completion so user can bring the wellplate to the spectrometry for absorbance reading. 

## Labware Required
This protocol requires the following custom labware:

[custom_labware/nunc_96_wellplate_optical_bottom_400ul.json](https://github.com/bingling-w/opentrons_protocols/blob/4070e261d453abb1e0a81ed08c07d66fa3a36a12/custom_labware/nunc_96_wellplate_optical_bottom_400ul.json)

## Protocol Validations
- $R^2$ value close to 1, signaling strong correlation between absorbance and concentration values. 

## Protocol Updates

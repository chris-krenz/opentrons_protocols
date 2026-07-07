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

Example Set Up image for 4 unknowns: <img width="774" height="589" alt="image" src="https://github.com/user-attachments/assets/5f159106-ed69-4114-9ab4-6372084885c8" />
- Liquid: Red = standards; orange = unknowns; blue = reagent B; green = reagent A
- Tipracks: Blue = 1000 uL; Yellow = 200 uL; Purple = 50 uL
### Procedure


## Labware Required
This protocol requires the following custom labware:

[custom_labware/nunc_96_wellplate_optical_bottom_400ul.json](https://github.com/bingling-w/opentrons_protocols/blob/4070e261d453abb1e0a81ed08c07d66fa3a36a12/custom_labware/nunc_96_wellplate_optical_bottom_400ul.json)

## Protocol Validations
- $R^2$ value close to 1, signaling strong correlation between absorbance and concentration values. 

## Protocol Updates

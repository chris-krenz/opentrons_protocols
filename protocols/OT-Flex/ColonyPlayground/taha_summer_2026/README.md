# Pierce Dilution-Free Rapid Gold BCA Protein Assay Kit (OT-Flex)

## Overview
[For protocol details, please see here](https://github.com/bingling-w/opentrons_protocols/blob/b1ec0c02c5e86098ba56da086d6d6e5b409ff91b/protocols/OT-Flex/Pierce_Gold_BCA_Assay/README.md)

This protocol version performs automated Pierce Gold BCA assay kit from a 96 well plate using the Opentrons Flex robot with an 1000uL 8-channel and 50 uL 1-channel  pipette. The protocol is flexible, allowing inputs for different numbers of BSA unknowns and different numbers of replicates. 

The code can accept up to 12 unknowns in tube rack columns 3-5 starting in row A and working down (A3, B3 ,... ,D5), and up to 4 repititions. 


## Protocol Summary
### Setup
Before automation, place all labware accordance to the screen visualization set up

Example Set Up image for 4 unknowns: <img width="809" height="587" alt="image" src="https://github.com/user-attachments/assets/7e9c8b7e-0ef1-4fc4-bbc4-8f5605bd0269" />

- Liquid: Red = standards; yellow = unknowns; blue = reagent B; green = reagent A
- Tipracks: Blue = 1000 uL; Yellow = 200 uL

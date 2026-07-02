# BSA Dilutions in Duplicates (OT-Flex)

## Overview
The protocol performs automated serial dilutions of BSA in 2 duplicates using the Opentrons Flex robot with an 1-channel 1000 µL pipette. The protocol is currently inflexible and only performs the set dilution process displayed below:

<img width="680" height="567.2" alt="Screenshot 2026-05-26 102554" src="https://github.com/user-attachments/assets/13179b49-0864-43ce-a262-7972b876983c" />

## Protocol Materials
- Robot: Opentrons Flex
- Pipette: Flex 1-Channel 1000 uL
- Tips: One 200 uL tip rack and one 1000 uL tip rack
- Plate: Collection plates from the promega miniprep kit
- Reservoir: Opentrons Tough 22 mL 12 Well Reservoir
- Others: One opentrons 24 tuberack holder

## Protocol Summary
### Set up
Before automation, place all labware accordance to the screen visualization set up

Example Set Up image:<img width="799" height="593" alt="image" src="https://github.com/user-attachments/assets/1258b839-7be1-4210-93d6-f9da6ef3cd02" />
Blue = water; Green = BSA stock

### Procedure
1. Place tubes in spot A1-A3 and B1-B3. Row A holding 1st set of BSA dilution, and row B holding the duplicates. Tube spot A6 and B6 will hold blanks.
2. Using the same tip, transfer all the water into the tubes.
3. Transfer BSA to the first column of tubes.
4. Perform serial dilution for row A.
5. Perform serial dilution for row B. 

## Protocol Validation
- Water test: Testing with water and 10% glycerol with water coloring to validate even mixing.
- Measure BSA concentration through BCA assay. 

## Protocol Updates
- Ver. 2: Changed tip size for transferring 200 uL volumes to increase accuracy. 
- Ver. 1: Code is updated with mixing at different heights

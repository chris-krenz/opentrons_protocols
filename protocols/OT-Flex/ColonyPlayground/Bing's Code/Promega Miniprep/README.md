> [!WARNING]
> Working in process, code not tested in actual protocol

# Wizard® MagneSil® Plasmid Purification System (OT-Flex)

## Overview
The protocol performs automated Promega miniprep from the provided 96 collection plate using 
the Opentrons Flex robot with an 1000uL 8-channel. The protocol is 
flexible, allowing inputs for different numbers of wells, up to 96 wells but only in multiples of 8. 

<details>
<summary>Click here for Promega Miniprep Information</summary>

The Promega miniprep is for rapid isolation of plasmid DNA in a multiwell format using paramagnetic particles for lysate clearing and DNA capturing. The use of paramagnetic particles skips the need for centrifuging. 

Here describes the keyword in each step of plasmid DNA isolation:
- **Resuspension**: cell pellet is suspended in a resuspension buffer to make the pellet a uniformed, liquid suspension. 
- **Lysis**: step to release plasmid DNA from the cell into the liquid, creating a lysate solution.
- **Neutralize**: step to precipitate gDNA, proteins and other debris, while keeping plasmid DNA suspended in the lysate.
- **Lysate Clearing**: step to remove the precipitated debris from the lysate. 
- **Bind**: capturing plasmid DNA and seperating it from the supernatant. 
- **Wash**: wash the bound DNA with 80% ethanol to remove remaining contaminants and impurities.
- **Elute**: the purified plasmid DNA is released by adding an elution buffer,  turning it into a solution called the eluate to be used for further downstream applications. 


</details>

## Protocol Materials
- Robot: Opentrons Flex
- Hardware: Heater shaker with the universal flat plate, magnetic block V1, flex gripper
- Pipette: Flex 8-Channel 1000 uL
- Tips: One 200 uL tip rack and one 1000 uL tip rack
- Plate: Collection plates from the promega miniprep kit
- Reservoir: Opentrons Tough 22 mL 12 Well Reservoir, greiner 96 deep well plate

## Protocol Summary
>[!IMPORTANT]
>Pelleting the bacteria and discarding the supernatant in the 96 deep wellplate must be done manually before starting automated protocol. 

### Set up
Before automation, place all labware accordance to the screen visualization set up

Example Set Up image: <img width="763" height="576" alt="image" src="https://github.com/user-attachments/assets/008d1d9b-a4c6-4573-bd3f-16d4f9b713d3" />

- Liquid: Black = cell pellet; Green = resuspension sultion; Aqua = Lysis solution; Yellow = Neutralization solution; Blue = MagneSil blue; Red = MagneSil red; Grey = 80% ethanol; Purple = Elution Buffer
  - The solutions are placed in order of their usage.
- Tiprack: Blue = 1000 uL; Orange = 200 uL

### Procedure
1. In deck space A2, place 3 of the collection plate stacked ontop of eachother.
2. Resuspends, lyses cell and neutralizes the cell.
3. Adds Magnesil BLUE and shakes on the shaker.
4. Transfers lysate to a collection plate on the magnetic block to clear lysate. Pellets form in this step.
5.  Adds Magnesil RED into a new binding collection plate, moved from the stack to a new deck using the flex gripper.
6.  Transfers cleared lysate to binding plate, to mix on the shaker.
7.  Flex gripper transfers binding plate to magnetic block to form pellets. Supernatant is discarded.
8.  Binding plate it put pack on the shaker, adding more magnesil RED and clear lysate. Mixed.
9.  Placed binding plate back on magnetic block to form pellets. Supernatant discarded.
10.  To wash ethanol is added, shakened, placed on magnetic block to form pellet, and excess liquid is discarded. Repeated twice more.
11.  Allows plate to dry for 10 minutes.
12.  Adds elution buffer to the binding plate, mixed and placed back on magnetic block to form pellets.
13.  Eluate is transferred to a new collection plate, moved from stack to a new deck using the gripper.
14.  Removes residual particles by placing new collection plate onto the magnetic block to allow pellets to form.
15.  Transfers the second eluate to a final collection plate to complete protocol. 

## Labware Required (WIP)
This protocol requires the following custom labware:

[custom_labware/greiner_96_deep_wellplate_2000ul.json](https://github.com/bingling-w/opentrons_protocols/blob/29361d83081d2a70c38b127bdfcdc24d1e554025/custom_labware/greiner_96_deep_wellplate_2000ul.json)

## Protocol Validations (WIP)
- Validate in Nanodrop

## Protocol Updates
- Ver. 2: Added transfer with liquid class function volatile (80% ethanol) and viscous (50% glycerol) liquids. Also added flow rate adjustments for small volumes.
- Ver. 1: Moved collection plate off deck when no longer needed to save deck space for the rest of the protocol. 

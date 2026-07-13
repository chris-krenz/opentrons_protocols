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
- Plate: 96 well collection plates from the promega miniprep kit
- Reservoir: Opentrons Tough 22 mL 12 Well Reservoir, greiner 96 deep well plate

<details>
<summary>Click here for materials reference image</summary>

  Heater-Shaker universal flat plate

  <img width="386" height="217" alt="image" src="https://github.com/user-attachments/assets/6d3ab0c3-4660-4dc9-8cd2-24c47ffe4edb" />

  Magnetic block V1

  <img width="320" height="180" alt="image" src="https://github.com/user-attachments/assets/5764cd49-03ae-450f-b735-6897b0fbd07a" />

  Promega kit collection 96 well plates:
  
  <img width="300" height="100" alt="image" src="https://github.com/user-attachments/assets/f9d349de-c989-41cc-afa0-0136f3bb1381" />
  
  Opentrons Tough 22 mL 12 Well Reservoir:
  
  <img width="350" height="260" alt="image" src="https://github.com/user-attachments/assets/a10b9586-7cb7-46e7-a837-904160e4ec50" />

  Greiner 96 deep well plate 2.2 mL:

  <img width="310" height="255" alt="image" src="https://github.com/user-attachments/assets/523d010e-a8e7-4f87-8ff6-615b63fac689" />

</details>

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
1. In deck space A2, place 3 of the plate stacked ontop of eachother.
2. Resuspends, lyses and neutralizes the cell in the deep wellplate. 
3. Adds Magnesil BLUE into the deep wellplate and shakes on the shaker.
4. Transfers lysate from deep wellplate to a clearing plate on the magnetic block to clear lysate. Unwanted pellets form in this step.
5.  A new binding place is placed onto a new deck space using the flex gripper.
6.  25 uL of Magnesil Red is added into the binding plate
7.  Transfer 120 uL of cleared lysate from the clearing plate to the binding plate. Binding plate is shaked to mix. 
8.  Binding plate is moved to magnetic block to form wanted pellets. Supernatant is discarded.
9.  Repeat step 6-8 for the binding plate, then discard clearing plate. 
12. To wash, 100 uL of 80% ethanol is added, then shaken to mix. Afterwards, it's placed on the magnetic block, and supernatant is discarded. Repeat two more times for a total of 3 washes. 
13.  Allow plate to dry for 10 minutes.
14.  Adds elution buffer to the binding plate, shake to mix and place back on magnetic block to form unwanted pellets.
15.  A new elution plate is placed, and the eluate from the binding plate is transferred to the elution plate.  
16.  Remove residual particles by placing the elution plate on the magnetic block to allow unwanted pellets to form.
17.  Transfers the eluate to a final collection plate to complete protocol. 

## Labware Required (WIP)
This protocol requires the following custom labware:

[custom_labware/greiner_96_deep_wellplate_2000ul.json](https://github.com/bingling-w/opentrons_protocols/blob/29361d83081d2a70c38b127bdfcdc24d1e554025/custom_labware/greiner_96_deep_wellplate_2000ul.json)

[custom_labware/greiner_96_microplate 280ulul.json](https://github.com/bingling-w/opentrons_protocols/blob/27faed698ad127100460ee679eb362f18b751a92/custom_labware/greiner_96_microplate_280ul.json)

## Protocol Validations (WIP)
- Validate in Nanodrop

## Protocol Updates
- Ver. 4: Changed code based on protocol.io promega miniprep protocol. 
- Ver. 3: Adjusted flex gripper offset to avoid liquid spilling when moving labwares. 
- Ver. 2: Added transfer with liquid class function volatile (80% ethanol) and viscous (50% glycerol) liquids. Also added flow rate adjustments for small volumes.
- Ver. 1: Moved collection plate off deck when no longer needed to save deck space for the rest of the protocol. 

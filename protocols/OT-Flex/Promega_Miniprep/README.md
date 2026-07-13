> [!WARNING]
> Working in process, code not tested in actual protocol

# Wizard® MagneSil® Plasmid Purification System (OT-Flex)

## Overview
The protocol performs automated Promega miniprep from the provided 96 collection plate using 
the Opentrons Flex robot with an 1000uL 8-channel. The protocol is 
flexible, allowing inputs for different numbers of wells, up to 24 wells in multiples of 8. 

The code is now flexible for choosing manual or automated resuspension steps.
- Manual resuspension is good for: users who pellets and resuspend bacterias in tubes to transfer to deep wellplates
- Automated resuspension is good for: users who pellets bacterias directly in the deep wellplates. 

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
- Tips: Two 200 uL tip rack, one 1000 uL tip rack, and one 50 uL tiprack
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
>Pelleting the bacteria, discarding the supernatant (and resuspending if chosen to do manually) the pellet must be done manually before starting automated protocol. 

### Set up
Before automation, place all labware accordance to the screen visualization set up

Example Set Up image: <img width="759" height="589" alt="image" src="https://github.com/user-attachments/assets/38229e29-000f-410d-bc44-7f7f011a8887" />

- Liquid: Black = cell pellet; Aqua = lysis solution; Yellow = Neutralization solution; Blue = MagneSil blue; Red = MagneSil red; Dark  Grey = 4/40 Wash, Light Grey: 80% ethanol; Purple = Elution Buffer; Brown = Isopropanol; Dark Blue = Resuspension solution
  - Solution placement can be checked in protocol visualization in the Opentrons App. 
- Tipracks: Blue = 1000 uL; Orange = 200 uL; Purple = 50 uL

### Procedure
1. In deck space A2, place the reservoir with all the reagents.
2. (Resuspends if done automated), Lyses and neutralizes the cell in the deep wellplate. 
3. Adds Magnesil BLUE into the deep wellplate and shakes on the shaker.
4. Transfers lysate to row (clearing row) next to it, and transfers deep wellplate to the magnetic block to clear lysate. Unwanted pellets form in this step.
6.  25 uL of Magnesil Red is added into the row (binding row) next to the clearing row.
7.  Transfers 120 uL of cleared lysate from the clearing row to the binding row. Deep wellplate is put on the shaker to mix. 
8.  Wellplate is moved to magnetic block to form wanted pellets. Supernatant is discarded.
12. To wash, 100 uL of 80% ethanol is added, then shaken to mix. Afterwards, it's placed on the magnetic block, and supernatant is discarded. Repeat two more times for a total of 3 washes. 
13.  Allow plate to dry for 10 minutes.
14.  Adds elution buffer to the binding plate, shake to mix and place back on magnetic block to form unwanted pellets.
15.  A new elution plate is placed, and the eluate from the binding plate is transferred to the elution plate.  
16.  Remove residual particles by placing the elution plate on the magnetic block to allow unwanted pellets to form.
17.  Transfers the eluate to a final collection plate to complete protocol. 

## Labware Required (WIP)
This protocol requires the following custom labware:

[custom_labware/greiner_96_deep_wellplate_2000ul.json](https://github.com/bingling-w/opentrons_protocols/blob/29361d83081d2a70c38b127bdfcdc24d1e554025/custom_labware/greiner_96_deep_wellplate_2000ul.json)

## Protocol Validations (WIP)
- Validate in Nanodrop

## Protocol Updates
- Ver. 5: Change code to use suitable tips for different volumes, flexible for two setup (manual resuspension or automated resuspension steps), added a second 200 uL tiprack for cell amount above 8 wells, and changed all microplates to the deep wellplate. 
- Ver. 4: Changed code based on protocol.io promega miniprep protocol. 
- Ver. 3: Adjusted flex gripper offset to avoid liquid spilling when moving labwares. 
- Ver. 2: Added transfer with liquid class function volatile (80% ethanol) and viscous (50% glycerol) liquids. Also added flow rate adjustments for small volumes.
- Ver. 1: Moved collection plate off deck when no longer needed to save deck space for the rest of the protocol. 

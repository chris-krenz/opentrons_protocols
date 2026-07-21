> [!WARNING]
> Working in process, not validated. 

# Wizard® MagneSil® Plasmid Purification System (OT-Flex)

## Overview
The protocol performs automated Promega miniprep from a 96 well deep wellplate using 
the Opentrons Flex robot with an 1000uL 8-channel. The protocol is 
flexible, allowing inputs for different numbers of bacteria cell pellet, up to 32 wells in multiples of 8. 
- Note: When there's more than 24 wells, the protocol will prompt for a tip refill in the middle of the protocol.  

The code is now flexible for choosing manual or automated resuspension steps.
- Manual resuspension is good for: users who pellets and resuspend bacterias in tubes to transfer to deep wellplates
- Automated resuspension is good for: users who pellets bacterias directly in the deep wellplates. 

<details>
<summary>Click here for Promega Miniprep Information</summary>

The Promega miniprep is for rapid isolation of plasmid DNA in a multiwell format using paramagnetic particles for lysate clearing and DNA capturing. The use of paramagnetic particles skips the need for centrifuging, making it ideal for automating. 

Here describes the keyword in each step of plasmid DNA isolation:
- **Resuspension**: cell pellet is suspended in a resuspension buffer to make the pellet a uniformed, liquid suspension. 
- **Lysis**: step to release plasmid DNA from the cell into the liquid, creating a lysate solution.
- **Neutralize**: step to precipitate gDNA, proteins and other debris, while keeping plasmid DNA suspended in the lysate.
- **Lysate Clearing**: step to remove the precipitated debris from the lysate. 
- **Bind**: capturing plasmid DNA and seperating it from the supernatant. 
- **Wash**: wash the bound DNA to remove remaining contaminants and impurities.
- **Elute**: the purified plasmid DNA is released by adding an elution buffer,  turning it into a solution called the eluate to be used for further downstream applications. 

</details>

## Protocol Hardwares
- Robot: Opentrons Flex
- Hardware:
  - Heater shaker with the universal flat plate
  - Flex gripper
  - Flex HEPA/UV module
- Pipette: Flex 8-Channel 1000 uL.

All labwares and consumable materials are listed [here](link to protocols.io materials sections here)

<details>
<summary>Click here for materials reference image</summary>

  Heater-Shaker universal flat plate

  <img width="386" height="217" alt="image" src="https://github.com/user-attachments/assets/6d3ab0c3-4660-4dc9-8cd2-24c47ffe4edb" />

</details>

## Protocol Summary
>[!IMPORTANT]
>The labware is labelled as the Opentrons Magnetic Block V1, but the protocol uses a different magnet block. Offset for the flex gripper is calibrated in the code already, but please calibrate the pipette to the height of the labware on the different magnet block. 

### Robot Set-up
Before automation, download the promega_miniprep.py file, edit the parameter to fit your needs, and import it into the Opentrons software.\
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

Example Set Up image: <img width="559" height="450" alt="image" src="https://github.com/user-attachments/assets/38229e29-000f-410d-bc44-7f7f011a8887" />

### Procedure
For automation prep and protocol procedures follow the instructions [here](Insert protocols.io link here)

## Labware Required (WIP)
This protocol requires the following custom labware:

[custom_labware/greiner_96_deep_wellplate_2000ul.json](https://github.com/bingling-w/opentrons_protocols/blob/29361d83081d2a70c38b127bdfcdc24d1e554025/custom_labware/greiner_96_deep_wellplate_2000ul.json)

## Protocol Validations (WIP)
- Validate in Nanodrop

## Protocol Updates
- Ver. 7: Dynamic mixing for resuspending cell pellets at different xyz coordinates for thorough resuspension. 
- Ver. 6: Allow for up to 32 wells of bacteria cell culture, and changed aspirate and dispense height to allow for less dead volume to be used. 
- Ver. 5: Change code to use suitable tips for different volumes, flexible for two setup (manual resuspension or automated resuspension steps), added a second 200 uL tiprack for cell pellet amount above 8 wells, and changed all microplates to the deep wellplate.
  - Increased accuracy, flexible for people who does not have/want to use a wellplate centrifuge, add more tipracks to avoid running out of tips mid protocol, and changed wellplates to further match up with the protocol.io protocol. 
- Ver. 4: Changed code based on protocol.io promega miniprep protocol, as protocol.io protocol has been tested to work automated on the Hamilton. 
- Ver. 3: Adjusted flex gripper offset to avoid liquid spilling when moving labwares. 
- Ver. 2: Added transfer with liquid class function volatile (80% ethanol) and viscous (50% glycerol) liquids. Also added flow rate adjustments for small volumes for more accurate pipetting. 
- Ver. 1: Moved collection plate off deck when no longer needed to save deck space for the rest of the protocol. 

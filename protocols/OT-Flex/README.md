# Creating New Opentrons Protocols
The Opentrons Flex runned using the Opentrons App with protocols coded in Python with the Opentrons Python API. For full documentation of the Opentrons Python API and its function please see [here](https://docs.opentrons.com/python-api/).  

For protocols that have parameters, account for making the Python script flexible for different inputs. 

1. Read over the manual protocols.io (or manual if protocols.io doesn't exist) and understand the experiment.
2. List the materials and hardware needed for the protocols, match and replace labware if needed. Write down API names for each materials and hardware.
3. Before writing the protocol, begin by adding the imports, metadata, and requirements.
      -  You can also use the opentrons official [Protocol Designer](https://designer.opentrons.com/?_gl=1*bagoc2*_ga*MTAyMjAwODcyMS4xNzc0MDM2NzU0*_ga_66HK7MC5D7*czE3ODQ3MzY0NTckbzUxJGcxJHQxNzg0NzM2NDY2JGo1MSRsMCRoMA..*_gcl_au*OTUzMDE4Nzc5LjE3ODE4MTgxMTA.*_ga_GNSMNLW4RY*czE3ODQ3MzY0NTckbzUxJGcxJHQxNzg0NzM2NDY2JGo1MSRsMCRoMTI2MTg1MjkzMA) to create a base script to then edit base off needs.
6. Begin formatting the script by adding protocol comments keep track of steps (action, volume, location and destination)  
   Example:
```
from opentrons import protocol_api

metadata = {
    "apiLevel": "2.16",
    "protocolName": "Promega Miniprep Draft",
    "description": """Example python script""",
    "author": "Your name"
}

requirements = {
    'robotType': 'Flex',
    'apiLevel': '2.25'
}

def run(protocol: protocol_api.ProtocolContext):
  protocol.comment('Adding 120 uL of neutralization solution to the lysis row in deep wellplate 1')

  protocol.comment('Shaking at 1800 rpm for 1 minute')

  protocol.comment('Adding 25 uL of magnesil blue to the lysis row in deep wellplate 1')

  protocol.comment('Adding 50 uL of magnesil red to the binding row in deep wellplate 1')
  ...
```
4. Explore Opentrons Python API documentation for commands and parameters that work with your protocol.
5. Edit the protocol based off dry runs, water runs, and runs with x% glycerol and food coloring if applicable.
   - Dry run: check for collisions, step order, flex gripper misalignment (if applicable).
   - Water run: check for bubbles, apiration/dispense speed, accurate pipetting (liquid left in and/or on tip), reducing dead volume.
     - Water have a much higher surface tension than most liquid, keep this in mind when testing to reduce dead volume. 
   - Glycerol run: check every in the water run when viscousity and surface tension is different. 

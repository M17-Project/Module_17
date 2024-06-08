## Ordering guide for Module17

This guide explains how to order Module17 boards on JLCPCB. JLCPCB is one of the websites that provides PCB assembly services to customers in small series. Other websites do provide the same services and the instructions might vary slightly.

### Production files

You will first need to locate the production files as you will have to upload them on JLCPCB website. 

* Mainboard files are located in `Module_17/hardware/mainboard/production/`:
    * `Module17_Rev_1.0.zip` contains the gerber files (the PCB fabrication files)
    * `bom.csv` contains the bill-of-materials, the list of components needed
    * `positions.csv` contains the position of all the components to assemble on the board (also called CPL file)

* HMI files are located in `Module_17/hardware/HMI/production/`:
    * `Module17-HMI.zip` contains the gerber files (the PCB fabrication files)
    * `bom.csv` contains the bill-of-materials, the list of components needed
    * `positions.csv` contains the position of all the components to assemble on the board (also called CPL file)

* Side panels files are located in `Module_17/hardware/side_panels/production/`:
    * `Module17-Side_Panels_Front.zip` contains the gerber files for the front panel
    * `Module17-Side_Panels_Back.zip` contains the gerber files for the back panel

### Ordering

#### Mainboard

The mainboard is the core part of Module17. It is required


### PCBA

It is advised to keep a close eye on those components when ordering:
* The LEDs are pre-populated by JLCPCB with RED leds. You should change the components selected for the blue (power), green (sync) and orange (error) LEDs.
* The components selected for some of the 10 nF capacitors (C304, C315, C503, C505, C506, C508), the 680pF capacitors (C504, C509), 1.5nF capacitor and some of the 100 nF capacitors (C306, C308, C309, C310, C401, C501, C502)  can be using X7R dielectric. It is advised to use C0G dielectric capacitors.
* Check that the crystal pre-populated by JLCPCB is designed to run with a 12pF capacitive load. Make sure to pick a crystal with a tolerance of 10ppm.

Sometimes, some components pre-selected in the BOM are not in stock at time of ordering. If this is the case, you can usually replace those with similar components availabel at the time of ordering.
Here is a list of alternative parts for some of the most problematic parts:

#### Tactile switch

If the original switch is not available, it is advised to pick another switch from the PTS645 series of surface-mount tactile switches

#### D203, D401 (BAT60A diodes)
The diodes for D203 and D401 are supposed to be BAT60A diodes but those can sometimes be hard to find. You can replace those with other low-Vf Schottky diodes, most notably the 1N5819WS is a basic part (no additional fees) that is widely available at JLCPCB.
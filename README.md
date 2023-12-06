# shared
shared files for public access

---

## keyboard projects
| PCB Name      | Size  | Firmware      | Mounting                  | Features                                                  |
| :------------ | ---:  | :------------ | :------------------------ | :-------------------------------------------------------- |
| merro60       | 60    | merro60       | gummy o-ring<br>SIMP kit  | MX / Alps                                                 |
| str.merro60   | 60    | str.merro60   | gummy o-ring<br>SIMP kit  | side-firing RGB underglow                                 |
| nki.merro60   | 60    | merro60       | pcb leaf-spring on tray   | MX / Alps                                                 |
| ppr.merro60   | 60    | ppr.merro60   | gummy o-ring<br>SIMP kit  | 1.2mm thickness<br>single optional horiz center flex cut<br>esc / caps lock indicator LED-capable|
| lfn.merro60   | 60    | lfn.merro60   | gummy o-ring<br>SIMP kit  | 2.0mm thickness                                           |
| piche60       | 60    | piche60       | general<br>misc           | MX / Alps<br>snappable halves<br>snappable usb -> db (udb compat)<br> esc / caps lock indictor LED-capable|

### merro60, str.merro60
This guide includes three main sections -
1. QMK guide (for flashing VIA-enabled QMK)
2. VIA / VIAL guide (for enabling VIA recognition)
3. physical installation guide

Two files are needed to configure the merro60 PCB.
- The \*.hex file is required for QMK flashing with VIA enabled
- The \*.json file is required for VIA operation

![merro60 kle](merro60/kle.svg)

---

#### QMK guide
The QMK hex file will enable all possible keys on the merro60 PCB.
1. Download [chlx_merro60_via.hex from caniusevia](https://www.caniusevia.com/docs/download_firmware)
2. Start up QMK Toolbox
3. Load in chlx_merro60_via.hex
4. Press reset button on PCB or short out reset contacts near spacebar socket
5. Flash it
6. Disconnect the PCB
7. Reconnect the PCB

Use VIA/VIAL to do the actual configuration.

---

#### VIA guide
Layout options available are -
- split backspace
- ANSI / ISO enter
- split left shift
- split right shift
- 6.25u / 7u / 10u bottom row

To set up VIA to recognize the merro60 PCB (no longer needed since VIA has integrated merro60 code) -
1. Download [merro60_via-layout.json](merro60/merro60_via-layout.json)
2. Start up VIA (merro60 should not be recognized yet, but we can keep going)
3. Go to 'Settings' tab
4. Enable 'Show Design tab'
5. Go to 'Design' tab
6. Load the \*.json file
7. Now use VIA as normal

~~Until I figure out how to push this json file into VIA's database, this is the only known way to program the merro60 PCB.~~

#### VIAL guide
Pretty much same as VIA, but 
1. QMK flash the keyboard with [chlx_merro60_vial.hex](merro60/chlx_merro60_vial.hex)
2. Use [VIAL](https://get.vial.today) to configure the keyboard

---

#### physical installation guide
This is just a guide for what I found easiest to install -
1. Use flat-top m2 screws
2. Leave the left and right screws in the case (green circles)
    - This is to give the PCB the expected height / distance from the case bottom
    - If bottoming out too often, you can unscrew the screws a little / add more padding material on the o-ring mounting points to give the PCB assembly more height  
    - You can leave the screws in the other posts too except the one under the spacebar
    ![tofu60 case](merro60/under-pcb.jpeg)
    - If using a Mekanisk Fjell / Klippe T case, all contact points circled in green need 1.5-2mm of increased height to prevent bottom-out (I used small cutouts of cork cabinet liner)
    ![klippe t case](merro60/klippet_fjell_adjustment.jpeg)
3. (Optional) Add a small piece of foam in the bottom left corner of the case
    - I experienced some tilting where the bottom left would dip and the top right would rise
    - Putting a small piece of foam here seems to prevent too much tilt and doesn't affect acoustics / feel
    - Update - When using a full plate (non-HHKB), the friction fit is tight enough to prevent tilting
4. Assemble stabilizers + switches + plate + PCB
    - Clip-in stabilizers for the spacebar are easiest to assemble
    - Optional configuration for screw-in stabilizers down below (only applies to v1.2, v2)
    - Unknown if clip-in stabilizers are also needed for full backspace
5. Run gasket between plate and PCB around the whole assembly
    - If screw-in spacebar stabilizers are desired, refer to "optional oring configuration" section below
6. Line up USB port to case opening first
7. Slip in pcb/plate/gasket assembly using the paper tabs method (credit: believe0101)
    ![assembly in 1](merro60/assemblyin-1.jpeg)
    ![assembly in 2](merro60/assemblyin-2.jpeg)
8. Screw in the spacebar post / PCB tab to ensure PCB can't fall out
    - Bare screw is ok to use without a washer
    - Area has been reinforced with disconnected / floating metal
    ![tofu60 secure](merro60/over-pcb.jpeg)

To pop the pcb/plate/gasket assembly out, reverse the paper tabs method (credit: believe0101)
    ![assembly out 1](merro60/assemblyout-1.jpeg)
    ![assembly out 2](merro60/assemblyout-2.jpeg)

#### optional oring configuration (allows screw-in stabilizers for tofu)
1. When running gasket between plate and PCB, run the gasket under the pcb through the cuts on the bottom pcb edge
    - Dotted light blue line shows original o-ring gasket route
    - Orange line shows optional oring configuration with layer change location
    ![optional oring config](merro60/oring_reroute_option.jpeg)
2. Continue assembly same as above except the paper tabs would go where the gasket changes layer

#### SIMP Kit Synergy (reduces physical support dependency on merro60 USB port)
- Tofu has a lack of supports at the top of the case
- Can use 3d-printed TPU SIMP kit tabs on the merro60 PCB at the upper half of left and right edges of the PCB to give additional support, specifically to the left of the typical "tab" spot and to the right of the "pipe / backslash" spot
- [geekhack reference](https://geekhack.org/index.php?topic=111539.0)

---

#### credits
- ai03 - reference footprints, PCB design guide, voyager series PCB references
- evyd13 - plain60 / plain60flex PCB references
- hugokeys, singakbd - mount style inspiration
- coolmanguy, spookyghost, believe0101 - prototype testers

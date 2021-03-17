# shared
shared files for public access

---

## keyboard projects
### merro60
Two files are needed to configure the merro60 PCB.
- The \*.hex file is required for QMK flashing with VIA enabled
- The \*.json file is required for VIA operation

![merro60 kle](merro60/kle.svg)

#### QMK guide
The QMK hex file will enable all possible keys on the merro60 PCB.
1. Download [chlx_merro60_via.hex](merro60/chlx_merro60_via.hex)
2. Start up QMK Toolbox
3. Load in chlx_merro60_via.hex
4. Press reset button on PCB or short out reset contacts near spacebar socket
5. Flash it
6. Disconnect the PCB
7. Reconnect the PCB

Use VIA to do the actual configuration.

#### VIA guide
Layout options available are -
- split backspace
- ANSI / ISO enter
- split left shift
- split right shift
- ANSI / tsangan bottom row

To set up VIA to recognize the merro60 PCB -
1. Download [merro60_via-layout.json](merro60/merro60_via-layout.json)
2. Start up VIA (merro60 should not be recognized yet, but we can keep going)
3. Go to 'Settings' tab
4. Enable 'Show Design tab'
5. Go to 'Design' tab
6. Load the \*.json file
7. Now use VIA as normal

Until I figure out how to push this json file into VIA's database, this is the only known way to program the merr60 PCB.

#### physical installation guide
This is just a guide for what I found easiest to install -
1. Use flat-top m2 screws
2. Leave the left and right screws in the case (green circles)
  - This is to give the PCB the expected height / distance from the case bottom
  - You can leave the screws in the other posts too except the one under the spacebar
  ![tofu60 case](merro60/under-pcb.jpeg)
3. (Optional) Add a small piece of foam in the bottom left corner of the case
  - I experienced some tilting where the bottom left would dip and the top right would rise
  - Putting a small piece of foam here seems to prevent too much tilt and doesn't affect acoustics / feel
4. Assemble stabilizers + switches + plate + PCB
5. Run gasket between plate and PCB around the whole assembly
6. Put bottom / spacebar side in place in the case first
7. Squeeze the plate + PCB towards the south to give enough clearance for the USB on top to slide down into the case
8. Screw in the spacebar post / PCB tab to ensure PCB can't fall out
  - Bare screw is ok to use without a washer and reinforced with disconnected / floating metal
  ![tofu60 secure](merro60/over-pcb.jpeg)

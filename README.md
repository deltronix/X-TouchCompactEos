# OSCII-bot script for interfacing between Behringer X-Touch devices and ETC Eos software



## Setup
 - Enable OSC Show Control in the EOS software: Set UDP RX Port to 8000, UDP TX Port to 8001 and UDP TX Ip Address to 127.0.0.1 (if you are running oscii-bot locally).
 - Load the eos_a.bin and eos_b.bin files into the X-Touch with the X-Touch Editor Software.
 - Put eos.txt in your "C:\Users\%UserName%\AppData\Roaming\oscii-bot\" folder
 - Connect and power up the X-Touch
 - Start oscii-bot and make sure it recognizes the X-Touch
 - Start the ETC Eos software and enjoy this physical interface

## Mapping:
By default the X-Touch is mapped as described below. 

 > !IMPORTANT Do not use Bank B! It is not finished and behaviour is not necessarily defined. If you implement some useful behaviour for Bank B feel free to submit it as a pull request though :) The issue is mostly that bank changes are not reported through MIDI. As a work around I now periodically update at least the fader positions (which are the same as Bank A for now). 

### Buttons:
 - Button row 1 is mapped to Macro 801-808
 - Button row 2 is mapped to the "Load" button for the corresponding fader
 - Button row 3 is mapped to the "Stop" button for the corresponding fader
 - Button row 4 is mapped to the "Bump" button for the corresponding fader

 - The << and >> buttons are mapped to "Select Last" and "Select Active" respectively
 - The "Loop" button is mapped to "Update"
 - The "Record" button is mapped to, you guessed it "Record"
 - The "Stop" buttons is mapped to "At"
 - The "Play" button is mapped to "Enter"

### Encoders:
The first 14 encoders are mapped to parameters as defined in the script, you could change these to what is useful to you. When pressing the encoder the associated parameter is posted to the command line.
 1. Red
 2. Green
 3. Blue
 4. Cyan
 5. Magenta
 6. Yellow
 7. Hue
 8. Saturation
 9. Intens
 10. Zoom
 11. Pan
 12. Tilt
 13. Edge
 14. Iris

Encoder 15 is used to change fader pages. By default the range is from page 1 to 8, a Macro in the range 811 to 818 is also fired to possibly update the Eos screen to show the corresponding fader states (perhaps through a Snapshot or a Magic Sheet View). 

Encoder 16 is mapped to the last and next keys.

### Faders 
Faders are mapped to fader 1-9 of page 1 through 8, therefore each tenth fader is not usable through the X-Touch. The fader page can be selected through encoder 15 and the active page is displayed on the LEDs of the second row of buttons. When you "Bump" a fader the motorized fader will reflect this change, which is somewhat annoying. Perhaps I will make it so the fader is not updated while the bump button is held in a future release.

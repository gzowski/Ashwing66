# Ashwing66 Winged Unibody Split Keyboard
66 Key keyboard with both MX and Choc V1 support.
![Ashwing66-rev1](https://github.com/gzowski/Ashwing66/blob/main/images/layouta.jpg)
![Ashwing66-rev1](https://github.com/gzowski/Ashwing66/blob/main/images/completed.jpg)

PCB available for purchase via my Etsy page: https://www.etsy.com/uk/listing/1765077057/ashwing66-mechanical-keyboard-pcb

## Features
* 66 Key layout 
* 67 Key for optional rotary encoder or additional key in the center
* Per key LED's for Row 1 and centre cluster keys
* Winged design for ergonomics at 15° angle.
* RP2040 Microcontroller (Pi Pico)
* QMK Firmware with VIA compatibility
* Pre-compiled firmware with VIA and experimental "snap tap" support within Firmware folder.
  * "Snap tap" Enable / disable "Lower + Esc" "LED Green On/LED Red Off"

## Parts

| Part | Quantity     | Description                | 
| :-------- | :------- | :------------------------- |
| Diodes| 67  | Through-hole 1N4148 or SMD 1N4148W |
| Microcontroller | 1 | Pi Pico RP2040 |
| Switches | 66 or 67 | MX or Choc V1 (67 instead of rotary encoder) |
| EC11 | 0 or 1 | Rotary Encoder for center (depending on configuration) |
| Keycaps | 66 or 67 | 1u switches (depending on configuration) |

## Optional Parts

| Part | Quantity     | Description                |
| :-------- | :------- | :------------------------- |
| LED Diodes | 18 |  SK6812 MINI-E |
| Top Plate | 1 | Lasercut or 3D print options in Plates folder |
| Base Plate | 1 | Lasercut or 3D print options in Plates folder |
| M2 Standoff | 10 | M2x8mm |
| M2 Screws | 10 | M2x6mm | 

## Build Guide

1. Solder PICO micro controller to the top of the PCB facing up (components on top).
  - Next solder the diodes of choice to the back of the PCB, these can be either surface mount or through-hole diodes
    - Take note of diode direction.
    - If using through-hole diodes you'll need to snip the excess from the legs on the other side.
2. If you are installing LED's under the 18 switches then you can do this now.
   - The LED's can be dropped into place from the rear of the board. 
   - Ensure that the notch on the GND pin lines up with the triangle marker on the PCB.
   - These can be fiddly to solder and take a bit of patience but once the first leg is soldered then the others become easier. 
3. If you are opting to use a rotary encoder then this can be soldered next.
  - This is positioned in the center and needs to be done before installing a top plate
4. If you are using a top plate read on, otherwise skip to step 5 (To hold switches in place)
   - Place each of your chosen switches into the top plate
     - The pins should be on orintated with the pins north of the the stem if looking straight on.
5. Place the switches down onto the main PCB, ensuring all switches are flush to the board.
   - Turn board over onto the reverse and begin soldering each of the switch pins to the PCB.
6. If you've got a base plate cut then this is where you'll use M2 screws and M2 standoffs to join the top plate to the base.
7. Installing Firmware/Flashing
   - Using QMK from github, building firmware
     - make ashwing66:default:flash or make ashwing66:via:flash (For VIA Support)
   - Copying U2F straight to RP2040 storage
     - Hold down the BOOT button on the Pico while connecting the USB, a new device should be detected as storage.
       - Copy the Ashwing66_via.uf2 file onto the storage.
       - Reconnect the keyboard once the USB storage disappears.

## Default Key Layout

![Layers](https://github.com/gzowski/Ashwing66/blob/main/images/layers.jpg)

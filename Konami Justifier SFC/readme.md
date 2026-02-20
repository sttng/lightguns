# Konami Justifier (Super Famicom)

(from https://problemkaputt.de/fullsnes.htm#snescontrollerskonamijustifierlightgun)

SNES Controllers Konami Justifier (Lightgun)

```
   -_______________________--
  |                :  :....: \_/\
  |________________:__:....:    /
   \________________\.:....; O  \_    <---- O = Start Button
                    |_ _____      |
                      \| ) |/\     \  <---- ) = Trigger
                       \___/  |     |
                              |     |
                              |_____|
               RJ12-socket ____/   \________ Cable (to SNES controller port)
            (for second gun)

```

  Blue Gun --> connects to SNES (and has 6pin RJ12 socket for second gun)
  
  Pink Gun --> connects to 6pin RJ12 socket of first gun


## Justifier Bits

-  1st..12th   Unused             (always 0=High)
-  13th..16th  ID Bit3-0          (MSB first, 1=Low=One, always 0Eh = 1110b)
-  17th..24th  Extra ID Bit7-0    (MSB first, 1=Low=One, always 55h = 01010101b)
-  25th        Gun 1 Trigger      (1=Low=Pressed?)
-  26th        Gun 2 Trigger      (1=Low=Pressed?)
-  27th        Gun 1 Start Button (1=Low=Pressed?)
-  28th        Gun 2 Start Button (1=Low=Pressed?)
-  29th        Previous Frame was H/V-latching Gun1/2 (1=Low=Gun1, 0=High=Gun2)
-  30th..32th  Unused             (always 0=High)
-  33th and up Unused             (always 1=Low)

For obtaining the H/V position & latch flag (Ports 213Ch,213Dh,213Fh), see:

SNES PPU Timers and Status

Note that the 29th bit toggles even when Gun2 is not connected.

## SNES Justifier Game(s)

  Lethal Enforcers (bundled with the hardware) (1993) Konami (US) (EU) (JP)


IOBit is used just like for the SuperScope. However, since two guns may be plugged into one port, which gun is actually connected to IOBit changes each time Latch cycles. Also note, the Justifier does not wait for the trigger to be pulled before attempting to latch, it will latch every time it sees the electron gun. Bit 6 of $213F may be used to determine if the Justifier was pointed at the screen or not.
Data2 is presumably not connected, but this is not known for sure.

Nardz: "Actually when I was a kid, I bought the SNES Justifier Battle Clash package. The Weird thing about it is that The package had A Sega Justifier in it, but it came with this SNES/Sega Adapter, which pluged into your SNES and the Sega Justifier would plug into the back of the connector." -- But, Battle Clash is a Super Scope game, not a Justifier game???

The pinouts of the 6pin RJ12-socket are:

- 1 Trigger Button
- 2 Start Button
- 3 Not connected
- 4 Ground
- 5 Light Sensor
- 6 Power

## Sega Version
There's also an identically looking Blue Gun for Sega (but with 9pin joystick connector). 

the Sega PCB looks 99% the same, except for the missing Konami print on the lower side and an additional hole at the top, plus a slide movement to the right of the top solder point. 
But this might be also due to a slight revision of the PCB in general. 

The Pink Gun can be used with both SNES and Sega Blue Gun versions.

## Convert blue gun into 2nd (pink) gun

http://www.markwylie.ca/2015/02/sega-konami-justifier-hack-convert.html

## Diode

Seems this one is compatible: Sharp IS485E https://www.mouser.de/ProductDetail/Sharp-Microelectronics/IS485E?qs=5S%2F4hkdqNNeR3cROBNqcQg%3D%3D&srsltid=AfmBOoovrUQq4HjEcKYwQhL7y4MbDu9yn4uFzzom2SWx9jFHF5sSnjGC

## BoM

### Bottom PCB

| Designator  | Footprint                                          | Quantity | Description   |
|-------------|----------------------------------------------------|----------|---------------|
| C           | Ceramic Capacitor                                  | 1        | 0.1µF (104)   |
| C           | Ceramic Capacitor                                  | 1        | 2.2nf (222)   |
| C           | Radial Electrolytic Capacitor                      | 1        | 10µF 25V      |
| R           | zero-ohm link or zero-ohm resistor                 | 1        | 0 Ohm         |
| IC1         | SO16W 7.5x10.3mm P1.27mm                           | 1        | Konami 056816 |


### Top PCB

| Designator  | Footprint                                          | Quantity | Description   |
|-------------|----------------------------------------------------|----------|---------------|
| C           | Ceramic Capacitor                                  | 1        | 0.1µF (104)   |
| D           | Diode (Sharp IS485E)                               | 1        | Sharp IS485E  |
| R           | ???                                                | 1        | ???           |


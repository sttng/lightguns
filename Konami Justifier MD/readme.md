# Konami Justifies Mega Drive / Genesis

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
               RJ12-socket ____/   \________ Cable (to Mega Drive controller port)
            (for second gun)

```

  Blue Gun --> connects to Mega Drive (and has 6pin RJ12 socket for second gun)
  
  Pink Gun --> connects to 6pin RJ12 socket of first gun

The Sega PCB looks 98% the same compared to the SNES, except for the missing Konami print on the lower side and an additional hole at the top, plus a slide movement to the right of the top solder point. Also it has different resistors and no capacitors (in difference to the SNES PCB). 

The Pink Gun can be used with both SNES and Sega Blue Gun versions.

## Convert blue gun into 2nd (pink) gun

http://www.markwylie.ca/2015/02/sega-konami-justifier-hack-convert.html

## BoM

### Bottom PCB

| Designator  | Footprint                                          | Quantity | Description   |
|-------------|----------------------------------------------------|----------|---------------|
| C1          | Radial Electrolytic Capacitor                      | 1        | 10µF 25V      |
| C2          | THT Capacitor Pink (brown, black, yellow , white)  | 1        | 100nF 10% Tolerance |
| MD-R2       | THT Resistor Beige (yellow, violet, brown, gold)   | 1        | 470k 5% Tolerance |
| U1          | SOP16 JEITA / EIAJ Type II 5.3x10.3mm P1.27mm      | 1        | Konami 056816     |

### Top PCB

| Designator  | Footprint                                          | Quantity | Description   |
|-------------|----------------------------------------------------|----------|---------------|
| C1          | THT Capacitor Pink (brown, black, yellow , white)  | 1        | 100nF 10% Tolerance |
| R1          | THT Resistor  Beige (brown, black, red, gold)      | 1        | 1k Ohm 5% Tolerance |
| D           | Diode (Sharp IS485E)                               | 1        | Sharp IS485E  |


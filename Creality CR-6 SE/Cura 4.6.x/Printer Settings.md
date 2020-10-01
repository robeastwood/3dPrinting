# Printer

Built on Cura CR-10 base.

## Printer Settings

X Width: 235
Y Depth: 235
Z Height: 250
Build Plate: Rectangular
Origin at center: false
Heated Bed: true
Heated build volume: false
G-code flavor: Marlin

## Printhead Settings

X min: -26
Y min: -32
X max: 32
Y max: 34
Gantry Height: 25
Number of Extruders: 1
Shared Heater: false

## Start G-code

    M201 X500.00 Y500.00 Z100.00 E5000.00 ;Setup machine max acceleration
    M203 X500.00 Y500.00 Z10.00 E50.00 ;Setup machine max feedrate
    M204 P500.00 R1000.00 T500.00 ;Setup Print/Retract/Travel acceleration
    M205 X8.00 Y8.00 Z0.40 E5.00 ;Setup Jerk
    M220 S100 ;Reset Feedrate
    M221 S100 ;Reset Flowrate
    G28 ;Home
    G92 E0 ;Reset Extruder
    G1 Z2.0 F3000 ;Move Z Axis up
    G1 X10.1 Y20 Z0.28 F5000.0 ;Move to start position
    G1 X10.1 Y200.0 Z0.28 F1500.0 E15 ;Draw the first line
    G1 X10.4 Y200.0 Z0.28 F5000.0 ;Move to side a little
    G1 X10.4 Y20 Z0.28 F1500.0 E30 ;Draw the second line
    G92 E0 ;Reset Extruder
    G1 Z2.0 F3000 ;Move Z Axis up

## End G-code

    G91 ;Relative positioning
    G1 E-2 F2700 ;Retract a bit
    G1 E-2 Z0.2 F2400 ;Retract and raise Z
    G1 X5 Y5 F3000 ;Wipe out
    G1 Z10 ;Raise Z more
    G90 ;Absolute positionning
    M106 S0 ;Turn-off fan
    M104 S0 ;Turn-off hotend
    M140 S0 ;Turn-off bed
    M84 X Y E ;Disable all steppers but Z

# Extruder 1

## Nozzle Settings

Compatible material diameter: 1.75
Nozzle offset X: 0
Nozzle offset Y: 0
Cooling Fan Number: 0

## Extruder Start G-code

    

## Extruder End G-code

    

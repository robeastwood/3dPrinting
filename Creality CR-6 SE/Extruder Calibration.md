# Extruder Calibration

My printer extruder had to be calibrated, as it was under-extruding by about 4% from the factory default.

I used Repetier-Host to connect directly to the printer via the USB port, then manual control to send it raw G-code commands.

This is the process to calibrate the extruder:

1. Send command M503 to read current settings. It will output a load of info to the console. Look for something like:

        Steps per unit:
        M92 X80.00 Y80.00 Z400.00 E93.00

The __E93.00__ at the end of this line is the current value for the steps for the extruder. in this case 93.00 (steps/mm)

2. Mark the filament some distance (say 50mm) away from the runout sensor. Tell the printer to extrude that length of filament. You can use the touchscreen interface to to this.

3. Measure again between the runout sensor and the mark you made, to work out exactly how much it actually extruded, eg 46mm

4. Calculate the new steps value.

    The formula is:
        
        (Amount requested x original steps value) / amount extruded

    In this example (50 x 93) / 46 = 101.087...
    So we want 101.1 as the new setting.

5. Set the new value with command **M92 Exxx** where __xxx__ = the new value. In this case **M92 E101.1**

6. Save the new setting to memory with command **M500**

7. Test! Do another extrude & measure, and check you have got it accurate. If not, repeat the process.

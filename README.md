# Klipper config and macros for my SKR 1.3 based CoreXY printer
This config is for my SKR 1.3 based CoreXY printer with dual-Z independent steppers (hence the Z-tilt macro before actual bed mesh levelling) and a fixed X/Y Voron 2.4 gantry (so it's basically a Trident but only with 2 Z stepper motors and not as pretty or boxed 🤣)

## Slicer adjustments so that the START_GCODE macro works
In Prusa Slicer, I have the following code in the Start Gcode field:
```M104 S0 ; convince Prusa Slicer not to pre-heat nozzle
M140 S0 ; convince Prusa Slicer not to pre-heat bed  
START_PRINT BED_TEMP=[first_layer_bed_temperature] EXTRUDER_TEMP=[first_layer_temperature] PRINT_MIN={first_layer_print_min[0]},{first_layer_print_min[1]} PRINT_MAX={first_layer_print_max[0]},{first_layer_print_max[1]}```

The End Gcode is:
```END_PRINT```


### WARNING
Please feel free to get inspired or use parts of the code if you wish, but you're doing so at your own risk! Each and every printer is unique and you'll need to adjust the code to your needs.

# UltiMaker Original +
Collection of information regarding my UltiMaker Original+

## History

The printer was purchased in November 2023 in Stockholm, Sweden, for SEK 1000.

Upon realizing that the firmware is no longer maintained by UltiMaker and that the latest release is labeled "DEV," I wanted to find an alternative firmware. Klipper came to mind, and after following the official documentation, the printer was up and running.

Currently, I am printing parts and tuning the machine. The current slicer I am using is Cura.

## BL-Touch

Running a BL-Touch on the UltiMaker V2 mainboard is not that common, at least not the documentation for how to do it. After following instructions found on a [french post](https://community.ultimaker.com/topic/15308-auto-levelling-sur-umo/) on the UltiMaker community forum, I was able to the sensor up and running in Klipper.

Using the following image as a reference to connect the sensor to the **EXP3** port.

![From the "french post" on UltiMaker community forum](/images/bl-touch-with-ultimaker-v2.jpg)

The following lines are then added to the `printer.cfg`` in Klipper:

```
[bltouch]
sensor_pin: ^PA7
control_pin: PB7
z_offset: 0 
```

Also, remember to change the endstop pin for the Z-axis:

```
[stepper_z]
...
endstop_pin: probe: z_virtual_endstop
```
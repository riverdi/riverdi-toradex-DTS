# Device tree overlays for Toradex 
## Introduction
The following files are prepared for the Verdin iMX8M Plus and Mini to working with standard Toradex DSI line. 7", 10.1", 12.1", 15.6" are supported. To complie all the necessary device tree overlays, [complied kernel](https://developer.toradex.com/linux-bsp/os-development/build-u-boot-and-linux-kernel-from-source-code/build-linux-kernel-from-source-code) is required. Toradex also provides documentation how to [build device tree overlays](https://developer.toradex.com/linux-bsp/os-development/build-u-boot-and-linux-kernel-from-source-code/build-device-tree-overlays-from-source-code/). Timings can be found in .dtsi files.
## Capacitive touch panels
### I2C
|Display size|Driver IC|Linux driver|
|------------|---------|------------|
|7"| ILI2132|ilitek_ts_i2c|
|10.1"| ILI2132|ilitek_ts_i2c|
|12.1"| ILI2511|ili210x|
|15.6"| ILI2510|ili210x|


In case of using 12.1" or 15.6" it is important to set the touchscreen size as follows:
<pre>
touch@41 {
    .
    .
    .
    touchscreen-size-x = <1920>;
    touchscreen-size-y = <1080>;
};	 
</pre>

### USB
After connecting touch panel via USB, the driver is loaded automatically

## Summary
Source [Toradex - device tree overlays](https://git.toradex.com/cgit/device-tree-overlays.git/)

If you decide to run displays on a different SBC, consider it as a template.
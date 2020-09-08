# Configuration guide for SKR Mini E3 v2.0

This guide documents all settings changed in files **Configuration.h** and **Configuration_adv.h** from Marlin bugfix 2.0.x config examples for **Creality Ender-5** with a **BLTouch**. 

This build started by using the `configuration.h` and `configuration_adv.h` from the examples provided by the Marlin team; https://github.com/MarlinFirmware/Configurations/tree/import-2.0.x/config/examples/Creality/Ender-5/BigTreeTech%20SKR%20Mini%20E3%202.0

SHA `863313f`


## 1. File Configuration.h

This section details all configurations made to Marlin main configuration file (**Configuration.h**).



### 1.1. Configure baudrate

From `#define BAUDRATE 115200` to `#define BAUDRATE 250000`.

Note - make sure you update the TFT if youre using the Bigtreetech TFT.




### 1.2. Enable and configure BLTouch

Follow the next steps to enable and configure BL Touch:

1. Uncomment `//#define BLTOUCH`.
2. Uncomment `//#define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN`.
3. Change `#define MESH_BED_LEVELING` to `#define AUTO_BED_LEVELING_BILINEAR`.
4. Uncomment `//#define Z_SAFE_HOMING`.

If you're using BL Touch mount from original Creality kit with the Micro Swiss `#define NOZZLE_TO_PROBE_OFFSET { 10, 10, 0 }` to `#define NOZZLE_TO_PROBE_OFFSET { -43, -7, -3 }`.

Otherwise you'll have to measure the offsets and set the values accordingly. 



### 1.3. Disable speaker

Disable speaker by commenting `#define SPEAKER`. The firmware will freeze on SKR Mini E3 if this feature is enabled.

# Zigbee Coordinator Firmware for Ebyte E72-2G4M20S1C module (cc2674p10 chip)

## Firmware description

Based on [Koenkk](https://github.com/Koenkk/Z-Stack-firmware/blob/master/coordinator/Z-Stack_3.x.0/firmware.patch) and [JetHome](https://github.com/jethome-ru/zigbee-firmware/tree/master/ti/coordinator/cc2652) patches for Z-Stack_3.x.0.

### Changes from original firmware
- Default TX power: 20dBm.
- Extended LEDs support
- DC/DC and VDDR enabled for high power TX
- HF XOSC CAPARRAY disabled

### TX power ajust

Power can be adjusted in zigbee2mqtt config:

    experimental:
      transmit_power: 5

Available TX power values: -20, -18, -15, -12, -10, -9, -6, -5, -3, 0, 1..20

### LEDs description
- Green (DIO8) turns OFF when the network is running, blinking when joining enable
- Red (DIO7) flashed when APS frame received
- When stick restarted - both double blinking (depends on zigbee-heardsman status and **disable_led** configuration)

Leds can be turned OFF/ON by zigbee2mqtt config (see disable_led).

### Buttons description
- Flash button on DIO15 used for bootloader activation (for firmware update)
- Reset button - you guess what it do.

### Flash tool

For flashing you may need [flash tool](https://github.com/egony/cc2674p10_Ebyte/tree/main/firmware/flash_tools), made especially for cc2674p10.  

### Notes

Strongly recommended to clear the memory after flashing (look about it on [cc2652 flashing page](https://github.com/egony/cc2652p_E72-2G4M20S1E/wiki/Flashing)).

### Sources

Sources you can download [here](https://github.com/egony/egony.github.io/blob/master/Devices/Misc/znp_TI_sdk_8_32_00_07_20260101.zip). Please let me know about any issues.

---

## Changelog

### 2026-02-09

- HF XOSC CAPARRAY disabled (when set to 0xFA RF is inaccurate)

### 2026-01-01

- Initial release.
- SDK 8.32.00.07
- Default TX power: 20dBm.
- Extended LEDs support
- DCDC and VDDR enabled
- HF XOSC CAPARRAY enabled
- SET_CCFG_MODE_CONF_XOSC_CAPARRAY_DELTA set to 0xFA

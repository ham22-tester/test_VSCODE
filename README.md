# TCA9555 ZMK Keyboard

This workspace contains a ZMK shield configuration for a keyboard using a TCA9555 GPIO expander over I2C.

## Wiring summary
- MCU: Aliexpress nRF52840 Nice Nano V2 compatible
- I2C: P1.04 = SCL, P1.06 = SDA
- TCA9555 address: 0x20 (default for A0-A2 tied low)
- TCA9555 pins:
  - P0.02 -> ROW1
  - P0.03 -> ROW2
  - P0.04 -> ROW3
  - P0.05 -> ROW4
  - P0.06 -> ROW5
  - P0.07 -> COL1
  - P0.10 -> COL4
  - P0.11 -> COL3
  - P0.12 -> COL2
- INTA -> MCU P0.11
- Matrix type: column2row with diodes on rows

## Build
Run the following from this folder:

```sh
west init -l config
west update
west build -b nice_nano -- -DSHIELD=tca9555_keyboard
```

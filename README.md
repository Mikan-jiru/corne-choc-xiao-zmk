# Corne Choc XIAO / XIAO nRF52840 Sense — OLED-less ZMK

This configuration is based on the supplied JonMuller/gerbers `corne-choc-xiao/zmk_starter/view`
configuration.

Target controller:
- Seeed Studio XIAO nRF52840 Sense (original/old Sense)

Important:
- OLED/display support has been removed.
- IMU/microphone support is not configured; the Sense is used as an XIAO nRF52840 keyboard controller.
- The original Chipper matrix GPIO assignments are retained.
- The matrix uses P0.02/P0.03, so the current ZMK/Zephyr NFC GPIO devicetree setting is included.
- Default diode direction is `col2row`, matching the supplied `view` firmware.

Build:
- `build.yaml` builds `chipper_left` and `chipper_right` for `xiao_ble//zmk`.
- This repo is intended to be used as a ZMK config repository / GitHub Actions build source.

Before flashing:
1. Confirm the physical diode orientation is the original `col2row` orientation.
2. Build both halves.
3. Flash the left UF2 to the left XIAO Sense and the right UF2 to the right XIAO Sense.
4. If the physical board uses the opposite diode orientation, do not flash this build as-is; the matrix definition must be changed to the corresponding row2col configuration.

The supplied repository also contained older display configurations and prebuilt firmware. Those are intentionally not copied here.

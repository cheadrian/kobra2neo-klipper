# Klipper on Anycubic Kobra 2 Neo

This repository provides a comprehensive guide and necessary resources for getting Klipper to work on the **Anycubic Kobra 2 Neo** 3D printer. It includes firmware, configuration files, profiles, wiring diagrams, and instructions for setting up Klipper and KlipperScreen on a Raspberry Pi.

## Directory Structure

- **CuraProfiles/**  
  Contains Cura profiles for the printer using the original stock firmware.
  
- **OriginalFirmware/**  
  Contains the stock firmware of the Anycubic Kobra 2 Neo, should you need to revert to the default setup.

- **ImagesMbWiring/**  
  Wiring diagrams and images that show how the Raspberry Pi is mounted and connected to the printer.

- **KlipperConfig/**  
  Configuration files for running Klipper on the Anycubic Kobra 2 Neo.

- **KlipperFirmware/**  
  Precompiled Klipper firmware files to be flashed onto the printer's controller board.

- **KlipperScreen/**  
  Instructions and files necessary for installing and setting up KlipperScreen on the Anycubic Kobra 2 Neo / Go screen connected to the Raspberry Pi.

- **OrcaSlicerProfiles/**  
  Slicing profiles for OrcaSlicer that are optimized for use with Klipper on the Anycubic Kobra 2 Neo.

- **RaspberryPiHolder/**  
  3D models for a custom holder mount to securely attach a Raspberry Pi to the printer.

## Getting Started

### 1. Preparing the Raspberry Pi

- Install the Raspberry Pi with a fresh copy of **Raspberry Pi OS**.
- Follow Klipper [documentation for installation via KIAHU](https://www.klipper3d.org/Installation.html#installing-via-kiauh).
- Follow the instructions in the `ImagesMbWiring/` directory to connect the Raspberry Pi to your Kobra 2 Neo printer (only if you want to use UART or KlipperScreen).

### 2. Flashing Klipper Firmware

- Download the appropriate firmware for your printer from the `KlipperFirmware/` directory.
- Flash the firmware to the printer's controller board as described unter `KlipperFirmware/README.md`.

### 3. Configuring Klipper

- Copy the contents of the `KlipperConfig/` directory to the Raspberry Pi, typically into the `~/printer_data/config` folder.
- Install moonraker dependencies. Connect via SSH, go to path `cd ~/` and clone dependencies:
```
git clone https://github.com/fluidd-core/fluidd-config.git
git clone https://github.com/protoloft/klipper_z_calibration.git
./klipper_z_calibration/install.sh
```
- Read comments of the `printer.cfg` and edit the configuration files as necessary based on your printer’s hardware. Default: USB mcu is configured
- Do not forget to do `PROBE_CALIBRATE` and bed mesh leveling.

### 4. Setting Up KlipperScreen (Optional)

- Follow the guide in the `KlipperScreen/` directory to set up KlipperScreen on a touchscreen connected to the Raspberry Pi. This provides an easy-to-use graphical interface for interacting with Klipper.

### 5. Slicer Profiles

- If you're using Cura, you can use the profiles in the `CuraProfiles/` directory for the stock firmware.
- For Klipper, it’s recommended to use OrcaSlicer with the profiles provided in the `OrcaSlicerProfiles/` directory for optimal performance.

### 6. Additional Resources

- Refer to the images in the `ImagesMbWiring/` folder for details on how to physically wire and mount the Raspberry Pi to your printer.
- If you need to revert back to the original firmware, you can find it in the `OriginalFirmware/` directory.

## Notes

- Adjust the configuration files according to your specific setup and hardware modifications.
- Ensure proper cooling and a proper PSU for your Raspberry Pi and other electronics to avoid overheating.
- I use a `LM2596` step-down module connected to the PSU to power the Raspberry Pi. Make sure you use proper gauge wires, otherwise you will experience power drop at load and throttle of the Raspberry Pi.
- Holder for `LM2596` is [here](https://www.thingiverse.com/thing:3324624/files).

## Contributions

Feel free to contribute to this repository by submitting pull requests or opening issues for any updates, corrections, or improvements.

# Kobra 2 Neo OrcaSlicer Profile

This repository contains a backup of the OrcaSlicer configuration for **Kobra 2 Neo** running **Klipper firmware**.

> ⚠️ Not compatible with stock firmware. For stock firmware, use Ultimaker Cura.

---

## Installation

Copy or merge the contents into:

```id="f9p8k1"
C:\Users\<YOUR_PC_USERNAME>\AppData\Roaming\OrcaSlicer\user
```

---

## Notes

* Existing profiles will be merged or overwritten depending on your setup.
* Recommended to back up your current configuration before applying changes.
* Profiles are structured as:

  * `filament/` → material presets
  * `machine/` → printer configuration
  * `process/` → slicing profiles

---

## Included Changes

### 🔧 Filament Profiles

* Added a new filament profile:

  * **PLA - OUTSIDE**

    * Optimized cooling (fan settings) for **low ambient temperature / outdoor printing**
    * Helps maintain print quality when environmental cooling is higher than normal

---

### ⚙️ Process Profiles

* Modified profile:

  * **0.20mm Standard @ Quality**

    * Reduced print speed for **first layers**
    * Purpose:

      * Improve bed adhesion
      * Reduce **warping / edge lifting (bending)**
    * Especially useful in:

      * Low-temperature environments
      * Prints with poor initial adhesion

---

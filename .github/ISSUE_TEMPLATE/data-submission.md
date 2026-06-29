---
name: OBD2 CSV data submission
about: Share a raw OBD2 CSV log to help Rovamate support more cars
title: "[Data]: <make> <model> <year>"
labels: data-submission
---

Thanks for contributing! 

**Before attaching anything: scrub your CSV.** Most OBD apps include your exact GPS coordinates, and sometimes your VIN, by default. Open the file and delete only the `Latitude` / `GPS Latitude`, `Longitude` / `GPS Longitude`, and `VIN` columns. **Keep everything else** — including altitude, bearing, GPS speed, the timestamp, and all PID columns (RPM, speed, temps, fuel, MAF, throttle, load, etc.).

## Vehicle

- **Make / Model / Year:**
- **Powertrain:** (petrol / diesel / hybrid / PHEV / EV)
- **Engine code (optional):**
- **OBD adapter:** (e.g. OBDLink MX+, vLinker MC+, generic ELM327 clone)
- **Which app exported the CSV?:** (Torque Pro / Car Scanner / OBD Fusion / OBDLink / other)

> Knowing the app matters — each one names columns, formats timestamps, and scales values differently.

## Attach your scrubbed CSV

Drag and drop your `.csv` file anywhere in this box to attach it.

## Notes (optional)

Anything unusual — manufacturer-specific PIDs, missing values, weird units, etc.

## Before submitting

- [ ] I removed the Latitude / Longitude (GPS coordinate) columns
- [ ] I removed the VIN column
- [ ] This data is from a vehicle I own
- [ ] I release this data under CC0 1.0 (public domain)

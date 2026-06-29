# obd-samples

Community-contributed raw OBD2 logs to help **Rovamate** *(under development — apps not public yet)* correctly parse real-world vehicle data across as many makes, models, and adapters as possible.

> **TL;DR** — Drive for a few minutes, export the CSV from your OBD app, **delete the latitude/longitude and VIN columns**, and attach it to a [new data submission](https://github.com/rovamate/obd-samples/issues/new?template=data-submission.md). Thank you!

---

## Why this repo exists

Rovamate reads live OBD2 data for trip logging, efficiency tracking, and diagnostics. The problem: OBD2 is only *loosely* standardized. Supported PIDs, units, value scaling, column names, and timestamp formats all vary between manufacturers and between the apps people use to log data.

We only have access to a few **Toyotas** from EU market to test against — one petrol, one diesel, and two hybrids. That's reasonable coverage of Toyota powertrains but **zero coverage of any other manufacturer**. Logs from non-Toyota cars (and any unusual Toyotas) are the single most useful thing you can contribute since they turn directly into "Rovamate works correctly on your car too."

This repo collects those samples. It's purely a place to gather and document test data.

---

## What's useful

Raw CSV logs exported from a standard OBD logging app:

- **Torque Pro / Torque Lite**
- **Car Scanner ELM OBD2**
- **OBD Fusion**
- **OBDLink app**
- …or any app that exports a CSV with column headers

A good sample is a **normal drive of a few minutes** that includes both idle and driving, so values have some range (RPM, speed, temps, fuel, load all moving). One clean drive is more useful than a huge messy dump.

---

## ⚠️ Privacy — please scrub before sending

**Most OBD logging apps include your exact GPS coordinates in the CSV by default**, and some include your VIN. We do **not** want those, and you shouldn't share them.

**Before submitting, open the CSV and delete only these columns:**

- `Latitude` / `GPS Latitude`
- `Longitude` / `GPS Longitude`
- `VIN`

**Keep everything else** — including altitude, bearing, GPS speed, the timestamp, and all the PID columns (RPM, speed, coolant/intake temp, fuel level, MAF, throttle position, engine load, etc.). These are used to improve Rovamate; only the exact lat/long coordinates and VIN need to go.

> If you accidentally upload a file with location data, **comment on your issue/PR and it will be deleted** — or delete it yourself.

---

## How to contribute

**Preferred:** [open a data submission](https://github.com/rovamate/obd-samples/issues/new?template=data-submission.md) and attach your CSV. This keeps everything public and auditable.

**Or:** open a pull request adding your file to `/data` following the naming convention below.

Either way, please include:

| Field | Example |
|---|---|
| **Make / Model / Year** | Toyota Corolla 2018 |
| **Engine** | 1.8L petrol (2ZR-FAE) |
| **OBD adapter** | vLinker MC+ / OBDLink MX+ / generic ELM327 clone |
| **Logging app** | Car Scanner ELM OBD2 |
| **Notes** (optional) | hybrid, manufacturer-specific PIDs, anything odd |

**Why "logging app" is required:** each app names columns, formats timestamps, and scales values differently. Knowing the source is what makes a CSV parseable — an unlabeled file is genuinely hard to use.

### File naming (for PRs)

```
data/<make>_<model>_<year>_<app>.csv
e.g. data/toyota_corolla_2018_carscanner.csv
```

---

## Data license

By submitting a sample, you release it under [**CC0 1.0**](https://creativecommons.org/publicdomain/zero/1.0/) (public domain). Only submit data from a vehicle you own, with location/identity columns removed as described above.

---

## Questions

Open an issue with the `question` label. Contributions of any size genuinely help — thank you for making Rovamate work on more cars.

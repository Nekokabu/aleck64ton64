# Aleck64 → N64 Cartridge Conversion Adapter r1.1

An adapter board that allows Aleck64 (SETA arcade system) cartridges to be used in a Nintendo 64 console.
Operation verified (tested on actual hardware with revision r1).

![top](preview/top.png)

## PCBWay Ordering Specifications
| Item | Setting |
|---|---|
| Upload | `Aleck64_to_N64_r1.1_gerber.zip` |
| Layer Count | 2 |
| Board Size | Approx. 136 × 64 mm |
| **Board Thickness** | **1.2 mm** (Required for N64 slot; 1.6 mm will not fit) |
| **Gold Fingers** | **Yes** (N64-side edge) + **45° Beveling** |
| Surface Finish | ENIG recommended (HASL also acceptable) |
| Min. Trace/Spacing | 0.2 / 0.2 mm; Min. Hole 0.3 mm |

## Components
- J2: **TE Connectivity 5145169-4** (PCI 64-bit / 5V key / 184-pin). Part numbers 5145169-8 and 1-5145169-2 share the same footprint.

## Assembly
1. **Cut off the divider (rib) on the 64-bit section of the connector.** Cut at the location marked "CUT RIB" (indicated by an 'X') on the silkscreen. Leave the 5V key (marked "KEY" on the silkscreen) intact.
2. Insert the connector from the silkscreen side (top) and solder it. The hole layout is asymmetrical, so it cannot be inserted backwards. 3. Insert the Aleck64 cartridge with the **label side (pins 81–160) facing up**. It will only fit in the orientation where the key aligns.

## Usage
- Insert with the connector side facing the **rear of the N64 console** (the silkscreen text "N64 FRONT SIDE" should face the front of the console).
- The cartridge extends horizontally from the rear of the console; supporting it is recommended due to its weight.

## Notes
- The total connector length of 128mm is longer than the genuine BURNDY part (approx. 110mm), which may cause interference with the bottom edge of the cartridge shell.
- The PCI connector is designed for 1.57mm thick PCBs; with a 1.2mm board, the retention tabs may not grip effectively (the connection is secured via soldering).
- Aleck64 pins 54, 55, 134, and 135 (all NC) are left unconnected as they align with the position of the removed rib.
- Some games may not function correctly on the N64.

## Verification
- KiCad DRC: 0 errors / 0 unconnected nets.
- Independent continuity re-check via rendered Gerber images: All 29 nets match expectations.
- Drill coordinates cross-referenced with TE drawings: Mounting hole spacing 64.77 / 59.69 mm; 4 rows (±1.27 / ±3.81 mm); 184 holes.

## Origins and Credits
- Pin mapping (netlist) was derived by analyzing continuity from the **N64 → Aleck64 conversion adapter r001** Gerber files published on arcade-projects.com and cross-referencing them with the pinout table (Seta 3D Rom PCB-2A) shared in the same thread. Gratitude to the original authors and publishers of the source data. - Thread: https://www.arcade-projects.com/threads/n64-cartridge-adapter-for-seta-aleck-64.20932/
- In addition to the r001 wiring, the following Aleck64-to-N64 connections were made: 74→8 (/WR), 77→44, and 156→45 (NMI).
- The N64 card edge dimensions were verified against the public data for **SummerCart64** (by Mateusz Faderewski; hardware licensed under CERN-OHL-S v2). No files were directly reused. 
- https://github.com/Polprzewodnikowy/SummerCart64
- Refer to the ConsoleMods Wiki for the N64 connector pinout. https://consolemods.org/wiki/N64:Connector_Pinouts
- The socket footprint is based on dimensions from TE Connectivity drawing ENG_CD_5145169 (the drawing itself is not included).

## License
This repository (PCB data, scripts, and documentation) is released under the **CC BY-SA 4.0** license. See `LICENSE.md` for details.

This project is not affiliated with or endorsed by Nintendo, SETA, or TE Connectivity. Product and company names are trademarks of their respective owners.

## No Warranty
This data is provided "as-is." The author assumes no liability for any damages arising from its use, including damage to or malfunctions of the PCB, cartridges, or the console itself. Use at your own risk.

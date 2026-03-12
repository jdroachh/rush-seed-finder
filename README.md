# Rush Seed Finder
 
A browser-based tool for Neon White speedrunners. Search for seeds that produce favourable level orders, parse any seed into its full level sequence, and reorder or standardize LiveSplit splits files across all four rush types.
 
---
 
## Supported Rushes
 
| Rush | Levels |
|---|---|
| White / Mikey | 96 |
| Violet | 8 |
| Red | 8 |
| Yellow | 8 |
 
---
 
## Tabs
 
### Find Seed
 
Search up to 2,147,483,647 seeds to find ones where specific levels appear early in the run.
 
#### Rush Name
Select which rush you are searching for. Changing the rush clears all level inputs and resets optional toggles automatically.
 
#### Search Depth
How many positions from the start of the run to search within. For example, a Search Depth of 10 means all Desired Starting Levels must appear within the first 10 positions. Defaults to the total number of levels for the selected rush. Automatically adjusts to fit at least as many positions as you have Desired Starting Levels.
 
#### Result Mode
- **First Match** — stops as soon as one qualifying seed is found.
- **Find Multiple** — continues searching until N seeds are found. Set N with the number input (default 5, max 100). Results appear in an expandable list as they are found, with the first result auto-expanded.
 
#### Order Matters? *(8-level rushes only)*
- **No — Any Order** — all Desired Starting Levels just need to appear somewhere within Search Depth, in any order.
- **Yes — Exact Order** — levels must appear in the exact sequence you enter them, starting from position 1. Search Depth is hidden in this mode.
 
#### Desired Starting Levels
A comma-separated list of levels you want to appear early. Accepts full names, partial names, or aliases (see [Level Name Formats](#level-name-formats) below).
 
#### Force First Level *(White / Mikey only)*
When enabled, pin a specific level to position 1. The Desired Starting Levels must still all appear within Search Depth. Throws an error if the forced level is also listed in Desired Starting Levels or Excluded Levels.
 
#### Excluded Levels
When enabled, exposes two fields:
- **Exclusion Window** — how many positions from the start must be free of the excluded levels.
- **Excluded Levels** — comma-separated list of levels that must not appear within the Exclusion Window.
 
Excluded levels are highlighted in **amber** wherever they appear in the results. Throws an error if any excluded level also appears in Desired Starting Levels or is the same as the Force First Level.
 
#### Results
Each found seed is shown in an expandable accordion. Click a seed entry to expand its full level sequence. Desired levels are highlighted in **green**, excluded levels in **amber**. A **COPY** button on each entry copies the seed number to the clipboard.
 
---
 
### Seed Parser
 
Enter a rush and a seed number to generate the full level order for that seed. Useful for quickly checking what a known seed plays like without running a search.
 
---
 
### Splits Updater
 
Takes Gold Splits and/or Segment Splits in **standard level order** (alphabetical / in-game index order) and reorders them into the order a specific seed will play them. Output is ready to paste into LiveSplit.
 
#### Inputs
- **Rush Name** — select the rush your splits are for.
- **Gold Splits** — best individual level times, one per line, in standard level order.
- **Segment Splits** — cumulative or per-segment run times, one per line, in standard level order.
- **Seed Number** — the seed you want to generate splits for.
 
At least one of Gold or Segment Splits must be filled in. Both can be provided at once.
 
#### Saved Splits
Use **SAVE SPLITS**, **LOAD SAVED**, and **CLEAR SAVED** to persist your pasted splits in your browser's local storage so you don't need to re-paste them each session. Saved splits are stored per-browser and never shared.
 
#### Output
Three output boxes appear after generation:
- **Gold Splits** — reordered gold times in seed play order.
- **Segment Splits** — reordered segment times in seed play order.
- **Level Order** — the level names in the order the seed plays them.
 
Each output box has a **COPY** button.
 
---
 
### Standardize Splits
 
The inverse of Splits Updater. Takes splits recorded in a specific **seed's play order** and converts them back to **standard level order**. Useful for updating your gold splits file after a run on a particular seed.
 
#### Inputs
- **Rush Name** — select the rush.
- **Gold Splits** — times in the order the seed played levels.
- **Segment Splits** — times in the order the seed played levels.
- **Seed Number** — the seed the run was played on.
 
#### Output
Gold and Segment Splits reordered back into standard level index order, ready to merge back into your splits file. Each has a **COPY** button.
 
---
 
## Level Name Formats
 
All level name inputs across every tab accept the following formats, case-insensitive:
 
- **Full name** — `The Third Temple`, `Absolution`, `Elevate Traversal I`
- **Partial name** — any substring that matches exactly one level, e.g. `clocktower`, `absol`, `breakthrough`
- **Alias** — shorthand codes listed below
 
If a partial name matches more than one level, an error is shown listing all matches.
 
### Aliases
 
| Alias | Level |
|---|---|
| `ttt` | The Third Temple |
| `ct`, `clocktower` | The Clocktower |
| `glort` | Glass Port |
| `ase` | All Seeing Eye |
| `rsi`, `rs1` | Resident Saw I |
| `rsii`, `rs2` | Resident Saw II |
| `eti`, `et1` | Elevate Traversal I |
| `etii`, `et2` | Elevate Traversal II |
| `boof trav` | Book of Life Traversal |
| `sfp` | Sunset Flip Powerbomb |
| `bm` | Balloon Mountain |
| `cg` | Climbing Gym |
| `fish sup`, `fish soup` | Fisherman Suplex |
 
---
 
## Standard Level Orders
 
### White / Mikey (96 levels)
Movement, Pummel, Gunner, Cascade, Elevate, Bounce, Purify, Climb, Fasttrack, Glass Port, Take Flight, Godspeed, Dasher, Thrasher, Outstretched, Smackdown, Catwalk, Fastlane, Distinguish, Dancer, Guardian, Stomp, Jumper, Dash Tower, Descent, Driller, Canals, Sprint, Mountain, Superkinetic, Arrival, Forgotten City, The Clocktower, Fireball, Ringer, Cleaner, Warehouse, Boom, Streets, Steps, Demolition, Arcs, Apartment, Hanging Gardens, Tangled, Waterworks, Killswitch, Falling, Shocker, Bouquet, Prepare, Triptrack, Race, Bubble, Shield, Overlook, Pop, Minefield, Mimic, Trigger, Greenhouse, Sweep, Fuse, Heaven's Edge, Zipline, Swing, Chute, Crash, Ascent, Straightaway, Firecracker, Streak, Mirror, Escalation, Bolt, Godstreak, Plunge, Mayhem, Barrage, Estate, Trapwire, Ricochet, Fortress, Holy Ground, The Third Temple, Spree, Breakthrough, Glide, Closer, Hike, Switch, Access, Congregation, Sequence, Marathon, Absolution
 
### Violet (8 levels)
Doghouse, Choker, Chain, Hellavator, Razor, All Seeing Eye, Resident Saw I, Resident Saw II
 
### Red (8 levels)
Elevate Traversal I, Elevate Traversal II, Purify Traversal, Godspeed Traversal, Stomp Traversal, Fireball Traversal, Dominion Traversal, Book of Life Traversal
 
### Yellow (8 levels)
Sunset Flip Powerbomb, Balloon Mountain, Climbing Gym, Fisherman Suplex, STF, Arena, Attitude Adjustment, Rocket
 
---
 
## Browser Compatibility
 
The tool runs entirely in the browser with no server required. All features work in any modern browser. The saved splits feature uses browser local storage and is private to your device.
 
> **Note for v3.0+ test builds:** The GPU-accelerated search path requires WebGPU support, currently available in Chrome 113+ and Edge 113+. Firefox and Safari will automatically fall back to the standard CPU search with no loss of functionality.
 

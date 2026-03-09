# rush-seed-finder
Neon White Rush seed finder for Heaven / Hell rushes (all colors). Allows you to find a seed given specific parameters, parse a seed, get splits for a specific seed and standardize splits back to standard rush order.
This project is entirely VIBE coded utilizing Claude code. The tool was adapted from Grange Nagy's C# / Python tool in order to implement a GUI for easier user interaction.

Tool Overview:
Find Seed - Determine your desired rush (from White/Mikey, Red, Yellow, or Violet). Find seeds with desired levels (denoted in the "desired starting levels" text box) within the first X number of stages (X = search depth). 
For White/Mikey rush, you can also pin a level to the first slot (so the tool will only find seeds with the pinned level in position 1). By checking the exclude levels from opening postion setting, you can also exclude levels from the first Y number of stages (Y = exclusion window)
Enable the find multiple setting to find multiple seeds given your search query.

Seed Parser - Input a seed # and view the seed's level order.

Splits Updater - Copy and paste your gold splits and segment splits from your favorite splits software into the appropriate fields, enter the seed # you'd like to re-order your splits to in the "seed number" field. Click generate splits to re-order the split times. Copy and paste the resulting list (gold splits, segment splits, level names) into the appropriate fields of your splits software.

Standardize Splits - Copy and paste your gold splits and segment splits from a specific seed number back into "standard order" (Movement first, Abso last/Doghouse first, RSII last, etc)

----------
Tab 1: Find Seed
----------

Search through all possible seeds (1 to 2,147,483,647) to find one whose level order matches your desired starting levels.

Inputs
-----
Rush Name: 
White / Mikey — 96-level rush, Violet/Red/Yellow — 8-level rush
Search Depth: 
How many levels deep into the sequence to look for your desired levels. For example, a depth of 10 means your desired levels must all appear somewhere within the first 10 positions of the run.
Tip: for faster load times, set depth higher than the number of levels you are searching for. Searching for 3 levels with a depth of 3 requires all 3 to be the very first levels — a depth of 10 or 15 gives much more flexibility.
Order Matters (Violet/Red/Yellow rushes only): 
No — Any Order: your desired levels just need to appear anywhere within the first N positions (where N is the Search Depth), in any order relative to each other.
Yes — Exact Order: your desired levels will appear in the exact order you specify in your search.
Desired Starting Levels: 
Comma-separated list of the levels you want to appear at the start of your run.
Accepts full level names (case insensitive), shorthand aliases, or partial names.
Force First Level: 
For White/Mikey rush, you can also pin a level to the first slot so the tool will only find seeds with the pinned level in position 1.
Exluded Levels: 
Levels you do want to see in the first [exclusion window] number of stages.
Exclusion Window:
How many levels appear in the sequence before the excluded levels appear. This is helpful if you want stages you're more comfortable running to appear towards the end of the rush.

Level Name Formats
---
The following input formats are all accepted:
Full name: 
The Third Temple, Absolution, The Clocktower
Shorthand aliases: 
TTT  =  The Third Temple
CT  =  The Clocktower
Glort  =  Glass Port
Partial names (must match exactly one level): 
Rico  =  Ricochet
Trig  =  Trigger
Glass  =  Glass Port
Green  =  Greenhouse
If a partial name matches more than one level, the tool will show an error listing all matches so you can be more specific.

Running a Search
---
Click FIND SEED to begin. The progress bar shows the percentage of seeds checked, current speed in seeds per second, and an estimated time remaining. Click STOP SEARCH at any time to cancel.

Results
---
When a match is found, the result section shows:
Found Seed: the seed number to enter in-game (plain integer, no commas).
Level Sequence: the full level order that seed produces, listed top to bottom. Your target levels are highlighted in green.

----------
Tab 2: Seed Parser
----------
Given a known seed number, generates and displays the complete level order that seed produces. Useful for previewing what a specific seed looks like before committing to it in-game.

Inputs
---
Rush Name: White / Mikey (96 levels).
Seed: any integer between 1 and 2,147,483,647.

Results
---
Click PARSE SEED to generate the full 96-level sequence for that seed, listed top to bottom.

----------
Tab 3: Splits Updater
----------
Takes your splits (stored in standard level order) and reorders them to match the level order of a specific seed. Use this to prepare your splits file before starting a run on a new seed.

Standard Order vs. Seed Order
---
Standard order is the fixed sequence of all 96 levels as listed in the game's level registry — Movement is always first, Absolution is always last. Your splits tool typically stores personal bests in this fixed order.
Seed order is the shuffled sequence that a specific seed produces — for example, seed 58685 might play The Clocktower first, then Absolution, then The Third Temple, and so on.
Splits Updater converts: Standard Order → Seed Order.

Inputs
---
Gold Splits: your best individual level times from your favorite splits software, one per line, in standard level order (Movement first, Absolution last).
Segment Splits: your cumulative or per-segment run times, one per line, in standard level order.
Seed Number: the seed you are about to run.
Paste times in standard level order. The first time pasted corresponds to Movement, the second to Pummel, and so on through all 96 levels.

Time Format
---
Times are accepted in the following format:
Seconds.Milliseconds       e.g.  17.993  =  17 seconds, 993ms
Minutes:Seconds.Milliseconds   e.g.  1:20.730  =  1 min, 20 sec, 730ms

Save / Load / Clear
---
Your splits can be saved to your browser's local storage so you do not need to paste them again each session:
SAVE SPLITS: saves the current Gold and Segment inputs to your browser cache.
LOAD SAVED: restores previously saved splits into the input fields.
CLEAR SAVED: removes the saved splits from your browser cache.
Saved splits persist between sessions in the same browser. They are stored locally on your device and are never sent anywhere.

Results
---
Clicking GENERATE SPLITS produces up to three copyable output textareas:
Gold Splits: your gold times reordered into the seed's level sequence.
Segment Splits: your segment times reordered into the seed's level sequence.
Level Order: the full list of level names in seed order, one per line.
Each section has a COPY button. Click it to copy the contents directly to your clipboard, ready to paste into your splits tool.

----------
Tab 4: Standardize Splits
----------
The inverse of Splits Updater. Takes splits recorded during a run (which are in seed order) and converts them back into standard level order for storage in your splits tool.
Standardize Splits converts: Seed Order → Standard Order.

When to Use This
---
After completing a run on a specific seed, your splits tool will have recorded times in the order the seed played levels. Before you can update your personal bests or use those times with a different seed, they need to be returned to standard order. Paste them here along with the seed you ran, and the tool will rearrange them back into standard order.

Inputs
---
Gold Splits: your times from the run, one per line, in the order the seed played levels (seed order).
Segment Splits: your segment times, one per line, in seed order.
Seed Number: the seed you ran.
Paste times in seed order — the order the seed played the levels during your run, not standard level order.

Save / Load / Clear
---
Standardize Splits has its own independent save/load/clear cache, separate from Splits Updater, so the two sets of splits do not overwrite each other.

Results
---
Clicking STANDARDIZE SPLITS produces two copyable output textareas:
Gold Splits: your times rearranged into standard level order.
Segment Splits: your segment times rearranged into standard level order.
Copy the outputs and paste them into your splits tool to update your personal bests.



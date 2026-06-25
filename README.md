# Shop Calculators
Mobile-first PWA for machine shop calculations.
Works offline and installs to your home screen.

## Calculators
**Tapered Hole Offset**
Z-axis move to hit a target diameter on a tapered bore.
Inputs: current diameter, target diameter, taper angle per side.
Outputs: Z move, angle, diameter change.

**Drill Tip Offset**
Depth offset introduced by a drill tip.
Inputs: drill diameter and tip angle.
Output: tip depth offset.

**X/Y Location**
Edge-finder position to center on a hole.
Inputs: hole diameter, X and Y position.
Outputs: corrected X and Y positions with full equation display.

**RPM / Feed Rate**
Spindle speed from surface footage and cutter diameter.
Optional second step: feed rate from chip load, flutes, and RPM.

## Features
**Pinned List**
Pin any result for quick reference. Reorder by press-and-hold.
Swipe left to delete. Edit any entry in place, no duplicates.

**Saved Entries**
Swipe right to multi-select, label, and save as a named snapshot.
Recall via search bar dropdown. Export and import as JSON.

**History**
Every calculation logged per module.
Accessible from the top-right button on each calculator screen.

**Formula Reference**
Tap ℹ on the home screen for the formula, industry reference,
and function name for every calculator.

**Offline / PWA**
Installs to home screen on iOS and Android.
Fully offline after first load.

## Math Integrity
RPM: `(SFM × 12) / (π × D)` via `Math.PI` — not the 3.82 approximation.
Taper: `|(Target Ø − Current Ø) / 2| / tan(angle°)` — degrees converted internally.
Feed: `Chip Load × Flutes × RPM`
XY: `Position − (Hole Diameter / 2)`
RPM rounds to nearest integer. Feed to 1 decimal (IPM).
Verified against Machinery's Handbook — 11/11 tests pass.

## Installation
iOS: Safari → Share → Add to Home Screen
Android: Chrome → Menu → Add to Home Screen

## Development
Single file PWA. All logic in `index.html`.
Supported by `manifest.json`, `sw.js`, and `icons/`.
Serve locally: `npx serve .`
Bump `CACHE_NAME` in `sw.js` on every release.
Keep `STORE_KEY` stable to preserve user data.

## Version History
**v1.1** — Saved entries, math overhaul, Feed results screen,
progress bars, UI polish and bug fixes.
**v1.0** — Four calculators, pinned list, history, swipe gestures, PWA scaffold.

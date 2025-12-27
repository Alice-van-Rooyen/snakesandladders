# Convalescent Board — Tuning & Appearance Guide

This document explains how to adjust the *feel*, *timing*, and *readability* of the board without changing core mechanics.  
All values below are safe to edit and designed for iteration.

---

## 1. Text Density & Readability

Text layout is controlled inside the `drawRichText()` function.

### Line spacing

const lineH = Math.round(fontSize * 1.12);
const gapH  = Math.round(lineH * 0.22);
Adjustments:

Effect	Suggested Values
Tighter text	lineH = 1.05, gapH = 0.15
Balanced (default)	1.12 / 0.22
Airy, spacious	1.25 / 0.35


2. Delay Before Square Text Appears
When you land on a square, the text appears after a short pause.

const SUB_DELAY_MS = 180;
Suggested values:

Feel	Value
Immediate	80
Natural	150–200
Dramatic	300–450


3. Fog / Obscurity Strength
Controls how obscured unread squares appear.

Located in fogAlphaForSquare():

const near = 0.55;
const far  = 0.92;
Tuning guide:

Effect	near	far
Light fog	0.45	0.80
Default	0.55	0.92
Heavy fog	0.65	0.97


4. Substitution Flash (When Text Changes)
When a square replaces its text, a brief visual cue appears.

const SUB_CUE_MS = 260;
Suggested ranges:

Feel	Value
Subtle	180
Balanced	260
Pronounced	350


5. Token Placement
Controls how far the player token sits from the square corner.

let TOKEN_PAD_FRAC = 0.12;
Recommended range: 0.10 – 0.16

Lower values move the token closer to the corner.


6. String / Tether Behaviour
Visual tether between player and origin square.

const STRING_COLOR = "rgba(184, 38, 60, 0.55)";
Adjust alpha for subtlety or intensity.

Additional motion parameters live near the drawTetherString() function:

stringJolt
internal wobble multipliers

These are safe to tune experimentally.


7. Timing & Motion Controls
Variable	Effect
SPIN_DURATION_MS	Length of spinner animation
RECALL_WINDOW_MS	Time allowed to return to origin
CHEAT_FLASH_MS	Duration of cheat flash


8. Design Philosophy
This system is tuned for:

Slight friction rather than speed
Visibility without certainty
Text that resists being skimmed

If something feels too easy, increase delay or fog.
If something feels unreadable, reduce spacing or opacity.

The goal is attentive discomfort, not difficulty.


9. Editing Safety
You can safely modify:

numeric values
color values
timing constants

Avoid renaming functions or removing blocks unless you intend to change behaviour.

End of document.

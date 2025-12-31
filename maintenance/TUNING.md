Convalescent Board — Tuning & Adjustment Guide

This document explains how to fine-tune feel, pacing, and readability without changing game logic.
All values listed here are safe to adjust and will not break behaviour.

1. Text Density & Readability

Text layout is controlled inside the drawRichText() function.

const lineH = Math.round(fontSize * 1.12);
const gapH  = Math.round(lineH * 0.22);

Adjusting readability
Effect	Suggested Values
Tighter / denser	1.05 / 0.15
Balanced (default)	1.12 / 0.22
Airy / spacious	1.25 / 0.35

Use tighter spacing when text density is high; looser spacing when you want calm or emphasis.

2. Delay Before Text Appears (Icon → Text)

When a square has an icon, the text appears after a short delay.

const SUB_DELAY_MS = 180;

Suggested ranges
Feel	Value
Immediate	80
Natural / soft	150–200
Dramatic pause	300–450

This controls perceived attentiveness — longer delays feel more intentional.

3. Visual Obscurity (“Fog” / Cipher Effect)

Controls how obscured unread squares appear.

const near = 0.55;
const far  = 0.92;

Effect	near	far
Light veil	0.45	0.80
Default	0.55	0.92
Heavy concealment	0.65	0.97

Lower = clearer, higher = more obscured.

4. Substitution Flash (Text Swap Cue)

When a square replaces its text (e.g. popup events), a brief visual cue occurs.

const SUB_CUE_MS = 260;

Feel	Value
Subtle	180
Balanced	260
Emphatic	350
5. Token Positioning

Controls how far the player token sits from the square corner.

let TOKEN_PAD_FRAC = 0.12;


Typical range: 0.10 – 0.16

Smaller = closer to the corner
Larger = more “floating” feel

6. Tether / String Behaviour

Visual connection between the token and square 1.

Key tunables:

STRING_COLOR — opacity & tone

stringJolt — how reactive the string is to movement

internal wobble values in drawTetherString()

These affect feel, not mechanics. Safe to experiment.

7. Timing Controls Summary
Variable	Purpose
SPIN_DURATION_MS	Length of spinner animation
RECALL_WINDOW_MS	Time allowed to recall after hospital pull
CHEAT_FLASH_MS	Flash duration when cheat mode toggles
8. Design Philosophy (Intentional Constraints)

This system is tuned for:

Slowness over efficiency

Legibility over density

Partial information over certainty

If something feels too easy, increase delay or obscurity.
If it feels frustrating, reduce opacity or timing—not structure.

9. Safe Editing Rules

You can safely change:

Numeric constants

Timing values

Colour values

Text strings

Avoid changing:

Function names

Control flow

Event wiring

Unless you want to alter behaviour.
Avoid renaming functions or removing blocks unless you intend to change behaviour.

End of document.

Convalescent Board — Tuning & Adjustment Guide
This document explains how to fine-tune feel, timing, and readability without altering core mechanics.

1. Text Density & Readability
Text layout is controlled inside the drawRichText() function.
jsconst lineH = Math.round(fontSize * 1.12);
const gapH  = Math.round(lineH * 0.22);
EffectValuesTighter1.05 / 0.15Balanced1.12 / 0.22Airy1.25 / 0.35

2. Delay Before Text Appears
When landing on a square, text appears after a short pause.
jsconst SUB_DELAY_MS = 180;
FeelValueImmediate80Natural150–200Dramatic300–450

3. Obscurity / Fog Control
Controls how unread squares appear.
jsconst near = 0.55;
const far  = 0.92;
EffectnearfarLight0.450.80Default0.550.92Heavy0.650.97

4. Substitution Flash
Controls the visual flash when a square's text changes.
jsconst SUB_CUE_MS = 260;
FeelValueSubtle180Balanced260Strong350

5. Token Position
Controls how far the token sits from the square corner.
jslet TOKEN_PAD_FRAC = 0.12;
Recommended range: 0.10 – 0.16

6. Tether Behaviour
Controls the visual connection between the player and the origin square.

STRING_COLOR
spring strength / wobble parameters


7. Timing Controls
VariablePurposeSPIN_DURATION_MSSpinner animation durationRECALL_WINDOW_MSTime allowed to recallCHEAT_FLASH_MSCheat mode flash length

8. Design Intent
This system is tuned for:

Slowness over speed
Attention over efficiency
Legibility over density


9. Safe Editing Guidelines
You may safely modify:

Numeric values
Colour values
Text strings

Avoid modifying:

Control flow
State transitions
Event wiring


End of document

# Convalescent Board — Tuning & Adjustment Guide

**Current architecture version**

This document describes the intentional tuning points available in the game. These affect feel, pace, and legibility — not core mechanics.

## 1. Text Readability & Density

Text rendering is handled by the rich-text layout system inside `drawRichText()`.

**Key controls:**
```javascript
const lineH = fontSize * 1.10;
const gapH  = lineH * 0.18;
```

**Effects:**

| Change | Result |
|--------|--------|
| Increase `lineH` | More vertical breathing room |
| Decrease `lineH` | Denser, more compressed text |
| Increase `gapH` | More paragraph separation |
| Decrease `gapH` | More compact reading block |

This affects all square text, magnifier text, and pop-ups.

## 2. Text Reveal Timing (Substitution Delay)

When a square contains hidden text, it reveals after a short pause.
```javascript
const SUB_DELAY_MS = 320;
```

**Suggested Ranges:**

| Feel | Value |
|------|-------|
| Snappy | 150–200 |
| Default | ~320 |
| Suspenseful | 400–500 |

This only affects substitution squares (not windows or spinners).

## 3. Spinner Reveal Timing

The delay between landing on a spinner and the snake icon appearing:
```javascript
const SPINNER_REVEAL_MS = 340;
```

**Important behavioural note (constraint):**
During this reveal delay, movement input is intentionally blocked so you cannot “step over” the spinner square. If you change `SPINNER_REVEAL_MS`, you are also changing how long the player is *held* before the spinner becomes visible.

**Guidance:**

| Feel | Value |
|------|-------|
| Immediate | 200 |
| Tactile / deliberate | 300–400 |
| Dramatic | 500+ |

This controls anticipation, not movement speed.

## 4. Token Positioning

Token placement within each square:
```javascript
let TOKEN_PAD_FRAC = 0.12;
```

Higher values push the token inward; lower values let it hug the corner.

**Safe range:** `0.10 – 0.16`

## 5. Tether / String Behaviour

The tether “string” between home and token is rendered as **static geometry**.

**Key controls:**
```javascript
const STRING_COLOR = "rgba(184, 38, 60, 0.55)";
```

**What you can tune safely:**
- Colour / alpha (`STRING_COLOR`)
- Stroke width (where the canvas line width is set)

- The string redraws only when the token moves, the board resizes, or another state change invalidates the canvas.

## 6. Spinner & Recall Timing

| Control | Meaning |
|---------|---------|
| `SPIN_DURATION_MS` | Duration of spinner animation |
| `RECALL_WINDOW_MS` | Time window to recall after hospital pull |

Longer values = more deliberation, less twitch.

## 7. Visibility & Revelation Model

Visibility is governed by:
- Player position
- `AHEAD` and `TRAIL_BEHIND` constants
- Cheat mode override

There is no fog layer anymore — visibility is purely logical.

## 8. Safe to Change / Do Not Touch

### Safe to adjust
- Numeric timing values
- Font sizes
- Padding and spacing
- Colour constants
- Text content

### Avoid unless refactoring intentionally
- Event ordering
- State transitions (`spinActive`, `windowArmed`, etc.)
- Movement logic (`recordMove`, `attemptStep`)
- Visibility rules

## 9. Engineering note (not tuning): render-on-demand

The game now uses render-on-demand for battery/perf hygiene. If you add new state transitions, ensure you explicitly trigger a redraw (via the project’s `invalidate()` mechanism) whenever state changes.

## 10. Design Intent (Anchor)

This system is tuned to feel:
- Deliberate, not fast
- Legible, not flashy
- Uncertain, not random
- Progressive, but never frictionless

Every delay, pause, and constraint exists to create thought, not friction.

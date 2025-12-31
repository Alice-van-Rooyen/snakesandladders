# Convalescent Board — Tuning & Adjustment Guide

This document explains how to fine-tune *feel*, *timing*, and *readability* without altering core mechanics.

---

## 1. Text Density & Readability

Text layout is controlled inside the `drawRichText()` function.
```js
const lineH = Math.round(fontSize * 1.12);
const gapH  = Math.round(lineH * 0.22);
```

| Effect   | Values      |
| -------- | ----------- |
| Tighter  | 1.05 / 0.15 |
| Balanced | 1.12 / 0.22 |
| Airy     | 1.25 / 0.35 |

---

## 2. Delay Before Text Appears

When landing on a square, text appears after a short pause.
```js
const SUB_DELAY_MS = 180;
```

| Feel      | Value   |
| --------- | ------- |
| Immediate | 80      |
| Natural   | 150–200 |
| Dramatic  | 300–450 |

---

## 3. Obscurity / Fog Control

Controls how unread squares appear.
```js
const near = 0.55;
const far  = 0.92;
```

| Effect  | near | far  |
| ------- | ---- | ---- |
| Light   | 0.45 | 0.80 |
| Default | 0.55 | 0.92 |
| Heavy   | 0.65 | 0.97 |

---

## 4. Substitution Flash

Controls the visual flash when a square's text changes.
```js
const SUB_CUE_MS = 260;
```

| Feel     | Value |
| -------- | ----- |
| Subtle   | 180   |
| Balanced | 260   |
| Strong   | 350   |

---

## 5. Token Position

Controls how far the token sits from the square corner.
```js
let TOKEN_PAD_FRAC = 0.12;
```

Recommended range: 0.10 – 0.16

---

## 6. Tether Behaviour

Controls the visual connection between the player and the origin square.

- `STRING_COLOR`
- spring strength / wobble parameters

---

## 7. Timing Controls

| Variable           | Purpose                    |
| ------------------ | -------------------------- |
| `SPIN_DURATION_MS` | Spinner animation duration |
| `RECALL_WINDOW_MS` | Time allowed to recall     |
| `CHEAT_FLASH_MS`   | Cheat mode flash length    |

---

## 8. Design Intent

This system is tuned for:

- Slowness over speed
- Attention over efficiency
- Legibility over density

---

## 9. Safe Editing Guidelines

**You may safely modify:**
- Numeric values
- Colour values
- Text strings

**Avoid modifying:**
- Control flow
- State transitions
- Event wiring

---

End of document

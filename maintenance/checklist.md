# Convalescent Board — Maintenance Checklist
## (Read Before Making Changes)

This project is intentionally constrained. Small changes can significantly alter how it behaves or what it communicates.

**Please review this checklist before editing anything.**

---

## ✅ Safe to Edit

You may change these without affecting core behaviour:

### Content

* `data/text.json` → wording, tone, phrasing of square text
* `data/popups.json` → temporary text shown on specific squares

### Visual tuning

* Colours in `tiles.json`
* Spacing, font sizes, or opacity values in `TUNING.md`
* Timing values clearly marked as tunable (e.g. delays, fade times)

**These changes affect presentation, not mechanics.**

---

## ⚠️ Edit With Caution

These areas control how the experience behaves:

* `index.html`
* Any logic involving:
   * Movement
   * Visibility
   * Timing
   * State transitions
   * "Recall", "spinner", or reset behaviour

**If you change these:**

* Test slowly
* Make one change at a time
* Expect knock-on effects

**If something breaks, revert rather than patching blindly.**

---

## 🚫 Do Not Change (Unless You Intend to Redesign the System)

* How movement is limited to one step at a time
* How visibility is restricted to nearby squares
* How regression / return to start works
* The fact that progress can be lost

**These constraints are intentional, not bugs.**

They are what make the experience represent recovery rather than progress.

---

## 🧭 Design Intent Reminder

This system is meant to feel:

* Slow
* Uneven
* Occasionally frustrating
* Partially unknowable

**If a change makes it:**

* More efficient
* More predictable
* Easier to "win"

**…then it is probably undermining the point.**

---

## 🔧 If Something Breaks

1. Revert to the last known working version
2. Re-introduce changes one at a time
3. Test behaviour, not just appearance

**If unsure, don't optimise — observe.**

---

## 🧠 Final Note

This project is not a technical demo. It is a designed experience.

**Treat the constraints as part of the message.**

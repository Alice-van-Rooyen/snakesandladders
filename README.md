# Convalescent Snakes & Ladders Board
## Overview & Maintenance Notes

**This repository is published as a reference artefact. Please fork rather than edit directly.**


---

## Purpose

This project is a deliberately constrained interactive system designed to model the experience of recovery rather than simulate recovery itself.

This board isn't meant to be efficient or strategic. It is not a game to be optimised or "won".

You can only move one step at a time. You can't see very far ahead. Sometimes progress reverses or stalls without warning.

**That is intentional.**

The system is designed to surface the emotional and cognitive texture of recovery — uncertainty, interruption, slow change — rather than represent it abstractly.

**The goal is not completion. The goal is experience.**

---

## How to Use This Repository

This repository is stable and should not require frequent modification.

If you are maintaining or adapting it, please treat it as a system with constraints, not a sandbox.

### Core files (do not restructure)

* `index.html` — Contains all logic, rendering, and interaction behaviour.
* `data/text.json` — Contains all visible text and icons for board squares.
* `data/tiles.json` — Controls tile colours only.
* `data/popups.json` — Defines temporary text substitutions on specific squares.

---

## Where to Make Changes (and Where Not To)

### ✅ Safe to edit

These files are designed for adjustment:

* `text.json` — Edit wording, tone, and content of square text.
* `TUNING.md` — Adjust timing, spacing, animation feel, and visual weight.
* `tiles.json` — Change colour assignments.

**These changes will not break behaviour.**

### ⚠️ Edit with care

This files controls behaviour and timing:

* `index.html`

You should only edit this file if you understand:
* State transitions
* Timing dependencies
* Visibility logic

**If something breaks, revert to a known-good copy rather than patching blindly.**

---

## Design Constraints (Intentional)

* Progress is slow and sometimes reversible.
* Information is partial by design.
* The system limits control on purpose.
* Confusion or friction is not a bug.

**These constraints are not technical limitations — they are the point.**

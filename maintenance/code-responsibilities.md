# ✅ Authoritative File Responsibilities

## 1. index.html (core logic + behaviour)

**This is the engine.**

**Handles:**
* Movement rules (step-by-step, tether, recall, hospital pull)
* Visibility logic (what you can see, when)
* Icon → text transitions (the "beat")
* Spinner mechanics
* Cheat mode
* Help overlay
* Magnifier
* Rendering system (render-on-demand, explicit invalidation, guarded RAF)

**Important:** All timing logic, reveal logic, and interaction rules live here. Rendering is no longer continuous; any state mutation that should be visible must explicitly invalidate the canvas.

**Additional guarantee:** Spinner landing enforces a movement constraint — player input is blocked between spinner landing and spinner reveal, preventing the player from stepping past the spinner square.

---

## 2. tiles.json — Tile colour layout

Defines which squares get which background colour.
```json
{
  "defaultTile": "blue",
  "tileSets": {
    "aqua": [ ... ],
    "green": [ ... ]
  }
}
```

**Used for:**
* Background tile colouring only
* No behaviour attached

---

## 3. text.json — The narrative layer

**This is now the single source of truth for:**
* Which squares have text
* Which squares have icons
* What text appears on each square

**Structure:**
```json
{
  "42": {
    "text": "Some text",
    "icon": "icons/example.svg"
  }
}
```

**Behaviour:**
* If a square has an icon → icon shows first, then text after a short delay
* If it has text only → text shows immediately
* If it has neither → blank tile

**✅ This replaces the need for windows.json.**

---

## 4. popups.json — Special text overrides

**Used only for:**
* Temporary text replacement when landing on certain squares
* These override the normal text.json content briefly, then revert

Nothing else touches this file.

---

## 5. jumps.json — Snakes / teleport logic

**Defines:**
* Which squares trigger a jump
* Where they send you

Used by the spinner system only.

---

## 6. Assets folder

* `board.png` → background
* `token.png` → player token
* `icons/*.svg` → doodle icons
* `tiles/*.svg` → background coloured tiles, and tiles with images baked in

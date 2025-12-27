# snakesandladders
Convalescent Snakes &amp; Ladders GitHub Page repository


## ✏️ Editing Square Text (JSON Guide)

Each square’s text lives in `data/text.json` and looks like this:

```json
"26": {
  "text": "Your text goes here",
  "icon": null
}
```

You only ever edit the **`text`** value.

---

### 1️⃣ Normal text
Just type words. Spaces and punctuation are fine.

```json
"text": "You feel very tired today."
```

---

### 2️⃣ Manual line breaks (recommended)
Use `\n` to force a new line.

```json
"text": "You feel very tired\ntoday."
```

**Blank line / pause** → use two line breaks:

```json
"text": "You feel very tired.\n\nYou lie down."
```

---

### 3️⃣ Italics
Wrap text in single asterisks `*`.

```json
"text": "*You deserve a nap*"
```

Mixed with normal text:

```json
"text": "*You deserve a nap*\nRest is medicine."
```

---

### 4️⃣ Bold
Wrap text in double asterisks `**`.

```json
"text": "**PAIN**"
```

Inside a sentence:

```json
"text": "You are in **PAIN** today."
```

---

### 5️⃣ Mixing everything (allowed)
You can combine line breaks, italics, and bold.

```json
"text": "*You deserve a nap*\n\nRest is **medicine**,\nnot morality."
```

---

### 6️⃣ Things NOT to do ❌
- ❌ Don’t use HTML (`<b>`, `<i>`)
- ❌ Don’t forget to close `*` or `**`
- ❌ Don’t remove the surrounding quotation marks
- ❌ Don’t worry about font size — it’s automatic

If text doesn’t appear, it’s usually:
- very long (it will shrink), or
- an asterisk wasn’t closed.

---

### 7️⃣ Font size behaviour (automatic)
- Starts large
- Shrinks only if needed to fit
- Never disappears

You just write — the board handles the rest.

---

### Safe example (copy + edit)
```json
"69": {
  "text": "*You deserve a nap*\n\nRest is **medicine**, not morality.",
  "icon": null
}
```

**TL;DR:**  
Edit `"text"` → use `\n` for line breaks → `*italic*` → `**bold**` → done.

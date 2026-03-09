# Investment Monitor — Style Lab

A browser-based design sandbox for experimenting with the visual style of a personal investment dashboard.
Open the HTML file locally — no server, no build step, no dependencies.

---

## What it does

The page shows a mock investment table (accounts from Leumi, Discount, Morgan Stanley, Julius Baer) and lets you interactively design how it looks.
Everything is live — changes appear instantly.

---

## Layout

Four free-floating panels. Drag them by their title bar, resize from the bottom-right corner.

| Panel | Contents |
|---|---|
| **Style Description** | Name, tagline, mood, and traits for the active style. Supports Hebrew (RTL) and English (LTR). |
| **Financial Monitor** | The mock table with bank filter buttons and the 10 style-selector keys. |
| **Session Notes** | Free-text area to jot down what worked. Copy to clipboard or send by email. |
| **Style Lab** | All the controls: Areas, Directives, and JSON export. |

**↺ Reset** (top-right of title bar) — returns all panels to their default positions.
**Ctrl+Z** — undoes the last move or resize.

---

## 10 Style Presets

| # | Name | Character |
|---|---|---|
| 1 | Classic Minimalist | Clean white, Apple-inspired |
| 2 | Flat Design | Light greys, rounded pill buttons |
| 3 | Soft Neumorphic | Embossed surfaces, pastel shadows |
| 4 | Glassmorphism | Dark navy, frosted-glass transparency |
| 5 | High-Contrast Pro | Near-black background, orange accents |
| 6 | Soft Skeuomorphic | Warm paper texture, brown tones |
| 7 | Neo-Brutalism | Yellow headers, black borders, zero radius |
| 8 | Maximalist | Sky-blue background, bold yellow CTAs |
| 9 | Soft Minimalism | Dark slate, cool blue accents |
| 10 | Card-Based Dashboard | Deep navy, indigo-purple accents |

Switch styles with the numbered buttons below the table, or the ◀ ▶ arrows.

---

## Fine-tuning with Areas

The **Areas** section lets you override individual zones on top of any preset:

- **Title** — background, text color, font size, bold
- **Header** — same controls
- **Body** — odd-row color, even-row color, text, size, bold
- **Buttons** — background, text, border color, border radius, size, bold

---

## Fine-tuning with Directives

Type a rule in the Directives box and click **Apply**:

```
buttons: pill          # fully round corners
buttons: square        # sharp corners
buttons: rounded       # slightly rounded
theme: calmer          # softer selection highlight
theme: louder          # pink/red highlight
theme: high-contrast   # orange highlight
header: bigger         # 15px header font
header: smaller        # 11px header font
header: subtle         # muted grey header text
body: compact          # tighter row padding
body: spacious         # more breathing room
desc-bg: #1e293b       # description panel background color
```

Multiple directives can be stacked — put each on its own line.

---

## Export

Click **Export current config** to get a full JSON snapshot of every CSS variable and area override.
Use **שלח במייל** (Send by email) from the Session Notes panel to email the config with your notes.

---

## Python backend (optional)

The style lab is a standalone HTML file, but the project also includes Python scripts that pull live account data from downloaded bank statements:

| File | Role |
|---|---|
| `TotalsFromFiles.py` | Parses `.txt` exports from Leumi, Discount, Morgan Stanley, and Julius Baer; fetches a live USD/ILS exchange rate; writes `OUTPUT.txt` (CSV). |
| `ShowResults.py` | Renders a rich formatted table in the terminal from memory or from `OUTPUT.txt`. |

These scripts are separate from the HTML and are not required to use the style lab.

---

## Files

```
index.html          ← the style lab (this page)
README.md
```

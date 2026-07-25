# Loopline Park — Theme Park Engineers

A five-day Grade 5 Python camp, themed as building a working theme park in code. Campers start Monday with a talking ticket booth and finish Friday by opening a roller coaster they designed and programmed themselves.

Nine self-contained HTML lesson pages. No build step, no framework, no server-side anything — every page carries its own CSS and JavaScript inline, and the only external request is Google Fonts.

---

## 🎡 Start here: the hub is the homepage

**[loopline_park_hub.html](loopline_park_hub.html)** is the entry point. It links to all five days plus the printables and the Coaster Lab.

Live: **https://silvermanjonathan.github.io/loopline-park/loopline_park_hub.html**

> Note: the bare repo URL (`.../loopline-park/`) does **not** open the hub, because this repo has no `index.html`. Always link to `loopline_park_hub.html` — that's the front door.

---

## The week

| Day | Page | Python introduced | Campers build |
|---|---|---|---|
| **1 · Monday** | [day1_opening_the_gates.html](day1_opening_the_gates.html) | `print()`, comments, variables, `input()`, `int()`, f-strings, turtle, `for` + `range()` | Park marquee, Ticket Booth, polygon track drawn with a loop |
| **2 · Tuesday** | [day2_safety_gates_midway.html](day2_safety_gates_midway.html) | `if` / `elif` / `else`, comparisons, lists, indexing | Ride Safety Gate, Midway guessing game, park map |
| **3 · Wednesday** | [day3_prize_wheel_stamps.html](day3_prize_wheel_stamps.html) | `random.choice()`, `def`, parameters, `math.sqrt()` | Prize Wheel, `draw_wheel(spokes, size)` |
| **4 · Thursday** | [day4_coaster_build.html](day4_coaster_build.html) | none new — the coaster engine is provided read-only | **Capstone:** the coaster engine assembled in five staged runs, plus an Operator's Booth the camper writes |
| **5 · Friday** | [day5_grand_opening.html](day5_grand_opening.html) | none new — review and repair | Fix-it clinic, Stretch Garage upgrade, Grand Opening walkthrough |

Each day page follows the same shape: numbered chunks, a *predict-before-you-reveal* question in every chunk, a "you should see" box after anything runnable, one hinge question that gates the build, a build brief with a sample solution, three exit gates (approaching / meets / exceeds), and a collapsed teacher panel with standards and evidence.

## Supporting material

- **[coaster_lab.html](coaster_lab.html)** — the engine room. Eight chunks taking the physics apart line by line, five broken coasters to diagnose, the Track Design Card, and the printable **Ride Log**. Used as reference on Days 2–5 and sent home Friday.
- **[coaster_stretch_cards.html](coaster_stretch_cards.html)** — three printable class cards: the track list (Day 2), the square root and the Fury 325 reality check (Day 3), and the no-graphics text ramp that previews the motion line (Day 3).
- **[day1_trace_table_handout.html](day1_trace_table_handout.html)** — printable trace table for Monday.

Printables have their own print buttons and `@media print` rules that hide answer keys. Print them from the page opened directly in a browser, not from inside an embed.

## How the coaster works

The simulator is about a hundred lines of pygame. Four lines do the physics:

```python
height = track[seg] + (track[seg + 1] - track[seg]) * frac
drop = top - height
speed = math.sqrt(2 * GRAVITY * drop)
position = position + speed * DT
```

Campers never edit those. They design the **track** — a list of hill heights in meters — and write the booth that chooses which track to load. The whole ride emerges from height traded for speed, sixty times a second: nothing in the program says "speed up."

The full engine, the four staged assembly files, and a no-install **turtle edition** are all embedded in the pages, so there are no `.py` files to distribute.

**pygame is the only third-party package** (`pip install pygame`). On managed school machines that install can need an IT ticket — verify it on real camper hardware early in the week. If it doesn't clear, the turtle edition runs the identical physics with nothing to install and the week proceeds unchanged.

## Deployment

Hosted with GitHub Pages and embedded in Google Sites as a **full-page embed → By URL**, pointing at the hub. Because all files live in one flat folder and link each other by relative filename, navigation works inside the embed.

Two constraints if you fork or move this:

1. Keep all files at the top level of the repo — no subfolders.
2. Don't rename anything. The hub finds each page by exact filename.

The hub also contains a `PAGES` map near the top of its script, for the alternative setup where each page is pasted into its own Google Sites page rather than hosted together. Leave it blank when hosting the files as a set.

## Standards

Mapped to the **CSTA 2026 PK–12 Computer Science Standards**. Each page's teacher panel lists its codes, whether they're addressed or mastered, the evidence collected, and what the page deliberately does *not* claim.

⚠️ **Codes ending in `??` are unverified placeholders.** The Programming-strand identifiers (`E5-PRO-VD-??`, `E5-PRO-PD-??`, `E5-PRO-RD-??`, `E5-PRO-TR-??`) need confirming against the published standards at <https://csteachers.org/pk12standards/> before these pages are used for reporting. The Algorithms and Systems codes are verified.

Mapped to: Computer Science Teachers Association. (2026). *2026 CSTA PK–12 computer science standards.* <https://csteachers.org/pk12standards/> · Licensed CC BY-NC-SA 4.0. "Mapped to" is this project's claim; it is not a CSTA-reviewed or CSTA-approved designation.

## Teacher planning

The camp workbook — scope and sequence, block-by-block daily plan, standards alignment, misconceptions, and assessment rubric — is maintained separately as a spreadsheet and is not required to run the site.

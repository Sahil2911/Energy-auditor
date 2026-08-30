# Open-Book Strategy

Paper 4 is open book, but only the **supplied 4th-edition guidebooks** are
allowed. No notes, no printouts, no photocopies, no formula sheets.

This has one blunt consequence: **anything you want with you in the hall must
already be inside those books.** Build that in from Day 1.

## The economics of a lookup

150 minutes, roughly 16 sub-parts — under 10 minutes each. A lookup that takes
30 seconds is free. A lookup that takes 4 minutes has cost you half a sub-part.

So sort everything into three buckets:

| Bucket | Rule | Examples |
|---|---|---|
| **Memorise** | Used in almost every question, or too slow to look up | ER relationship, h_fw ≈ T, Cp values, 860 kCal/kWh, 1 TR = 3024 kCal/hr |
| **Tab** | Needed often, impossible to memorise | Steam tables, GCV tables, loss formulas, correction-factor charts |
| **Ignore** | Rare and derivable | Obscure charts you have never seen examined |

The mistake is treating the guidebook as a safety net for method. It is not.
**Method must be automatic; the books hold the numbers.**

## Tab scheme

Coloured sticky tabs, code written on each. Build progressively — do not try to
do this on Day 15.

| Code | Section | Added on |
|---|---|---|
| ST | Steam tables — saturated & superheated | Day 1 |
| BE | Boiler efficiency — indirect method losses | Day 2 |
| CA | Combustion — theoretical air, excess air | Day 3 |
| CP | Specific heat values | Day 1 |
| GCV | Fuel GCV table | Day 1 |
| TU | Turbine / cogeneration, Mollier chart | Day 4 |
| HX | Heat exchanger — LMTD correction factors, NTU | Day 5 |
| FU | Furnace heat balance | Day 6 |
| PU | Pump curves, affinity laws | Day 8 |
| FA | Fan laws, FAD test | Day 9 |
| MO | Motor loading, VSD | Day 10 |
| CT | Cooling tower | Day 10 |
| AC | HVAC, psychrometric chart | Day 11 |
| PP | Power plant heat rate, PAT | Day 12 |
| SC | Sector norms — cement, steel, textile | Day 13 |
| FI | Discount factor tables | Day 13 |

## The contents card

Inside the front cover of Book 4, write a card:

```
TAB   WHAT                              BOOK  PAGE
ST    Saturated steam table              4     ___
ST2   Superheated steam table            4     ___
CP    Specific heat — flue gas/steam     4     ___
...
```

Fill in page numbers as you tab. This card is your index. It is legal — it is
written inside the supplied book, not brought in separately.

## What you may legitimately write in the books

The rule bars *other* books and written materials. Annotating your own supplied
guidebook is normal practice. So:

- Underline and highlight freely
- Write the contents card inside the cover
- Note cross-references in margins ("→ see p. 212 for correction factor")
- Flag worked examples that match past-paper patterns

Do **not** paste in extra sheets or insert loose paper — that is a separate
written material and risks being treated as unfair means. Keep everything
written directly on the book's own pages.

## Getting the guidebook onto your machine

The guidebook is not in this repository and should not be. It is ~357 MB — over
GitHub's 25 MB web-upload limit and its 100 MB hard push limit — and it is BEE
copyright material issued to registered candidates, while this repository is
public.

Keep it in private cloud storage (Drive, OneDrive, Dropbox) if you want it on
more than one machine. What belongs in the repo instead is
`reference/guidebook-index.md` — the page index, which is a couple of kilobytes
and is the part that actually speeds you up.

If the file is unwieldy locally, it is almost certainly a high-resolution scan.
Ghostscript will shrink it hard without ruining the tables:

    gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook \
       -dNOPAUSE -dQUIET -dBATCH \
       -sOutputFile=book4-small.pdf book4.pdf

Use `/ebook` (150 dpi), not `/screen` (72 dpi) — at 72 dpi the property tables
and correction-factor charts become unreadable, which defeats the point. Expect
roughly 20–40 MB out.

If the 357 MB is all four guidebooks in one file, split Book 4 out first — it is
the only one permitted in the hall for Paper 4.

## Rehearse the lookups

From Day 5 onward, every timed question is done with the books at hand and a
timer running. Track lookup time in the study log. If any lookup repeatedly takes
over 60 seconds, either tab it better or move it to the memorise bucket.

By Day 15 you should be able to find any of the sixteen tabbed sections in under
ten seconds.

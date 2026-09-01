# Unit Discipline — The Three-Line Method

One error has now cost the same 5 marks twice: mixing kCal and kJ inside a single
multi-term ratio. It is not a knowledge gap — both conversions were known and used
correctly elsewhere in the same question. It is a **layout** problem.

## Why it keeps happening

The EUF expression has three terms with three different natural units:

```
              electrical output  +  heat output
    EUF  =  ───────────────────────────────────────
                     fuel energy input
```

- Electrical output arrives as **kW** — a power, not an energy
- Heat output comes from enthalpies, usually **kJ**
- Fuel input comes from GCV, usually **kCal**

Written as one long expression, you are converting three things while also
building a fraction. Something slips. Both times, exactly one term was left in
the wrong system:

| Attempt | Electrical | Heat | Fuel | Result |
|---|---|---|---|---|
| First | kCal ✓ | kJ ✗ | kJ ✗ | 0.611 |
| Second | kCal ✓ | kJ ✗ | kJ (×4.18) ✗ | 0.611 |
| Correct | kCal | kCal | kCal | **0.788** |

Note the second attempt actually converted the *fuel* into kJ deliberately — so
two terms agreed and one did not. Consistency in two of three is still wrong.

## The fix — never convert inside a fraction

**Compute each term on its own line, label its unit, convert it there, and only
then combine.**

```
    Electrical  = 21,410 kW × 860            = 1,84,12,600  kCal/hr
    Heat        = 91,000 × (2529 − 504.7)    = 18,42,11,300 kJ/hr
                                     ÷ 4.18  = 4,40,69,689  kCal/hr
    Fuel        = 17,630 × 4500              = 7,93,33,822  kCal/hr

    EUF = (1,84,12,600 + 4,40,69,689) / 7,93,33,822 = 0.788
```

Four lines. Every one carries a unit. The division happens once, at the end, with
all three terms already in kCal/hr.

**Rule: no unit conversion may appear inside a fraction bar.** If you find
yourself writing `× 4.18` in a numerator or denominator, stop and split the term
onto its own line first.

## Converting power to energy — the piece that causes trouble

`21,410` is **kW**. That is a rate, not a quantity. To use it in an energy balance
you must multiply by time:

```
    21,410 kW × 1 hour  →  21,410 kWh
```

Then convert kWh to whichever unit you need:

```
    × 860   → kCal/hr      (1 kWh = 860 kCal)
    × 3600  → kJ/hr        (1 kWh = 3600 kJ)
```

Both are right. `21,410 × 4.18` is **not** — that is kW multiplied by a
kJ-per-kCal factor, which is dimensionally meaningless. Watch for that specific
slip: 4.18 converts *energy to energy*, never *power to energy*.

## The three constants, and what each converts

| Factor | Converts | Never use it for |
|---|---|---|
| **4.18** | kCal → kJ (energy ↔ energy) | power → energy |
| **860** | kW → kCal/hr (power → energy rate) | kJ → kCal |
| **3600** | kW → kJ/hr (power → energy rate) | anything else |

Sanity: 860 × 4.18 = 3595 ≈ 3600. The two power conversions agree, as they must.

## Deciding which system to work in

Look at the **fuel** data. It is almost always in kCal (Indian practice quotes GCV
in kCal/kg), so:

> **Default to kCal/hr for the whole energy balance.** Convert enthalpies from kJ
> by dividing by 4.18 as you write each line.

The alternative — everything in kJ — is equally valid but means converting the
fuel term, which is the one most likely to be forgotten.

## Checking pass addition

Add to step 2 of the checking pass in `precision-and-rounding.md` §5:

> **Every term in a multi-term ratio must have the same unit written beside it.**
> If any term lacks a written unit, that is where the error is.

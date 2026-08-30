# Day 1 — Exam Craft, the Open-Book System, and Boilers I

**Time: 3.5 hours. Book-4 Chapter 1.**

Goals for today:
1. Understand what Paper 4 actually tests, and why candidates fail it.
2. Set up your guidebook indexing system — you will add to it every day.
3. Master the **direct method** and **evaporation ratio**, the paper's most
   frequently examined calculation (8 of 8 sittings).

---

## Block A — Concept (45 min)

### A1. What Paper 4 really tests

Papers 1–3 asked *do you know this?* Paper 4 asks *can you assess a plant from
imperfect data and produce a defensible number?*

Three practical consequences:

**The data is deliberately over-supplied.** A 20-mark question gives you 15–20
parameters. Some are irrelevant, some are there for a later sub-part. Read all
sub-parts *before* you start calculating — sub-part (a) often produces a number
that (c) and (e) reuse.

**Method earns marks, not just the answer.** Look at any model solution in
`papers/` — they are laid out as a chain of named quantities, each with units.
An arithmetic slip in step 4 costs you step 4, not the whole question, provided
the examiner can see the method. **Write the formula, substitute, then evaluate.**
Never jump to a number.

**Units are the trap.** kg/cm², kCal/kg, TPH, m³/hr, MU, TOE. Mixing kCal and kJ
is the most common fatal error. Decide at the start of each question which system
you are in and stay there.

### A2. Why candidates fail an open-book paper

Because open book removes the *memory* constraint but not the *time* constraint.
You have 150 minutes and roughly 16 sub-parts. That is under 10 minutes each. If
you spend four minutes finding the specific heat of flue gas, you have lost the
question.

The guidebook is for **lookups you cannot reasonably memorise** — property
tables, steam tables, standard coefficients. It is not for learning method during
the exam. Method must be automatic.

### A3. The direct method

The simplest boiler assessment: heat *out* over heat *in*.

```
                 Q × (h_steam − h_feedwater)
    η_direct  =  ───────────────────────────  × 100
                        q × GCV
```

| Symbol | Meaning | Typical unit |
|---|---|---|
| Q | Steam generated | kg/hr |
| h_steam | Enthalpy of steam at operating pressure | kCal/kg |
| h_feedwater | Enthalpy of feedwater ≈ its temperature in °C | kCal/kg |
| q | Fuel consumed | kg/hr |
| GCV | Gross calorific value of fuel | kCal/kg |

Two things to internalise:

- **h_feedwater ≈ feedwater temperature in °C.** Because the specific heat of
  water is ~1 kCal/kg°C, water at 84 °C carries ~84 kCal/kg. This shortcut appears
  in every model solution.
- **Enthalpy of steam comes from the steam table** — indexed by pressure. This is
  a genuine guidebook lookup. Tab it today.

### A4. Evaporation ratio — the highest-yield relationship

**Evaporation ratio (ER)** = kg of steam raised per kg of fuel burnt.

```
    ER  =  Q / q
```

Combine with the direct method and you get the relationship the exam asks for
over and over:

```
                η × GCV
    ER  =  ─────────────────
            h_steam − h_fw
```

and rearranged:

```
            ER × (h_steam − h_fw)
    η  =  ────────────────────────
                   GCV
```

Learn this rearrangement cold. It has been examined in the 17th, 18th and 25th
sittings in near-identical form — two boilers, same ER, same fuel, find the
second efficiency.

Typical ER values worth recognising as sanity checks:

| Fuel | ER |
|---|---|
| Coal | 4 – 6 |
| Furnace oil / fuel oil | 13 – 15 |
| Natural gas | 11 – 13 |
| Bagasse / husk | 2 – 3.5 |

If you compute an ER of 40 for coal, you have made an error. Use these to catch
yourself.

> **Careful — a True/False trap.** The 25th paper asked: *"Evaporation ratio is
> based on actual performance data and does not depend on whether efficiency is
> expressed on GCV or NCV basis."* **True.** ER is a raw mass ratio — steam out
> over fuel in. It is measured, not derived, so no efficiency basis enters it.
> But the *efficiency* you calculate from it absolutely does depend on whether you
> used GCV or NCV. Keep those two ideas separate.
>
> And from the same paper: *"If wet steam is generated, a high evaporation ratio
> indicates high boiler efficiency."* **False.** Wet steam carries less enthalpy
> per kg, so you raise more kg per kg of fuel — ER rises while efficiency does
> not. ER alone is never proof of efficiency.

---

## Block B — Guided practice (60 min)

### B1. Set up the guidebook index (20 min)

Do this before any calculation. You need physical tabs in Book 4 and Book 2.

Tab these today:

| Tab | What | Why |
|---|---|---|
| ST | Steam tables (saturated + superheated) | Every boiler and turbine question |
| BE | Boiler efficiency — indirect method loss formulas | Day 2 |
| CA | Combustion — theoretical air, excess air formulas | Day 3 |
| CP | Specific heat values (flue gas 0.24, steam 0.45, air 0.24) | Constantly |
| GCV | Typical GCV table for fuels | Sanity checks |

Use coloured sticky tabs, write the code on each, and keep a **contents card** on
the inside front cover listing tab → page number. Add to it every single day. By
Day 15 this index is worth more than any note you could have brought.

> A model solution in the 24th paper literally says *"Cp = SP ht of flue gas =
> 0.24 Kcal/KgC (Value referred from the guidebook)"*. The examiners expect you
> to look things up. Make it fast.

### B2. Worked example — the 24th sitting, N-1 (25 min)

A textile plant runs a 20 TPH travelling-grate coal boiler and is considering
switching to paddy husk.

```
Average monthly steam demand   : 10,800 tonnes
Operating hours per month      : 720 hours
Coal-fired boiler efficiency   : 67 %
Steam enthalpy                 : 665 kCal/kg
Feedwater temperature          : 84 °C
GCV of coal                    : 4200 kCal/kg
Cost of coal                   : Rs 12,000/tonne
Auxiliary cost, coal boiler    : Rs 750/tonne of steam
```

**(a) Evaporation ratio of the coal boiler**

Use the rearranged relationship. Note h_fw = 84 kCal/kg directly from the 84 °C.

```
    ER = (η × GCV) / (h_steam − h_fw)
       = (0.67 × 4200) / (665 − 84)
       = 2814 / 581
       = 4.84 kg steam / kg coal
```

Sanity check: 4.84 sits inside the 4–6 band for coal. Good.

**(b) Steam cost, Rs/tonne**

ER = 4.84 means one tonne of coal makes 4.84 tonnes of steam. So the coal cost
per tonne of steam is the coal price divided by ER:

```
    Fuel cost  = 12,000 / 4.84  =  Rs 2,479 / tonne of steam
    Aux cost   =                    Rs   750 / tonne of steam
    ────────────────────────────────────────────────────────
    Total      =                    Rs 3,229 / tonne of steam
```

Notice what happened: **the monthly steam demand, the operating hours and the
20 TPH rating were never used.** They belong to other sub-parts. This is exactly
the over-supplied-data pattern from A1. Do not be unsettled by unused numbers.

The remaining sub-parts (c), (d), (e) need the indirect method and combustion
stoichiometry — Days 2 and 3. You will return and finish this question on Day 3.

### B3. Your turn, with the solution covered (15 min)

From the 25th sitting, Section II, L-1:

> In a petrochemical industry, both the LP and HP boilers operate with the same
> evaporation ratio of 14, using the same fuel oil.
>
> | | LP Boiler | HP Boiler |
> |---|---|---|
> | Pressure | 10 kg/cm²a | 32 kg/cm²a |
> | Temperature | Saturated | 400 °C |
> | Enthalpy of steam | 665 kCal/kg | 732 kCal/kg |
> | Feedwater temperature | 80 °C | 105 °C |
> | Evaporation ratio | 14 | 14 |
>
> If the efficiency of the LP boiler is 82%, calculate the efficiency of the
> HP boiler.

Hint: same fuel means same GCV, and GCV cancels if you set up a ratio. You do not
need to know the GCV at all — though you can find it if you prefer.

Check yourself against `papers/25-1.pdf`. Both routes are in the model answer.

---

## Block C — Timed question (60 min)

Attempt **one full 20-mark question, closed notes, guidebooks only, 25 minutes on
the clock.** Then stop, regardless of where you are.

Do: **18th sitting, Set A, N-1** — a 10 TPH natural gas fired boiler
(`papers/18-1.pdf`).

Rules:
- Phone away. Timer visible.
- Write formula → substitute → evaluate, every step.
- If stuck for more than 3 minutes, write down what you would need and move on.

Then spend the remaining 35 minutes marking yourself against the model answer.

## Block D — Log your errors (25 min)

Open `log/study-log.md` and record, honestly:

- Marks you would award yourself out of 20
- Every error, tagged: **concept** / **method** / **arithmetic** / **units** / **lookup speed**
- How long the guidebook lookups took
- Anything you could not find in the books at all

That tagging matters. Four arithmetic slips and four concept gaps call for
completely different responses from the tutor.

---

## Homework before Day 2

1. Finish the two remaining L-questions from the 25th sitting.
2. Tab the five guidebook sections in B1 and start the contents card.
3. Memorise — genuinely memorise, these are too slow to look up:
   - η = ER × (h_steam − h_fw) / GCV
   - h_feedwater ≈ temperature in °C
   - Cp flue gas = 0.24, Cp steam = 0.45 kCal/kg°C
   - ER bands: coal 4–6, oil 13–15, gas 11–13, husk 2–3.5

## Day 1 checklist

- [ ] Read Block A, understand ER vs efficiency
- [ ] Guidebook tabs placed, contents card started
- [ ] Worked example B2 followed end to end
- [ ] B3 attempted before looking at the solution
- [ ] One 20-mark question done under time
- [ ] Errors logged and tagged in `log/study-log.md`

**Tomorrow:** Boilers II — the indirect method and the seven losses. This is the
single most-examined calculation in Paper 4, and it is where the 24th paper's
question (c) is waiting for you.

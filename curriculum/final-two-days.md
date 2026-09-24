# The last two days — Thursday 24 and Friday 25 September

**Exam: Saturday 26 September, 14:00–16:30.**

> ## The honest position, stated plainly
>
> **The five-day topic plan assumed Monday started on Monday. It is Thursday and
> you are five questions into Monday's list.** Cogeneration and power plant are now
> thoroughly covered — 80/100 across five 20-markers, and 94% on the last three.
> **HVAC, pumps, fans, compressed air and boilers have had no time in the final
> week at all.**
>
> **Two days remain — about seven working hours.** The rest of the plan does not
> fit in them. So this page does the triage, and it drops things on purpose.

## What is being dropped, and why it is safe

| Dropped | Why |
|---|---|
| Group 2.2, 2.3 (22nd, 23rd/25th turbine heat rates) | **Same method you now have.** 2.1 proved it. Read the keys, do not work them |
| Group 3 (EUF, heat-to-power, steam rate) | **Read Part A's back-pressure section + the 19th N-1 key.** Concepts, not practice |
| Group 4 (gas turbine / trigeneration) | Five of six carry an absorption chiller — **they come free with Thursday's HVAC** |
| A fourth full mock | You have sat three. **Time is better spent on untouched topics** |

**Nothing here is dropped because it is unimportant.** It is dropped because you can
already do it, or because another day covers it.

---

# THURSDAY 24 — HVAC, chillers and cooling towers · ~3½ hours

**This is the highest-value untouched topic**, for two reasons: it appears in
**6 questions across the sittings**, and **chiller heat rejection has cost you marks
twice** — Mock 1's N-4(A) and again in Day 15's review.

## Read first — 20 minutes

**`reference/concept-distinctions.md` entry on chiller rejection**, and this, which
is the whole topic in four lines:

```
    Q_rejected  =  Q_cooling  +  the energy you spent doing it

    General form:   condenser duty = TR × 3024 × (1 + 1/COP)

    VCR at COP 4.4:  × 1.227        VAR at COP 1.2:  × 1.833
```

**A VAM rejects about 50% more heat than a compression chiller for the same
cooling**, which is why it needs a bigger cooling tower. **That single sentence has
been worth marks in two sittings.**

## Then, in this order

| | Question | Marks | Why this one |
|---|---|---|---|
| **1** | **21st N-2** — 2400 TR, centrifugal vs double-effect VAM | 20 | ⭐ **The rejection concept in BEE's own words**, with the general form printed |
| **2** | **22nd N-2(b)** — air-fin cooler + water-cooled chiller | 20 | **You ran out of time on it in Mock 2.** Finish it |
| **3** | **20th N-4(D)** — hospital, 700 kW gas engine + VAM | 20 | Trigeneration **and** chiller in one — covers Group 4 as well |
| **4** | **18th N-2** — 25 TPD ice plant | 20 | Only if time. The cleanest straight refrigeration question |

**25 minutes each, hard stop.** Mark yourself against the key before moving on.

## The two traps to watch, both already yours

- **kW/TR is an inverse.** Lower is better. **Never compare on it** — convert to
  COP or to kW and compare those. *(Same family as the heat rate that cost you
  1.4 part 2.)*
- **Hold the service constant.** Both options must deliver the same TR. Carrying
  one machine's COP into the other's arithmetic is the error the 22nd is built on.

---

# FRIDAY 25 — Boilers, rotating equipment, then stop · ~3 hours + the checklist

**Morning — boilers, 90 minutes.** You did a full indirect method on Monday and
scored 8.5/10; the method is sound and the only error was a constant.

- **Rewrite the eight losses from memory**, once, with the Cp beside each:
  ```
     L1 dry flue gas   Cp 0.24      L5 CO           5654
     L2 H₂             Cp 0.45      L6 fly ash      GCV of ash
     L3 fuel moisture  Cp 0.45      L7 bottom ash   GCV of ash
     L4 air moisture   Cp 0.45      L8 radiation    given
  ```
  **`0.24 gas · 0.45 vapour`. Wherever 584 appears, the Cp beside it is 0.45.**
- **One question: 20th N-2**, pressurised hot water circulation — the same shape as
  the 19th N-3 you scored 20/20 on, and never yet worked cold.

**Midday — rotating equipment, 60 minutes. Read, do not work.**

- **The pitot chain** (`curriculum/day-17.md`, Rung 192 and Day 13 Rung 137B):
  ```
     ρ = 1.293 × (P_bar ± P_static)/10334 × 273/(273 + t)      static SIGNED
     v = C√(2gh/ρ) → Q = vA → fan η = Q Δp/(102 × motor kW)
  ```
  **Negative static in three sittings** — the 21st at −850, the 22nd at −440 and
  −28, the 16th's N-4(D). **Suction ducts carry a minus sign.**
- **Skim the 21st N-4(A)** (cement raw mill fan) and the **22nd N-4(C)** keys. Read
  the chains; do not compute.

## Afternoon — the checklist outranks the questions

1. **Tab the four guidebooks.** Steam tables · the eight boiler losses · psychrometric
   chart · the constants page. **You may only carry the supplied 4th edition.**
2. **Write the exam card from memory, three times.** Not reading it — writing it.
3. **Read `reference/formula-sheet.md` once**, end to end. It already contains every
   constant you have got wrong this week.
4. **Pack.** Admit card, ID, calculator *and a spare*, pens, the guidebooks.
5. **Stop at 20:00.** No new material after that. Nothing learnt on the last night
   has ever been worth the sleep it cost.

---

# The exam card — the whole of it

**Write this from memory on Friday. If a line needs the file, that line is your
last twenty minutes.**

```
LADDER      turbine < gross < net             ALWAYS
            gross = turbine/η_boiler ;  net = gross/(1 − APC)
            "overall" or "plant" efficiency = 860/GROSS, never net, never turbine
            engine or GT given by efficiency: HR = 860/η

CURRENCY    η = 860/HR (kCal)   or   3600/HR (kJ)      860 × 4.186 = 3600
            860 converts kW ↔ kCal/h and NOTHING else
            already kCal/h (mass × enthalpy, fuel × GCV, TR × 3024) → no 860

REHEAT      heat IN  = MS(h_MS − h_fw) + RH(h_HRH − h_CRH)     ← the heat rate
            work OUT = MS(h_MS − h_CRH) + RH(h_HRH − h_exh)    ← the power
            denominator is the GENERATOR, not the shaft

STEAM       h = h_f + x·h_fg        h_f, never h_g
            condenser load = m(h_exhaust − h_f)     no dryness needed

RATIOS      heat rate, kW/TR, SEC, steam rate — LOWER IS BETTER
            never conclude on them: convert to efficiency or COP first
            they do NOT add — re-divide on the totals

CHILLER     Q_rejected = TR × 3024 × (1 + 1/COP)
            VCR COP 4.4 → ×1.227     VAM COP 1.2 → ×1.833

BOILER      0.24 dry flue gas (L1) · 0.45 water vapour (L2, L3, L4)
            m_dfg = AAS + 1 − (M + 9H₂ + ash)
            TA = 11.6C + 34.8(H₂ − O₂/8) + 4.35S    EA = O₂/(21 − O₂)

PITOT       ρ = 1.293 × (P_bar ± P_static)/10334 × 273/(273 + t)   SIGNED

BANDS       turbine HR 2000–2600 · gross 2300–3000 · net 2600–3300
            turbine CYCLE η 45–50 % · PLANT η 28–36 %
            boiler η 80–90 % · dryness 0.86–0.93
            condenser load > kW × 860, roughly twice it

HABITS      1. alarm fires → STOP → back one line → rewrite
            2. every number must have a parent in the data or a line above
            3. read the number back off the line above when you carry it down
            4. reread the question's LAST NOUN before you move on
               (difference · per day · annual · per tonne)
            5. one answer on the page — strike what you rejected
            6. 25 minutes per 20-marker, hard stop
```

---

# In the exam room

**Section III is "answer any ONE of four" on N-4.** You are now strongest on
**power plant and cogeneration** — if one of the four is a heat rate or a
cogeneration question, **take it**, and do not read the other three past their
first line.

**Read every sub-part before calculating.** Star the one-liners. **A part that
looks independent usually is** — 1.3's condenser load did not need the dryness
fraction, and three marks were lost behind a two-mark error.

**When a quantity cannot be calculated, say so.** The 22nd's N-4(A) key does exactly
that about the station heat rate and awards the marks for naming the missing datum
with a reasonable assumption. **Naming what is missing beats inventing it.**

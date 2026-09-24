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

# FRIDAY 25 — the last day · revised after Thursday

> **Thursday ran 23:13 → 23:58.** Nine of ten sub-parts correct, but the openings
> of four questions instead of the whole of one — and **every one stopped exactly
> where the marks start.** See `assessments/thu-hvac-review.md`.
>
> **So Friday changes shape.** Fewer questions, finished. **Finish what you start**
> is now the rule, above coverage.

## 1 · FIRST — 21st N-2 part (d) · 25 minutes · do this before anything

**The part you stopped one line short of, and the reason that question was ranked
first.** Chiller heat rejection has cost you marks twice.

```
    Q_rejected = Q_cooling + the energy you spent doing it

    condenser duty = TR × 3024 × (1 + 1/COP)

    centrifugal COP 4.4 → × 1.227      absorption COP 1.2 → × 1.833
    2400 TR:  89,07,055  vs  1,33,05,600  ⟹ additional 43,98,545 kCal/h
    CW = 43,98,545/(1000 × 8) = 549.82 m³/hr
```

**A VAM rejects ~50% more heat for the same cooling.** Write that line on the card.

## 2 · Finish ONE HVAC question end to end · 25 minutes

**20th N-4(D)**, the hospital trigeneration — you did part 1 and have three parts
left, worth 18 of 20 marks. **It is also the whole of Group 4 in one question:**
`HR = 860/η`, then the engine's heat split three ways.

```
    heat rate = 860/0.28 = 3071   gas = 625 × 3071/9000 = 213.3 Sm³/h  ✓ done
    jacket heat = 29 % of engine heat input  →  TR = jacket × COP 1.65/3024
    hot water   = 20 % of exhaust heat/(60 − 30)
    savings     = grid cost − gas cost, 7500 h/yr
```

**Tabulate the engine's heat balance before answering any part** — shaft, jacket,
exhaust, each with its percentage. **Then answer all four parts.**

## 3 · Boilers from memory · 45 minutes, writing not reading

**Rewrite the eight losses from memory, once, with the Cp beside each:**
```
   L1 dry flue gas   Cp 0.24      L5 CO           5654
   L2 H₂             Cp 0.45      L6 fly ash      GCV of ash
   L3 fuel moisture  Cp 0.45      L7 bottom ash   GCV of ash
   L4 air moisture   Cp 0.45      L8 radiation    given

   TA = 11.6C + 34.8(H₂ − O₂/8) + 4.35S      EA = O₂/(21 − O₂)
   AAS = TA(1 + EA)      m_dfg = AAS + 1 − (M + 9H₂ + ash)
```
**`0.24 gas · 0.45 vapour`. Wherever 584 appears, the Cp beside it is 0.45.** You
scored 8.5/10 on this in 1.4 and the only error was that constant.

## 4 · Read-only, 30 minutes — the pitot chain

```
   ρ = 1.293 × (P_bar ± P_static)/10334 × 273/(273 + t)      static SIGNED
   v = C√(2gh/ρ)   →   Q = vA   →   fan η = Q Δp/(102 × motor kW)
```
**Negative static in three sittings** — 21st −850, 22nd −440 and −28, 16th N-4(D).
**Suction ducts carry a minus sign.** Skim the 21st N-4(A) key. Do not compute.

## 5 · The checklist — this outranks everything above

1. **Tab the four guidebooks** — steam tables · the eight losses · psychrometric
   chart · the constants page. **Supplied 4th edition only.**
2. **Write the exam card from memory, three times.** Writing, not reading.
3. **Pack:** admit card, ID, calculator **and a spare**, pens, guidebooks.
4. **Stop at 20:00.** Nothing learnt on the last night has ever been worth the sleep
   it cost — and Thursday is the proof: the work was fine, the hour was not.

> ### If the day compresses again, do these three and nothing else
> **21st N-2 (d) · the eight losses from memory · the exam card three times.**
> Forty-five minutes, and it covers the two concepts that have cost you the most
> marks plus everything you need to carry in.

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

CHILLER     Q_rejected = Q_cooling + the energy spent doing it
            condenser duty = TR × 3024 × (1 + 1/COP)
            VCR COP 4.4 → ×1.227     VAM COP 1.2 → ×1.833
            a VAM rejects ~50 % MORE heat for the same cooling
            3.516 kW/TR = 3024/860   (NOT 3.413, which is Btu/Wh)

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
               (difference · per day · annual · per tonne · 'output')
               rated capacity is NOT output — the 18th's 25 TPD plant
               delivers 15 T/day and the question says per tonne 'output'
            7. FINISH the question you started. The back half holds the
               marks; the openings are the parts you can already do
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

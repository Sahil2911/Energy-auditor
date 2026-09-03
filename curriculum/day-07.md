# Day 7 — Consolidation and Mock A

**Time: 3.5 hours.** The first real checkpoint.

Four chapters are complete — **Boilers (1), Furnaces (2), Cogeneration and
Turbines (3), Heat Exchangers (4)**. Together these carry roughly half of a
typical Paper 4.

Today: a **60-mark half-paper under exam conditions**, then a full self-review.

> **Prerequisite check.** Every question is drawn from Days 1–6. Nothing here
> needs pumps, fans, HVAC, power plants or the sector chapters.

---

## Structure

| | Section | Marks | Time |
|---|---|---|---|
| I | True / False, 10 questions | 10 × 1 = 10 | 10 min |
| II | Short numericals, 2 questions | 2 × 5 = 10 | 15 min |
| III | Long numericals, 2 questions | 2 × 20 = 40 | 60 min |
| | **Total** | **60** | **85 min + 5 review** |

**60 marks in 90 minutes is the real paper's pace** (100 marks in 150 minutes).
This is a genuine half-paper, not a lighter one.

## Rules — follow them exactly

- **One sitting. Timer visible. Phone away.**
- **Guidebooks only.** No notes, no formula sheet, no reference files from this
  repository. This is the open-book condition you will actually face.
- Write formula → substitute → evaluate, every step.
- **Sanity sentence on every final answer.**
- **Run the two-minute checking pass** before you stop — and record what it
  caught.
- If stuck past 3 minutes, write what you would need and move on. Come back.

Do not look at the answers below Section III until you have finished everything.

---

# SECTION I — True or False

**10 questions, 1 mark each, 10 minutes.**

1. The evaporation ratio of a boiler depends on whether its efficiency is
   expressed on a GCV or an NCV basis.

2. In the indirect method of boiler efficiency calculation, blowdown loss is one
   of the losses subtracted from 100.

3. In the dry flue gas loss (L1), the specific heat used is that of superheated
   steam, approximately 0.45 kCal/kg°C.

4. For a real steam turbine, the actual exhaust enthalpy is higher than the
   enthalpy after an isentropic expansion to the same pressure.

5. A back-pressure cogeneration plant has a much higher heat rate than a
   condensing plant, which shows that it uses fuel less efficiently.

6. The log mean temperature difference is always smaller than the arithmetic mean
   of the two terminal temperature differences.

7. In a parallel-flow heat exchanger, the cold fluid outlet temperature can exceed
   the hot fluid outlet temperature.

8. A reheating furnace shows a much larger percentage dry flue gas loss than a
   boiler mainly because its exhaust gas temperature is far higher.

9. Preheating combustion air using a recuperator reduces the fuel required for the
   same furnace output.

10. In a heat exchanger with water on one side and air on the other, increasing
    the water-side velocity is an effective way to raise the overall heat transfer
    coefficient.

---

# SECTION II — Short Numericals

**2 questions, 5 marks each, 15 minutes.**

### L-1 (5 marks)

A reheating furnace fires fuel oil. Measurements give:

```
    O₂ in flue gas                = 8 %
    Exit flue gas temperature     = 800 °C
    Ambient temperature           = 35 °C
    Theoretical air (typical, oil)= 14 kg air / kg fuel
    Specific heat of flue gas     = 0.24 kCal/kg°C
    GCV of fuel oil               = 10,000 kCal/kg
```

Calculate the percentage heat loss in dry flue gas.

### L-2 (5 marks)

A back-pressure steam turbine has:

```
    Inlet steam enthalpy                        = 3300 kJ/kg
    Isentropic exhaust enthalpy at back pressure = 2500 kJ/kg
    Isentropic efficiency                        = 85 %
    Steam flow                                   = 60 TPH
    Gearbox efficiency                           = 97 %
    Generator efficiency                         = 98 %
```

Calculate the electrical output in MW.

---

# SECTION III — Long Numericals

**2 questions, 20 marks each, 60 minutes.**

### N-1 (20 marks) — `papers/25-1.pdf`, question N-2

A boiler fired with 200 kg/hr of a hydrogen-enriched hydrocarbon fuel. Given the
dry flue gas composition by weight, determine the fuel's constituents, their
percentages, and the dry flue gas mass flow.

**Open the paper and work it there.** Do not read past the question.

> This is a **reverse combustion problem** — everything you did on Day 2A run
> backwards. Instead of going fuel → air → flue gas, you go flue gas → air →
> fuel. Every tool you need is from Rungs 1–9. Think about what each flue gas
> component can only have come from.

### N-2 (20 marks) — `papers/17.pdf`, question N-2

A beverage industry product stream cooled in two stages — first by cooling water,
then by chilled water. Heat exchanger duties, flows and areas.

**Open the paper and work it there.**

---

*Stop. Finish everything above, run the checking pass, then continue.*

---

# ANSWERS AND MARKING

## Section I

<details><summary>Answers with reasons</summary>

1. **False.** ER is a raw mass ratio — kg of steam per kg of fuel — measured, not
   derived. No efficiency basis enters it. The *efficiency* you compute from it
   does depend on GCV vs NCV. (Day 1, A4)

2. **False.** The indirect method accounts for heat leaving in the *flue gas and
   ash*. Blowdown leaves as hot *water* — a real loss, but outside this
   calculation. (Day 3, blowdown)

3. **False.** L1 heats **gas** — Cp ≈ 0.24. The 0.45 (or 0.43) belongs to
   superheated steam and is used in L2, L3 and L4. (Day 3, Rung 13)

4. **True.** Friction inside the sealed, adiabatic turbine returns work to the
   steam as heat, so h₂ > h₂s. (concept-isentropic-expansion.md)

5. **False.** The first half is true, the conclusion is wrong. Heat rate charges
   *all* the fuel against power alone, and a back-pressure plant makes little
   power per kg of steam. Its exhaust heat runs the process rather than being
   dumped. EUF is the right measure, and it is far higher. (Day 4, Rung 28)

6. **True.** The temperature gap closes exponentially, and the log mean of an
   exponential decay is always below the arithmetic mean. (Day 5, Rung 41)

7. **False.** That is a temperature cross, and parallel flow cannot achieve it —
   both streams march toward a common temperature and neither passes the other.
   Only counterflow can. (Day 5, Rung 43)

8. **True.** Same L1 formula, but the furnace gas leaves at 700–1000 °C against a
   boiler's 180 °C — roughly 4.7× the ΔT. High excess air compounds it, but the
   temperature is the main cause. (Day 6, Rung 54)

9. **True.** Preheated air carries energy back into the furnace that was already
   paid for, so less fuel is needed. Roughly 1% per 20 °C at normal excess air.
   (Day 6, Rung 62)

10. **False.** The resistances are in series and the **air film dominates** — it
    can be 100× the water-side resistance. Improving the water side changes almost
    nothing. Add area on the air side instead, which is why such exchangers are
    finned. (Day 5, Rung 37)
</details>

## Section II

<details><summary>L-1 — furnace flue gas loss</summary>

```
    Excess air = 8 / (21 − 8) × 100          = 61.54 %          [1]
    AAS        = 14 × 1.6154                 = 22.62 kg/kg      [1]
    m_fg       = 22.62 + 1                   = 23.62 kg/kg      [1]
    L1         = 23.62 × 0.24 × (800 − 35) / 10,000 × 100
                                             = 43.4 %           [2]
```

*Sanity:* furnace L1 should be 40–60%. 43.4% sits in the band. ✓
</details>

<details><summary>L-2 — back-pressure turbine</summary>

```
    h₂  = 3300 − 0.85 × (3300 − 2500) = 3300 − 680 = 2620 kJ/kg  [2]
    Δh  = 680 kJ/kg
    Shaft power = 60,000/3600 × 680 = 11,333 kW = 11.33 MW       [2]
    Electrical  = 11.33 × 0.97 × 0.98 = 10.77 MW                 [1]
```

*Sanity:* h₂ = 2620 lies between 2500 and 3300. ✓ Efficiencies multiply, never
add.
</details>

## Section III

Mark against the model answers in the papers themselves. For N-1, the key chain:

<details><summary>N-1 — outline only, check details in the paper</summary>

Work **per 100 kg of dry flue gas**:

```
    Carbon, from CO₂:   12 × 12/44                = 3.273 kg
    Air, from N₂:       85 / 0.77                 = 110.39 kg
    O₂ supplied:        0.23 × 110.39             = 25.39 kg
    O₂ consumed:        25.39 − 3                 = 22.39 kg
    O₂ used by carbon:  3.273 × 32/12             = 8.73 kg
    O₂ left for H₂:     22.39 − 8.73              = 13.66 kg
    Hydrogen:           13.66 / 8                 = 1.708 kg

    Fuel per 100 kg fg = 3.273 + 1.708 = 4.98 kg
    Composition: C 65.7 %,  H₂ 34.3 %
    Dry flue gas for 200 kg/hr fuel = 200/4.98 × 100 = 4,016 kg/hr
```

Every step is a Day 2A tool used backwards: 12/44 from the CO₂ reaction, 0.77 for
nitrogen in air, 0.23 for oxygen, 8 kg O₂ per kg H₂.
</details>

---

# SELF-ASSESSMENT

Complete this honestly and put it in `assessments/` — it drives what changes next.

## Score

| Section | Marks | Yours |
|---|---|---|
| I — True/False | 10 | |
| II — Short numericals | 10 | |
| III — N-1 | 20 | |
| III — N-2 | 20 | |
| **Total** | **60** | |

**Pass equivalent: 30/60.**

## Marking a long question

| Component | Marks (of 20) |
|---|---|
| Correct formula stated | 4 |
| Correct substitution, units consistent | 4 |
| Correct intermediate quantities | 6 |
| Correct final answer with units | 4 |
| Sanity / interpretation where asked | 2 |

A wrong final number with sound method still earns 12–14. Mark that way — it is
how the examiner marks.

## Diagnostics — the part that matters more than the score

| Question | Time taken | Started? | Finished? |
|---|---|---|---|
| Section I | | | |
| Section II | | | |
| N-1 | | | |
| N-2 | | | |

**Did you finish inside 90 minutes?** yes / no — and if not, where did the time go?

**Every lost mark, tagged:** concept / method / arithmetic / units / lookup / time

**What did the checking pass catch?** — write "caught nothing" if so.

**Guidebook lookups over 60 seconds:**

---

# WHAT THE SCORE MEANS

| Score | Reading | Action |
|---|---|---|
| **45+/60** | Comfortably above pass on the hardest half | Proceed to Day 8 as planned |
| **30–44** | Passing, with identified gaps | Proceed, but re-drill whatever the tags concentrate on |
| **25–29** | Borderline | Insert a repair day before Day 8 on the weakest chapter |
| **< 25** | Foundation not holding | Stop. Rebuild the weakest chapter before any new material |

**Whatever the score, the tag distribution decides what changes.** Mostly
*concept* means the teaching was too fast. Mostly *arithmetic* or *units* means
the teaching worked and the checking pass is not running. Mostly *time* means the
method is sound and needs rehearsal, not re-teaching.

---

## Day 7 checklist

- [ ] Mock A attempted in one sitting, timed, guidebooks only
- [ ] Every section attempted — nothing skipped
- [ ] Sanity sentence written on each final answer
- [ ] Checking pass run, and what it caught recorded
- [ ] Self-marked against the scheme above
- [ ] Every lost mark tagged
- [ ] Times recorded per question
- [ ] Result written up in `assessments/`

**Next (Day 8):** pumps and pumping systems — 7 of 8 sittings, and the start of
Phase 2, where your electrical background works for you.

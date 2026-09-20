# Day 19 — The Final Week

**Five working days: Mon 21 → Fri 25 September. Exam Saturday 26th, 14:00–16:30.**

**Three missing concepts, then the clock.** Part 0 exists because you were right that the
skipped questions were walls, not the stopwatch.

---

## ⚠️ This page was rewritten on 20 Sep. The first version was wrong.

It opened: *"You are not short of knowledge. You are short of a stopwatch."*

**You said the skipped questions were concept gaps, not time. You were right, and
the repository proves it.** Three things the exam asked for are not in this
curriculum anywhere:

| What you stopped on | Marks | In the curriculum? |
|---|---|---|
| **`gross HR = turbine HR ÷ boiler efficiency`** — N-3 part 2 | 10 | **Nowhere.** Day 12 names all three heat rates and never joins them |
| **Thermal mass of the pipework itself** — N-2 | ~5 | **Nowhere.** Zero mentions in eighteen sessions |
| **Pitot traverse → flow → fan efficiency, as one chain** — N-4(A)(c) | 10 | Both halves taught, **never joined**; Day 9's drill hands you the flow |

**Of the ~24 marks I called a clock problem, about 20 were walls.** And it explains
the three N-4 attempts: you were not being undisciplined, you were **searching for
one you could finish** after the first two hit something untaught. That is the
correct response to a wall.

> ### The seventh prerequisite breach, and a new kind
>
> Mock 3 **passed both checks**. The data-item check asked *"does this topic have a
> rung?"* — heat rate does, fan efficiency does, `m·Cp·ΔT` does. **It never asked
> whether the transitions between them had bridges.**
>
> **The rule is now: check the joins, not just the pieces.** A curriculum can teach
> every noun in a question and still leave it unanswerable.

**Part 0 below is the three missing bridges.** The clock material is still here and
still true — Section III did run 129 and 162 minutes — but it is **Part 2 now**,
because a stopwatch does not help against a wall.

---

# Part 0 — The three missing bridges

## Rung 190 — The heat rate ladder

You wrote `η_turbine = 860/2450 = 35.1%` and `η_unit = 860/2790 = 30.8%`, then
`Unit-1 Unit Heat rate =` and stopped. **You stopped in exactly the right place,
because the next line was never given to you.**

And `860/2450` is not a plant efficiency at all — 2450 is a *turbine* heat rate, so
that ratio is the turbine cycle's efficiency, not the unit's. There was no way
onward from there.

### The three heat rates are a ladder, and each rung divides by one more loss

```
     TURBINE HEAT RATE        heat in the STEAM per kWh generated
             │
             │  ÷ boiler efficiency        ← the boiler's losses enter here
             ▼
     GROSS (UNIT) HEAT RATE   FUEL energy per kWh generated
             │
             │  ÷ (1 − APC)                ← the station's own consumption
             ▼
     NET (STATION) HEAT RATE  FUEL energy per kWh EXPORTED
```

```
    Gross HR = Turbine HR / η_boiler
    Net HR   = Gross HR / (1 − APC)
```

**Each step is a division by a number less than one, so each heat rate is larger
than the one above it.** Turbine < gross < net, always. That ordering is the sanity
check — if your gross comes out below your turbine heat rate, you multiplied.

### Why it divides

Turbine heat rate counts only the heat that **reached the steam**. To get the
*fuel* you must add back what the boiler lost:

```
    fuel energy = steam energy / η_boiler
```

Divide both sides by the same kWh and the heat rates inherit the relationship.
Identical logic to net heat rate: the fuel is unchanged, the kWh you can sell
shrinks by the auxiliary power, so you divide.

### Mock 3's N-3, finished

```
    Unit 1: turbine HR 2450, boiler efficiency 85.8 %
            gross HR = 2450/0.858                      = 2855 kCal/kWh

    Unit 2: gross HR given directly                    = 2790 kCal/kWh
            ⟹ UNIT 2 is more efficient (lower heat rate)

    Station gross = (2855 + 2790)/2                    = 2822 kCal/kWh
    Station net   = 2822/(1 − 0.10)                    = 3136 kCal/kWh
```

> **The trap the question was built on** is that Unit 1 is quoted as a *turbine*
> heat rate and Unit 2 as a *unit* heat rate. **Read the label before comparing.**
> Compare 2450 with 2790 and Unit 1 looks better; it is not, because 2450 does not
> include the boiler.
>
> **This also unblocks Mock 3's N-4(C) part (iv)**, which asks for the station gross
> heat rate and cannot be answered without this ladder — BEE's key says so outright
> and awards marks for stating the missing boiler efficiency as an assumption.

**Self-check.** A unit has a turbine heat rate of 2100, a boiler at 88%, and 7%
auxiliary power. Gross and net heat rate?

<details><summary>Answer</summary>

```
    Gross = 2100/0.88                                  = 2386 kCal/kWh
    Net   = 2386/0.93                                  = 2566 kCal/kWh
```
2100 < 2386 < 2566 ✓ — the ladder only ever goes up.
</details>

---

## Rung 191 — Heating a system heats its container

Nowhere in eighteen sessions did anything say this, and Mock 3's N-2 was built on
it. **It is one sentence:**

> **When a question raises the temperature of a *system*, every mass in that system
> is raised — the fluid AND the metal holding it.**

```
    Q = Σ (m · Cp · ΔT)   over every material present
      = m_fluid · Cp_fluid · ΔT  +  m_metal · Cp_metal · ΔT
```

### Why it is never negligible, even though steel's Cp is low

Steel's specific heat is 0.12 — one-eighth of water's. It feels ignorable. **It is
not, because there is more steel than water:**

```
    water   (π/4)(0.1)² × 2000 × 1000                  = 15 708 kg
    steel   (π/4)(0.108² − 0.1²) × 2000 × 8000         = 20 910 kg   ← 33 % MORE

    water   15 708 × 1.00 × 90                         = 14,13,717 kCal   (86 %)
    steel   20 910 × 0.12 × 90                         =   2,25,833 kCal   (14 %)
                                                         ─────────────
                                                         16,39,550 kCal
```

**A pipe wall only 4 mm thick outweighs the water inside it**, because steel is
eight times denser. Low Cp, high mass — they nearly cancel, and 14% is what
survives.

### The annulus, which is where the arithmetic goes wrong

```
    metal volume = (π/4)(D_outer² − D_inner²) × L        NOT (π/4) D_outer² L
    fluid volume = (π/4) D_inner² × L                    with D, not R
```

**And `(π/4)D²` never `πD²`** — that was the 4× error in your N-2.

### Where else this appears

| Situation | The container that also heats |
|---|---|
| Hot water / thermic fluid circuit start-up | the piping |
| Furnace heat-up from cold | the refractory lining |
| Batch reactor or autoclave | the vessel wall |
| Boiler cold start | drum, tubes, headers |

**The cue in the question:** any sentence saying *"the system also gets heated"*,
*"from cold"*, *"after a shutdown"*, or *"during start-up"*. Mock 3's N-2 said
*"the entire piping system carrying water also gets heated from 50 °C to 140 °C"* —
that clause is an instruction to compute a second mass.

---

## Rung 192 — Pitot traverse to fan efficiency, as one chain

You wrote `Q × ΔP/102`, then `= 4.04 √ΔP`, and stopped. **Those are two different
formulas using two different pressures**, and the curriculum taught them 40 pages
apart without ever connecting them.

### The collision: two pressures both called "Δp"

```
    DYNAMIC pressure  →  VELOCITY       v = C_p √(2g·Δp_dynamic/ρ)
                                        (14.5 mmWC in the 21st's question)

    STATIC pressure   →  FAN POWER      P = Q × Δp_static/102
                                        (30 − (−850) = 880 mmWC)
```

**A pitot's dynamic tapping gives you velocity. The fan's static rise gives you
power. They are never the same number**, and in that question they differ by 60×.

*(`v = 4.04√Δp` is the same velocity formula pre-solved for standard air at
ρ = 1.2. In a hot duct ρ is not 1.2, so you must use the full form.)*

### The full chain, in order

```
   1.  CORRECT THE DENSITY      ρ = ρ_NTP × (P_bar + P_static)/10 334 × 273/(273+t)
                                    P_static is SIGNED — suction is negative

   2.  VELOCITY                 v = C_p √(2g · Δp_dynamic / ρ)

   3.  AREA                     A = π D²/4

   4.  FLOW                     Q = v × A                       m³/s

   5.  FAN STATIC PRESSURE      Δp_static = p_outlet − p_inlet   mmWC
                                            (mind the signs)

   6.  EFFICIENCY               η = Q × Δp_static
                                    ──────────────────────────── × 100
                                    102 × motor kW × η_motor
```

**Step 6's denominator is SHAFT power.** The question gives motor input, so multiply
by the motor efficiency to get down to the shaft. `102` is `1000/9.81` and needs
**m³/s and mmWC** — Rung 173.

### Mock 3's N-4(A) part (c), worked

```
   1.  ρ = 1.35 × (10 323 − 850)/10 323 × 273/(273 + 70)  = 0.986 kg/m³
   2.  v = 0.86 √(2 × 9.81 × 14.5/0.986)                  = 14.61 m/s
   3.  A = π(3.5)²/4                                      = 9.621 m²
   4.  Q = 14.61 × 9.621                                  = 140.6 m³/s
   5.  Δp_static = 30 − (−850)                            = 880 mmWC
   6.  η = 140.6 × 880/(102 × 1450 × 0.95) × 100          = 88.0 %
```

> **Day 9's Drill 51 handed you the flow** — "a fan handles 166.6 m³/s per inlet" —
> so you never had to *get* a flow from a traverse. Day 13's Rung 137B does steps
> 1–4 but stops at mass flow for a heat balance. **Steps 1–6 in sequence appear
> here for the first time.** That is the gap, and it is mine.

**Sanity anchors:** a large ID or process fan runs **75–88%** static efficiency;
duct velocities are **10–20 m/s**. If either lands outside, check step 1's sign.

---

# Part 2 — The clock, made physical

## Rung 193 — Write the four deadlines before you write anything else

Rung 170 said "25 minutes maximum". In Mock 3 it held on N-1 (you left at 29 and
moved) and failed completely on N-3 (45 minutes, unfinished). **An intention is not
a mechanism.**

**In the first sixty seconds of the exam, before reading a single question, write
this down the margin of your answer sheet:**

```
        start 14:00
        Sec I + II   →  14:20
        N-1 ends     →  14:45
        N-2 ends     →  15:10
        N-3 ends     →  15:35
        N-4 ends     →  16:00
        check        →  16:30
```

*(Adjust to the real start time. The paper is 150 minutes: 20 for Sections I and
II, 25 per long question, 10 to check, 20 spare.)*

**These are clock times, not durations.** A duration needs arithmetic under
pressure; a clock time needs a glance. When your watch passes the number on the
page, **you stop and move — mid-line if necessary.** Leave four blank lines and go.

> **Why mid-line is safe.** A half-finished question you return to costs thirty
> seconds to pick up. A question never opened costs everything in it.

## Rung 194 — Choose your N-4 once, in ninety seconds, and never revisit

**You answered N-4 three times. Only one can be submitted.** Thirty-one minutes,
zero marks.

**The protocol, done once, before N-1:**

1. **Read all four N-4 options — headings and the "calculate the following" list
   only.** Ninety seconds, not more.
2. Score each on one question: **"how many of these sub-parts can I start right
   now, without thinking?"**
3. **Pick the highest. Write "N-4 = (B)" at the top of your sheet. Circle it.**
4. **That decision is final.** If it turns out badly, you finish it badly and take
   the partial marks. You do not start another.

**Why this is right even when the choice is wrong.** A 20-mark question done
half-well scores 10–13. Two questions each done a third of the way score 6–8
*combined*, because the marks cluster in the later parts that build on the earlier
ones. **Switching is almost always worse than finishing.**

> **Pick the option whose *first* parts you can do.** Mock 3's N-4(C) gave you
> 4 marks on part (i) in two minutes. Its part (i) was reachable; that is the
> signal, not how interesting the question looks.

## Rung 195 — Allocate to the cheapest marks first, not the most interesting

**Mock 3's clearest single lesson.** N-2 was the simplest twenty marks on the
paper — two `m·Cp·ΔT` calculations and a division. It got **16 minutes** and came
back with two errors. N-3 was the most expensive — eight loss terms from an
ultimate analysis — and it got **45 minutes** and stopped at part 2 of 4.

**Before starting Section III, spend two minutes ranking the four long questions by
how fast the marks come.** Then do them in that order.

| Signal that a question is CHEAP | Signal that it is EXPENSIVE |
|---|---|
| Two or three formulas you know cold | An ultimate analysis (7–8 loss terms) |
| Data table maps 1:1 onto the formula | A pitot traverse with density correction |
| Parts are independent | Every part feeds the next |
| `m·Cp·ΔT`, affinity laws, direct efficiency | A full heat balance or mass balance |

**Doing the cheap ones first buys two things:** the marks are banked before the
clock gets tight, and you arrive at the expensive question knowing exactly how many
minutes you can afford.

**You already know the expensive one when you see it.** An indirect-method boiler
question is always 35–45 minutes. If it is compulsory, do it **last** and cap it
hard.

---

# Part 3 — The six slips, drilled

Fifteen minutes each. Do them on paper, not in your head.

## Rung 196 — Six substitutions that cost 19 marks

### 1. Pipe volume: `πD²L` is four times too big

```
    V = π r² L        with r = D/2
      = (π/4) D² L
```

**100 mm pipe, 2 km: 15.7 m³.** Not 62.8. A pipe you can grip does not hold three
road tankers. *(Mock 3 N-2.)*

### 2. Heating a system heats its metal too

A pressurised water circuit at start-up contains **more steel than water**:

```
    water   π/4 (0.1)² × 2000 × 1000                 = 15,708 kg
    steel   π/4 (0.108² − 0.1²) × 2000 × 8000        = 20,910 kg   ← 33 % MORE
```

Low specific heat (0.12) still leaves it at **14% of the start-up load**. Any
question that says "the piping also gets heated" is telling you to compute two
masses. *(Mock 3 N-2.)*

### 3. `m_dfg` minus the ash, for coal and biomass

```
    m_dfg = (AAS + 1) + N₂_fuel − 9H₂ − M − ASH
```

`(AAS + 1)` assumes the whole kilogram of fuel becomes gas. **Ash does not** — it
leaves through the furnace bottom, which is what the bottom-ash loss already
counts. At 8% ash it is worth 0.13 points; **at 35% ash it is worth 0.6 and a
mark.** *(Rung 168; Mock 1 and Mock 3.)*

### 4. Same units on both sides of a ratio

```
    L₅ = [%CO/(%CO + %CO₂)] × C × 5654/GCV × 100
```

**150 ppm = 0.015%, and CO₂ is 7%, not 0.07.** Both are percentages or both are
fractions — never one of each. And the constant is **5654** kCal per kg of carbon
burnt only to CO, not 565. *(Mock 3 N-3.)*

### 5. Wet steam: `h = h_f + x·(h_g − h_f)`

A condenser table gives `h_f` and `h_g`. **If a dryness fraction is given, the
exhaust is wet and you must apply it:**

```
    h_exhaust = 49 + 0.98 × (610 − 49)                = 599 kCal/kg
```

Using 610 directly cost 5 marks in Mock 3's N-4(C). **Unused data is the tell** —
the 0.98 was printed for a reason. *(Day 1 wet steam; Day 4 isentropic.)*

### 6. Turbine heat rate: both heat inputs, and generator output

```
                 MS flow (h_MS − h_fw)  +  RH flow (h_HRH − h_CRH)
    Turbine HR = ───────────────────────────────────────────────────
                            GENERATOR output, kW
```

**The boiler heats the steam twice** on a reheat unit — main steam and reheat. And
heat rate is per kWh **sent out**, so the denominator is the generator's MW
(after gearbox and generator efficiency), not the turbine shaft's. *(Mock 3
N-4(C): 1831 vs 2165 — a 15% error from the two together.)*

### Bonus — moisture content vs moisture regain

```
    moisture CONTENT  = water / WET mass   →  bone dry = wet × (1 − m)
                                          →  wet = bone dry / (1 − m)   ← DIVIDE
    moisture REGAIN   = water / DRY mass   →  water = dry × m           (multiply)
```

**BEE's papers always mean content.** Divide by `(1 − m)`, never multiply by `m`.
*(Rung 148; Mock 3 N-4(B).)*

---

## Rung 197 — Two directions from Section I

**Reheat is not regenerative.**

```
    REHEAT        turbine → BOILER → turbine    re-superheats between stages;
                                                raises mean temperature of heat
                                                addition, keeps LP exhaust dry
    REGENERATIVE  turbine → FEEDWATER HEATERS   bleeds steam to preheat feedwater;
                                                less fuel per kg of steam
```

Both are on the same large unit. **The word "heaters" in the statement means
regenerative**, whatever the sentence calls itself.

**More extraction raises EUF, it does not lower it.**

```
    EUF = (power + useful process heat) / fuel energy
```

More steam to the extractions = more useful heat for the same fuel. Power drops a
little; heat rises more; **EUF counts both equally, so EUF rises.** This is the same
fact as "a back-pressure set's heat rate looks terrible and its EUF looks
excellent" — heat rate ignores the heat.

---

# Part 4 — The exam-day card

## Rung 198 — What to write in the first ninety seconds

**Before reading any question.** Guidebooks tabbed, watch on the desk.

```
  ──────────────────────────────────────────────────────────────
   DEADLINES        Sec I+II →  ____     N-3 ends →  ____
                    N-1 ends →  ____     N-4 ends →  ____
                    N-2 ends →  ____     check    →  ____

   N-4 = ( __ )     chosen once, final

   CONSTANTS
     1 kWh = 860 kCal      1 TR = 3024 kCal/h = 3.517 kW
     1 kCal = 4.186 kJ  →  kJ ÷ 4.186        water = 1.0 kCal/kg°C
     367 = 3600/9.81 (m³/h, m)     102 = 1000/9.81 (m³/s, mmWC)
     36.7 = 3600/98.067 (compressor)         540 kCal/kg latent

   DIRECTIONS
     heat rate ↓ = better       kW/TR ↓ = better      COP ↑ = better
     approach / TTD / DCA ↓ = better
     net heat rate = gross/(1 − APC)     always WORSE than gross
     STEC per kg CLINKER · SEEC per tonne CEMENT
     ID fan > FD fan       dew point ↓ = drier

   BEFORE I COMPARE TWO OPTIONS: what is the SERVICE that stays the same?
   BEFORE I DIFFERENCE TWO CASES: is the conversion factor the same in both?
  ──────────────────────────────────────────────────────────────
```

**Ninety seconds. It pays for itself the first time you avoid one inversion.**

## Rung 199 — The checking pass, final form

Ten minutes at the end. **Every item has cost you marks at least once.**

```
  ☐ 1.  Did I produce every quantity the question NAMED?
  ☐ 2.  Is every total ≥ its largest component?
  ☐ 3.  Did every part I computed actually reach its total?
  ☐ 4.  Stock or flow — does the unit match what was asked?
  ☐ 5.  Is every answer inside its sanity anchor?
  ☐ 6.  Any inverse quantity — converted before comparing?
  ☐ 7.  Two cases with different constants — converted each before differencing?
  ☐ 8.  Any data item I never used?  (dryness fraction, ash %, a second mass)
  ☐ 9.  Did I answer the question's WORDING — "whether", "the reduction", "in MW"?
  ☐ 10. Every long question opened, and the chosen N-4 the only one submitted?
```

**Item 8 is new and it would have caught three of Mock 3's six slips** — the
dryness fraction, the ash, and the steel pipe.

---

# The five days — superseded 20 Sep

> **The day-by-day plan now lives in `curriculum/revision-plan.md`.**
>
> She proposed a **topic-wise** week instead of re-doing Mock 3 question by
> question: Monday cogeneration, Tuesday HVAC and cooling towers, Wednesday pumps
> and fans and compressed air, Thursday boilers, Friday miscellaneous.
>
> **Accepted, and it is the better plan.** The Mock 3 stalls were topic-shaped, not
> paper-shaped — a heat-rate join, a thermal-mass idea, a fan chain. Drilling one
> topic across ten sittings builds pattern recognition a fourth full paper would
> not.
>
> **The three bridges fit her days without being moved:** the heat rate ladder is
> Monday's (it *is* cogeneration and power plant), the pitot chain is Wednesday's
> (it is a fan question), the container's thermal mass is Thursday's (a hot-water
> boiler start-up is a boiler question).
>
> **The one trade, named:** it drops the last full-length timed paper. So every
> 20-marker in the revision plan is worked **on a timer at 25 minutes, hard stop** —
> the clock discipline goes inside the topic work rather than needing its own day.
>
> **Two date errors corrected at the same time.** This table had labelled 20 Sep
> "Saturday"; it is a **Sunday**, so every label was off by one. And
> `exam-brief.md` said the exam was a *Friday*; **26 September 2026 is a
> Saturday**. Date right, weekday wrong — check your admit card.

**Rungs 190–199 below all stand.** Part 0's three bridges are the priority; Parts
2–4 (the clock, the six slips, the exam card) are unchanged.

> **Friday's stop time is not a suggestion.** You have sat three full papers in
> three weeks; the marginal value of a fourth on the eve is negative.
>
> **See `curriculum/revision-plan.md` for the day-by-day question lists.**

---

## What the record says, going in

- **Every Book-4 chapter taught**, 15 of 15, plus four gaps closed after a full
  sweep of every equipment noun in ten sittings, plus **three joins between taught
  topics** closed here.
- **Three full mocks**, all passed: 84 · 73 · 58, against a pass mark of 50.
- Eight errors found in BEE's own model answers.
- **Two curriculum gaps found by you** — the air preheater on 09 Sep, and these
  three bridges on 20 Sep. Both times by auditing the curriculum against a paper,
  and both times against my stated diagnosis.

**The corrected reading of Mock 3:** about 20 of the 24 unclaimed marks were behind
walls that are now gone. The clock material in Part 2 still stands — 162 minutes is
162 minutes — but it is second, not first.

> **On pushing back.** You have contradicted my diagnosis three times: the mock's
> "unseen" claim, the air preheater, and now this. **You were right all three
> times.** Keep doing it in the exam — against the paper, not against me. The
> question that seems to need something you were never given is usually a question
> where you are missing one bridge, and naming it on the page earns method marks
> even when the number never comes.

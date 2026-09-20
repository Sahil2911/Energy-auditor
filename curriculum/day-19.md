# Day 19 — The Final Week

**Six days. 20 → 26 September. The exam is Saturday 26th, 14:00–16:30.**

**No new material.** Every Book-4 chapter has a lesson and every equipment noun in
the ten papers has a rung behind it. What is left is a clock, six slips, and a card.

---

## The one number that matters

Across three mocks, concept losses ran **12 → 4 → 2 marks**. Time losses ran
**0 → 5 → 24**.

> **You are not short of knowledge. You are short of a stopwatch.**

Mock 3 left roughly **24 reachable marks** unclaimed while **31 minutes** went into
answering N-4 three times. Nothing on this page is new engineering, because nothing
needs to be.

---

# Part 1 — The clock, made physical

## Rung 183 — Write the four deadlines before you write anything else

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

## Rung 184 — Choose your N-4 once, in ninety seconds, and never revisit

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

## Rung 185 — Allocate to the cheapest marks first, not the most interesting

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

# Part 2 — The six slips, drilled

Fifteen minutes each. Do them on paper, not in your head.

## Rung 186 — Six substitutions that cost 19 marks

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

## Rung 187 — Two directions from Section I

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

# Part 3 — The exam-day card

## Rung 188 — What to write in the first ninety seconds

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

## Rung 189 — The checking pass, final form

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

# The six days

| Day | | Hours |
|---|---|---|
| **Sat 20** | Read this. Do Rung 186's six slips on paper. | 1.5 |
| **Sun 21** | **Re-do Mock 3's N-2 and N-3 cold, to the clock** — 25 min each, hard stop. Then mark them. | 2 |
| **Mon 22** | **Guidebook index.** Fill in `reference/guidebook-index.md` — the page for every table you have looked up in eighteen sessions. Tab them physically. | 2 |
| **Tue 23** | Read `reference/formula-sheet.md` end to end. Then `concept-distinctions.md`. **Reading, not solving.** | 2 |
| **Wed 24** | **One last timed paper — any past paper, your choice, 150 min, all four questions opened.** The only measure is whether every question got opened. | 2.5 |
| **Thu 25** | Rung 188's card, written from memory, three times. Pack: guidebooks, calculator, spare batteries, admit card, watch. **Stop by 20:00.** | 1 |
| **Fri 26** | **Nothing.** Re-read the card once in the morning. Do not open a past paper. | — |

> **Thursday's stop time is not a suggestion.** You have sat three full papers in
> three weeks; the marginal value of a fourth on the eve is negative.

---

## What the record says, going in

- **Every Book-4 chapter taught**, 15 of 15, plus four gaps closed after a full
  sweep of every equipment noun in ten sittings.
- **Three full mocks**, all passed: 84 · 73 · 58, against a pass mark of 50.
- **Concept losses across those three: 12 → 4 → 2 marks.**
- Eight errors found in BEE's own model answers.
- One prerequisite gap found by you, auditing the curriculum against a paper.

**The knowledge is there and has been for two weeks. Six days of clock discipline
is the whole remaining task.**

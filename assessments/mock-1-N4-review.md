# Mock 1, N-4(B) Review — DRI Steel Plant

**08:44 → 09:14, thirty minutes.** 24th sitting N-4(D), 20 marks.

## Score: **20 / 20**

And more than that — her arithmetic is **better than BEE's own model answer**.

---

## The experiment, and its result

Mock 1's N-4 deliberately offered three options: one HVAC question she had drilled
the concepts for, and **two sector questions she had only read about**. The note in
the paper said:

> *"You judged that the sector chapters can be handled from the book plus general
> concepts rather than from drilled practice. Options B and C test exactly that."*

**She picked a sector question and scored full marks on it in thirty minutes.**

Her judgement was right, and the plan change was the correct call. The sector
chapters do not need drilling; they need the concepts underneath them — heat rate
as a sourcing conversion, yield chains, specific energy denominators — and those
were already in place from Days 6, 11 and 12.

---

## Part 1 — Base year, 12.409 million kCal/tonne ✓

```
  SEC of sponge iron = 300[(1300 × 6000) + (110 × 860/0.2606)]
                     = 300 × 8 163 000              = 2448.903 million kCal/day
  Ingots             = 0.85 × 300                   = 255 t/day
  SEC for ingots     = 850 × 860/0.2606             = 2.805 million kCal/t
                     × 255                          =  715.275 million kCal/day
  Plant SEC = (2448.903 + 715.275)/255              = 12.409 million kCal/t ingot
```

**A sharp piece of reading in the margin:** *"850 is not SEC but Specific Power
Consumption."* Exactly right. The data table calls it "SEC of Steel Melting Shop"
but the units are kWh/tonne — it is a *power* consumption, and it only becomes a
specific *energy* consumption after the heat rate is applied. Noticing that the
paper's own label is loose is the habit that stops you multiplying by 860 out of
reflex.

## Part 2 — Assessment year, 11.01 million kCal/tonne ✓

```
  SEC of sponge iron = 300[(1150 × 6200) + (95 × 860/0.2774)]
                     = 2227.356 million kCal/day
  SEC for ingots     = 830 × 860/0.2774             = 2.573 million kCal/t
  Plant SEC = 2227.356/(0.88 × 300) + 2.573         = 11.01 million kCal/t ingot
```

**Neater than the model answer.** Instead of computing the SMS energy for the day
and then dividing the sum by the ingot tonnage, she divided the sponge iron energy
by the ingots and added the ingot SEC straight on. Algebraically identical, one
line shorter, one fewer place to lose a digit.

## Part 3 — 41.54 TPD ✓ against the model answer's method

```
  Total energy saving = (2448.903 − 2227.356) + (715.275 − 2.573 × 264)
                      = 221.547 + 36.003            = 257.55 million kCal/day
  Coal reduction      = 257.55 × 10⁶/(6200 × 10³)   = 41.54 TPD
```

**BEE's model answer states 41.85 TPD, and it is wrong by its own arithmetic.**

```
  Model answer:  "Energy Saving in Steel Melting Plant = (2.805 × 255 − 2.573 × 264)
                  = 38.07 million kCal/day"

  Actually:       715.275 − 679.272 = 36.00,  not 38.07
  So the total is 221.4 + 36.00 = 257.4,  not 259.47
  And the coal figure is 41.5 TPD,  not 41.85
```

Her 41.54 is the model answer's method executed correctly. **Full marks, and one
more error in an official key** — the sixth this curriculum has found.

---

## But there is something underneath this question worth more than the marks

**The model answer's method is physically wrong**, and it is worth seeing why,
because the flaw is a general one.

The question asks for the **reduction in coal consumption in tonnes per day**. So
compute the coal tonnage in each year and subtract:

```
  Base year       coal = (2448.903 + 715.275) × 10⁶ / 6000 / 1000   = 527.37 TPD
  Assessment year coal = (2227.356 + 679.272) × 10⁶ / 6200 / 1000   = 468.82 TPD
  Reduction                                                          =  58.55 TPD
```

Cross-checked the long way, stream by stream, and it agrees exactly:

```
  Base:        DRI 300 × 1.3   = 390.0  +  CPP 249 750 kWh × 3300/6000/1000 = 137.37
                                                                     total = 527.37
  Assessment:  DRI 300 × 1.15  = 345.0  +  CPP 247 620 kWh × 3100/6200/1000 = 123.82
                                                                     total = 468.82
```

**58.55, not 41.5.** The gap is 40%.

### Where the model answer loses 17 tonnes a day

It computes the **energy** saving first, then converts once, at one GCV. That is
only valid if the GCV is the same in both years. **It is not** — the coal improved
from 6000 to 6200 kCal/kg, and that improvement saves coal all by itself.

Decompose the true 58.55 and both halves appear:

```
   using less energy (at the base year's 6000 GCV)  = 42.92 TPD
   burning better coal (6000 → 6200, same energy)   = 15.63 TPD
                                                      ───────────
                                                       58.55 TPD
```

The model answer's 41.5 is essentially the first term only. **The 15.6 tonnes a day
that better coal saves are invisible to it**, because differencing the energy first
throws that information away.

### The general rule — and it belongs with the reciprocal traps

> **When the conversion factor differs between two cases, convert each case first,
> then take the difference. Never difference first and convert once.**
>
> ```
>     Δ(E)/k  ≠  Δ(E/k)      whenever k is not the same on both sides
> ```

The distributive law you rely on without thinking only holds when `k` is constant.
The same trap is waiting in:

- coal or fuel savings when the **GCV** changes between the two cases
- cost savings when the **tariff** differs between the two cases
- CO₂ reductions when the **emission factor** differs between two fuels
- TOE or e-certificate calculations across a year in which a fuel was switched

### What to write in the exam

The examiner marks against the model answer, so give them both and let the working
speak:

```
   Base year coal      = 527.37 TPD
   Assessment year coal = 468.82 TPD
   REDUCTION           = 58.55 TPD

   (Converting the energy saving of 257.55 million kCal/day at the assessment
    year's GCV of 6200 gives 41.5 TPD; the tonnage difference above is used
    because the GCV changes between the two years.)
```

The primary answer directly answers "reduction in coal consumption **in tonnes per
day**", the parenthesis contains the model answer's number so a marker with the key
in hand finds it, and the one clause explains the difference. **You cannot lose
marks for that layout, and you may gain one.**

---

## Timing

Thirty minutes for 20 marks against a 25-minute budget — **1.2× budget**, and this
was a chapter she had read once and never drilled, worked from the guidebook. On
the day, a 1.2× on your chosen N-4 is comfortably absorbed.

---

## Error tally

| # | Error | Type | Fix |
|---|---|---|---|
| — | None against the model answer | — | — |
| ⓘ | Followed the model answer's flawed conversion (as intended) | **Concept — general** | Convert each case, then difference. Now `concept-distinctions.md` entry 14 |

---

## Verdict

**20/20 on a sector question, from the book, cold.** The hypothesis behind the plan
change is confirmed: the sector chapters are reachable with the concepts already
built, and drilling them would have been time better spent elsewhere.

The remaining Mock 1 questions — Section I, Section II, N-1, N-2, N-3 — are
outstanding. **Sit them in one 2-hour block** rather than singly, because the thing
Mock 1 is really measuring is whether the pace holds across a whole paper, and that
cannot be measured a question at a time.

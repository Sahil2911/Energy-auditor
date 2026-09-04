# Assessment — Day 10

Two questions: the 17th sitting N-1 (cooling tower, 20 marks) and the 24th Set B
L-2 pump question outstanding from Day 8.

---

## 17th N-1, cooling tower — strong, one part unreachable

**Time: 18:17 → 18:50, thirty-three minutes** (target 30).

Everything attempted is correct:

```
    Before: effectiveness 60% → range 6 °C, T_out 29 °C, 500 m³/hr
    After:  effectiveness 70% → range 7 °C, T_out 28 °C, 428.571 m³/hr

    Head = 40 − (−1) = 41 m
    Hydraulic:   55.858 → 47.879 kW
    Motor input: 116.226 → 101.503 kW  (reduction 14.723 kW)

    Evaporation: 4.59 m³/hr both cases
    Blowdown:    1.84 → 1.15 m³/hr
    Makeup:      154.2 → 137.76 m³/day
```

**The suction head sign was handled correctly** — 4 kg/cm²(g) is 40 m, suction
−1 m, head 41 m not 39. Flagged as this chapter's sign trap on Day 8; it did not
catch her.

### An interpretation mark left on the table

Evaporation comes out **identical** before and after — 4.59 m³/hr both times.

That is not coincidence. Evaporation follows heat rejected, and `m × range = Q` is
fixed by the process. Raising effectiveness changes flow and range in exactly
inverse proportion, so evaporation cannot move. **The entire water saving comes
from the COC change and none from the refurbishment.**

Stating that would earn interpretation marks. It is visible in her own two numbers
and went uncommented.

### Two gaps

1. **Makeup *reduction* not stated** — both figures computed, but the question asks
   for the difference: 16.52 kL/day. **Second occurrence** of the Day 8 tracer
   pattern.
2. **Fan power not reached** — "Air Flow =" written and left blank. See the Tutor
   fault below.

---

## 24th Set B L-2, pump — **5 / 5**

**Time: 19:10 → 19:15. Five minutes** (target 8).

```
    η_hydraulic = (QH/367 × 1000) / (√3·V·I·cos φ − 19,500) = 81.83 %
    η_overall   = (QH/367 × 1000) / (√3·V·I·cos φ)          = 76.92 %
```

Verified at 81.73% and 76.83%. The model's 81.4% and 76.5% come from rounding
hydraulic power to 249 kW — **hers carries full precision and is the better
answer.**

**Sixth reciprocal-family catch.** She first wrote 76.921 for the *hydraulic*
efficiency, struck it out, and replaced it with 81.828 — recognising that pump
efficiency measures against motor **output** (after the 19.5 kW of losses) while
overall efficiency measures against **input**. That distinction is the question.

---

## Tutor fault — fifth prerequisite breach

The fan part needs the **air flow**, which comes from the **L/G ratio**. Rung 105b
did not exist when the question was set, and the prerequisite check passed anyway
because "fan power" mapped to Day 9's Rung 84 — while the step that gets you *to*
the fan did not exist.

| Day | Question | Untaught | Marks |
|---|---|---|---|
| 1 | 18th N-1 | Indirect method | 18/20 |
| 4 | 18th N-2 | Gas turbine cogeneration | 20/20 |
| 5 | 25th N-1 | Pump, fan, chiller SEC | 14/20 |
| 7 | 17th N-2 | Chiller COP | 10/20 |
| **10** | **17th N-1** | **Air flow from L/G** | **~5/20** |

**Fixed:** Rung 105b added to Day 10 with the full chain and a drill, verified
against the model — 28.43 kW and 24.82 kW fan motor input, total reduction
18.13 kW.

**Process change:** sub-part checking is not sufficient. The framework now also
requires that **every quantity the question supplies has a taught use**. This
question handed over an L/G ratio, an air density and a fan pressure; none of the
three appeared anywhere in the lesson. Sub-parts are ambiguous; a data table is not.

## Tags

| Tag | Note |
|---|---|
| Method — question reading | Makeup reduction not stated (2nd occurrence) |
| **Curriculum** | Air flow from L/G, not taught |
| Arithmetic, units, concept | 0 |

## Verdict

Chapter 5 complete. Book-4 chapters 1–8 now done. Both questions inside or at
budget, and the pump question beat the published answer.

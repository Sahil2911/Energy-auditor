# Day 12 Review — Power Plants, Heat Rate and PAT

**Attempted 05 Sep. Block C 14:02 → 14:30. Drills 14:32 → 14:39.**

| Question | Marks | Score | Time | Budget |
|---|---|---|---|---|
| 23rd N-1 — pet coke boiler, ER, flash steam | 20 | **20** | 28 min | 30 |
| 25th L-1 — PAT e-certificates | 5 | **5** | 4 min | 8 |
| 19th L-1 — two-plant comparison | 5 | **3** | 3 min | 8 |
| **Total** | **30** | **28** | 35 min | 46 |

---

## Block C — 20/20, and the checking pass earned its keep

Every value reproduces the model answer:

| | Hers | Verified |
|---|---|---|
| Theoretical air | 11.649 | 11.649 ✓ |
| Excess air | 40% | 40% ✓ |
| Actual air supplied | 16.309 | 16.309 ✓ |
| Dry flue gas mass | 16.971 | 16.971 ✓ |
| L₁ dry flue gas | 12.983% | 12.982% ✓ |
| L₂ hydrogen | 2.653% | ✓ |
| L₃ fuel moisture | 0.115% | ✓ |
| L₄ air humidity | 0.395% | ✓ |
| L₅ radiation / L₆ unburnt | 1% / 0.5% | ✓ |
| **Efficiency** | **82.354%** | **82.355%** ✓ |
| Evaporation ratio | 11.15 | ✓ |
| Flash steam fraction | 0.441 kg/kg | ✓ |

**Two errors were made and both were caught on the page.**

1. Theoretical air first written as **27.153**, struck out, corrected to **11.649**.
2. `m_dfg` written as 16.9971 but **17.309 carried into L₁**, giving 13.241 — struck
   out, re-substituted with 16.971, giving 12.983.

The second is the more valuable catch. A wrong number substituted one line after it
was correctly computed is the hardest kind to find, because the working *looks*
consistent. She found it, and the correction propagated cleanly into a right final
efficiency. **That is the checking pass doing exactly the job it was added for.**

Flash steam — taught for the first time in Rung 132, from an energy balance rather
than a quoted formula — was applied correctly at the first attempt, and she wrote
`hg₂ − hf₂` rather than reaching for a tabulated `hfg`. Sound.

**28 minutes for 20 marks against a 30-minute budget.** Eighth consecutive timed
question at or inside budget.

---

## Drill 65 — 25th L-1 PAT — 5/5 in four minutes

```
  Assessment year NHR = 2300/0.92          = 2500 kCal/kWh
  Reduction           = 2600 − 2500        = 100 kCal/kWh
  e-Certificates      = 100 × 5000 × 10⁶/10⁷ = 50 000
```

Correct, and the MU → kWh and kCal → TOE conversions were handled in one line
without an intermediate slip. Four minutes against an eight-minute budget.

**She also corrected my pointer.** Day 12 sent her to "25th sitting L-2"; in
`papers/25-2.pdf` (Pink set) the PAT question is **L-1**. She wrote *"L-1 not L-2"*
at the top of the page. My error — the sets reorder the questions, and I quoted the
Green-set position against the Pink-set paper. `curriculum/day-12.md` corrected.

---

## Drill 64 — 19th L-1 — 3/5, and the finding of this session

Her work:

```
  NHR of plant A = 2400/0.92 = 2608.696 kCal/kWh
  Hence, NHR of Plant A (2608.696) is higher than the same of Plant B (2500).
  ⇒ Plant A is more efficient.                                          ✗
```

**The answer is Plant B.**

Look carefully at what happened, because it is not the error the lesson warned
about.

Day 12 predicted candidates would compare **2400 against 2500** and pick A. She did
not. She converted A to a net basis, correctly, and then wrote a correct comparison
sentence — *A's heat rate is higher than B's*. Everything up to that point is right,
including the step most candidates miss.

**Then the inference flipped.** "Higher heat rate" became "more efficient".

### Diagnosis

This is not a knowledge gap about heat rate, and it is not carelessness about the
basis. It is the **reciprocal family, in its purest form and uncaught** — the first
uncaught member since Day 1.

Heat rate is *inverse* efficiency. She knows the formula `η = 860/HR`; Rung 123
teaches it and she used the surrounding material perfectly all afternoon. What she
did not do is apply the direction: on an inverse quantity, **bigger is worse**, and
that reverses the ordinary reading of a comparison. Every other quantity in this
paper — efficiency, COP, evaporation ratio, effectiveness — runs the normal way, so
the habit of "the bigger number wins" is heavily reinforced and fires automatically.

Note this is *sharper* than Trend 2 from the phase-2 checkpoint. Trend 2 was right
work with a **missing** final sentence. This is right work with an **inverted** one,
which costs more marks and reads worse to an examiner, because the conclusion
directly contradicts the line above it.

### The fix, and it generalises

Do not compare on an inverse quantity. **Convert both sides to the direct quantity
first**, where "higher is better" is unambiguous:

```
    Plant A:  η = 860/2608.7 = 32.97 %
    Plant B:  η = 860/2500   = 34.40 %      →  B is better
```

Two extra divisions, and the direction cannot invert, because efficiency is a
quantity nobody misreads.

The same rule covers three pairs already in this curriculum:

| Inverse quantity (lower is better) | Direct quantity (higher is better) |
|---|---|
| Heat rate, kCal/kWh | Efficiency, `860/HR` |
| kW/TR | COP, `3024/(kW/TR × 860)` |
| Specific energy consumption | Production per unit energy |

**Tutor action taken:** Day 12 Rung 123 now carries an explicit direction rule with
the 32.97 / 34.40 anchor, and the drill answer states the conversion rather than
just the verdict. `reference/reciprocal-traps.md` entry 11 added.

---

## Error tally

| # | Error | Type | Fix |
|---|---|---|---|
| 1 | Theoretical air 27.153 | Arithmetic | **Caught on the page** |
| 2 | m_dfg 17.309 carried into L₁ | Method | **Caught on the page** |
| 3 | Higher heat rate read as more efficient | **Concept — direction** | Convert to efficiency before comparing |

Two caught, one not. The uncaught one is a concept-direction error, which is the
type worth spending a rung on — and one has been added.

---

## Verdict

**28/30, and chapter 11 is secure.** The 20-mark question — six losses, an
evaporation ratio and a flash steam fraction she had never seen before that
morning — came back complete, correct and inside budget, with two self-caught
errors along the way.

The three marks lost are a single inverted inference on a one-line question, not a
gap in the material. It is worth exactly one rung of attention and no more anxiety
than that. **The pattern to watch is whether the inversion she gets wrong is one
she has already met** — and this one, she now has.

**Book-4 chapter 11 complete. Chapters done: 1–9, 11.**

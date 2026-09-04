# Assessment — Day 6

**Question:** 24th sitting L-2, re-rolling reheating furnace. 5 marks.
**Time: 20:39 → 20:56, seventeen minutes** (target 10).

## Score: 5 / 5

```
    η              = 38.302 %                 ✓
    SEC            = 40.429 kg/tonne          ✓
    Cost, oil      = Rs 2,223.595/tonne       ✓
    Cost, electric = Rs 1,788.303/tonne       ✓
    Conclusion: electric furnace economical   ✓
```

## Notable — first clean reciprocal catch

SEC was first written as `36000/(1565 × 0.93)`, struck out, and replaced with
`(1565 × 0.93)/36`. Fourth appearance of the reciprocal family and **the first
caught on the first pass without prompting.**

## The slip that didn't propagate

`5,985,473.68 / 860 = 6,959.85 kWh/hr` was transcribed as **695.985** and carried
into SEC as 19.333 kWh/tonne instead of 193.33. But the final cost line reads
Rs 1,788.303, which requires 193.33 × 9.25 — so the arithmetic performed was
correct and only the two written intermediates were a factor of ten out.

**Lucky, not caught.** The anchor that kills it instantly: one tonne of steel to
1250 °C needs 0.13 × 1215 = 157,950 kCal ≈ **184 kWh irreducibly**. An answer of
19.3 kWh/tonne is ten times below the thermodynamic minimum.

## Tags

| Tag | Marks | Note |
|---|---|---|
| Arithmetic | 0 | Factor-of-ten transcription, no effect on the answer |
| All others | 0 | |

## Verdict

Full marks on a chapter met that day, with sound method and a self-caught
inversion. Timing 70% over target, but this was a first furnace question.

## Instruction to Tutor

Order-of-magnitude anchors added to `reference/precision-and-rounding.md` §5, with
a table of physical limits — steel heating energy, ER bands, efficiency bands, L1
bands, theoretical air, furnace SEC, turbine heat rates, pump power scale. The
checking pass now requires an order-of-magnitude check on every **intermediate**,
not only the final answer.

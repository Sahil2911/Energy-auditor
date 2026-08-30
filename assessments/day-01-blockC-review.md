# Assessment — Day 1, Block C (corrected question)

**Questions:** 18th sitting L-1 (LP/HP steam cost, 5 marks), plus a redo of the
furnace oil calculation from the original N-1.

**Score: 3 / 5.** Method correct throughout, final step inverted.

## The work

**Furnace oil requirement (redo)**

```
    0.84 = 8 × (665 − 90) / (q × 10000)
    q = 0.547 tonnes/hr
```

Correct. Note the crossed-out **1.826** above it — that is exactly 1/0.5476.
An inversion, spotted and fixed unprompted. Hold that thought.

**LP/HP boilers**

```
    η_LP = η_HP
    Q(666 − 95) / (q × 10000) = Q(737 − 105) / (q × 10000)
    (Q/q)_HP = 571/632 × (Q/q)_LP = 0.903 (Q/q)_LP
```

**This is entirely correct.** ER_LP = 14.536, ER_HP = 13.133, ratio 0.9035.
Setting the efficiencies equal and cancelling GCV is a clean, economical route —
better than computing both evaporation ratios separately.

**Final step**

```
    Cost of HP steam = 0.903 × 3000 = Rs 2709/tonne        ✗
    Correct:           3000 / 0.903 = Rs 3322/tonne
```

Steam cost is **inversely** proportional to evaporation ratio. The HP boiler
raises less steam per kg of fuel, so its steam costs *more*, not less.

## The pattern — this is the finding

Two inversions in one sitting:

| Where | Inversion | Outcome |
|---|---|---|
| Furnace oil, q vs 1/q | 1.826 instead of 0.547 | **Caught** and corrected |
| Steam cost vs ER | ×0.903 instead of ÷0.903 | **Missed** |

The same failure mode twice, in one hour. Not carelessness — the ratio algebra is
demonstrably solid. What is missing is the habit of asking *which way should this
go* before committing the final number.

A single sentence would have caught it: HP steam is higher grade and the boiler
makes less steam per kg of fuel, so it must cost more than Rs 3000. The answer
2709 is below 3000 and was therefore wrong before any arithmetic check.

The model answer states this reasoning explicitly before calculating — worth
imitating in the script, since examiners award marks for it.

## Timing

13:27 → 13:34. **Seven minutes against an eight-minute target**, including
writing out the algebra in full. Speed is not a problem on this class of
question. Accuracy at the last step is.

That combination — fast and confident, wrong at the inversion — is the one to
watch. There is time in hand for a sanity check, and it is being spent finishing
early instead.

## Error tags

| Tag | Marks | Note |
|---|---|---|
| Concept | 0 | Efficiency, ER and the algebra are understood |
| **Method** | **2** | Reciprocal relationship inverted at the final step |
| Arithmetic | 0 | Every number computed correctly |
| Units | 0 | Clean |
| Lookup | 0 | Nothing needed |

## Verdict

Genuine progress from the Day 1 diagnostic. Correct setup, efficient route, good
speed, and one self-caught error. The remaining gap is narrow and specific: a
verification habit, not a knowledge gap.

## Instruction to Tutor

1. `reference/reciprocal-traps.md` added — every reciprocal pair in Paper 4 and
   the three-second check. Read before Day 2.
2. Teach the **quantity-tracking method** as the inversion-proof alternative.
   The model answers accept it for full marks.
3. From Day 2 onward, require one written sanity sentence per final answer:
   *"This should be larger/smaller than X because…"* Marked as part of the answer.

## Watch next

Whether the sanity sentence appears unprompted on Day 2, and whether any
reciprocal pair is inverted again. Day 11 (COP vs kW/TR) is the next place this
trap is waiting.

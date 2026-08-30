# Assessment — Day 3 practice

**Tasks:** 18th sitting N-1 redone unaided, then 20th sitting N-1 (5 parts,
20 marks) on an unseen fuel.

**Score: 18 / 20 on the 20th. The strongest session so far.**

---

## 20th sitting N-1 — near-complete

| Part | Her answer | Model | Verdict |
|---|---|---|---|
| A_th | 16.2 | 16.2 | ✓ |
| Excess air | 23.5% | 23.5% | ✓ |
| AAS | 20.01 | 20.0 | ✓ |
| m_dfg | 19.12 | 19.02 | slip — see below |
| L1 | 7.6% | 7.56% | ✓ (follows from m_dfg) |
| η | 80.96% | 81% | ✓ |
| (a) Steam:fuel | 18.651 | 18.7 | ✓ |
| (b) Air, m³/min | 127.154 | 126.76 | ✓ |
| (c) % improvement | **2.63%** | 2.41% | **hers is correct** |
| (d) Gas saving | **15.686 m³/hr** | 14.4 | **hers is correct** |
| (e) Yearly saving | **Rs 33,54,294** | Rs 30,79,296 | **hers is correct** |

**Recognised that L2 and L3 were given.** She began computing L2 from first
principles, then struck it out on seeing 9.92% in the data. That is good exam
economy — reading the data table before calculating saved several minutes.

**Timing:** parts (c) to (e) written between 23:13 and 23:16. Three minutes for
three sub-parts. Speed is not a constraint.

### She is more accurate than the official model on (c), (d) and (e)

Not a rounding coincidence — a real methodological difference.

```
    exact:   SFR₈₀ = 18.6512    SFR₉₅ = 19.1412    diff = 0.4900  →  2.63 %
    model:   SFR₈₀ = 18.7       SFR₉₅ = 19.15      diff = 0.45    →  2.41 %
```

The model rounded to 3 significant figures before subtracting. A 0.25% input
error became a **9% output error**, because subtracting two similar numbers keeps
the absolute error while shrinking the quantity. The same distortion carries into
(d) — 10.06 kg/hr against the true 10.98 — and into (e).

Her instinct to carry full precision is correct and should be reinforced.

The model answer also contradicts itself in (e): "Rs 30,79,296 = Rs 33.793 lakhs".
30,79,296 is 30.79 lakhs. Her 33,54,294 is nearer the model's *stated* lakh figure
than the model's own arithmetic.

### The elegant route she did not take

```
    % improvement = SFR₉₅/SFR₈₀ − 1 = (666−80)/(666−95) − 1 = 586/571 − 1
                  = 15/571 = 2.63 %
```

Efficiency and GCV cancel entirely. The answer depends only on the two feedwater
temperatures. One line, fifteen seconds, no rounding exposure.

Worth teaching as a habit: **before grinding a difference, check what cancels.**

### The one genuine error

```
    m_dfg = (20.01 + 1) − 9 × 0.22 = 21.01 − 1.98 = 19.03
    written:                                        19.12
```

19.12 is exactly what 21.01 − 9(0.21) gives. Hydrogen was transcribed as 0.21
instead of 0.22 in that single line — it is correct everywhere else on the page.
A transcription slip, not a method error. Cost: L1 reads 7.6% instead of 7.56%,
which changes nothing downstream.

---

## 18th sitting N-1 — correct answer, then un-corrected

This is the finding that matters.

```
    First written:  431.52 × 0.82 × 3.67 = 1298.6     ← 0.82 is the EFFICIENCY
    Corrected to:   431.52 × 0.73 × 3.67 = 1154.66    ← carbon fraction   ✓
    Difference:     1688.2 − 1154.66     =  533.54    ✓
    Green energy:   533.54 × 720 / 0.8   = 4,80,186   ✓  (model: 4,78,890)
```

Both correct lines were then struck out and replaced with **389.6** and
**3,50,640** — the values that follow from the original, wrong 1298.6.

**She reached the right answer and then replaced it with the wrong one.**

Two separate things happened:

1. **The original slip:** using efficiency (0.82) where the carbon fraction (0.73)
   belongs. Both are decimals attached to the same fuel and sit adjacent in the
   working. Caught unaided — good.
2. **The revert:** the correction was applied to the CO₂ line but the subtraction
   below it kept its old result, and when the two versions competed the wrong one
   was chosen.

The second is the expensive habit. Under exam pressure, a page carrying both a
struck-out and a corrected chain resolves wrongly about half the time.

**Fix:** on correcting a number, rule a line across the page and rework the chain
downward from the corrected value. Never leave two live versions.

---

## Error tags

| Tag | Note |
|---|---|
| Arithmetic | m_dfg — 0.21 for 0.22 in one line |
| **Method** | Correction not propagated; correct answer discarded |
| Concept | 0 |
| Units | 0 |
| Curriculum | 0 |

## Verdict

A large step up. A full five-part 20-mark question on an unseen fuel, completed
with sound method, correct data-table economy, and **better numerical discipline
than the published answer**. The indirect method chain is now reliable.

The remaining risk is not knowledge. It is bookkeeping under pressure: propagating
corrections, and not discarding good work.

## Instruction to Tutor

1. `reference/precision-and-rounding.md` added — the subtraction trap, the
   cancellation shortcut, correction propagation, and the running list of model
   answer errors.
2. Teach the "rule a line and rework downward" correction discipline explicitly
   in Day 4.
3. Add to the sanity-sentence habit: **on any difference/saving/improvement
   sub-part, ask what cancels before calculating.**
4. Reinforce that full precision is correct practice, and that diverging from a
   printed model answer is not by itself an error.

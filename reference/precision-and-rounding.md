# Precision, Rounding, and Correcting Your Own Work

Two habits that cost marks independently of whether you know the physics.

## 1. Never round an intermediate you are about to subtract

Rounding is harmless when numbers are multiplied. It is destructive when two
similar numbers are **subtracted**, because the difference keeps the absolute
error while shrinking the quantity it sits in.

Real case — 20th sitting N-1(c), % improvement in steam-to-fuel ratio:

| | SFR at 80 °C | SFR at 95 °C | Difference | % improvement |
|---|---|---|---|---|
| Full precision | 18.6512 | 19.1412 | 0.4900 | **2.63%** |
| Rounded to 3 s.f. first | 18.7 | 19.15 | 0.45 | 2.41% |

Rounding the inputs by about 0.25% moved the answer by **9%**. The official model
answer took the rounded route and reports 2.41%; the correct value is 2.63%.

The same thing happened in part (d): exact gas saving is 10.98 kg/hr; the rounded
route gives 10.06 — a 9% error carried into the yearly savings.

**Rule: carry full calculator precision through the whole chain. Round only the
final answer.** Write intermediates to 4 significant figures if you must record
them, but keep the unrounded value in the calculator.

**Warning sign:** any sub-part asking for a *difference*, a *saving*, an
*improvement* or a *reduction*. Those are exactly where early rounding bites.

## 2. Look for the exact route

Sometimes a difference collapses to something clean. Same question:

```
    % improvement = (SFR₉₅ − SFR₈₀) / SFR₈₀

    SFR = η × GCV / (h_steam − h_fw)

    so the ratio is  (666 − 80) / (666 − 95)  =  586/571

    % improvement = 586/571 − 1 = 15/571 = 2.63 %
```

Efficiency and GCV **cancel completely**. You never needed 0.81 or 13,500 — the
answer depends only on the two feedwater temperatures. One line, no rounding
error possible, and it takes fifteen seconds.

Before grinding through a difference, check whether the common factors cancel.

## 3. When you correct an input, propagate the correction

The most expensive error type observed so far: fixing a mistake and then
continuing with the unfixed number.

Real case — 18th sitting N-1, CO₂ from the natural gas boiler:

```
    First written:  431.52 × 0.82 × 3.67 = 1298.6      ← 0.82 is the EFFICIENCY
    Corrected to:   431.52 × 0.73 × 3.67 = 1154.66     ← 0.73 is the carbon fraction  ✓
    Difference:     1688.2 − 1154.66     =  533.54     ✓
    Green energy:   533.54 × 720 / 0.8   = 4,80,186    ✓  correct
```

Then both of the last two lines were struck out and replaced with 389.6 and
350,640 — the values that follow from the *original wrong* 1298.6. A correct
answer was reached and then un-corrected.

**Rule: when you fix a number, immediately strike every line below it and rework
downward.** Do not leave both versions on the page for later reconciliation —
under exam pressure the wrong one gets chosen roughly half the time.

A practical technique: when correcting mid-question, draw a line across the page
and restart the chain from the corrected value. Cleaner for you and unambiguous
for the examiner.

## 4. Model answers are not infallible

Three errors found in official model answers so far:

| Paper | Error |
|---|---|
| 24th N-1 | States m_dfg = 6.34; its own inputs give 6.42 |
| 20th N-1(c),(d) | Rounds intermediates early — 2.41% and 10.06 kg/hr should be 2.63% and 10.98 |
| 20th N-1(e) | States "Rs 30,79,296 = Rs 33.793 lakhs" — 30,79,296 is 30.79 lakhs |

**This does not mean you should chase the model's digits.** Examiners mark
method. A defensible chain with full precision earns full marks even where it
diverges slightly from the printed answer. Show the working and state
assumptions.

# Assessment — Electrical & Fluids Diagnostic

**Score: 28 / 30.** Pass equivalent 15/30.
**Time: 20:45 → 21:15, thirty minutes** against a forty-five-minute allowance.

| Section | Marks | Score |
|---|---|---|
| I — True/False | 5 | **5/5** |
| II — Pump efficiency | 5 | 4/5 |
| III — Cooling tower and sump | 20 | **19/20** |

---

## Section I — 5/5, and she found an error in the answer key

Answers: False, True, False, True, **True**.

Question 5 asked whether a tower reaching 30 °C at a 25 °C wet bulb is performing
worse than one reaching 32 °C at a 28 °C wet bulb.

**The answer key said False**, on the assertion that both approaches were 5 °C.
They are **5 °C and 4 °C** — 32 − 28 = 4. The second tower has the tighter approach
and is the better performer, so the first *is* worse. **The statement is True.**

She wrote False, struck it out, and wrote True.

That correction is worth more than the mark. Writing False would have been the
pattern-matched answer — the rule is "judge against the wet bulb", and the question
looks designed to reward saying "they are the same". **She computed both approaches
instead of matching the pattern, and the arithmetic disagreed with the expected
answer.** She followed the arithmetic.

The question as intended needed 33 °C against a 28 °C wet bulb. Answer key corrected.

## Section II — 4/5

```
    H = 45 − (−3) = 48 m                          ✓  the main trap, handled
    Q = 3600 × π(0.15)²/4 = 63.585 m³/hr          ✓
    Hydraulic = 48 × 63.585/367 = 8.32 kW         ✓
    η = 8.32 / 16.7 = 49.8 %                      ✗
```

**The suction lift sign was correct** — 48 m, not 42. That was the trap the question
was built around.

The final step divided by the **motor input** of 16.7 kW, which gives the
**overall pump-set efficiency**. The question asks for the **pump** efficiency, so
the motor efficiency comes off first:

```
    Shaft power = 16.7 × 0.90 = 15.03 kW
    Pump efficiency = 8.32 / 15.03 = 55.4 %
```

The two answers differ by exactly 0.90 — 49.8/55.4 = 0.900 — which confirms the
omitted step.

**Notable:** this is the same distinction she got *right* on Day 10's pump question,
where she struck out 76.921 and replaced it with 81.828 on realising that pump
efficiency measures against motor output. Here, three sessions later and under a
tighter clock, it went the other way. The concept is understood; its application is
not yet automatic.

## Section III — 19/20

```
    Circulating water = 45 × 440              = 19,800 m³/hr        ✓
    Range = 0.63 × 4/0.37                     = 6.81 °C             ✓
    Evaporation = 0.00153 × 19,800 × 6.81     = 206.327 m³/hr       ✓
    COC = 2000/500 = 4, blowdown = 206.327/3  = 68.776 m³/hr        ✓
    Makeup = E + B                            = 275.103 m³/hr       ✓
    Sump = 100 × 15 × 40                      = 60,000 m³           ✓

 b) One pump:  6000/(275.103 − 200) = 79.89 hours                   ✓
 c) Both:      6000/(350 − 275.103) = 80.11 hours                   ✓
```

**Mass flow diagram drawn**, as part (a) required — the first time a diagram has
been produced unprompted, and the question allocates marks to it.

One slip: cooled water shown as **16,593.673** where 19,800 − 206.327 =
**19,593.673**. A digit transcription, 19 → 16, in a figure nothing else depends on.

**The range derivation is the part most candidates miss.** Effectiveness is given
as 63% and approach as 4 °C, and `Range = eff × approach/(1 − eff)` has to be
rearranged from `eff = R/(R + A)`. She did it in one line.

---

## Tags

| Tag | Marks | Note |
|---|---|---|
| **Method** | 1 | Overall efficiency reported where pump efficiency was asked |
| Arithmetic | 0 | Diagram transcription, nothing depends on it |
| Concept, units, reading | 0 | |
| **Tutor** | — | Answer key error in Section I Q5 |

## Verdict

**28/30, in two-thirds of the allotted time.** Phase 2 is secure.

The one lost mark is the pump-versus-overall efficiency distinction — understood in
principle, applied correctly three sessions ago, missed here under a faster clock.
It belongs to the same family as the reciprocal habit, which took five sessions to
become automatic.

Per the diagnostic's own scale: **24+ is "strong, Phase 2 secure — proceed".**

## Instruction to Tutor

1. **Add to the checking pass:** when a question asks for *an efficiency*, name
   which one before computing. Pump, overall, motor, isothermal, hydraulic — they
   differ by exactly one efficiency each, and every one of them looks plausible.
2. Answer key corrected and the error recorded. Diagnostics are written by the
   Tutor and are not exempt from checking.

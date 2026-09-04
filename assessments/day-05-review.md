# Assessment — Day 5

*Written retrospectively, as for Day 4.*

---

## 18th sitting L-2, shell-and-tube — **5 / 5**

**Time: 21:07 onward.**

```
    m_w   = 2670 × 2.1 × 45 / (4190 × 50) = 1.204 kg/s       ✓
    LMTD  = 0.82 × (25 − 20)/ln(25/20) = 18.374 °C           ✓
    A     = 4190 × 50 × 1.204 / (950 × 18.374) = 14.451 m²   ✓
```

Clean throughout. The correction factor applied in the right place, and the
energy balance used to find the unknown water flow — the move that unlocks most
questions in this chapter.

**One self-correction on the page:** the LMTD line first showed 2.547, struck out
and replaced with 18.374.

---

## 25th sitting N-1, pharmaceutical chilled water — part (a) only

**Time: 21:18 onward.**

### Part (a) — correct

```
    ΔT_LMTD = [(20−12) − (14−7)] / ln[(20−12)/(14−7)] = 7.489 °C     ✓
    A = 200 × 4.18 × 5 × 1000 / (2.8 × 3600 × 7.489) = 55.372 m²     ✓
```

Model answer: 55.2 m². Hers carries more precision.

### Part (b) — attempted, two errors

She computed the hydraulic powers correctly in **value**:

```
    Chilled water pump: 200/3600 × 1000 × 9.8 × 18 = 9,800 W  = 9.80 kW   ✓
```

The model gives 9.81 kW. But:

**1. Labelled kW where the value is W.** 9,800.078 written as kW. Power-versus-unit
slip — the third of this family after `21,410 × 4.18` on Day 4.

**2. Multiplied by the efficiencies instead of dividing:**

```
    Written:  (0.92 × 0.78 × 9800)  = 7.03 kW
    Correct:  9.81 / (0.78 × 0.92)  = 13.67 kW   (model: 13.7)
```

Efficiency is output over input, so recovering the input **divides**. Third
appearance of the reciprocal family, and at this point still being missed.

**3. Used 166 m³/hr for the condenser pump**, where part (b) specifies 600 m³/hr.
Understandable given the topic was untaught.

### Parts (c) and (d) — not attemptable

**Tutor fault — third prerequisite breach.** Parts (b), (c) and (d) need pump
power (Day 8), fan power (Day 9) and chiller SEC and ISEER (Day 11). **Fourteen of
twenty marks were untaught when the question was set.**

That she computed a correct hydraulic power on an untaught topic is worth noting
separately.

---

## Tags

| Tag | Note |
|---|---|
| **Method — reciprocal** | Multiplied by efficiencies instead of dividing |
| Units | kW written where W was meant |
| **Curriculum** | 14 of 20 marks untaught |
| Concept, arithmetic | 0 |

## Verdict

The heat exchanger work is solid — the taught chapter was executed correctly on
both questions. Everything lost was either untaught or the reciprocal habit, which
was still forming at this point.

## The student's own criticism, and what it changed

She said after this session: *"there's no technical depth about heat exchanger in
curriculum. All I learnt is two formulas only."* Correct — Day 5 taught LMTD and
`A = Q/(U·LMTD)` for a chapter appearing in 7 of 8 sittings.

Day 5 was subsequently rewritten **three times** in response:

1. Depth added — U as series resistances, fouling, approach economics, temperature
   cross, ε–NTU, exchanger selection
2. Merged back to one session at her request, the chapter being short
3. **Rebuilt from first principles** after she pointed out it still opened with
   `Q = m·Cp·ΔT` rather than building to it — now Rungs 35–50, with the LMTD
   **derived by integration** rather than quoted

The master plan's teaching standard gained two clauses from this session: depth in
proportion to a topic's exam weight, and *build to the formula, never open with it*.

## Instruction to Tutor

1. Prerequisite rule created after this session (later tightened twice).
2. Reciprocal handling needs reinforcement — it was still being missed here.
   *(Now closed: six of the next seven were caught.)*

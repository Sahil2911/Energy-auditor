# Day 7B — Reverse Calculations from Flue Gas Analysis

**Time: 2.5 hours.** Rungs 65–72.

Mock A's N-1 was lost here. Every tool was recalled correctly and the setup still
started from the fuel composition, which was the answer. This session fixes that
specifically.

> **Prerequisite check:** Days 2A, 2B and 3 only.

---

## Rung 65 — Why anyone works backwards

An auditor arrives at a plant. What can actually be measured?

| Measurable | How |
|---|---|
| Flue gas composition | Portable analyser at the stack — minutes |
| Flue gas temperature | Thermocouple |
| Fuel consumption | Flow meter or tank dips |
| **Fuel composition** | **Send a sample to a lab. Days. Often refused.** |

So the flue gas is the *easy* measurement and the fuel analysis is the hard one.
Working backwards is not an exam trick — **it is normal practice.**

It also cross-checks: if a supplier's declared fuel analysis disagrees with what
the stack says, one of them is wrong, and it is usually not the stack.

---

## Rung 66 — What the analyser actually reports

An **Orsat analyser** absorbs each gas in turn and measures the volume shrinkage:

1. CO₂ absorbed in potassium hydroxide
2. O₂ absorbed in alkaline pyrogallol
3. CO absorbed in cuprous chloride
4. **N₂ by difference** — whatever is left

Two consequences that decide how you set up every reverse problem:

**It reports by VOLUME.** Volume shrinkage is what is read. For gases, volume
fractions equal **mole** fractions.

**It reports DRY.** The sample cools on the way to the instrument and its water
condenses out. Every flue gas analysis is a *dry* analysis unless stated otherwise
— which is why "mass of **dry** flue gas" is the quantity that keeps appearing.

> **The single most important question before starting: is this analysis by
> VOLUME or by WEIGHT?** Modern papers sometimes state weight explicitly (Mock A's
> N-1 did). A classic Orsat question means volume. Using the wrong basis produces a
> plausible, wrong answer.

---

## Rung 67 — Converting between the bases

Volume fraction is mole fraction. Mass = moles × molecular weight. So:

```
    weight fraction ∝ volume fraction × molecular weight
```

then normalise. Molecular weights you need:

| Gas | MW |
|---|---|
| CO₂ | 44 |
| O₂ | 32 |
| N₂ | 28 |
| CO | 28 |
| H₂O | 18 |

**Drill 47.** Orsat gives CO₂ 17.27%, O₂ 3.45%, N₂ 79.28% by volume. Convert to
weight %.

<details><summary>Answer</summary>

```
    CO₂ : 17.27 × 44 = 759.9
    O₂  :  3.45 × 32 = 110.4
    N₂  : 79.28 × 28 = 2219.8
                       ───────
    Total              3090.1

    CO₂ = 759.9/3090.1  = 24.6 %
    O₂  = 110.4/3090.1  =  3.6 %
    N₂  = 2219.8/3090.1 = 71.8 %
```

Notice CO₂ rises from 17.3% to 24.6% — it is the heaviest molecule, so it carries
more weight than volume. **The two bases give genuinely different numbers.**
</details>

---

## Rung 68 — The three anchors

The whole method rests on three conservation statements. Each says *this component
can only have come from one place.*

**1. Carbon.** Every carbon atom in the fuel leaves as CO₂ (or CO). Carbon does not
accumulate, and there is no carbon in air.

```
    C in fuel  =  C in CO₂  +  C in CO
    C from CO₂ = mass of CO₂ × 12/44
    C from CO  = mass of CO  × 12/28
```

**2. Nitrogen.** Essentially all N₂ came in with the air. Fuel nitrogen is under
1% and is normally ignored.

```
    Air supplied = mass of N₂ / 0.77
```

**This is the step that unlocks the problem.** Nitrogen is inert, so it passes
through untouched — it is a *tracer* for how much air went in.

**3. Oxygen.** What was supplied either got used or came out unused.

```
    O₂ supplied = 0.23 × air
    O₂ in flue gas = the unused remainder
    O₂ consumed = supplied − unused
```

And oxygen is consumed only by carbon, hydrogen and sulphur:

```
    O₂ consumed = C×(32/12) + H₂×8 + S×1
```

Rearranged, that gives you the hydrogen — the one constituent no flue gas
component reveals directly, because its water condensed out before the analyser
saw it.

---

## Rung 69 — The reverse chain

**Work per 100 kg of dry flue gas.** Percentages become kilograms, and no
assumption about fuel rate is needed until the end.

```
    Step 1   Carbon      = %CO₂ × 12/44
    Step 2   Air         = %N₂ / 0.77
    Step 3   O₂ supplied = 0.23 × air
    Step 4   O₂ consumed = O₂ supplied − %O₂
    Step 5   O₂ for C    = carbon × 32/12
    Step 6   O₂ for H₂   = O₂ consumed − O₂ for C
    Step 7   Hydrogen    = O₂ for H₂ / 8
    Step 8   Fuel        = carbon + hydrogen (+ S, moisture if present)
    Step 9   Composition = each constituent / fuel × 100
    Step 10  Scale       = actual fuel rate / fuel per 100 kg × 100
```

Every constant is one you already use forwards. **Only the direction changes.**

Note the shape: steps 1 and 2 are the two **anchors** — each computable
immediately from the data with no unknowns. Everything else chains outward from
them. That is the general method for any inverse problem: find what you can
compute directly, then work outward.

---

## Rung 70 — The standard formula, and where it comes from

For a **volume-basis** Orsat analysis, textbooks quote:

```
                11·CO₂ + 8·O₂ + 7·(CO + N₂)
    m_dfg  =  ──────────────────────────────  × C
                     3 · (CO₂ + CO)
```

giving kg of dry flue gas per kg of fuel, with the gas percentages **by volume**
and C the carbon fraction of the fuel.

It looks arbitrary. It is not — it is Rung 69 compressed:

- The denominator `3(CO₂ + CO)` is the carbon balance. The 3 is 12/4, arising from
  the mole-to-mass bookkeeping.
- The numerator weights each gas by its molecular mass per unit of carbon: 11 from
  44/4 for CO₂, 8 from 32/4 for O₂, 7 from 28/4 for CO and N₂ alike.

**Verified.** Burn pure carbon at 20% excess air. Mass balance gives m_dfg =
14.913 kg/kg. The formula, with CO₂ 17.27%, O₂ 3.45%, N₂ 79.28% by volume, gives
**14.911**. They agree.

Use the formula when the analysis is volumetric and you want m_dfg quickly. Use
Rung 69 when you need the fuel composition itself, or when the analysis is by
weight.

---

## Rung 71 — Worked in full: Mock A N-1

`papers/25-1.pdf`, question N-2. Fuel 200 kg/hr; dry flue gas **by weight**:
CO₂ 12%, O₂ 3%, N₂ 85%.

**Check the basis first — it says by weight, so Rung 67 is not needed.**

```
    Per 100 kg of dry flue gas:

    Step 1  Carbon      = 12 × 12/44           = 3.273 kg
    Step 2  Air         = 85 / 0.77            = 110.39 kg
    Step 3  O₂ supplied = 0.23 × 110.39        = 25.39 kg
    Step 4  O₂ consumed = 25.39 − 3            = 22.39 kg
    Step 5  O₂ for C    = 3.273 × 32/12        = 8.73 kg
    Step 6  O₂ for H₂   = 22.39 − 8.73         = 13.66 kg
    Step 7  Hydrogen    = 13.66 / 8            = 1.708 kg
    Step 8  Fuel        = 3.273 + 1.708        = 4.981 kg

    (b) Composition:  C = 3.273/4.981 = 65.7 %,  H₂ = 1.708/4.981 = 34.3 %

    (c) Dry flue gas   = 200 / 4.981 × 100     = 4,016 kg/hr
```

**Sanity checks:**
- Carbon plus hydrogen must total 100% for a CₙHₘ–H₂ fuel. 65.7 + 34.3 = 100 ✓
- 34% hydrogen is very high — ordinary hydrocarbons run 11–23%. The question says
  *hydrogen-enriched*, so it fits. ✓
- Each kg of fuel makes about 20 kg of dry flue gas. Compare natural gas at 19.2
  from Day 2B. ✓

---

## Rung 72 — Recognising an inverse problem

> **If the thing you would normally start from is the thing being asked for, the
> problem runs backwards.**

Concretely, before writing anything:

1. Write down what is **given**
2. Write down what is **asked**
3. Check whether your usual starting point is in the given list

Flue gas analysis given, fuel asked → reverse.

**Other inverse forms in this paper** (see `reference/inverse-problems.md`):

| Given | Asked | Anchor to start from |
|---|---|---|
| Flue gas analysis | Fuel composition | Carbon from CO₂ |
| Efficiency + output | Fuel input | `fuel = useful heat/(η × GCV)` |
| Duty + temperatures | Area, or area ratio | `A = Q/(U·LMTD)`; the ratio cancels U |
| Efficiency | Heat rate | `860/η` |
| Motor output | Motor input | `÷ (η_pump × η_motor)`, never × |

---

## Practice (45 min)

1. **Redo Mock A N-1 cold**, without looking at Rung 71. Target 20 minutes.
2. **Variant.** An Orsat analysis of a coal-fired boiler's flue gas gives, **by
   volume**: CO₂ 12%, O₂ 6%, CO 0.5%, N₂ 81.5%. The coal is 72% carbon. Find the
   mass of dry flue gas per kg of coal using the standard formula, then the excess
   air.

<details><summary>Variant answer</summary>

```
    m_dfg = [11(12) + 8(6) + 7(0.5 + 81.5)] / [3(12 + 0.5)] × 0.72
          = [132 + 48 + 574] / 37.5 × 0.72
          = 754/37.5 × 0.72 = 14.48 kg per kg coal

    Excess air, with CO present, uses the corrected form:
    % EA = [O₂ − CO/2] / [21 − (O₂ − CO/2)] × 100
         = (6 − 0.25)/(21 − 5.75) × 100 = 37.7 %
```

The CO correction matters: CO in the gas means some oxygen was supplied but not
fully used, so the plain formula overstates excess air.
</details>

---

## Day 7B checklist

- [ ] Can say why auditors work backwards from flue gas
- [ ] Know an Orsat reports by **volume** and **dry**, and why
- [ ] Can convert volume % to weight % and back
- [ ] Can state the three anchors and what each conserves
- [ ] Know nitrogen is the tracer that reveals the air
- [ ] Can run the ten-step reverse chain unaided
- [ ] Know where the standard formula comes from
- [ ] Can recognise an inverse problem before starting
- [ ] Mock A N-1 solved cold, and the variant done

**Next (Day 8):** pumps and pumping systems.

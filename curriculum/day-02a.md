# Day 2A — Combustion Air, One Rung at a Time

**Time: 2.5 hours. Lighter than a normal day, on purpose.**

**Source:** BEE Book 2 Ch 1 §1.6
([2Ch1.pdf](https://beeindia.gov.in/sites/default/files/2Ch1.pdf))

> **Why this day exists.** The first Day 2 taught five new ideas and then asked
> you to follow an eight-step worked example that used all of them at once. If
> any one link was unclear the whole example became unreadable — which is exactly
> what happened. That is a fault in how it was built, not in how you read it.
>
> This version moves one rung at a time. Every rung is a single idea with a
> single number you can check in under a minute. Nothing chains until every rung
> holds.

**Today has one goal only:** given a fuel's composition, work out how much air it
needs. Nothing about losses, nothing about efficiency, no CO₂. Just air.

---

## The fuel we will use all day

Furnace oil. Keep this in front of you:

| Constituent | % by weight | In 1 kg of fuel |
|---|---|---|
| Carbon | 84 | 0.84 kg |
| Hydrogen | 11 | 0.11 kg |
| Sulphur | 4 | 0.04 kg |
| Oxygen | 0.5 | 0.005 kg |
| Nitrogen | 0.5 | 0.005 kg |

That right-hand column is the whole trick of reading an ultimate analysis.
**Percentages are just kg per kg of fuel.** 84% carbon means every kilogram of
this oil contains 840 grams of carbon.

---

## Rung 1 — How much oxygen does the carbon need?

Carbon burns: **C + O₂ → CO₂**

Work in kilograms using atomic masses. Carbon is 12, oxygen molecule O₂ is 32:

```
    12 kg of carbon  needs  32 kg of oxygen
     1 kg of carbon  needs  32/12 = 2.67 kg of oxygen
```

Our fuel has 0.84 kg of carbon, so:

```
    0.84 × 2.67 = 2.24 kg of oxygen
```

**Drill 1.** A coal has 45% carbon. How much oxygen does 1 kg of it need for the
carbon alone?

<details><summary>Answer</summary>

0.45 × 2.67 = **1.20 kg of oxygen**
</details>

**Stop here until this feels obvious.** Everything else today is this same move
repeated.

---

## Rung 2 — Oxygen is not air

You cannot buy oxygen; you draw in air. **Air is only 23% oxygen by mass.**

So to obtain 2.24 kg of oxygen you must pull in considerably more air:

```
    air needed = 2.24 / 0.23 = 9.74 kg
```

Check it the other way round: 9.74 kg of air × 0.23 = 2.24 kg of oxygen. ✓

The other 7.5 kg is nitrogen. It does nothing useful — it just gets heated and
thrown away. **That is the single most important fact in this whole paper**, and
Day 2B is largely about what it costs you.

**Drill 2.** From Drill 1 you needed 1.20 kg of oxygen. How much air is that?

<details><summary>Answer</summary>

1.20 / 0.23 = **5.22 kg of air**
</details>

---

## Rung 3 — Where 11.6 comes from

Look at what we did to the carbon: multiplied by 2.67, then divided by 0.23.

```
    2.67 / 0.23 = 11.6
```

So we can go straight from carbon to air in one step:

```
    air for carbon = 0.84 × 11.6 = 9.74 kg          ← same answer as Rung 2
```

**That is the 11.6 in the formula.** It is not a magic number to memorise — it is
"oxygen per kg of carbon, converted into air." If you ever forget it, rebuild it:
32/12 ÷ 0.23.

---

## Rung 4 — Now hydrogen

Hydrogen burns: **2H₂ + O₂ → 2H₂O**

```
    4 kg of hydrogen  needs  32 kg of oxygen
    1 kg of hydrogen  needs  32/4 = 8 kg of oxygen
```

Hydrogen is thirsty — 8 kg of oxygen per kg, against carbon's 2.67.

Our fuel has 0.11 kg of hydrogen:

```
    oxygen = 0.11 × 8    = 0.88 kg
    air    = 0.88 / 0.23 = 3.83 kg
```

And the one-step constant:

```
    8 / 0.23 = 34.8       ⟹  0.11 × 34.8 = 3.83 kg      ✓
```

**Drill 3.** Natural gas is 23% hydrogen. Air needed for the hydrogen in 1 kg?

<details><summary>Answer</summary>

0.23 × 34.8 = **8.00 kg of air**

Note how much that is. Hydrogen is why gas needs so much air.
</details>

---

## Rung 5 — And sulphur

**S + O₂ → SO₂**

```
    32 kg of sulphur  needs  32 kg of oxygen      ⟹  1 kg needs 1 kg
```

One to one — the easy one.

```
    oxygen = 0.04 × 1    = 0.04 kg
    air    = 0.04 / 0.23 = 0.174 kg
    constant: 1 / 0.23   = 4.35    ⟹  0.04 × 4.35 = 0.174    ✓
```

Sulphur contributes very little air. It matters for corrosion and SO₂, not for
the air calculation.

---

## The three constants, rebuilt

You have now derived all three yourself:

| Element | O₂ per kg | ÷ 0.23 | Constant |
|---|---|---|---|
| Carbon | 32/12 = 2.67 | | **11.6** |
| Hydrogen | 32/4 = 8.0 | | **34.8** |
| Sulphur | 32/32 = 1.0 | | **4.35** |

Never memorise these. Rebuild them — it takes fifteen seconds and cannot be
misremembered.

---

## Rung 6 — The oxygen already in the fuel

Our fuel contains 0.005 kg of its own oxygen. That is oxygen you **do not have to
supply**, so it must be subtracted.

Which element does it serve? Hydrogen. From 2H₂ + O₂ → 2H₂O, 8 kg of oxygen pairs
with 1 kg of hydrogen. So fuel oxygen cancels hydrogen at 8:1:

```
    hydrogen already supplied with oxygen = 0.005 / 8 = 0.000625 kg
    hydrogen still needing air = 0.11 − 0.000625 = 0.109375 kg
```

**That is the `O₂/8` term.** For furnace oil it barely matters. For biomass it
matters enormously — paddy husk is 32.5% oxygen, which cancels most of its
hydrogen. That is why husk needs so little air per kg.

---

## Rung 7 — Add it up

```
    carbon    0.84     × 11.6  =  9.744
    hydrogen  0.109375 × 34.8  =  3.806
    sulphur   0.04     × 4.35  =  0.174
                                 ───────
    A_th                       = 13.72 kg air / kg fuel
```

**That is theoretical air.** And that is the whole formula:

```
    A_th = { 11.6·C + 34.8·(H₂ − O₂/8) + 4.35·S } / 100
```

The `/100` is only because the formula takes percentages (84) while we used
fractions (0.84). Same arithmetic.

Sanity anchor: **oil and gas need 13–17 kg of air per kg of fuel; coal 6–8;
biomass 3–5.** If your answer is far outside, something is wrong.

**Drill 4.** Paddy husk: C 33.95%, H₂ 5.01%, S 0.09%, O₂ 32.52%. Find A_th.

<details><summary>Answer</summary>

```
    carbon    0.3395 × 11.6 = 3.938
    hydrogen  O₂/8 = 0.3252/8 = 0.04065
              effective H₂ = 0.0501 − 0.04065 = 0.00945
              0.00945 × 34.8 = 0.329
    sulphur   0.0009 × 4.35 = 0.004
                              ───────
    A_th                    = 4.27 kg air / kg husk
```

Inside the biomass band of 3–5. ✓

Look what the oxygen credit did: it cancelled **81%** of the hydrogen. That is
why husk needs a third of the air that oil does.
</details>

---

## Rung 8 — Real furnaces use more air than this

Theoretical air assumes every oxygen molecule finds its fuel molecule. Real
mixing is imperfect, so at exactly theoretical air some fuel leaves unburnt.

So you deliberately supply **excess air**. But every extra kg is more nitrogen
heated and discarded:

```
    too little air  →  unburnt fuel, CO, soot
    too much air    →  heat carried out by nitrogen
```

Somewhere between is the optimum. Tuning that is what combustion engineers do.

**Measuring it.** You cannot easily meter the air in, but you can measure the
oxygen coming *out* — whatever was left over:

```
    % excess air = [ %O₂ / (21 − %O₂) ] × 100
```

Of the 21% oxygen that entered, `%O₂` came out unused, so `21 − %O₂` was
consumed. Leftover ÷ consumed = excess ÷ theoretical.

> **Why 21 here but 23 earlier?** Analysers read by **volume** (21% O₂); mass
> balances use **mass** (23% O₂). Same air, two bases. Use 23 for air quantities,
> 21 for excess air from a reading.

Then:

```
    AAS = (1 + EA/100) × A_th
```

**Drill 5.** Flue gas O₂ reads 4%. Find excess air, then AAS for our furnace oil.

<details><summary>Answer</summary>

```
    EA  = 4 / (21 − 4) × 100 = 23.5 %
    AAS = 1.235 × 13.72 = 16.95 kg air / kg fuel
```
</details>

Useful anchors — recognise these:

| Flue gas O₂ | Excess air |
|---|---|
| 2% | 10.5% |
| 4% | 23.5% |
| 6% | 40% |
| 8% | 61.5% |

---

## Consolidation (30 min)

No exam question today. Just the ladder again, on a fuel you have not used.

Coal: C 45%, H₂ 3.5%, S 0.5%, O₂ 8%, N₂ 1%, moisture 5%, ash 37%.
Flue gas O₂ = 6%.

Find, in order: (1) oxygen for carbon, (2) air for carbon, (3) air for hydrogen
after the oxygen credit, (4) air for sulphur, (5) A_th, (6) excess air, (7) AAS.

<details><summary>Answers</summary>

```
1. 0.45 × 2.67                     = 1.20 kg O₂
2. 0.45 × 11.6                     = 5.22 kg air
3. O₂/8 = 0.08/8 = 0.01
   effective H₂ = 0.035 − 0.01     = 0.025
   0.025 × 34.8                    = 0.87 kg air
4. 0.005 × 4.35                    = 0.022 kg air
5. A_th = 5.22 + 0.87 + 0.022      = 6.11 kg air / kg coal
6. EA = 6/(21−6) × 100             = 40 %
7. AAS = 1.40 × 6.11               = 8.55 kg air / kg coal
```

A_th of 6.11 sits in the coal band of 6–8. ✓
Ash and moisture play no part in the air calculation — they do not burn.
</details>

---

## Day 2A checklist

- [ ] Can read an ultimate analysis as kg per kg of fuel
- [ ] Can find oxygen for carbon, hydrogen and sulphur from the reactions
- [ ] Know air is 23% oxygen by mass, and why that division is needed
- [ ] Can rebuild 11.6, 34.8 and 4.35 without looking
- [ ] Understand the `O₂/8` credit and why it dominates for biomass
- [ ] Can compute A_th for any fuel
- [ ] Can get excess air from a flue gas O₂ reading, and know why it uses 21
- [ ] All five drills plus the consolidation done

**If any box is unticked, say which one.** Do not move on — every later day rests
on this, and it is much cheaper to fix here.

**Tomorrow (Day 2B):** what comes *out* of the furnace — flue gas mass, CO₂, and
why the indirect method exists. Same one-rung-at-a-time approach.

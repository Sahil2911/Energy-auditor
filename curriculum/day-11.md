# Day 11 — HVAC, Chillers and Refrigeration

**Time: 4 hours. Book-4 Ch 9 (p. 115).**

**Source:** [4Ch9.pdf](https://beeindia.gov.in/sites/default/files/4Ch9.pdf) (free).

Appears in **7 of 8 sittings**. Rungs 109–121.

> **Prerequisite check — data-item level.** Today's timed question is the 25th
> sitting N-1, deferred from Day 5. Every quantity it supplies now maps to a taught
> rung: process and chilled water flows and temperatures and U → Day 5 · pump
> efficiencies and head → Day 8 · fan flow, pressure and efficiency → Day 9 · motor
> efficiency → Day 8 · cooling load, ISEER, hours and tariff → today. **Nothing
> orphaned.**

---

# Part 1 — Refrigeration

## Rung 109 — Heat does not flow uphill by itself

Everything so far has moved heat *downhill* — hot flue gas to cold water, hot
effluent to cold air. Heat does that on its own; you only had to provide surface.

Refrigeration moves heat **the wrong way** — from a cold space to a warm one. That
does not happen spontaneously, so **work must be supplied**. A chiller is a machine
for pumping heat uphill, and the electricity it draws is the price of the lift.

Two consequences follow immediately:

- **The heat rejected is always more than the heat absorbed.** Everything absorbed
  in the evaporator, plus the work put in by the compressor, comes out at the
  condenser. `Q_rejected = Q_absorbed + W`. That is why cooling towers on chiller
  plants are always bigger than the cooling duty.
- **The bigger the lift, the more work.** Raise the condenser temperature or lower
  the evaporator temperature and the compressor works harder for the same cooling.
  Rung 118 makes that numerical, and it is where most chiller savings live.

---

## Rung 110 — The vapour compression cycle

Four components in a loop, and each does one thing:

```
              ┌──────── condenser ────────┐   heat OUT, to cooling water
              │                            │
        compressor                    expansion valve
              │                            │
              └──────── evaporator ───────┘   heat IN, from chilled water
```

| Component | What happens | Why |
|---|---|---|
| **Evaporator** | Liquid refrigerant boils at low pressure | Boiling absorbs latent heat — this is the cooling |
| **Compressor** | Vapour raised to high pressure | Raising pressure raises its saturation temperature |
| **Condenser** | Vapour condenses at high pressure | Condensing releases latent heat to the cooling water |
| **Expansion valve** | Liquid throttled back to low pressure | Drops it back to the low saturation temperature |

**The whole trick is that a fluid's boiling point depends on pressure.** Compress
the refrigerant and it will condense at 40 °C; throttle it and the same fluid boils
at 2 °C. The machine simply shuttles it between two pressures so it can absorb heat
cold and reject it hot.

Latent heat does the work in both heat exchangers, which is why the flows are small
compared with a water-side heat exchanger of the same duty.

---

## Rung 111 — The ton of refrigeration

Cooling is measured in **tons of refrigeration**, and the unit is historical: the
cooling you would get from melting one ton of ice per day.

```
    1 short ton = 2000 lb, latent heat of fusion 144 Btu/lb
    2000 × 144 = 2,88,000 Btu per 24 hours
              = 12,000 Btu/hr
              × 0.252 kCal/Btu = 3,024 kCal/hr
              ÷ 860           = 3.517 kW
```

```
    1 TR = 3,024 kCal/hr = 12,000 Btu/hr = 3.517 kW
```

**It is a rate, not a quantity** — a unit of power, despite sounding like a mass.
Worth reconstructing once so it never has to be memorised.

**Drill 59.** A plant carries an average cooling load of 850 kW. How many TR?

<details><summary>Answer</summary>

850 / 3.517 = **241.7 TR** ≈ 242 TR
</details>

---

## Rung 112 — COP, and why it exceeds 1

```
    COP = cooling effect / work input
```

Real chillers achieve **4 to 6**. That looks like an efficiency above 100%, and it
is not a mistake.

**COP is not an efficiency.** An efficiency compares output energy to input energy
of the same kind. COP compares **heat moved** to **work done** — and moving heat is
far cheaper than creating it. The refrigerant does the carrying; the compressor
only provides the lift.

**The ceiling is Carnot**, and it depends only on the two temperatures:

```
    COP_Carnot = T_cold / (T_hot − T_cold)          T in kelvin
```

For chilled water evaporating at 7 °C and condensing at 40 °C:

```
    COP_Carnot = 280 / (313 − 280) = 8.48
```

A real chiller at COP 5 is therefore running at about **59% of Carnot** — respectable
for a real machine with pressure drops, superheat and mechanical losses.

**The ceiling formula also tells you where savings come from.** The denominator is
the temperature lift. Shrink it and COP rises fast. That is Rung 118.

---

## Rung 113 — kW/TR, and the reciprocal trap

Indian practice quotes chiller performance as **kW per TR** — compressor input
power divided by cooling delivered.

```
    kW/TR = 3.517 / COP              COP = 3.517 / kW/TR
```

The 3.517 is just the TR-to-kW conversion from Rung 111.

> ⚠️ **These run in opposite directions, and this is the exam's favourite version
> of the reciprocal trap.**
>
> **Higher COP is better. Lower kW/TR is better.**
>
> A chiller improving from 0.9 to 0.7 kW/TR has got **better**, and its COP has
> risen from 3.9 to 5.0. If you compute a "saving" that makes kW/TR go up, you have
> inverted something.

| COP | kW/TR | EER |
|---|---|---|
| 3.0 | 1.172 | 10.2 |
| 4.0 | 0.879 | 13.7 |
| 5.0 | 0.703 | 17.1 |
| 6.0 | 0.586 | 20.5 |

> ⚠️ **The two numbers may sit on different sides of the motor.** COP is usually
> quoted against the compressor's **shaft** power; kW/TR is usually quoted against
> the **motor input**, since that is what the meter records. When motor losses are
> given, `3.517 / (kW/TR)` will *not* reproduce the quoted COP — the gap is the
> motor efficiency. Check which basis a question is using before converting.
>
> **And for any energy saving, use the electrical basis.** A reduction in cooling
> load is not a reduction in electricity: convert TR to kW by multiplying by kW/TR
> on motor input. Dividing the thermal load by 860 gives the heat no longer moved,
> not the power no longer drawn — an error of roughly 4× at typical chiller
> performance.

**Anchors:** a good centrifugal chiller runs **0.55–0.70 kW/TR**; a reciprocating
or scroll machine **0.8–1.1**; anything above 1.2 needs investigating.

**Drill 60.** A chiller draws 193.2 kW and delivers 242 TR. Find kW/TR and COP.

<details><summary>Answer</summary>

```
    kW/TR = 193.2 / 242 = 0.799
    COP   = 3.517 / 0.799 = 4.40
```

*Sanity:* 0.80 kW/TR is mid-range — not a poor machine, not a great one. ✓
</details>

---

## Rung 114 — EER and ISEER

**EER** — Energy Efficiency Ratio, used for small units, mixing Btu with watts:

```
    EER = cooling (Btu/hr) / power (W)          EER = 12 / (kW/TR) = 3.413 × COP
```

**ISEER** — Indian Seasonal Energy Efficiency Ratio, the number on every BEE star
label:

```
    ISEER = total annual cooling delivered / total annual energy consumed
```

The word that matters is **seasonal**. A chiller's COP changes with ambient
temperature and part load; ISEER weights performance across a whole year's
Indian weather profile rather than one design point. It is therefore a **seasonal
average COP**, and you use it exactly like a COP:

```
    Chiller input power = cooling load / ISEER
```

**Drill 61.** Cooling load 850 kW, ISEER 4.4. Chiller electrical input?

<details><summary>Answer</summary>

850 / 4.4 = **193.2 kW**
</details>

---

# Part 2 — The system around the chiller

## Rung 115 — A chiller is not the whole plant

The compressor is the biggest single consumer, but it is not alone. A central
chilled water plant has **four** electrical loads:

```
    chilled water pump ──► EVAPORATOR ──► compressor ──► CONDENSER ──► condenser pump
                                                              │
                                                        cooling tower fan
```

| Load | Typical share |
|---|---|
| Chiller (compressor) | 65–75% |
| Condenser water pump | 10–15% |
| Chilled water pump | 5–10% |
| Cooling tower fan | 5–8% |

**Auxiliaries are 25–35% of the plant.** An audit that looks only at the chiller
misses a third of the consumption — which is exactly why exam questions ask for the
combined load.

Each auxiliary is a Day 8 or Day 9 calculation, unchanged:

```
    Pump: Q(m³/hr) × H(m) / 367,  then ÷ (η_pump × η_motor)
    Fan:  Q(m³/s) × Δp(mmWC) / 102,  then ÷ (η_fan × η_motor)
```

**Drill 62.** Chilled water pump 200 m³/hr at 18 m, η 78%. Condenser pump
600 m³/hr at 18 m, η 80%. Cooling tower fan 28 m³/s at 42.83 mmWC, η 62%. All
motors 92%. Total auxiliary load?

<details><summary>Answer</summary>

```
    Chilled pump:  200 × 18/367 =  9.81 kW  →  9.81/(0.78 × 0.92) = 13.67 kW
    Condenser pump:600 × 18/367 = 29.43 kW  → 29.43/(0.80 × 0.92) = 39.98 kW
    CT fan:       28 × 42.83/102 = 11.76 kW → 11.76/(0.62 × 0.92) = 20.61 kW
                                                                     ─────────
                                                          Total    = 74.3 kW
```

Note the **condenser pump is the largest auxiliary** — it carries more water than
the chilled side, because it must remove the cooling *plus* the compressor work
(Rung 109).
</details>

---

## Rung 116 — Specific energy consumption: chiller vs system

```
    Chiller SEC = chiller input / TR delivered
    System SEC  = (chiller + all auxiliaries) / TR delivered
```

Both in kW/TR. The gap between them is the auxiliary burden, and quoting only the
first is how plants flatter themselves.

**Drill 63.** From Drills 61 and 62: 242 TR, chiller 193.2 kW, auxiliaries 74.3 kW.

<details><summary>Answer</summary>

```
    Chiller SEC = 193.2 / 242         = 0.799 kW/TR
    System SEC  = (193.2 + 74.3) / 242 = 1.106 kW/TR
```

**The auxiliaries add 38% to the specific consumption.** The chiller looks
mid-range; the system looks mediocre. Same plant.
</details>

---

## Rung 117 — Where chiller savings actually come from

Rung 112 gave the Carnot ceiling: `COP ∝ T_cold / (T_hot − T_cold)`. Everything
that shrinks the lift saves compressor power.

| Measure | Effect | Rule of thumb |
|---|---|---|
| **Raise chilled water temperature** | Raises T_cold | **2–3% per °C** |
| **Lower condenser water temperature** | Lowers T_hot | **2–3% per °C** |
| Clean condenser tubes | Lowers condensing temperature | scale of 0.5 mm costs ~5% |
| Clean evaporator tubes | Raises evaporating temperature | similar |
| Improve cooling tower approach | Lowers T_hot | Day 10 |
| Reduce load — insulation, fresh air control | Less to lift | direct |

> **The single most common finding:** chilled water supplied colder than the
> process needs. Every degree the setpoint can be raised is 2–3% of the compressor
> bill, and the change costs nothing.

**Fouling shows up as approach temperature** on both sides — evaporator approach is
chilled water out minus refrigerant temperature; condenser approach is refrigerant
temperature minus cooling water out. Both widen as tubes foul, exactly as in Day 5.

---

## Rung 118 — Air conditioning and AHUs

Where the chilled water actually does its work.

```
    Sensible cooling  = m_air × Cp × ΔT           (dry bulb drop)
    Latent cooling    = m_air × (h_in − h_out)    (moisture removed)
    Total             = sensible + latent
```

**Sensible heat ratio** = sensible / total. Typically 0.65–0.75 for comfort
cooling — a quarter to a third of the energy goes on dehumidification, not on
temperature.

Practical points that appear as "suggest measures":

- **Fresh air is expensive.** Every m³ must be cooled from ambient. Excess fresh
  air is a common and easily fixed waste.
- **Reheat is doubly expensive** — you cool to dehumidify, then heat back up. Avoid
  where possible.
- **Filters** — a blocked filter costs fan power continuously.
- **Setpoint and dead band** — 24–25 °C is comfortable; 20 °C is expensive.

---

## Rung 119 — What an auditor checks at a chiller plant

1. **Measure chilled water flow and ΔT** → cooling delivered in TR
2. **Measure compressor input kW** → kW/TR and COP
3. **Compare with design and with the anchors** (0.55–0.70 for centrifugal)
4. **Measure both approach temperatures** → fouling on either side
5. **Add up the auxiliaries** → system SEC, not just chiller SEC
6. **Check the chilled water setpoint** against what the process actually needs
7. **Check condenser water temperature** against the cooling tower's capability
8. **Check part-load operation** — several chillers each at 40% is worse than two
   at 80%

**Recommendations by value:** raise the chilled water setpoint, clean condenser
tubes, lower condenser water temperature, sequence chillers properly, fix cooling
tower performance, reduce fresh air, VSD on chilled water pumps.

---

# Practice

## Timed — 25th sitting N-1 (40 min)

`papers/25-1.pdf` — the pharmaceutical chilled water plant. **20 marks, 30
minutes.** All four parts.

**This is the question deferred from Day 5**, where 14 of its 20 marks were
untaught. Every part is now covered:

| Part | Needs | Rung |
|---|---|---|
| a) Heat exchanger area | LMTD, area | Day 5, 41–42 |
| b) Combined pump and fan load | Pump + fan power | Day 8 Rung 75, Day 9 Rung 84, Rung 115 |
| c) Chiller and overall SEC | TR, ISEER, SEC | 111, 114, 116 |
| d) Annual energy and cost | Arithmetic | — |

You already solved part (a) correctly on Day 5 — 55.37 m² against the model's 55.2.

**Add one thing this time:** after part (c), write one sentence commenting on
whether this plant's SEC is good, and why. Recent papers ask for that, and the
Phase 2 checkpoint flagged interpretation as the habit not yet forming.

## Then — 17th sitting N-2, parts (ii) and (iii) (15 min)

`papers/17.pdf` — the beverage cooling train. You did part B(i) in Mock A; **parts
(ii) and (iii) need chiller COP**, which you now have.

## Log

Record start and finish times. Six points so far, all at or inside budget.

---

## Day 11 checklist

**Refrigeration**
- [ ] Can explain why refrigeration needs work and heat rejected exceeds heat absorbed
- [ ] Can name the four components and say what each does and why
- [ ] Know a fluid's boiling point depends on pressure — the trick of the cycle
- [ ] **Can reconstruct 1 TR = 3024 kCal/hr = 3.517 kW** from the ton of ice
- [ ] Can explain why COP exceeds 1 and is not an efficiency
- [ ] Can compute the Carnot ceiling and say what real machines achieve
- [ ] **Know COP and kW/TR run in opposite directions**, and the anchors for each
- [ ] Can convert between COP, kW/TR and EER
- [ ] Know what makes ISEER *seasonal*, and use it as a COP

**Systems**
- [ ] Can name the four electrical loads and their typical shares
- [ ] Can compute total auxiliary load from pump and fan data
- [ ] Can distinguish chiller SEC from system SEC and say why it matters
- [ ] Know the 2–3% per °C rules and where they come from
- [ ] Can read fouling from approach temperatures
- [ ] Can list audit checks and rank recommendations

**Next (Day 12):** power plants, heat rate and PAT — 7 of 8 sittings.

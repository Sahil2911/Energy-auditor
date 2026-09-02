# Day 6 — Furnaces, Waste Heat Recovery and Insulation

**Time: 3.5 hours. Book-4 Ch 2 (p. 27).**

**Source:** BEE Book 4 Ch 2, *Energy Performance Assessment of Furnaces* —
[4Ch2.pdf](https://beeindia.gov.in/sites/default/files/4Ch2.pdf) (14 pp, free).

Rungs 50–58.

> **Prerequisite check:** every part of today's practice question is covered by
> Day 1–3 (direct method, SEC) plus today. Nothing deferred.

---

## Rung 50 — Why a furnace is not a bad boiler

A boiler runs at 80–90% efficiency. A reheating furnace runs at **25–40%**.

That is not sloppy engineering. It is physics, and understanding why is the key
to the whole chapter.

**A boiler's job is to make steam at ~180 °C.** Once the heat is in the water,
the flue gas has nothing left to do, so you cool it right down — an economiser
takes it to 150–180 °C before it leaves.

**A furnace's job is to heat steel to 1250 °C.** The gas must be *hotter than the
stock* to push heat into it, so it can never leave much below the stock
temperature. Real reheating furnaces exhaust at 700–1000 °C.

Now put that in the flue gas loss formula from Day 3:

```
    L1 = m_fg × Cp × (T_gas − T_ambient) / GCV × 100
```

| | Boiler | Furnace |
|---|---|---|
| Flue gas temperature | 180 °C | 750 °C |
| ΔT | 150 | **710** |
| Ratio | 1 | **4.7×** |

**Same formula, nearly five times the temperature difference.** The BEE worked
example gives a flue gas loss of **57%** — against a boiler's 6–8%.

> **The high-temperature process is the loss.** You cannot avoid it, only recover
> it — which is why waste heat recovery matters far more on furnaces than on
> boilers, and why Rung 56 is the most valuable measure in this chapter.

A second penalty compounds it: furnaces often run at very high excess air.
The same example has **12% O₂ in flue gas = 133% excess air**, against a boiler's
15–25%. Doors open, cold air leaks in, and every kilogram of it is heated to
750 °C and thrown away.

---

## Rung 51 — Direct method and specific energy consumption

**Direct method** — heat into the stock over heat in the fuel:

```
    η = m × Cp × (t₂ − t₁) / (fuel × GCV) × 100
```

`m` is the **stock** (billets, ingots), not the fuel. `t₂ − t₁` is the
temperature rise of the metal.

**Specific energy consumption** is how furnace performance is actually quoted in
industry — energy per tonne of product:

```
    SEC = fuel consumed / production        (litres/tonne, kg/tonne, kWh/tonne)
```

Typical for oil-fired reheating furnaces: **40–60 litres/tonne**. SEC is the
number a plant tracks month to month, because it needs no instrumentation beyond
a fuel meter and a weighbridge.

**Drill 37.** 36 TPH production, billets 35 → 1250 °C, Cp 0.13 kCal/kg°C. Furnace
oil 1565 litres/hr, density 0.93, GCV 10,200. Find efficiency and SEC.

<details><summary>Answer</summary>

```
    Heat to billet = 36,000 × 0.13 × (1250 − 35) = 56,86,200 kCal/hr
    Fuel           = 1565 × 0.93 = 1455.45 kg/hr
    Heat input     = 1455.45 × 10,200 = 1,48,45,590 kCal/hr

    η   = 5,686,200 / 14,845,590 = 38.3 %
    SEC = 1565/36 = 43.5 litres/tonne  (= 40.43 kg/tonne)
```

38.3% and 43.5 L/t — both squarely in the normal band. ✓
</details>

---

## Rung 52 — The furnace loss set is not the boiler loss set

The indirect method is the same idea — `η = 100 − losses` — but **the losses are
different**, and using the boiler list will lose marks.

| Loss | Boiler | Furnace | Note |
|---|---|---|---|
| Dry flue gas | ✓ | ✓ **dominant** | 6–8% vs ~57% |
| Moisture in fuel | ✓ | ✓ | same formula |
| Hydrogen in fuel | ✓ | ✓ | same formula |
| Moisture in air | ✓ | — | usually ignored |
| CO / incomplete | ✓ | ✓ | |
| Radiation & convection | ✓ (given) | → **skin loss**, calculated |
| Unburnt in ash | ✓ | — | |
| **Openings** | — | ✓ | radiation through doors — furnace only |
| **Cooling water** | — | ✓ | skids, rolls — furnace only |
| **Scale formation** | — | ✓ | oxidised metal lost — furnace only |

The three at the bottom exist only because a furnace is hot and open in ways a
boiler is not.

---

## Rung 53 — Working the flue gas loss for a furnace

Identical machinery to Day 2A/3, but note where furnace questions differ:
theoretical air is often **given as a typical value** rather than computed from an
ultimate analysis.

```
    Excess air = %O₂ / (21 − %O₂) × 100
    AAS        = A_th × (1 + EA/100)
    m_fg       = AAS + 1
    L1         = m_fg × Cp × (T_fg − T_amb) / GCV × 100
```

**Drill 38.** 12% O₂ in flue gas, A_th = 14 kg/kg (typical for fuel oil), flue gas
750 °C, ambient 40 °C, Cp 0.24, GCV 10,000.

<details><summary>Answer</summary>

```
    EA   = 12/(21 − 12) × 100 = 133 %
    AAS  = 14 × 2.33 = 32.6 kg/kg
    m_fg = 33.6 kg/kg
    L1   = 33.6 × 0.24 × 710 / 10,000 × 100 = 57.3 %
```

**Fifty-seven percent up the stack.** Two causes multiply: 133% excess air
inflates m_fg, and 710 °C inflates ΔT. Halving the excess air would cut this loss
by roughly a third — which is why door seals and damper control are the first
recommendations in any furnace audit.
</details>

---

## Rung 54 — Openings loss, and where the chart comes from

Look into a furnace door and you feel the heat on your face. That is **radiation**,
and it is a real energy loss.

```
    Q = black body radiation × area × radiation factor × emissivity
```

- **Black body radiation** — read from a chart against furnace temperature
- **Radiation factor** — from a chart, using D/X (opening size ÷ wall thickness).
  A thick wall shields more, so a deep opening radiates less
- **Emissivity** — 0.8 for furnace brickwork

> **Where the chart actually comes from.** It is the Stefan–Boltzmann law:
> `E = σT⁴`, with σ = 5.67 × 10⁻⁸ W/m²K⁴. At 1340 °C (1613 K) that gives
> 383,800 W/m² = **33 kCal/cm²/hr**, and the BEE chart reads 36. The chart is
> Stefan–Boltzmann, plotted.
>
> **The T⁴ is the point.** Double the absolute temperature and radiation goes up
> **sixteen-fold**. That is why openings matter enormously on a 1340 °C furnace
> and hardly at all on a 180 °C boiler — and why leaving a door open for a minute
> at temperature is genuinely expensive.

**Drill 39.** Opening 1 m × 1 m, wall 460 mm, furnace 1340 °C. D/X = 2.17 gives a
radiation factor of 0.71; black body radiation 36 kCal/cm²/hr; emissivity 0.8. Fuel
GCV 10,000, consumption 368 kg/hr.

<details><summary>Answer</summary>

```
    Q = 36 × 10,000 cm² × 0.71 × 0.8 = 2,04,480 kCal/hr
    Equivalent oil = 204,480/10,000 = 20.45 kg/hr
    % loss = 20.45/368 × 100 = 5.56 %
```

One square metre of open door costs 5.6% of the furnace's entire fuel bill.
</details>

---

## Rung 55 — Skin loss

Heat escaping through the furnace shell, by **natural convection plus radiation**
from the outer surface.

Measure surface temperatures at many points, average them by zone, then read
heat release per m² from a chart (or compute it) and multiply by area.

```
    Skin loss = (heat release, kCal/m²/hr) × area
```

**Drill 40.** Roof and side walls at 122 °C, releasing 1252 kCal/m²/hr over
70.18 m². Other areas at 85 °C, 740 kCal/m²/hr over 12.6 m². Fuel GCV 10,000,
consumption 368 kg/hr.

<details><summary>Answer</summary>

```
    Hot zone   = 1252 × 70.18 = 87,865 kCal/hr → 8.79 kg/hr oil
    Other zone = 740 × 12.6   =  9,324 kCal/hr → 0.93 kg/hr oil
    Total 9.71 kg/hr → 9.71/368 × 100 = 2.64 %
```

Note the non-linearity: 122 °C releases 1252 and 85 °C releases 740 — a 44%
temperature rise gives a 69% heat release rise, because radiation is climbing as
T⁴ while convection climbs roughly as ΔT^1.25.
</details>

**Full picture for the BEE example:**

| Loss | % |
|---|---|
| Flue gas | 57.3 |
| Hydrogen | 9.1 |
| Openings | 5.6 |
| Skin | 2.6 |
| Moisture | 1.4 |
| **Total** | **76.0** |
| **Efficiency** | **24.0%** |

Cross-checks against the direct method at ~25%. Both agree, and both say the same
thing: **three-quarters of the fuel never reaches the steel.**

---

## Rung 56 — Waste heat recovery: grade matters more than quantity

A furnace throws away 57% of its fuel at 750 °C. That is a large quantity of
**high-grade** heat, and grade determines what you can do with it.

```
    Q_recoverable = m × Cp × (T_in − T_out)
```

**What the temperature lets you do:**

| Exhaust grade | Typical use |
|---|---|
| **> 650 °C** (furnaces, kilns) | Combustion air preheat, waste heat boiler, another process |
| **230–650 °C** (boilers, turbines) | Steam generation, air preheat, drying |
| **< 230 °C** (condensers, jackets) | Feedwater heating, hot water, space heating, absorption chilling |

**The two furnace devices — know the difference cold, it is a standard question:**

| | **Recuperator** | **Regenerator** |
|---|---|---|
| Principle | Continuous, through a wall | Cyclic, stores then releases |
| Construction | Gas-to-air heat exchanger | Two chambers of refractory checkerwork |
| Flow | Both streams flow at once | Flow reverses every few minutes |
| Air preheat | 300–600 °C | up to 1000 °C |
| Cost / bulk | Lower / compact | Higher / very large |
| Leakage | Low | Some cross-contamination at reversal |
| Used on | Reheating furnaces, most industry | Glass tanks, coke ovens, blast stoves |

**Why air preheat is the highest-value furnace measure.** Preheated combustion air
carries energy back into the furnace that you already paid for. The rule of thumb:

> **Every 20 °C of combustion air preheat saves roughly 1% of fuel.**

Preheating to 300 °C therefore saves around 15%. Nothing else in a furnace audit
comes close.

**Drill 41.** Flue gas 33.6 kg per kg oil at 750 °C, cooled to 400 °C in a
recuperator, Cp 0.24. Heat recovered per kg of oil, as a % of a 10,000 kCal/kg GCV?

<details><summary>Answer</summary>

```
    Q = 33.6 × 0.24 × (750 − 400) = 2,822 kCal per kg oil
    = 28.2 % of the fuel's energy, returned to the furnace
```

Half the flue gas loss, recovered — which is why recuperators are standard on
reheating furnaces.
</details>

---

## Rung 57 — Insulation and economic thickness

Heat loss through a wall, in series like the heat exchanger's U (Day 5B):

```
    Q = ΔT / (x/k + 1/h)          per m²
```

Adding insulation increases `x/k`, cutting the loss. But:

> **Insulation has diminishing returns.** The first 25 mm might cut the loss by
> 70%; the next 25 mm cuts the remainder by 70% again — a much smaller absolute
> saving for the same cost.

**Economic thickness** is where the marginal cost of more insulation equals the
value of the heat it saves. Beyond it you are spending more than you save.

For an auditor, the practical test is **surface temperature**:

| Surface temperature | Verdict |
|---|---|
| Near ambient +10–20 °C | Adequate |
| 60–80 °C | Marginal — check economics |
| > 100 °C | Under-insulated or damaged |

Also: hot spots mean damaged or missing insulation, and **uninsulated valves and
flanges** are a classic finding — one bare 150 mm valve can lose as much as
several metres of bare pipe.

---

## Rung 58 — What an auditor does at a furnace

1. **Measure flue gas O₂ and temperature.** Together they give the dominant loss.
2. **Compute SEC** and compare with the plant's own history and sector norms.
3. **Check for air ingress** — doors, cracks, damper settings. High O₂ with no
   corresponding excess fuel means leakage.
4. **Thermography the shell** for hot spots and skin loss.
5. **Time the door openings.** Openings loss scales with how long they stay open.
6. **Check whether a recuperator exists**, and if so whether the preheat
   temperature matches design (a fouled or leaking recuperator quietly stops
   working).
7. **Check scale formation** — excessive scale means over-long residence or too
   much excess air, and is both a yield and an energy loss.

Standard recommendations, in order of value: **combustion air preheat**, reduce
excess air, seal doors and cracks, insulate, minimise door-open time, optimise
loading to reduce residence time.

---

## Block C — Timed question (35 min)

**24th sitting L-2** (`papers/24-1.pdf`) — the re-rolling reheating furnace,
5 marks, 10 minutes. Direct method and SEC, then an economic comparison against a
95% efficient electric furnace.

Prerequisite check: covered by Rung 51 plus Day 1. **All parts attemptable.**

Then re-do **Drills 38–40** as one continuous indirect-method calculation, to see
the whole loss picture assemble.

## Block D — Log (20 min)

Record start and finish times. Log what the checking pass caught — including
"caught nothing".

---

## Day 6 checklist

- [ ] Can explain why furnace efficiency is 25–40% and it is not bad engineering
- [ ] Know the furnace loss set differs from the boiler's, and how
- [ ] Can compute direct efficiency and SEC
- [ ] Can compute the flue gas loss and say why it dominates
- [ ] Know openings loss follows T⁴ and what that implies
- [ ] Can compute skin loss from surface temperature and area
- [ ] Can distinguish recuperator from regenerator
- [ ] Know the 20 °C preheat ≈ 1% fuel rule
- [ ] Understand economic thickness and the surface temperature test
- [ ] Can list what an auditor checks and recommend measures in order of value

**Next (Day 7):** consolidation and Mock A — thermal only, 50 marks, timed.

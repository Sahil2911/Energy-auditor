# Day 6 — Furnaces, Waste Heat Recovery and Insulation

**Time: 4 hours. Book-4 Ch 2 (p. 27).**

**Source:** BEE Book 4 Ch 2 —
[4Ch2.pdf](https://beeindia.gov.in/sites/default/files/4Ch2.pdf) (14 pp, free).

**How this day is built.** Same as Day 5 — nothing asserted. We start from what a
furnace is and what physically happens inside one. The loss inventory is *derived*
from that picture rather than listed; the openings chart is traced back to
Stefan–Boltzmann; the skin-loss chart is reproduced from its own formula; and the
"1% per 20 °C" preheat rule is worked out rather than quoted.

Rungs 51–64.

> **Prerequisite check:** every part of today's practice question is covered by
> Day 1–3 plus today. Nothing deferred.

---

# Part 1 — What a furnace is

## Rung 51 — The problem being solved

A boiler and a furnace both burn fuel, but they are asked for different things.

**A boiler** transfers heat into water to make steam at 180–250 °C. The steam is
the product; the water is contained in tubes and never touches the flame.

**A furnace** heats a *solid* — billets, ingots, glass, clinker — to a temperature
at which it can be worked. A reheating furnace takes steel to **1250 °C** so it
can be rolled.

Three consequences follow, and they define the entire chapter:

1. The **stock is inside the furnace**, exposed to the gas. It must be loaded,
   heated, and taken out — so the furnace has **doors**, and doors leak and
   radiate.
2. To push heat *into* metal at 1250 °C, the gas around it must be **hotter than
   1250 °C**. So the furnace runs at 1300–1400 °C.
3. Gas leaving the furnace cannot be much colder than the stock it just passed
   over. So it exhausts at **700–1000 °C**, not 180 °C.

Point 3 is the whole story of furnace efficiency, and Rung 54 makes it numerical.

---

## Rung 52 — How heat gets into the stock

Same three mechanisms as Day 5, but the balance is completely different.

**Convection** — hot gas flowing over the stock. Rate roughly proportional to ΔT.

**Radiation** — the furnace walls, the flame and the gas all glow, and that energy
lands on the stock. Rate proportional to **T⁴** (Stefan–Boltzmann):

```
    E = σ · T⁴          σ = 5.67 × 10⁻⁸ W/m²K⁴,  T in kelvin
```

At room temperature radiation is trivial. At furnace temperature it dominates
utterly. Compare the two mechanisms from a surface to 30 °C surroundings:

| Surface | Radiation | Convection | Ratio |
|---|---|---|---|
| 100 °C | 0.6 kW/m² | 0.70 kW/m² | 0.9 |
| 500 °C | 19.8 | 4.7 | 4× |
| 1000 °C | 148 | 9.7 | 15× |
| **1300 °C** | **347** | **12.7** | **27×** |

**At furnace temperatures radiation is 27 times convection.** That single fact
explains most of what follows:

- Heat gets into the stock mainly by **radiation from the walls and flame** — which
  is why furnace design is about hot refractory surfaces, not gas velocity
- Heat escapes an **open door** by radiation, and enormously (Rung 59)
- Heat escapes the **outer shell** by radiation as much as by convection (Rung 60)
- In a boiler at 180 °C, none of this applies — radiation is negligible, which is
  why boiler chapters never mention it

> Doubling the absolute temperature multiplies radiation **sixteen-fold**. Nothing
> else in this paper is that non-linear.

---

## Rung 53 — Types, and why each exists

Furnace design answers: *how do I hold this material at temperature for the right
time, and get it in and out?*

**Batch furnaces** — the stock is loaded, heated, and removed as a batch.

| Type | Description | Used for |
|---|---|---|
| Box / bogie hearth | A heated box; stock on a trolley | Forging, heat treatment, small lots |
| Pit | Vertical, sunk into the floor | Long shafts, ingots |
| Bell | Cover lifted over the stock | Annealing coils, controlled atmosphere |

Batch furnaces suffer **heat storage loss** — the whole brick structure is heated
and cooled every cycle, and that energy is thrown away each time.

**Continuous furnaces** — the stock moves through while the furnace stays hot.

| Type | Description | Used for |
|---|---|---|
| Pusher | Billets pushed along a hearth | Reheating for rolling |
| Walking beam | Beams lift and step the stock forward | Large reheating, less scale |
| Rotary hearth | Circular hearth rotates | Rings, forging stock |
| Roller hearth | Stock rides on driven rollers | Strip, plate |

Continuous furnaces avoid the storage loss and can be **zoned** — preheat, heating,
soaking — each at its own temperature. Nearly all reheating furnaces are
continuous, and it is what the exam sets.

**Two more distinctions that matter to the calculation:**

- **Direct-fired** — flame in the same chamber as the stock. Efficient, but
  combustion products touch the metal (scale, contamination).
- **Indirect-fired (muffle)** — stock separated from the flame by a wall. Clean,
  but the wall is another resistance, so efficiency is lower.

---

## Rung 54 — Why a furnace cannot be efficient

Not sloppy engineering. A thermodynamic ceiling, and it is worth seeing precisely.

Recall the flue gas loss from Day 3:

```
    L1 = m_fg × Cp × (T_gas − T_ambient) / GCV × 100
```

Nothing in that formula is different for a furnace. Only the numbers are:

| | Boiler | Furnace |
|---|---|---|
| Product temperature | 180 °C steam | **1250 °C steel** |
| Exhaust gas temperature | 180 °C | **750 °C** |
| ΔT in the loss formula | 150 | **710** |
| Ratio | 1 | **4.7×** |

**The exhaust cannot be cooled further inside the furnace**, because the gas must
stay hotter than the stock to keep heating it. A boiler can bolt on an economiser
and drag the gas down to 150 °C; a furnace cannot, because there is nothing left
inside that is cold enough to receive the heat.

A second penalty compounds it. Furnaces have **doors that open** and **shells that
crack**, so air leaks in. The BEE example runs **12% O₂ in flue gas = 133% excess
air**, against a well-run boiler's 15–25%. Every kilogram of that leaked air is
heated to 750 °C and thrown away.

Both effects multiply in the same formula: more mass (`m_fg`), and a bigger ΔT.

> **Expect 25–40% efficiency and 55–60% flue gas loss.** If you compute a furnace
> efficiency of 80%, you have made an error.
>
> And note where this points: since the loss is *irreducible inside* the furnace,
> the only way to recover it is *outside* — which is why waste heat recovery
> matters far more here than on a boiler, and why Rung 62 is the most valuable
> measure in this chapter.

---

# Part 2 — Building the equations

## Rung 55 — How much heat does the job actually need?

Start with the *purpose*: raise the stock from loading temperature to working
temperature. That heat is unavoidable — it is the job.

```
    Q_useful = m × Cp × (t₂ − t₁)
```

`m` is the **stock**, not the fuel. For steel billets Cp ≈ 0.12–0.13 kCal/kg°C.

Everything else the fuel does is loss. So efficiency is simply useful over
supplied:

```
                m × Cp × (t₂ − t₁)
    η  =  ──────────────────────────── × 100
                fuel × GCV
```

That is the **direct method** — and note it did not need to be introduced, it fell
out of asking what the furnace is for.

**Drill 41.** 36 TPH of billets, 35 → 1250 °C, Cp 0.13. Furnace oil 1565 litres/hr,
density 0.93, GCV 10,200.

<details><summary>Answer</summary>

```
    Q_useful   = 36,000 × 0.13 × 1215      = 56,86,200 kCal/hr
    Fuel       = 1565 × 0.93               = 1455.45 kg/hr
    Heat input = 1455.45 × 10,200          = 1,48,45,590 kCal/hr

    η = 5,686,200 / 14,845,590 = 38.3 %
```

Inside the 25–40% band predicted by Rung 54. ✓
</details>

---

## Rung 56 — Specific energy consumption

A plant does not measure efficiency daily — that needs stock temperatures and a
Cp. It measures **fuel per tonne of product**, which needs only a fuel meter and a
weighbridge:

```
    SEC = fuel consumed / production        litres/tonne, kg/tonne, kWh/tonne
```

Typical for oil-fired reheating furnaces: **40–60 litres/tonne**.

SEC is what benchmarking uses, what PAT targets, and what a plant tracks month to
month. It is also how you compare *different* energy sources — put both on a
common basis and the comparison is direct.

**Drill 42.** From Drill 41: SEC in litres and kg per tonne. Then compare against a
95% efficient electric furnace, with oil at ₹55/kg and electricity at ₹9.25/kWh.

<details><summary>Answer</summary>

```
    SEC_oil = 1565/36 = 43.5 litres/tonne = 40.43 kg/tonne
    Cost    = 40.43 × 55 = Rs 2,224 per tonne

    Electric: heat needed = 0.13 × 1000 × 1215 = 157,950 kCal/tonne
              input = 157,950/0.95 = 166,263 kCal/tonne = 193.3 kWh/tonne
              Cost  = 193.3 × 9.25 = Rs 1,788 per tonne
```

**Electric is cheaper by ₹436/tonne** — because 95% efficiency beats 38%, and the
efficiency gap outweighs electricity's higher price per unit of energy.
</details>

---

## Rung 57 — Where the rest goes: deriving the loss inventory

Do not memorise a list. **Walk around the furnace and ask where heat can leave.**

| Route | Loss | Boiler too? |
|---|---|---|
| Out of the chimney, hot | Flue gas sensible heat | ✓ |
| As water vapour from burning hydrogen | Hydrogen loss | ✓ |
| As water vapour from fuel moisture | Moisture loss | ✓ |
| As CO, unburnt | Incomplete combustion | ✓ |
| **Radiating out of the doors** | **Openings loss** | ✗ — a boiler has none |
| Through the shell to the boiler house | **Skin loss** | ✓ (given, not calculated) |
| **In water cooling the skids and rolls** | **Cooling water loss** | ✗ |
| **In the oxidised scale falling off the billet** | **Scale loss** | ✗ |
| Heating the brickwork every cycle | Storage loss (batch only) | ✗ |

The three the boiler lacks all exist for the same reason: **a furnace is hot and
open in ways a boiler is not.** Doors radiate, hot rails must be water-cooled, and
steel at 1250 °C oxidises.

Then, as always:

```
    η = 100 − Σ losses
```

> **Using the boiler loss list on a furnace loses marks.** The openings loss alone
> is typically 5–6%.

---

## Rung 58 — Flue gas loss, the dominant term

Identical machinery to Day 2A and Day 3. One difference in furnace questions:
theoretical air is often **given as a typical value** (14 kg/kg for fuel oil)
instead of computed from an ultimate analysis.

```
    Excess air = %O₂/(21 − %O₂) × 100
    AAS        = A_th × (1 + EA/100)
    m_fg       = AAS + 1
    L1         = m_fg × Cp × (T_fg − T_amb) / GCV × 100
```

**Drill 43.** 12% O₂, A_th = 14, flue gas 750 °C, ambient 40 °C, Cp 0.24,
GCV 10,000.

<details><summary>Answer</summary>

```
    EA   = 12/(21 − 12) × 100 = 133 %
    AAS  = 14 × 2.33 = 32.6 kg/kg
    m_fg = 33.6 kg/kg
    L1   = 33.6 × 0.24 × 710 / 10,000 × 100 = 57.3 %
```

Two causes multiply, exactly as Rung 54 predicted: 133% excess air inflates
`m_fg`, and 710 °C inflates ΔT. **Halve the excess air and this loss falls by
about a third** — which is why door seals and damper control lead every furnace
audit.
</details>

---

## Rung 59 — Openings loss, from Stefan–Boltzmann

Rung 52 established that radiation ∝ T⁴ and dominates at furnace temperature. An
open door is a hole through which the furnace's interior radiates to the room.

Start from the physics:

```
    E = σ · T⁴
```

At 1340 °C = 1613 K:

```
    E = 5.67×10⁻⁸ × 1613⁴ = 3,83,800 W/m² = 33 kCal/cm²/hr
```

**BEE's black-body chart reads 36 at that temperature.** The chart *is*
Stefan–Boltzmann, plotted — you have just reproduced it.

Two corrections turn the ideal figure into a real one:

- **Emissivity** — furnace brickwork is not a perfect black body. E ≈ 0.8.
- **Radiation factor** — a hole in a *thick* wall radiates less, because the wall
  shades part of the view. Read from a chart against `D/X` (opening size ÷ wall
  thickness). A deep, narrow opening loses least.

```
    Q = black body radiation × area × radiation factor × emissivity
```

**Drill 44.** Opening 1 m × 1 m, wall 460 mm, furnace 1340 °C. D/X = 2.17 → factor
0.71. Black body 36 kCal/cm²/hr, emissivity 0.8. Oil GCV 10,000, consumption
368 kg/hr.

<details><summary>Answer</summary>

```
    Q = 36 × 10,000 cm² × 0.71 × 0.8 = 2,04,480 kCal/hr
    Equivalent oil = 20.45 kg/hr
    % loss = 20.45/368 × 100 = 5.56 %
```

**One square metre of open door costs 5.6% of the entire fuel bill.** And because
of T⁴, the same hole on a 700 °C furnace would cost roughly a *tenth* of that.
That is why "keep the doors shut" is a real energy measure and not just tidiness.
</details>

---

## Rung 60 — Skin loss, and reproducing its chart

Heat escaping the outer shell leaves by **both** mechanisms — the surface is at
80–150 °C, where Rung 52's table shows radiation and convection are comparable.

So the heat release per m² is their sum:

```
    Q = a·(t₁ − t₂)^1.25  +  4.88·E·[((273+t₁)/100)⁴ − ((273+t₂)/100)⁴]
        └── natural convection ──┘   └────────── radiation ──────────┘
```

- `a` — orientation factor: **ceiling 2.8, side walls 2.2, hearth 1.5**. Hot air
  rises, so an upward-facing surface convects best.
- The 1.25 exponent is natural convection's characteristic — not linear in ΔT,
  because the buoyant plume itself strengthens as ΔT grows.
- The second term is Stefan–Boltzmann again, rewritten in °C-friendly units.

**Check it against BEE's chart.** Side wall at 122 °C, ambient 30 °C, E = 0.8:

```
    convection = 2.2 × 92^1.25          = 627
    radiation  = 4.88 × 0.8 × [3.95⁴ − 3.03⁴] = 621
    total                                = 1,248 kCal/m²/hr
```

**BEE's chart reads 1252.** The chart is this formula. Note also that convection
and radiation are almost exactly equal here — precisely what Rung 52's table
predicted for ~100 °C.

**Drill 45.** Roof and walls at 122 °C (1252 kCal/m²/hr) over 70.18 m²; other areas
at 85 °C (740 kCal/m²/hr) over 12.6 m². GCV 10,000, fuel 368 kg/hr.

<details><summary>Answer</summary>

```
    Hot zone   = 1252 × 70.18 = 87,865 kCal/hr → 8.79 kg/hr oil
    Other zone =  740 × 12.6  =  9,324 kCal/hr → 0.93 kg/hr oil
    Total 9.71 kg/hr → 2.64 %
```

A 44% temperature rise (85→122 °C) gives a 69% rise in heat release — the T⁴ term
climbing faster than the convection term.
</details>

**The complete picture** for the BEE example:

| Loss | % |
|---|---|
| Flue gas | 57.3 |
| Hydrogen | 9.1 |
| Openings | 5.6 |
| Skin | 2.6 |
| Fuel moisture | 1.4 |
| **Total losses** | **76.0** |
| **Efficiency** | **24.0** |

The direct method on the same furnace gives ~25%. **Two independent routes agree**
— which is exactly the cross-check an auditor uses to trust their measurements.

---

# Part 3 — Recovering what escapes

## Rung 61 — Waste heat: grade matters more than quantity

57% of the fuel leaves at 750 °C. That is a lot of heat, and it is **high-grade** —
which decides what you can do with it.

```
    Q_recoverable = m × Cp × (T_in − T_out)
```

| Grade | Sources | Uses |
|---|---|---|
| **> 650 °C** | Furnaces, kilns, incinerators | Combustion air preheat, waste heat boiler, another process |
| **230–650 °C** | Boiler exhaust, turbine exhaust, dryers | Steam generation, air preheat, drying |
| **< 230 °C** | Condensers, cooling water, jackets | Feedwater heating, hot water, space heating, absorption chilling |

High-grade heat can always be *degraded* to a lower use, but never upgraded. So
recover at the **highest grade the process allows** — sending 750 °C gas to heat
washroom water wastes most of its value.

**The two furnace devices — a standard exam comparison:**

| | **Recuperator** | **Regenerator** |
|---|---|---|
| Principle | Continuous, through a wall | Cyclic — stores, then releases |
| Construction | Gas-to-air heat exchanger | Two chambers of refractory checkerwork |
| Flow | Both streams flow together | Reverses every few minutes |
| Air preheat achieved | 300–600 °C | up to 1000 °C |
| Cost and bulk | Lower, compact | Higher, very large |
| Leakage | Low | Some cross-contamination at reversal |
| Typical use | Reheating furnaces, most industry | Glass tanks, coke ovens, blast stoves |

A recuperator is just a heat exchanger (Day 5) working gas-to-air — and it suffers
exactly the problem Rung 37 predicted: **gas on both sides**, so both film
coefficients are poor and U is low. Hence recuperators are large.

---

## Rung 62 — Deriving the air preheat rule

Preheated combustion air carries energy back into the furnace that you already
paid for. Less fuel is then needed for the same job.

**How much?** Per kg of fuel you supply `AAS` kg of air. Preheating it by ΔT
returns:

```
    Heat returned = AAS × Cp_air × ΔT          kCal per kg of fuel
```

As a fraction of what a kg of fuel delivers:

```
    Fuel saving % = AAS × Cp_air × ΔT / GCV × 100
```

Put numbers in — and notice the answer depends on excess air:

| Condition | AAS | Saving per °C | "1% per…" |
|---|---|---|---|
| 25% excess air (well-run) | 17.5 | 0.042% | **1% per 24 °C** |
| 133% excess air (BEE example) | 32.6 | 0.078% | 1% per 13 °C |

> **That is where "1% fuel saving per 20 °C of air preheat" comes from.** It is
> not a magic constant — it is `AAS × Cp / GCV`, and it holds for a furnace at
> normal excess air.
>
> There is a subtlety worth noticing: a furnace running *badly* (high excess air)
> saves **more** per degree of preheat, because there is more air to preheat. But
> fixing the excess air first is cheaper and saves more overall.

Preheating to 300 °C at 25% excess air therefore saves around **13%** of fuel.
Nothing else in a furnace audit comes close.

**Drill 46.** Flue gas 33.6 kg per kg oil at 750 °C, cooled to 400 °C in a
recuperator, Cp 0.24, GCV 10,000. Heat recovered, as a % of fuel energy?

<details><summary>Answer</summary>

```
    Q = 33.6 × 0.24 × (750 − 400) = 2,822 kCal per kg oil = 28.2 % of GCV
```

Half the flue gas loss, captured. Not all of it becomes fuel saving — some is lost
in the recuperator itself — but this is why recuperators are standard equipment on
reheating furnaces.
</details>

---

## Rung 63 — Insulation and economic thickness

A furnace wall is the same resistance chain as Day 5, seen from outside:

```
    Q = ΔT / (x/k + 1/h)          per m² of wall
```

Adding insulation increases `x/k`, so Q falls. But the relationship is
**hyperbolic, not linear**:

| Insulation | Resistance x/k | Relative loss |
|---|---|---|
| None | 0 | 100% |
| 25 mm | + 0.5 | ~33% |
| 50 mm | + 1.0 | ~20% |
| 75 mm | + 1.5 | ~14% |

The first 25 mm removes two-thirds of the loss. The second 25 mm removes a further
13 points, the third only 6. **Each layer costs the same and saves less.**

**Economic thickness** is where the marginal cost of the next layer equals the
value of the heat it saves. Beyond it you spend more than you save.

The auditor's quick test is **surface temperature**:

| Surface | Verdict |
|---|---|
| Ambient +10–20 °C | Adequate |
| 60–80 °C | Marginal — check economics |
| > 100 °C | Under-insulated or damaged |

Two classic findings: **hot spots** (damaged or missing insulation) and
**uninsulated valves and flanges** — one bare 150 mm valve can lose as much heat
as several metres of bare pipe, because of its surface area and the fact that
nobody insulates it for fear of hiding leaks.

---

## Rung 64 — What an auditor does at a furnace

1. **Measure flue gas O₂ and temperature.** Together these give the dominant loss
   in one measurement.
2. **Compute SEC** and compare with plant history and sector norms.
3. **Check for air ingress** — doors, cracks, damper settings. High O₂ *without*
   correspondingly high fuel means leakage rather than deliberate excess air.
4. **Thermography the shell** for hot spots and skin loss.
5. **Time the door openings.** Openings loss scales directly with how long they
   stay open (Rung 59).
6. **Check the recuperator** if fitted — is the preheat temperature at design? A
   fouled or internally leaking recuperator quietly stops working and nobody
   notices.
7. **Check scale formation.** Heavy scale means excessive residence time or too
   much excess air, and is both a yield and an energy loss.

**Recommendations, in order of value:**

1. Combustion air preheat (Rung 62) — biggest single measure
2. Reduce excess air — cheap, immediate
3. Seal doors and cracks
4. Minimise door-open time
5. Insulate, to economic thickness
6. Optimise loading to cut residence time and scale

---

# Practice

## Timed — 24th sitting L-2 (35 min)

`papers/24-1.pdf` — the re-rolling reheating furnace, 5 marks, 10 minutes. Direct
method, SEC, and the electric furnace comparison.

**Prerequisite check: fully covered** by Rungs 55–56 plus Day 1.

Then work **Drills 43–45 as one continuous indirect-method calculation**, so the
whole loss picture assembles in one pass, and check it against the 24% in Rung 60.

## Log (20 min)

Record start and finish times. Log what the checking pass caught — including
"caught nothing".

---

## Day 6 checklist

**Understanding**
- [ ] Can explain why a furnace exhausts at 750 °C and a boiler at 180 °C
- [ ] Know radiation goes as T⁴ and dominates convection 27:1 at 1300 °C
- [ ] Can name batch and continuous types and say why continuous is preferred
- [ ] Can predict 25–40% efficiency before calculating anything

**Derivation**
- [ ] Can derive the loss inventory by walking round the furnace
- [ ] Can reproduce the black-body chart from σT⁴
- [ ] Can explain the skin-loss formula's two terms and its 1.25 exponent
- [ ] **Can derive the "1% per 20 °C" preheat rule** from AAS × Cp / GCV

**Calculation**
- [ ] Can compute direct efficiency and SEC
- [ ] Can compute flue gas, openings and skin losses
- [ ] Can cross-check direct against indirect

**Judgement**
- [ ] Can distinguish recuperator from regenerator and say when each is used
- [ ] Can match a waste heat grade to a sensible use
- [ ] Understand economic thickness and the surface-temperature test
- [ ] Can list audit checks and rank recommendations by value

**Next (Day 7):** consolidation and Mock A — thermal only, 50 marks, timed.

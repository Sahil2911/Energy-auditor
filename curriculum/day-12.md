# Day 12 — Power Plants, Heat Rate and PAT

**Time: 3.5 hours. Book-4 Ch 11.**

Appears in **7 of 8 sittings** and rising. Rungs 122–133.

> Book-4 Ch 11 in the **4th edition** is Power Plants. In the 3rd edition that
> number was Financial Analysis, so the chapter BEE publishes online at `4Ch11.pdf`
> is *not* this one. This is built from first principles and the past papers. Your
> supplied guidebook has the right chapter — tab it (**PP**).

> **Prerequisite check — data-item level.** The timed question's parts A and B are
> Day 3 (indirect method, evaporation ratio). Part C needs **flash steam**, which
> is Rung 132 below — added because the question supplies three enthalpies that
> nothing else in the curriculum used.

---

# Part 1 — Power plant performance

## Rung 122 — The chain, and where the energy goes

A thermal power plant is four machines you already know, in series:

```
    fuel ──► BOILER ──► steam ──► TURBINE ──► GENERATOR ──► electricity
                                     │
                                CONDENSER ──► cooling tower
```

Each has an efficiency, and they multiply:

```
    η_overall = η_boiler × η_turbine × η_generator
              ≈ 0.88 × 0.42 × 0.98  ≈ 36 %
```

**The turbine is the bottleneck**, and not because it is badly made. A steam
cycle's efficiency is capped by the temperatures it works between (Carnot again,
Day 11 Rung 112). With steam at 540 °C and a condenser at 40 °C:

```
    η_Carnot = 1 − 313/813 = 61 %
```

Real cycles reach 40–45% of the *cycle*, giving ~36% overall. **Around 55% of the
fuel leaves through the condenser as low-grade heat** — which is why a power
station's cooling tower is the biggest thing on the site.

That is not recoverable at the condenser: it is at 40 °C, below anything useful.
**Recovering it is the whole point of cogeneration** (Day 4) — and now you can see
why a back-pressure plant's heat rate looks so bad and its EUF so good.

---

## Rung 123 — Heat rate, three of them

**Heat rate is the inverse of efficiency**, expressed as heat in per unit of
electricity out:

```
    Heat rate (kCal/kWh) = heat input / electricity generated
```

Since 1 kWh = 860 kCal:

```
    η = 860 / heat rate              heat rate = 860 / η
```

A 36% plant has a heat rate of 860/0.36 = **2,389 kCal/kWh**. That is the anchor:
good coal plants run **2,300–2,600**; poor ones above 3,000.

> **Reciprocal alert.** Lower heat rate is better; higher efficiency is better.
> Same family as COP and kW/TR. `reference/reciprocal-traps.md`.

**Three heat rates, differing by what they count:**

| | Measures | Formula |
|---|---|---|
| **Turbine heat rate** | Steam energy per unit generated | heat in steam / kWh |
| **Gross heat rate** | Fuel energy per unit **generated** | fuel × GCV / gross kWh |
| **Net heat rate** | Fuel energy per unit **exported** | fuel × GCV / net kWh |

The difference between gross and net is the **auxiliary power** the station
consumes itself.

---

## Rung 124 — Auxiliary power, and the conversion that trips people

A power station runs its own fans, pumps and mills. Coal plants consume **8–10%**
of what they generate.

```
    Net generation = Gross generation × (1 − APC)
```

Heat input is unchanged, so:

```
    Net heat rate = Gross heat rate / (1 − APC)
```

> **The division is the point.** Net heat rate is always **worse** (higher) than
> gross, because the same fuel now buys less exported electricity. If your net heat
> rate comes out lower than gross, you have inverted it.

**Drill 64.** Plant A: gross heat rate 2400 kCal/kWh, auxiliary power 8%.
Plant B: net heat rate 2500. Which is more efficient?

<details><summary>Answer</summary>

```
    Plant A net = 2400 / (1 − 0.08) = 2400/0.92 = 2608.7 kCal/kWh
```

**Plant B is more efficient** — 2500 against 2608.7.

The trap is comparing 2400 with 2500 and choosing A. **They are not the same
quantity.** Always convert to a common basis before comparing, and net is the
honest basis because it is what leaves the gate.
</details>

---

## Rung 125 — Plant load factor and availability

```
    PLF = actual generation / (rated capacity × hours) × 100
    Availability = hours available / total hours × 100
```

PLF matters for energy because **part-load operation is inefficient**. A turbine
designed for full flow runs poorly at 60%, and heat rate rises. A plant at 60%
PLF may show a heat rate 5–8% worse than at full load, with no equipment fault at
all.

Availability and PLF differ: a plant can be available and not despatched.

---

# Part 2 — PAT

## Rung 126 — What the scheme is

**Perform, Achieve and Trade** is the mechanism the Energy Conservation Act uses
on designated consumers. You met the Act in Paper 1.

The logic:

1. Each designated consumer gets a **baseline** specific energy consumption from
   its own historical performance
2. BEE sets a **target** reduction over a three-year cycle
3. Beat the target and you earn tradable **ESCerts**; miss it and you must buy them

For a thermal power plant the metric is **net heat rate**, in kCal/kWh.

## Rung 127 — TOE, and the e-certificate calculation

The certificate unit is the **tonne of oil equivalent**:

```
    1 TOE = 10⁷ kCal        (1000 kg × 10,000 kCal/kg)
    1 e-Certificate = 1 TOE
```

The calculation is a three-step chain, and every step is a unit conversion:

```
    1. Reduction in net heat rate  = baseline NHR − assessment year NHR   kCal/kWh
    2. Energy saved                = reduction × generation                kCal
    3. e-Certificates              = energy saved / 10⁷                    TOE
```

**Drill 65.** Assessment year gross heat rate 2300 kCal/kWh, auxiliary power 8%.
Baseline net heat rate 2600. Baseline generation 5000 MU.

<details><summary>Answer</summary>

```
    Assessment year NHR = 2300/(1 − 0.08)        = 2500 kCal/kWh
    Reduction           = 2600 − 2500            = 100 kCal/kWh
    Energy saved        = 100 × 5000 × 10⁶       = 5 × 10¹¹ kCal
    e-Certificates      = 5 × 10¹¹ / 10⁷         = 50,000
```

*Sanity:* 1 MU = 10⁶ kWh, so 5000 MU = 5 × 10⁹ kWh. **Check that conversion
first** — an error there moves the answer by a factor of a thousand and everything
downstream looks reasonable.
</details>

**The three unit anchors for this calculation:**

| | |
|---|---|
| 1 MU | 10⁶ kWh |
| 1 TOE | 10⁷ kCal |
| 1 kWh | 860 kCal |

---

# Part 3 — Blowdown heat recovery and flash steam

## Rung 128 — Why blowdown is worth recovering

From Day 3: boiler water concentrates as steam leaves pure, so some must be blown
down. It leaves as **saturated water at boiler pressure** — at 115 bar that is
water at about 320 °C carrying 352 kCal/kg.

Throwing it down the drain wastes both the heat and the treated water. On a large
boiler blowdown is 2–5% of steam production, so this is real money.

## Rung 129 — What flash steam is, and deriving how much

Drop high-pressure saturated water to a lower pressure and something specific
happens. At the lower pressure it is now **above** the saturation temperature — it
holds more energy than saturated water at that pressure can hold. The excess
boils off instantly.

**That is flash steam**, and the amount follows from a single energy balance.

Per kg of blowdown, let `x` be the fraction that flashes:

```
    Energy before = energy after

    hf₁  =  x · hg₂  +  (1 − x) · hf₂
```

where `hf₁` is saturated liquid enthalpy at the **high** pressure, and `hg₂`, `hf₂`
are saturated vapour and liquid enthalpies at the **low** pressure.

Rearranging:

```
             hf₁ − hf₂          hf₁ − hf₂
    x  =  ─────────────  =  ───────────────
             hg₂ − hf₂            hfg₂
```

**In words: the excess enthalpy above saturated liquid at the new pressure,
divided by the latent heat it takes to make vapour there.**

**Drill 66.** Blowdown from a drum at 115 bar g, saturated liquid enthalpy
352 kCal/kg, flashed to 2 bar g. At 2 bar g: total enthalpy of steam 646 kCal/kg,
latent heat 526 kCal/kg. How much flash steam per kg of blowdown?

<details><summary>Answer</summary>

```
    hf₂ = hg₂ − hfg₂ = 646 − 526        = 120 kCal/kg
    x   = (352 − 120)/526               = 0.441 kg per kg of blowdown
```

**44% of the blowdown flashes to usable low-pressure steam.** The remaining 56%
is still hot water at 120 kCal/kg, which can preheat feedwater in a heat
exchanger.

*Sanity:* x must lie between 0 and 1. And the bigger the pressure drop, the more
flashes — which is why blowdown from a high-pressure drum is worth recovering and
blowdown from a 10 bar boiler barely is.
</details>

**The standard recovery scheme:** blowdown → flash vessel → LP steam to the
deaerator, hot condensate through a heat exchanger to preheat makeup water. Two
recoveries from one stream.

---

## Rung 130 — What an auditor checks at a power plant

1. **Compute all three heat rates** and compare with design at the same load
2. **Measure auxiliary power** — a creeping APC is often ID/FD fans or CW pumps
3. **Check condenser vacuum.** A 10 mmHg loss of vacuum costs roughly 1–1.5% of
   heat rate — the single most sensitive parameter on the plant
4. **Check condenser approach and cooling tower performance** (Day 10)
5. **Check boiler efficiency** by the indirect method (Day 3)
6. **Check blowdown rate** and whether its heat is recovered
7. **Check PLF and the load profile** — heat rate at part load

**Recommendations by value:** restore condenser vacuum, reduce excess air, recover
blowdown heat, cut auxiliary consumption (VSDs on fans and pumps — Days 8–10),
improve feedwater heating, minimise part-load running.

---

# Practice

## Timed — 23rd sitting N-3 (35 min)

`papers/23-1.pdf` — an oil refinery captive power plant with a pet coke fired
boiler. **20 marks, 30 minutes.**

| Part | Marks | Needs |
|---|---|---|
| A) Boiler efficiency, indirect method | 12 | Day 3 |
| B) Evaporation ratio | 3 | Day 1 |
| C) Flash steam per kg of blowdown | 5 | Rung 129 |

**Prerequisite check: all parts covered.** Note the fuel has moisture *and*
sulphur, and the question supplies a humidity figure — so L4 is in play.

<details><summary>Check yourself after attempting</summary>

```
    A_th  = [11.6(88.8) + 34.8(3.6 − 1.4/8) + 4.35(3.6)]/100 = 11.649
    EA    = 6/(21−6) × 100 = 40 %,  AAS = 16.31,  m_dfg = 16.97

    L1 = 16.97 × 0.29 × 220/8340 × 100        = 12.98 %
    L2 = 9(0.036)(584 + 0.45×220)/8340 × 100  =  2.65 %
    L3 = 0.014(584 + 0.45×220)/8340 × 100     =  0.12 %
    L4 = 16.31 × 0.0204 × 0.45 × 220/8340 × 100 = 0.40 %
    Radiation 1.0 %, unburnt 0.5 %
                                                ────────
    Total losses 17.65   →   η = 82.35 %

 B) ER = 0.8235 × 8340/(816 − 200) = 11.15 kg steam/kg fuel
 C) x  = (352 − 120)/526 = 0.441 kg flash steam per kg blowdown
```
</details>

## Then — 25th sitting L-2 (10 min)

`papers/25-2.pdf` — the PAT e-certificate question. 5 marks, 8 minutes. Drill 65
is this question.

Also do **19th L-1** (`papers/19-1.pdf`) — the two-plant comparison, Drill 64.
It is a one-line answer that most candidates get backwards.

## Log

Record start and finish times. **Add the interpretation sentence** — for the pet
coke boiler, comment on whether 82% is good for a solid fuel boiler and why.

---

## Day 12 checklist

**Power plant**
- [ ] Can explain why overall efficiency is ~36% and where the 55% goes
- [ ] Know heat rate is the inverse of efficiency, and `η = 860/HR`
- [ ] Can distinguish turbine, gross and net heat rate
- [ ] **Know net heat rate = gross/(1 − APC)** and that net is always worse
- [ ] Can compare two plants quoted on different bases
- [ ] Know why part-load operation raises heat rate

**PAT**
- [ ] Can explain baseline, target and ESCerts
- [ ] Know 1 TOE = 10⁷ kCal and 1 MU = 10⁶ kWh
- [ ] **Can run the e-certificate chain** and sanity-check the MU conversion

**Blowdown**
- [ ] Can explain what flash steam is and why it forms
- [ ] **Can derive `x = (hf₁ − hf₂)/hfg₂`** from an energy balance
- [ ] Know both recoveries from a blowdown stream

**Next (Day 13):** cement, steel, textile, sugar and financial analysis — the
4th-edition sector chapters, appearing more in recent papers.

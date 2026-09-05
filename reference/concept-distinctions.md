# Concept Distinctions

**Pairs of things Paper 4 expects you to tell apart.** Section I (10 × 1) and
Section II are almost entirely built from these, and they are cheap marks — a
distinction understood once is a mark every sitting.

This file grows. **Every time a mock turns up a distinction you were not sure of,
it gets added here**, with the physics rather than the definition.

---

## 1. Vapour compression vs vapour absorption refrigeration

Both machines do the same job — move heat from a cold place to a hot one — and
both obey the same law: that never happens by itself, so something must be spent.
**The difference is what gets spent: work, or heat.**

### The common skeleton

Every refrigeration cycle needs four things:

```
   EVAPORATOR  — refrigerant boils at low pressure, absorbing heat   ← the cooling
        │
   [ raise the vapour's pressure ]                                   ← the cost
        │
   CONDENSER   — refrigerant condenses at high pressure, rejecting heat
        │
   EXPANSION   — pressure drops back, refrigerant cools
```

Only the middle step differs.

### VCR — raise the pressure with a compressor

A motor drives a compressor that squeezes the refrigerant vapour. Compressing a
**gas** is expensive: the work is roughly `∫V dp`, and a gas has a large specific
volume, so the integral is large. That work is the electricity bill.

| | |
|---|---|
| Input | **Electrical work**, at the compressor shaft |
| Refrigerants | R-134a, R-410A, R-123, ammonia (R-717) |
| COP | **4–6** for a good water-cooled chiller |
| kW/TR | 0.6–0.9 at the motor |
| Reaches | Any temperature, including deep sub-zero |

### VAR — raise the pressure with a "thermal compressor"

The trick: **dissolve the refrigerant vapour in a liquid, pump the liquid, then
boil it back out.** Pumping a liquid costs almost nothing, because a liquid is
nearly incompressible — its specific volume is ~1/1000 of the vapour's, so `∫V dp`
collapses. The compressor is replaced by:

```
   ABSORBER   — vapour dissolves into the absorbent (weak → strong solution)
        │        this RELEASES heat, so the absorber needs cooling water
   PUMP       — strong solution pumped to high pressure   ← tiny work, ~1% of VCR
        │
   GENERATOR  — solution is HEATED, driving the refrigerant back off as vapour
        │        ← this is where the energy actually goes in
   (weak solution returns to the absorber through a heat exchanger)
```

Two working pairs, and which one you have decides what the machine can do:

| Pair | Refrigerant | Absorbent | Reaches | Note |
|---|---|---|---|---|
| **LiBr–water** | water | lithium bromide | **> 0 °C only** — water freezes | Comfort cooling, process chilled water. Risk: **crystallisation** of LiBr if the solution gets too cold or too strong |
| **Ammonia–water** | ammonia | water | **sub-zero** | Cold storage, ice plants. Needs a rectifier and ammonia handling |

| | |
|---|---|
| Input | **Heat** at the generator — steam, hot water, exhaust gas, or direct firing |
| COP | **0.6–0.7** single effect · **1.1–1.4** double effect · ~1.7 triple |
| Reaches | LiBr above 0 °C; ammonia–water below |

**Single vs double effect.** In a double-effect machine the vapour driven off in
the first (high-temperature) generator is not sent straight to the condenser — its
*condensation heat* is used to drive a second generator at lower pressure. The same
heat does two jobs, and the COP roughly doubles. It is the identical idea to
multiple-effect evaporation in a sugar plant.

### The comparison that traps people

> **A VAR's COP of 1.2 is not "worse" than a VCR's COP of 5.**

They are not the same ratio. The VCR's denominator is **electrical work** — high-
grade energy, three units of fuel burnt to deliver one. The VAR's denominator is
**low-grade heat**, which may be exhaust gas that was going up a stack anyway.

**So never compare COPs across the two. Compare cost per TR-hour**, which is
exactly what the 20th sitting's N-3 asks:

```
  Absorption, COP 1.2, gas at ₹27/m³, 9450 kCal/m³, 80% firing:
     heat to generator = 3024/1.2 = 2520 → fuel 2520/0.8 = 3150 kCal/h
     cost = 3150 × 27/9450                            = ₹9.00 per TR-h

  Centrifugal, 0.8 kW/TR at ₹8.5/kWh:
     cost = 0.8 × 8.5                                 = ₹6.80 per TR-h
```

### The number an auditor actually cares about: heat rejection

**This is the one that shows up in exam questions and in real retrofits.**
Everything that goes in must come out at the condenser side.

```
  VCR  rejects = cooling load + compressor SHAFT work
               = 3024 + (0.8 × 0.875) × 860  = 3626 kCal/h per TR

  VAR  rejects = cooling load + generator heat
               = 3024 + 2520                 = 5544 kCal/h per TR
```

**A VAR throws away about 50% more heat per TR than a VCR.** So:

- Replacing a VCR with a VAR **needs a bigger cooling tower** — a standard audit
  finding, and a standard exam question.
- Replacing a VAR with a VCR **frees tower capacity**, which is why the 20th
  sitting then asks whether the freed capacity covers a new process load.
- A VAR's cooling water flow is roughly 1.5× a VCR's for the same TR, so pump power
  goes up even as chiller power goes down. Count it.

### Choosing between them

| Choose **VAR** when | Choose **VCR** when |
|---|---|
| Waste heat is available and otherwise wasted | No waste heat on site |
| Electricity is expensive, or demand charges bite | Power is cheap and reliable |
| Electrical supply is limited | Space or cooling water is limited |
| Refrigerant-free operation is wanted | Sub-zero temperatures needed (unless NH₃–water) |
| Load is steady | Load swings — VCR part-loads better |

**Maintenance and life:** a VAR has almost no moving parts (one small solution
pump), so it is quiet and long-lived — but it runs under deep vacuum, so **air
in-leakage is its characteristic fault**, and a purge unit that runs constantly is
the tell.

---

## 2. Evaporation ratio vs boiler efficiency

**Not the same thing, and the 25th sitting asks about it twice.**

```
    ER = kg of steam raised / kg of fuel burnt          (a measured ratio)
    η  = ER × (h_steam − h_feedwater) / GCV             (an energy fraction)
```

- **ER is blind to steam quality.** If the boiler carries over water — wet steam —
  the mass on the steam meter goes *up* while the enthalpy per kg goes *down*.
  **High ER with wet steam means poor efficiency, not good.** *(25th S-7 → False.)*
- **ER is blind to feedwater temperature.** Raise feedwater from 40 °C to 105 °C
  and ER rises with no change in the boiler at all.
- **ER does not care about GCV vs NCV**, because it never uses a calorific value.
  Efficiency does, and must state its basis. *(25th S-1 → True.)*

Use ER for day-to-day tracking on one boiler with one fuel. Use efficiency to
compare anything.

---

## 3. Direct vs indirect boiler efficiency — and why blowdown is in neither

| | Direct | Indirect |
|---|---|---|
| Method | Output ÷ input | 100 − Σ losses |
| Needs | Steam flow, fuel flow, two enthalpies | Ultimate analysis, flue gas analysis, temperatures |
| Gives | One number | **Where the losses are** |
| Weakness | Tells you nothing about *why* | Long; needs a lab |

**Blowdown appears in neither.** *(25th S-5, 23rd, 18th → False.)* The indirect
method counts what leaves in the **flue gas** — dry gas, hydrogen's water, fuel
moisture, air humidity, radiation, unburnt. Blowdown leaves in the **water**, on
the other side of the boiler shell entirely. It is a real loss and a real audit
finding; it just is not one of the seven.

---

## 4. Back-pressure vs extraction-condensing turbine

```
  BACK-PRESSURE      steam in → work out → ALL steam leaves at process pressure
                     no condenser. Power is dictated by the process steam demand.

  EXTRACTION-COND.   steam in → some bled off at process pressure
                                → the rest expands to a condenser at ~0.1 bar
```

| | Back-pressure | Extraction-condensing |
|---|---|---|
| Power per kg steam | Low (small Δh) | High (large Δh) |
| Fuel wasted at the condenser | **None** | ~55% of the fuel |
| EUF | **75–85%** | 35–45% |
| Heat rate | Looks terrible (~34,000) | Looks normal (~2,500) |
| Flexibility | None — power follows steam | Power and steam set independently |

**A back-pressure set's heat rate is a meaningless number**, because heat rate
charges all the fuel to the electricity and ignores the steam, which was the point.
Judge cogeneration on **EUF** or **heat-to-power ratio**, never on heat rate.

---

## 5. Condenser vacuum vs condenser back pressure

Two ways of quoting the same state, and they run **opposite**:

```
    vacuum (mmHg) = barometric pressure − absolute back pressure
    e.g. 755 − 82 = 673 mmHg vacuum
```

**Higher vacuum = lower back pressure = better.** More vacuum means a bigger
enthalpy drop across the LP turbine, so more work from the same steam. This is why
**colder cooling water improves heat rate** *(25th S-9 → True)*: colder water
condenses at a lower pressure, deepening the vacuum.

The limit is the cooling water temperature. You cannot condense below it.

---

## 6. TTD and DCA — feedwater heater performance

Regenerative feedwater heaters bleed steam from the turbine to preheat feedwater.
Two approach temperatures grade them:

```
    TTD = saturation temp of the bled steam − feedwater OUTLET temp
    DCA = drain (condensate) temp − feedwater INLET temp
```

**Lower is better for both** *(25th S-6 → True)* — each says the heater is
transferring more heat, so less bled steam is needed for the same feedwater
temperature, so more steam stays in the turbine making power. Rising TTD usually
means fouled or air-bound tubes; rising DCA means a drain-cooler problem or a
level fault.

---

## 7. Range vs approach (cooling towers)

```
    range    = hot water in − cold water out        ← set by the PROCESS
    approach = cold water out − ambient WET BULB    ← set by the TOWER
```

**Judge a tower on approach, never on cold water temperature.** A tower giving
30 °C on a 25 °C wet bulb (approach 5) is doing worse than one giving 32 °C on a
28 °C wet bulb (approach 4). Range says nothing about the tower — double the heat
load at the same water flow and range doubles with the tower unchanged.

**Effectiveness = range/(range + approach)** ties them together.

---

## 8. COP, EER, kW/TR, ISEER

All the same physics, four dresses:

```
    COP    = cooling ÷ power,   both in the same units        — dimensionless
    kW/TR  = power ÷ cooling                                  — INVERSE, lower better
    EER    = Btu/h of cooling per watt = COP × 3.412
    ISEER  = seasonal, weighted over an Indian temperature/load profile
```

```
    COP × kW/TR = 3024/860 = 3.517         so  COP = 3.517/(kW/TR)
```

**Watch the basis.** COP is conventionally on **shaft** power; kW/TR is on **motor
input**. They differ by the motor efficiency. For an *energy saving* — what the
meter stops paying for — the electrical basis is the right one.

**ISEER vs COP:** a rated COP is one operating point at full load and design
ambient. Real equipment part-loads most of the year. ISEER integrates over the
season and is always lower than the rated COP.

---

## 9. GCV vs NCV

```
    NCV = GCV − latent heat of the water formed from the fuel's hydrogen
        ≈ GCV − 53 × %H₂ ... (kCal/kg)
```

GCV assumes the water vapour condenses and gives its latent heat back. It does not,
in a normal boiler — it goes up the stack as vapour. So:

- **Indian practice quotes GCV**, and BEE's papers use GCV unless told otherwise.
- Efficiency on NCV always reads **higher** than on GCV, for the same boiler.
- **Always state which basis you used.** An unlabelled efficiency is ambiguous.
- The gap is largest for hydrogen-rich fuels: ~10% for natural gas, ~6% for oil,
  ~4% for coal.

---

## 10. Static, velocity and total pressure (fans and ducts)

```
    total = static + velocity            p_v = ρv²/2
```

- **Static pressure** pushes against the duct walls — it is what overcomes friction.
- **Velocity pressure** is the air's kinetic energy — what a pitot reads directly.
- A fan's rating is usually **static** or **total** — check which, because using
  the wrong one throws the efficiency out.

**Fan efficiency uses total pressure** (mechanical), or static pressure (static
efficiency). They are different numbers for the same fan.

---

## 11. FAD vs swept volume (compressors)

**Free Air Delivery is what the compressor actually delivers, referred back to
ambient conditions at the intake.** Swept volume is what the pistons displace.
FAD/swept volume is the **volumetric efficiency**, typically 65–85% — the gap is
clearance volume, valve losses and leakage.

A compressor's nameplate CFM is usually FAD. A pump-up test measures FAD directly,
and correcting it back to intake temperature is the step people skip.

---

## 12. Simple payback vs NPV vs IRR vs PI

| Measure | Question it answers | Blind to |
|---|---|---|
| **Simple payback** | How long till I get my money back? | Everything after that date; time value of money |
| **NPV** | How much value does this create, in today's rupees? | Project size — ₹1 lakh NPV on a ₹1 lakh or ₹1 crore investment |
| **IRR** | What return does the project itself earn? | Scale; can be misleading with irregular cash flows |
| **PI** | Value per rupee invested — ranks projects when capital is short | — |

**Discounted payback** is always longer than simple payback, and the gap is the
whole argument for discounting.

⚠️ **PI has two conventions.** Standard is `PV of inflows / I`; **BEE's model
answers use `NPV / I`**. They differ by exactly 1. Write the formula you used.

---

## 13. Sensible vs latent heat

```
    sensible  Q = m·Cp·ΔT       changes TEMPERATURE — a thermometer sees it
    latent    Q = m·h_fg        changes PHASE       — a thermometer sees nothing
```

Every drying, cooling-tower, HVAC and boiler question splits along this line. The
latent term usually dominates and is usually the one omitted: **540 kCal to boil a
kg of water, against 100 to heat it from 0 to 100 °C.**

Where each appears:

| | Sensible | Latent |
|---|---|---|
| Building load | walls, roof, glass, lights, equipment | people, infiltration, wet processes |
| Cooling tower | the range | the evaporation |
| Boiler losses | dry flue gas | hydrogen, fuel moisture |
| Stenter drying | warming the water to 80 °C | the 540 that evaporates it |
| Thermic fluid | **all of it** — no phase change | none |

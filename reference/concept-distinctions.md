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
Everything that goes in must come out at the condenser side — conservation of
energy with nowhere else to go:

```
    Q_rejected  =  Q_cooling  +  the energy spent doing the cooling
```

What changes between the machines is **what "spent" is made of**:

```
  VCR  spent = compressor SHAFT work
       per TR = 3024 + (kW/TR × η_motor) × 860
              = 3024 + (0.8 × 0.875) × 860  = 3024 +  602 = 3626 kCal/h

  VAR  spent = GENERATOR heat
       per TR = 3024 + 3024/COP
              = 3024 + 2520                 = 3024 + 2520 = 5544 kCal/h
```

> **The motor losses are NOT in the VCR line.** They become heat in the motor
> housing and the plant room, not in the refrigerant. The tower sees **shaft**
> power — which is why the same 87.5% that belongs in the COP belongs here.

**On a tower-adequacy question, write these two lines first:**

```
    CAPACITY  = what the OLD machine rejected   (the tower was sized for it)
    NEW LOAD  = what the NEW machine rejects  +  anything newly connected
```

Two different rejection figures, two different roles. Using one figure on both
sides compares the old plant to itself and answers nothing.

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

---

## 14. Difference-then-convert vs convert-then-difference

> **When the conversion factor differs between the two cases, convert each case
> first, then take the difference. Never difference first and convert once.**

```
    Δ(E)/k  ≠  Δ(E/k)        whenever k is not the same on both sides
```

The distributive law you use without thinking — `(a − b)/k = a/k − b/k` — needs the
**same k** on both terms. The moment the two cases have different conversion
factors, it fails, and it fails silently: the answer looks reasonable and is out by
tens of per cent.

**Worked, from the 24th sitting's DRI steel question.** Coal improved from GCV 6000
to 6200 between the base and assessment years.

```
  Difference first, convert once (what BEE's model answer does):
      energy saved = 257.55 million kCal/day
      ÷ 6200                                                    = 41.5 TPD

  Convert each year, then difference (physically correct):
      base coal       = 3164.18 × 10⁶ / 6000 / 1000             = 527.37 TPD
      assessment coal = 2906.63 × 10⁶ / 6200 / 1000             = 468.82 TPD
      reduction                                                  =  58.55 TPD
```

**A 40% gap.** Decompose it and both halves show up:

```
    using less energy   (at the base year's GCV)      = 42.92 TPD
    burning better coal (6000 → 6200, same energy)    = 15.63 TPD
                                                        ───────────
                                                         58.55 TPD
```

Differencing the energy first **throws away the fuel-quality half entirely**.

### Where this trap is waiting

| Situation | The factor that changes |
|---|---|
| Fuel saving across two years | **GCV** — a fuel switch or a better grade |
| Cost saving between two options | **Tariff** — grid vs captive, day vs night |
| CO₂ reduction from a fuel switch | **Emission factor** — coal vs gas vs biomass |
| PAT / TOE across a period | **Any** fuel mix change inside the period |
| Coal per kWh across two plants | **Heat rate** and **GCV**, both |

### The tell

**If two cases quote different values for the same conversion constant, you are in
this trap.** Look at the data table before you start: two GCVs, two tariffs, two
emission factors in the same problem is the warning.

### And in the exam

BEE's model answers sometimes use the shortcut. Give the correct answer first, then
the model answer's number in one parenthetical line saying why they differ — the
marker finds their number in your working, and the reasoning can only earn credit.

---

## 15. Comparing options: hold the SERVICE constant, not the input

```
     RIGHT:  both options must deliver the same OUTPUT
     WRONG:  both options must consume the same INPUT
```

Before comparing anything, write one line naming **what stays the same** — the job
being done. Then ask each option what it costs to deliver that job.

| Comparison | The invariant |
|---|---|
| Diesel heater vs heat pump | kCal delivered to the water |
| Absorption vs centrifugal chiller | TR of cooling |
| Throttle vs VSD | m³/hr at the required head |
| Coal vs gas boiler | kg/hr of steam at the required enthalpy |
| Old vs new motor | shaft kW at the driven machine |

**Worked, from the 16th sitting's L-1.** A 70%-efficient diesel heater vs a heat
pump at COP 2.5, both delivering 24,000 L/day lifted 40 °C.

```
   The service = 24 000 × 40 × 1 = 960 000 kCal/day    ← belongs to the WATER

   Diesel:     burns 960 000/0.7 = 1 371 429 kCal → 150.7 L → ₹7535/day
   Heat pump:  supplies 960 000 kCal
               electricity = 960 000/2.5 = 384 000 kCal = 446.5 kWh → ₹4465/day
   REDUCTION                                                        = ₹3070/day
```

Running the heat pump on 1,371,429 kCal instead makes it heat the water **and**
recreate the diesel heater's 30% loss. The saving then comes out at ₹1157 — a third
of the truth.

> **The tell:** an efficiency or a COP belonging to *one* option appearing anywhere
> inside the *other* option's calculation.

---

## 16. Stock vs flow — decide before writing the unit

```
   STOCK  (a quantity)   kWh, MWh, kCal, Gcal, tonnes, litres, m³, ₹
   FLOW   (a rate)       kW, MW, kCal/hr, TPH, m³/hr, TPD, ₹/day, kg/s
```

A stock has no time in it. **A flow already contains one, so a second "per time" on
a flow is an error, not emphasis** — "MW per day" is not a unit.

Two questions before writing any unit:

1. **Does the question want a stock or a flow?** "Power output in MW" → flow.
   "Annual energy in Gcal" → stock. "Coal reduction in TPD" → flow.
2. **Is that what I have?** If the answer should be MW and your working carries a
   `/day`, divide by 24.

**Worked.** A cement WHRB recovering 910.656 Gcal/day through a 36% cycle:

```
   910.656 × 0.36 × 0.95 × 0.96 ÷ 860 = 347.659 MWh per DAY     ← a stock/day
   ÷ 24 h                              =  14.49 MW              ← the power
```

### Sanity anchors — an answer outside its range is wrong until proved otherwise

| Quantity | Range |
|---|---|
| Cement WHR power | ~2 MW per 1000 TPD of kiln |
| Cement STEC | 700–800 kCal/kg clinker |
| Cement SEEC | 65–80 kWh/t cement |
| Kiln heat of formation | 380–420 kCal/kg clinker |
| Boiler efficiency, solid fuel | 65–85 % |
| Electric chiller | 0.6–0.9 kW/TR, COP 4–6 |
| Absorption chiller COP | 0.6–0.7 single, 1.1–1.4 double effect |
| Cooling tower approach | 3–6 °C |
| Power plant net heat rate | 2300–2800 kCal/kWh |
| Stenter drying efficiency | 45–55 % |
| Motor efficiency | 88–95 % |
| Pump efficiency | 65–85 % |


---

## 17. Four "which way does it move?" questions

All four were dropped in Mock 2's Section I. None needs a remembered sentence —
each is settled by following the physics one step.

### Dew point and moisture move **together**

Dew point is the temperature at which air becomes saturated.

```
    more moisture → saturation reached sooner on cooling → HIGHER dew point
    less moisture → must be cooled further to condense   → LOWER dew point
```

So *"lower dew point ⟹ higher moisture"* is **False**. Dew point can never exceed
dry bulb, and equals it at 100 % RH.

### The ID fan is always the bigger machine

On balanced draft, follow the mass:

```
    FD fan → combustion AIR only, at ambient
                ↓ + fuel mass, + casing air in-leakage, + heated to 150–200 °C
    ID fan → all of the above, at a much larger volume
```

Three mechanisms stack the same way and none runs the other way. **FD flow capacity
is lower.**

### Small approach / TTD / DCA is always good

| Quantity | Small means |
|---|---|
| Cooling tower **approach** | got close to the wet bulb |
| Heat exchanger **approach** | used the surface well |
| Condenser **TTD** | tight to the cooling water — **higher** heat transfer rate |
| Feedwater heater **TTD / DCA** | less bled steam for the same duty |

They all measure *how close you got to the theoretical limit*. Smaller is better
everywhere; it just costs surface area.

### Only C, H and S burn

```
    A_th = [11.6 C + 34.8 (H₂ − O₂/8) + 4.35 S]/100
                            ↑ the fuel's own oxygen, SUBTRACTED
```

Fuel-bound oxygen is already oxidised — it releases nothing and *reduces* the air
required, which is exactly what the minus sign encodes. Nitrogen passes through
inert. So **"oxygen and nitrogen in the fuel do not contribute to calorific value"
is True.**

---

## 18. A constant is not a quantity

Before using any tabulated constant, **say its units out loud and check they cancel
into what you want.**

| Constant | Is really | Needs |
|---|---|---|
| **1210** | ρ·Cp of air, J/(m³·K) | a flow in m³/s **and** a ΔT |
| **3010** | ρ·h_fg of water, J/(m³·(g/kg)) | a flow in m³/s **and** a Δ(g/kg) |
| **367** | 3600/9.81 | m³/h **and** metres of head |
| **102** | 1000/9.81 | m³/s **and** mmWC |
| **860** | kCal per kWh | a kWh (or a kW and an hour) |
| **3024** | kCal/hr per TR | a TR |
| **4.186** | kJ per kCal | an energy in one of the two |

```
   want W = J/s :   1210 J/(m³·K) × V̇ m³/s × ΔT K   →  J/s      ✓
                    1210 J/(m³·K) × 2               →  J/(m³·K)  ✗
```

**And a constant means the same thing on line 9 as it did on line 4.** If 1210
needed a flow and a ΔT earlier in the question, it needs them later too.


---

## 19. Reheat vs regenerative — both are on the same unit

```
   REHEAT        turbine → BOILER → turbine
                 Steam is returned to the boiler and re-superheated between
                 stages. Raises the mean temperature of heat addition and keeps
                 the LP exhaust dry (less blade erosion).

   REGENERATIVE  turbine → FEEDWATER HEATERS
                 Steam is bled at several points to preheat the feedwater on its
                 way back. Less fuel per kg of steam raised.
```

**A large unit has both**, which is why the papers swap their names. **The word
"heaters" in a statement means regenerative**, whatever the sentence calls itself.
The 21st sitting states the regenerative description and labels it "reheat cycle" →
**False**.

Their performance measures differ too: reheat shows up in the **turbine heat rate**
(two heat inputs to the boiler), regenerative in **TTD and DCA** on each heater.

---

## 20. Extraction raises EUF — it does not lower it

```
    EUF = (power + useful process heat) / fuel energy
```

Send more steam through the extractions of a back-pressure set and:

- **process heat rises** — that steam is now doing useful work in the plant;
- **power falls a little** — it expanded through fewer stages;
- **fuel is unchanged.**

**EUF counts power and heat equally**, so the larger rise wins and EUF **increases**.
The 22nd sitting's "higher extraction flow ⟹ lower EUF" is **False**.

> This is the same fact as *"a back-pressure set's heat rate looks terrible and its
> EUF looks excellent"* (entry 4). **Heat rate ignores the heat; EUF does not.**
> Judge cogeneration on EUF or heat-to-power ratio, never on heat rate.

---

## 21. `h = h_f + x·h_fg` — h_f, never h_g

**Wet steam is water, plus the fraction of it that has been boiled.**

```
    h  =  h_f    +    x · h_fg
          ▲                ▲
    start from SATURATED    add back the latent heat,
    WATER — the bottom      but only the fraction x of it
```

**Starting from `h_g` leaves nothing to add**, and the equation collapses:
`554 = 554 + x(…)` forces x toward zero. If your dryness comes out near 0 or above
1, this is the swap that did it.

### ⚠️ The number collision the papers exploit

```
    Condenser temperature                      : 45.5 °C
    Enthalpy of water at that condition        : 45.5 kCal/kg
```

**The same figure, twice, meaning different things.** Below 100 °C, water's enthalpy
in kCal/kg equals its temperature in °C, because `Cp = 1`. The 19th sitting prints
both in adjacent rows, next to `h_fg = 571.6`, and the near-miss invites 45.5 into
the h_fg slot.

**Label every enthalpy before you use it.** Three lines, fifteen seconds:
`h_f = 45.5 · h_fg = 571.6 · h_exhaust = 554`.

**Sanity range:** a condensing turbine exhausts at **0.86–0.93** dry. Below ~0.85
the last-stage blades erode, so no operating plant reports it. **Anything under 0.8
is not "low", it is impossible.**

---

## 22. "Overall efficiency" always means 860 / GROSS heat rate

Three rungs, three efficiencies, and only one of them answers the question as
usually asked:

```
    860 / turbine HR  =  turbine CYCLE efficiency      ← a different question
    860 / GROSS HR    =  OVERALL / PLANT efficiency    ← this one
    860 / net HR      =  efficiency of EXPORTED power  ← a different question
```

**Why gross.** Overall efficiency is fuel-in against **what the plant made**. A
60 MW set made 60 MW; the 6 MW its auxiliaries ate was still generated. **A plant
does not become less efficient for consuming some of its own output** — that is a
commercial fact, not a thermodynamic one.

**BEE names the other two when it wants them** — *"turbine cycle efficiency"*,
*"efficiency of power exported"*, *"net efficiency"*. **Unqualified "overall" or
"plant" means gross, every time.**

> ### The route with no rung to pick
>
> ```
>     η = (generator kW × 860) / (fuel kg/hr × GCV)
>         ─────────────────────   ─────────────────
>            what came out           what went in
> ```
> **Output over input, no heat rate involved.** Two lines, and it cannot be got
> wrong. Use it whenever you are unsure which rung the question means.

---

## 23. When 860 belongs in a calculation — the audit

**860 converts between kW and kCal/h. It does nothing else, ever.**

```
    kW  ──× 860──▶  kCal/h          kCal/h  ──÷ 860──▶  kW
```

**So before writing 860, ask what unit the expression is already in:**

| Expression | Already | 860? |
|---|---|---|
| `steam kg/hr × Δh kCal/kg` | kCal/hr | **no** |
| `fuel kg/hr × GCV kCal/kg` | kCal/hr | **no** |
| `generator output kW` | kW | **× 860** |
| `TR × 3024` | kCal/hr | **no** |

**A heat rate's numerator is a heat flow, never a power** — so in a heat rate built
from steam or from fuel, **860 never appears in the numerator.** It appears only in
the efficiency at the end, and there it sits on the *kWh*.

**Where it legitimately appears mid-calculation:** an EUF, where power (kW) and
process heat (kCal/h) must be brought to one currency —
`EUF = (kW × 860 + steam kCal/h) / fuel kCal/h`. **The 860 is on the power, not on
the steam.** *(19th N-1.)*

**The failure mode is silent and large:** multiplying an already-thermal numerator
by 860 gives an answer 860× too big, which looks like a different kind of mistake
entirely. `2133 → 18,34,294`.

---

## 24. Heat IN is not work OUT — the two brackets of a reheat turbine

**The same two steam streams answer both questions, and the reheat term flips.**

```
               ┌────────┐         ┌──────────┐         ┌──────────┐
  feedwater ──►│ BOILER ├──h_MS──►│    HP    ├──h_CRH─►│ REHEATER │
     h_fw      └────────┘         └──────────┘         └─────┬────┘
                                                             │ h_HRH
                                         ┌──────────┐        │
                     h_exh ◄─────────────┤    LP    │◄───────┘
                                         └──────────┘

  WORK OUT  (power at the shaft)       HEAT IN  (the heat rate numerator)
    HP:  h_MS  − h_CRH                   boiler:   h_MS  − h_fw
    LP:  h_HRH − h_exh                   reheater: h_HRH − h_CRH
         ▲ subtract what comes OUT                 ▲ subtract what went IN
```

**The reheat stream appears in both**, but it ends at the **LP exhaust** for work and
starts at the **cold reheat** for heat. Using the work term inside the heat rate
double-counts the reheater and inflates the answer.

> ### The check
>
> **Heat in must exceed work out, by the condenser loss.** On the 16th sitting's
> unit:
> ```
>     heat in  = 2459.7 + 470  = 2929.7 kJ/kg
>     work out =   360  + 1134 = 1494   kJ/kg
>     ratio                    = 51 %      ← the cycle efficiency, near enough
> ```
> **Any heat-rate bracket larger than `(h_MS − h_fw) + (h_HRH − h_CRH)` is wrong by
> construction.**

**And the efficiency bands that separate the two rungs:**

```
    turbine CYCLE efficiency   45 – 50 %    ← no boiler inside the box
    PLANT / overall            28 – 36 %    ← boiler inside the box
```

**If a question contains no fuel at all, nothing you compute can be a plant
efficiency.** A 32% answer to "turbine cycle efficiency" is a rung error, not a bad
machine.

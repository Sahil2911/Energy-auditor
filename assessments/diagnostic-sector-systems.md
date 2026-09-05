# Diagnostic — Sector and Systems

**Scheduled after Day 13. 40 marks, 60 minutes, two long questions.**

Covers Days 11, 12, 13 and 13B — HVAC and chillers, power plants and heat rate,
cement, steel, textile, sugar, financial analysis and building loads. Book-4
chapters 9–15.

> **Prerequisite check — data-item level.** Both questions were checked against the
> curriculum item by item before being set.
>
> **Q1** needs the kiln heat balance (Day 13 Rung 137), the **hot-duct pitot
> correction** (Rung 137B — added to Day 13 specifically so this question would be
> reachable), and Day 9's pitot traverse. Every one of the 22 data rows has a
> taught use.
>
> **Q2** needs COP and kW/TR (Day 11 Rungs 111–115), the **shaft-power vs
> motor-input basis** (Day 11, and the point you lost marks on twice), heat
> rejection to a cooling tower (Day 10 Rung 102), and `Q = m·Cp·ΔT` (Day 5). The
> motor efficiency of 87.5% **is** used here — twice.

## Rules

- **One sitting, timer visible, guidebooks only.** No notes, no reference files
  from this repository, no worked examples.
- Formula → substitute → evaluate. Show the formula even when you know it.
- **Sanity sentence on every final answer**, and answer the question that was
  actually asked.
- **Run the checking pass** before stopping, and record what it caught.
- **Record start and finish times.**

Budget: 30 minutes per question. If Q1 runs past 35, leave it and start Q2 — the
marks are evenly split and an unstarted question scores zero.

---

# QUESTION 1 — Cement kiln specific coal consumption (20 marks, 30 min)

**16th sitting N-4(D)** — `papers/16.pdf`

As an energy auditor auditing a cement plant, assess the **specific coal
consumption in kg of coal per kg of clinker** from the data below.

| # | Parameter | Value |
|---|---|---|
| 1 | Reference temperature | 20 °C |
| 2 | Barometric pressure | 10 329 mmWC |
| 3 | Density of the preheater gas at NTP | 1.436 kg/m³ |
| 4 | Density of air | 1.293 kg/m³ |
| 5 | Pitot tube constant | 0.85 |
| 6 | Clinker production rate | 4127 TPD |
| 7 | Static pressure of preheater gas in the duct | 640 mmWC |
| 8 | Dynamic pressure of preheater gas in the duct | 15.8 mmWC |
| 9 | Temperature of the preheater gas | 320 °C |
| 10 | Specific heat of the preheater gas | 0.247 kCal/kg°C |
| 11 | Area of the preheater duct | 8.5 m² |
| 12 | Temperature of the exit clinker | 128 °C |
| 13 | Specific heat of the clinker | 0.193 kCal/kg°C |
| 14 | Static pressure of the cooler exhaust gas in the duct | 42 mmWC |
| 15 | Dynamic pressure of the cooler exhaust gas in the duct | 15.5 mmWC |
| 16 | Temperature of the cooler exhaust gas | 290 °C |
| 17 | Specific heat of the cooler exhaust gas | 0.247 kCal/kg°C |
| 18 | Area of the cooler exhaust duct | 7.1 m² |
| 19 | Heat of formation of clinker | 405 kCal/kg clinker |
| 20 | All other heat losses except preheater gas, exiting clinker and cooler exhaust | 84.3 kCal/kg clinker |
| 21 | All heat inputs except combustion of coal | 29 kCal/kg clinker |
| 22 | GCV of the coal | 6200 kCal/kg |

*(Both duct static pressures are drafts — the ducts are on the suction side of
their fans.)*

---

# QUESTION 2 — Chiller changeover and cooling tower adequacy (20 marks, 30 min)

**20th sitting N-3** — `papers/20-1.pdf`

A process industry plans to replace an existing **300 TR directly-gas-fired double
effect absorption chiller** with a **300 TR centrifugal water chiller**, as a cost
saving measure. The absorption chiller rejects its heat into a cooling tower; the
proposed centrifugal chiller will reject its heat to the **same** cooling tower.

Management also plans to connect the heat load of a **water-cooled process heat
exchanger** to that same cooling tower. The cooling water will cool hot oil from
**110 °C to 50 °C**, and the hot oil flow rate is **20,000 kg/hr**.

| Parameter | Value |
|---|---|
| COP of the double effect absorption chiller | 1.2 |
| Electrical energy input to the centrifugal chiller motor | 0.8 kW/TR |
| GCV of natural gas | 9450 kCal/m³ |
| Cost of gas | ₹27/m³ |
| Efficiency of gas firing | 80% |
| Electrical energy cost | ₹8.5/kWh |
| Specific heat of the oil to be cooled | 0.5 kCal/kg°C |
| Motor efficiency | 87.5% |
| Annual operating hours | 7920 hrs |

Find:

**(a)** The yearly monetary saving from operating the centrifugal chiller in place
of the double effect absorption chiller. *(8 marks)*

**(b)** The COP of the centrifugal chiller. *(2 marks)*

**(c)** Whether the cooling tower's capacity is sufficient to take the additional
heat load of the process heat exchanger **in addition to** that of the centrifugal
chiller. *(10 marks)*

---

# Marking scheme

Per the Reviewer framework: formula 4, substitution 4, intermediates 6, final
answer with units 4, interpretation 2.

| Band | Meaning |
|---|---|
| **32+** | Sector chapters secure. Proceed to Full Mock 1. |
| 24–31 | Sound. Note the specific losses and re-drill those rungs only. |
| 16–23 | One systematic gap. Re-read the rung it maps to before the mock. |
| < 16 | Curriculum problem, not a student problem. Tutor re-teaches. |

---

<details><summary>ANSWER KEY — do not open until you have finished and timed yourself</summary>

## Q1 — specific coal consumption

**Preheater gas** *(static is a draft, so subtract)*

```
  ρ = 1.436 × (10 329 − 640)/10 334 × 273/(273 + 320)      = 0.6198 kg/m³
  v = 0.85 × √(2 × 9.81 × 15.8/0.6198)                     = 19.0 m/s
  V̇ = 19.0 × 8.5 = 161.5 m³/s                              = 581 400 m³/h
  ṁ = 581 400 × 0.6198                                      = 360 351 kg/h

  clinker = 4127 × 1000/24                                  = 171 958 kg/h
  gas per kg clinker = 360 351/171 958                      = 2.095 kg/kg
  Q_preheater = 2.095 × 0.247 × (320 − 20)                  = 155.2 kCal/kg
```

**Exiting clinker** *(per kg of clinker, so mass = 1)*

```
  Q_clinker = 1 × 0.193 × (128 − 20)                        = 20.84 kCal/kg
```

**Cooler exhaust gas** *(air density, and again a draft)*

```
  ρ = 1.293 × (10 329 − 42)/10 334 × 273/(273 + 290)        = 0.6241 kg/m³
  v = 0.85 × √(2 × 9.81 × 15.5/0.6241)                      = 18.76 m/s
  V̇ = 18.76 × 7.1 = 133.2 m³/s                              = 479 577 m³/h
  ṁ = 479 577 × 0.6241                                       = 299 317 kg/h
  gas per kg clinker = 299 317/171 958                       = 1.741 kg/kg
  Q_cooler = 1.741 × 0.247 × (290 − 20)                      = 116.1 kCal/kg
```

**The balance**

```
  IN  = m_coal × 6200 + 29
  OUT = 405 + 155.2 + 20.84 + 116.1 + 84.3            = 781.4 kCal/kg

  m_coal × 6200 = 781.4 − 29 = 752.4
  m_coal = 752.4/6200 = 0.121 kg coal per kg of clinker
```

**Answer: 0.121 kg of coal per kg of clinker** — i.e. 121 kg of coal per tonne.

*Sanity:* 0.121 × 6200 = 752 kCal/kg of clinker of fuel heat, which sits in the
700–800 band for a modern dry-process kiln. It checks.

> **Two notes.** BEE's own model answer uses Cp = 0.244 for the cooler exhaust
> where the data table says 0.247, giving 114.63 instead of 116.1 and a final
> 0.121 either way — the answer is insensitive to it. And BEE quotes 155.24 for the
> preheater against 155.2 here; pure rounding.

**Interpretation line to write:** the preheater gas alone carries **155 of the 752
kCal/kg** fired — about 21% of the fuel out of the stack — which is why a waste
heat recovery boiler on the preheater is the first recommendation for this plant.

## Q2 — chiller changeover

**(a) Yearly monetary saving — work per TR, then scale**

```
  Absorption, per TR:
    heat into the generator   = 3024/1.2                    = 2520 kCal/h
    fuel heat at 80% firing   = 2520/0.80                   = 3150 kCal/h
    gas cost                  = 3150 × 27/9450              = ₹9.00 per TR-h

  Centrifugal, per TR:
    electricity cost          = 0.8 × 8.5                   = ₹6.80 per TR-h

  saving = 9.00 − 6.80 = ₹2.20 per TR-h
  yearly = 2.20 × 300 × 7920                                = ₹52 27 200
                                                            = ₹52.27 lakh/year
```

**(b) COP of the centrifugal chiller**

```
  COP is refrigeration effect ÷ SHAFT power, so remove the motor loss first:
    shaft power per TR = 0.8 × 0.875                        = 0.7 kW/TR

    COP = 3024 / (0.7 × 860) = 3024/602                     = 5.02
```

*(Equivalently 3024/(0.8 × 0.875 × 860). The 0.875 must be there — 0.8 kW/TR is
what the **meter** sees, not what the compressor shaft absorbs.)*

**(c) Cooling tower adequacy**

The tower was sized for the absorption chiller, so that fixes its capacity:

```
  Absorption rejects  = chilling load + generator heat
                      = 3024 + 2520                          = 5544 kCal/h per TR
  Existing tower capacity = 5544 × 300                        = 16 63 200 kCal/h

  Centrifugal rejects = chilling load + shaft work
                      = 3024 + 0.7 × 860                      = 3626 kCal/h per TR
  New chiller load    = 3626 × 300                            = 10 87 800 kCal/h

  Heat exchanger load = 20 000 × 0.5 × (110 − 50)             =  6 00 000 kCal/h

  Total new load      = 10 87 800 + 6 00 000                  = 16 87 800 kCal/h
```

**16,87,800 > 16,63,200 — the cooling tower is NOT adequate**, by about
24,600 kCal/h, or 1.5%.

**Interpretation line to write:** the changeover *frees* tower capacity — an
absorption chiller rejects 5544 kCal/h per TR against a centrifugal's 3626, because
the absorption machine's fuel heat is rejected too — but the process heat exchanger
consumes more than the freed amount. It is a marginal 1.5% shortfall, so a modest
tower upgrade or a fan-speed increase would cover it; write that rather than a bare
"no".

</details>

---

## Traps this diagnostic is specifically testing

| # | Trap | Where it comes from |
|---|---|---|
| 1 | Duct static pressure is a **draft** — subtract, do not add | Rung 137B |
| 2 | Every kiln balance term is **per kg of clinker** | Rung 137 |
| 3 | Heat of formation sits on the **OUT** side | Rung 137 |
| 4 | 4127 **TPD** → kg/h before dividing | Unit discipline |
| 5 | **COP is on shaft power**, kW/TR is on motor input | Day 11 — lost twice |
| 6 | Absorption rejects **more** heat than an electric chiller of the same TR | Day 11 |
| 7 | The tower's *capacity* is set by what it was sized for | Day 10 |
| 8 | Part (c) asks **whether**, so the answer is a yes/no sentence with numbers | Trend 2 |

Trap 8 is the one to watch. Trend 2 in `assessments/checkpoint-phase-2.md` says the
current failure mode is arithmetic that is right and a final sentence that is
missing. Both questions here end in a *judgement*, not a number.

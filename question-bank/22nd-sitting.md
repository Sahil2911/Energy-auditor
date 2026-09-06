# 22nd Sitting (July 2022) — recovered from scan

**`papers/22-1.pdf` (Green) and `papers/22-2.pdf` (Pink), 15 pages each.**
Recovered 06 Sep, same method as the 21st: rendered at 170 dpi and read directly.
All questions and model answers legible. Sets differ only in order.

Date 31.07.2022, 14:00–16:00, 2 hrs, 100 marks.

---

## Section I — True/False (10 × 1)

| # | Statement | Ans |
|---|---|---|
| 1 | The lower the dew point of air, the higher the moisture in air | FALSE |
| 2 | In a boiler, the higher the %CO₂ in flue gas, the better the combustion efficiency | TRUE |
| 3 | Air infiltration in an air-conditioned building increases **both** latent and sensible load | TRUE |
| 4 | Turbine cycle efficiency rises as condenser inlet cooling water temperature falls | TRUE |
| 5 | *(fill in)* FD fan flow capacity vs ID fan on balanced draft is ⟶ | **Lower** |
| 6 | Waste heat 3440 kCal/hr into a heat pump + 1.5 kW compressor ⟹ heat developed 6.6 kW | FALSE *(3440/860 + 1.5 = **5.5 kW**)* |
| 7 | *(fill in)* Lower the TTD in a steam condenser, the heat transfer rate is ⟶ | **Higher** |
| 8 | In extraction back-pressure cogeneration, higher extraction steam flow ⟹ lower EUF | FALSE |
| 9 | Rated power of a motor is the power consumed by the motor | FALSE *(it is shaft **output**)* |
| 10 | NPSH **required** of a centrifugal pump increases with flow | TRUE |

> **Q5 and Q7 are not True/False — they are fill-in-the-blank.** Read the answer
> column before assuming the format. Q6 is a one-line arithmetic check disguised as
> a T/F, and Q9 is the rated-power trap that catches most candidates.

## Section II — Short (2 × 5)

| Q | Topic | Answer |
|---|---|---|
| **L-1** | Edible oil plant thermic fluid heater: 60 m³/h, 210→230 °C, ρ 826, choose **oil (80%, ₹70/kg, 10 000 GCV)** or **briquettes (65%, ₹7/kg, 3200 GCV)** | Q = 49 560 × (Cp/4.186) × 20 ≈ **5,28,750 kCal/hr**; oil 66.09 kg/h → **₹4626/hr**; briquettes 254.21 kg/h → **₹1779/hr** ⟹ **recommend briquettes** |
| **L-2** | 25 TPH steam let down 20→5 bar(g) through PRDS; replace with a back-pressure turbine to drive a 900 kW gas compressor. 0.045 kWh/kg steam | steam = 900/0.045 = **20 TPH**; saving = 900 × 8 = **₹7200/hr** |

> **L-1 is the "hold the service constant" question.** The heat load belongs to the
> *thermic fluid*, not to either fuel; each fuel then answers what it costs to
> deliver it.
>
> ⚠️ **BEE's own inconsistency:** the data table prints Cp = **2.223** kJ/kg°C, the
> model answer computes with **2.233**. Either gives briquettes; the numbers differ
> by 0.4%. Use the printed value and say so in a line.

## Section III — Long (4 × 20)

### N-1 — Effluent plant biogas back-pressure cogeneration ⭐
40 bar/350 °C boiler on biogas → back-pressure turbine at 8 bar → process (direct
steam, nil condensate) + a **2000 TR absorption chiller** → condenser → cooling tower.

```
  i)   generator heat = 900 × 860/(0.97 × 0.98 × 0.85)    = 9,57,909 kCal/h
       Δh = 720 − 660 = 60      steam to turbine          = 15.96 TPH
  ii)  chiller heat = 2000 × 3024/0.8 = 75,60,000
       steam to chiller = 75,60,000/(660 − 100)           = 13.5 TPH
  iii) steam to process = 15.96 − 13.5                    = 2.46 TPH
  iv)  mixed condensate = (13.5×100 + 2.46×30)/15.96      = 89.2 °C
       biogas = 15 960 × (720 − 89.2)/(0.75 × 7000)       = 1917.6 Sm³/hr
  v)   VAM rejects = 2000×3024 + 13 500×(660 − 100)       = 1,36,08,000 kCal/h
       CT flow = 1,36,08,000/3/1000                       = 4536 m³/hr
       pump kW = (4536/3600)×15×9.81/(0.75 × 0.93)        = 265.8 kW
```

> **⭐ Part (v) is the chiller-rejection concept again, from the other side.** The
> VAM's rejection is the cooling load **plus the steam heat that drove it** — and
> here the steam heat (75.6 lakh) is *larger* than the cooling load (60.5 lakh).
> Note "NIL CONDENSATE" from the process: that is why the mixing temperature needs
> the 30 °C makeup, not 100 °C.

### N-2 — (a) two-stage air compressor (b) air-fin cooler + water-cooled chiller
(a) 11.67 m³/min FAD at 7 kg/cm²g, isothermal efficiency 60%, motor 90%, belt 97%
— motor input power, specific power kW/m³/hr, and the reduction at 6 kg/cm²g.
(b) 160 TPH process gas 55→35 °C by cooling water; propose air-fin cooler to 35 °C
then a water-cooled chiller (COP 4.2) to 30 °C, worth ₹450 lakh/yr of process
benefit.

```
  additional power = 117.6 (chiller) + 442 (fan) + 11 (CT)   = 570.6 kW
  power cost = 570.6 × 9 × 8000/10⁵                          = ₹410.8 lakh/yr
  net = 450 − 410.8                                          = ₹39.17 lakh/yr → viable
```

### N-3 — Large water tube boiler and air preheater
210 TPH boiler, design vs operating conditions.

```
  i)   design: 4.67 % = m × 0.23 × (145 − 36)/3585 ⟹ m = 6.68 kg dfg/kg coal
       M = 6.68 × 43 000 = 2,87,240 kg/h → loss 72,01,107 kCal/h
  ii)  operating: 3,24,000 × 0.23 × (165 − 37)                = 95,38,560 kCal/h
  iii) increase 23,37,453 → /3240 = 721.4 kg/h → /0.83        = 0.869 T/h
  iv)  × 7000 h × ₹9500/T                                     = ₹577.97 lakh/yr
  v)   APH leakage = (O₂out − O₂in)/(21 − O₂out)
       25 % EA → 4.2 % O₂;  44.8 % EA → 6.5 % O₂
       = (6.5 − 4.2)/(21 − 6.5) × 100                         = 15.86 %
  (N3-B)  APH effectiveness = (294 − 40)/(315 − 40) × 100     = 92.4 %
```

> **Part (v) runs the excess-air formula backwards** — given EA, find %O₂:
> `%O₂ = 21 × EA/(1 + EA)`. And part (i) runs the dry flue gas loss backwards to
> get `m_dfg` from a given loss percentage. Two inversions in one question.

### N-4 — answer any ONE

| | Topic | Key answers |
|---|---|---|
| **(A)** | 500 MW-class turbine: HP/IP/LP powers, isentropic efficiency, turbine and station heat rate | HP 62.03, IP 68.6, LP 89.98 MW → 220.67 MW; generator 209.76 MW; **turbine HR 2164.9 kCal/kWh**. *BEE states SGHR is **not calculable** — boiler efficiency is not given — and awards marks for any assumption of 85–88%* |
| **(B)** | Commercial building: grid power vs an 850 kW gas engine cogen with WHRB + steam absorption chiller | 1000 kW total, 15,12,000 kCal/h cooling, centrifugal 0.45 kW/TR, grid ₹10.35/kWh |
| **(C)** | Cement preheater and cooler: pitot heat losses per kg clinker, 6-stage upgrade, cooler recuperation | ρ = 1.40 × 273 × (10336 − **440**)/((273 + 355) × 10336) = **0.583**; v 19.7 m/s; **1.686 Nm³/kg clinker**; net saving **₹1,30,56,480/yr**; cooler saving 27.94 kCal/kg |
| ~~**(D)**~~ | ~~DRI steel plant, base 2020 vs current 2021~~ | ⛔ **This is the twin of the 24th N-4(D)** — same question, different numbers. She scored 20/20 on the 24th version as Day 13 Block C. **Not usable as unseen.** See below. |

> **(C) has the negative static pressures printed: −440 and −28 mmWC.** Between
> this, the 21st N-4(A)'s −850, and the 16th N-4(D), the hot-duct pitot with a
> draft is now confirmed in **three** sittings. Day 13 Rung 137B is not optional.
>
> **(A) is worth reading for its answer alone:** BEE says a quantity **cannot be
> calculated** from the data given, and awards marks for stating that with a
> reasonable assumption. That is a real exam skill — saying what is missing beats
> inventing it.

---

## 22nd N-4(D) — the twin, and why it is a drill rather than a mock question

Same DRI steel plant as the 24th N-4(D), different numbers, and **the yield runs
backwards** — 88% in the base year falling to 85%.

| | Base 2020 | Current 2021 |
|---|---|---|
| Specific coal | 1.3 T/T | 1.15 T/T |
| Specific power | 110 kWh/T | 95 kWh/T |
| Yield | **88 %** | **85 %** |
| SMS SEC | 850 kWh/t | 830 kWh/t |
| CPP heat rate | 3300 | 3100 kCal/kWh |
| GCV of coal | **5000** | **5200** kCal/kg |

```
  Plant SEC   base 10.60  →  current 9.955 million kCal/tonne of ingot
  Coal        base 559.9  →  current 488.2 TPD    REDUCTION = 71.7 TPD
```

**The GCV changes again — 5000 to 5200 — so the trap from Day 13 is here too:**

```
   difference-then-convert:  (2800.84 − 2538.45) × 10⁶/5200/1000  = 50.2 TPD
   convert-then-difference:  559.9 − 488.2                        = 71.7 TPD
```

A 43% gap this time, bigger than the 24th's, because the GCV moved further.
**Assigned as Day 15 Drill 76** — it is the cleanest possible re-test of
`concept-distinctions` entry 14, on a question whose method she already owns.

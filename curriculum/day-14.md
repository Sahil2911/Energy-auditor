# Day 14 — Full Mock 1

**100 marks · 2 hours 30 minutes · open book (guidebooks only) · one sitting.**

This is the first paper at full length and full time. Sit it the way you will sit
the real one: **14:00 start if you can**, phone away, both guidebooks tabbed, no
reference files from this repository, no worked examples, no calculator apps beyond
a plain scientific calculator.

> **Every question here is unseen.** Nothing in this paper has appeared in a lesson,
> a drill, Mock A or a diagnostic.

## Structure — the real 26th-NCE shape

| Section | Content | Marks | Suggested time |
|---|---|---|---|
| I | 10 True/False | 10 | 10 min |
| II | 2 short numericals | 10 | 10 min |
| III | 4 long numericals, **N-4 is a choice of three** | 80 | 100 min |
| — | Checking pass | — | 10 min |

**Attempt Section III first if you want** — the marks are there. But do not leave
Sections I and II to the last five minutes; twenty marks in twenty minutes is the
best rate on the paper.

**Record: start time, the time you finish each section, and end time.**

---

# SECTION I — True or False (10 × 1 = 10 marks)

State True or False. **One line of reason each** — the reason is what proves you
did not guess, and it costs eight seconds.

1. A vapour absorption chiller with a COP of 1.2 is less efficient than a vapour
   compression chiller with a COP of 5.0, and should always be replaced by one.

2. Replacing a 300 TR vapour absorption chiller with a 300 TR vapour compression
   chiller reduces the heat load on the cooling tower.

3. In a back-pressure cogeneration plant, a high heat rate indicates poor
   performance.

4. For a boiler burning a hydrogen-rich fuel, efficiency calculated on an NCV basis
   will be lower than the same boiler's efficiency on a GCV basis.

5. Raising the feedwater temperature to a boiler increases its evaporation ratio
   without necessarily improving its efficiency.

6. In a cooling tower, doubling the process heat load at constant water flow
   doubles the range and worsens the approach.

7. The cooling load temperature difference (CLTD) for a roof is larger than that
   for a wall of the same construction because the roof receives more direct solar
   radiation and has a longer thermal lag.

8. A pitot tube reading taken in the suction duct of an induced draft fan must be
   corrected using a gas density calculated at barometric pressure **plus** the
   measured static pressure.

9. In an integrated cement plant, the specific thermal energy consumption is
   reported per tonne of cement, while the specific electrical energy consumption
   is reported per tonne of clinker.

10. Improving the yield of a steel melting shop from 85% to 88% reduces the plant's
    specific energy consumption per tonne of finished product, even if no fuel or
    electricity saving is made anywhere.

---

# SECTION II — Short Numericals (2 × 5 = 10 marks)

### L-1 — `papers/25-1.pdf`, question L-1

In a petrochemical industry both the LP and HP boilers operate with the **same
evaporation ratio of 14**, using the same fuel oil.

| Particulars | LP boiler | HP boiler |
|---|---|---|
| Pressure | 10 kg/cm²a | 32 kg/cm²a |
| Temperature | Saturated | 400 °C |
| Enthalpy of steam | 665 kCal/kg | 732 kCal/kg |
| Feed water temperature | 80 °C | 105 °C |
| Evaporation ratio | 14 | 14 |

If the efficiency of the LP boiler is 82%, **calculate the efficiency of the HP
boiler.**

### L-2 — `papers/16.pdf`, question L-1

A luxury hotel uses a **diesel fired heater at 70% efficiency** to supply hot water
at 60 °C from an initial temperature of 20 °C. The hot water requirement is
**24,000 litres per day**.

Management is considering an **electric heat pump with a COP of 2.5**. Find the
**reduction in daily operating cost**, ignoring auxiliary energy.

Electricity ₹10/kWh · Diesel ₹50/litre · GCV of diesel 9100 kCal/litre.

---

# SECTION III — Long Numericals (4 × 20 = 80 marks)

**N-1, N-2 and N-3 are compulsory. For N-4, answer any ONE of the three.**

### N-1 (20 marks) — `papers/16.pdf`, question N-2

A gas engine-based **trigeneration** plant, operating in two modes, with a proposed
vapour absorption chiller on the jacket cooling water.

**Open the paper and work it there. Do not read past the question.**

> Four parts: average EUF, daily useful energy, daily gas requirement, and a
> feasibility check on a 60 TR hot-water-driven VAR chiller.

### N-2 (20 marks) — `papers/19-1.pdf`, question N-3

A **pressurised hot water boiler** fired on sawdust briquettes, supplying heating
coils in a drier. Ultimate analysis and flue gas analysis given.

**Open the paper and work it there.**

> One question: the **hot water circulation rate in m³/hr**. Everything before it
> is the indirect method, including two loss terms you have met but not drilled —
> **CO** and **bottom ash**.

### N-3 (20 marks) — `papers/24-1.pdf`, question N-3

A steam turbine power plant's **circulating water system with an induced draft
cooling tower**, two makeup pumps, and a sump.

**Open the paper and work it there.**

> Three parts: evaporative loss, blowdown and a **mass flow diagram**; then the
> hours for which one pump runs, and the hours for which both run.
>
> **Draw the diagram.** Marks are allocated to it, and you did this unprompted in
> the electrical & fluids diagnostic.

### N-4 — answer any ONE (20 marks)

| Option | Paper | Topic |
|---|---|---|
| **(A)** | `papers/20-1.pdf`, N-3 | Absorption → centrifugal chiller changeover, and whether the cooling tower can take an added process load |
| **(B)** | `papers/24-1.pdf`, N-4(D) | DRI steel plant — specific energy consumption per tonne of finished product, base and assessment year, and coal reduction |
| **(C)** | `papers/24-1.pdf`, N-4(C) | Cement plant WHRB — power output from preheater and cooler gas, and heat of formation of clinker |

> **This choice is the experiment.** You judged that the sector chapters can be
> handled from the book plus general concepts rather than from drilled practice.
> Options B and C test exactly that. **Pick the one you would pick in the exam**,
> and afterwards note in the log why — that reasoning is as useful as the marks.

---

*Stop. Finish everything above. Run the checking pass. Record your times. Only then
continue.*

---

# ANSWERS AND MARKING

<details><summary>SECTION I — answers with reasons</summary>

1. **False.** They are not comparable ratios. The VCR's denominator is electrical
   work — high-grade energy costing ~3 units of fuel per unit delivered. The VAR's
   is low-grade heat, often waste. Compare **cost per TR-hour**, not COP.

2. **True.** A VCR rejects cooling load + compressor shaft work (~3626 kCal/h per
   TR). A VAR rejects cooling load + **generator heat** (~5544 kCal/h per TR at
   COP 1.2). Swapping VAR → VCR frees roughly a third of the tower duty.

3. **False.** Heat rate charges all the fuel to the electricity and ignores the
   process steam, which was the entire purpose. A back-pressure set's heat rate
   near 34,000 kCal/kWh is normal. Judge it on **EUF** or heat-to-power ratio.

4. **False — it will be higher.** NCV is smaller than GCV, and it sits in the
   denominator. Same boiler, smaller denominator, larger efficiency.

5. **True.** ER = steam/fuel. Hotter feedwater means less heat per kg of steam, so
   more kg from the same fuel — ER rises with nothing about the boiler improved.
   The efficiency formula `η = ER(h_s − h_fw)/GCV` compensates through the smaller
   `(h_s − h_fw)`.

6. **False on the second half.** Range doubles, yes. But **approach is set by the
   tower's ability against the wet bulb**, and here it barely moves — the tower is
   simply asked to reject more heat over a bigger range. Range says nothing about
   tower performance; approach does.

7. **True.** Horizontal, full sun all day, and the slab's thermal mass delays the
   peak. The 23rd sitting's data — roof 42 °C against wall 12 °C — is why roof
   insulation is the first recommendation for an Indian commercial building.

8. **False — minus, not plus.** An ID fan's suction duct is **below** atmospheric
   pressure. The static reading is a draft, so `ρ = ρ_NTP × (P_bar − P_static)/10334
   × 273/(273+t)`. Adding it overstates density by ~13% in a kiln duct.

9. **False — the two are the other way round.** Thermal energy is per **kg of
   clinker** (STEC); electrical is per **tonne of cement** (SEEC). Cement exceeds
   clinker, and mixing the denominators makes both numbers wrong.

10. **True.** The same energy is now carried by more finished product. The
    denominator grows, so specific energy falls. Yield improvement *is* an energy
    saving, and saying so earns an interpretation mark.

</details>

<details><summary>SECTION II — worked</summary>

**L-1 — HP boiler efficiency**

The two boilers share a fuel, so they share a GCV. Find it from the LP boiler, then
use it on the HP boiler.

```
   η = ER × (h_steam − h_feedwater) / GCV

   LP:  0.82 = 14 × (665 − 80)/GCV
        GCV  = 14 × 585 / 0.82                  = 9987.8 kCal/kg

   HP:  η = 14 × (732 − 105)/9987.8
          = 8778/9987.8                         = 87.9 %
```

**Answer: 87.9%.** Sanity: the HP boiler does more work per kg of steam (627 against
585 kCal/kg) at the same evaporation ratio, so it *must* be the more efficient
machine. The direction checks.

**L-2 — heat pump vs diesel heater**

The heat duty is the same either way — compute it once.

```
   Q = 24 000 L × (60 − 20) °C × 1 kCal/L·°C     = 960 000 kCal/day

   Diesel:  fuel = 960 000 / (0.70 × 9100)       = 150.7 L/day
            cost = 150.7 × 50                    = ₹7535/day

   Heat pump:  kWh = 960 000 / 2.5 / 860         = 446.5 kWh/day
               cost = 446.5 × 10                 = ₹4465/day

   Reduction = 7535 − 4465                       = ₹3070 per day
```

**Answer: ₹3070/day.** Note the COP of 2.5 does the work — the heat pump *moves*
2.5 units of heat per unit of electricity rather than making one. That is the only
reason electricity at ₹10/kWh beats diesel here.

</details>

<details><summary>N-1 — trigeneration, outline</summary>

```
  1.  Average EUF, time-weighted over the day:
         (0.85 × 10 + 0.73 × 14)/24                       = 0.78

  2.  Daily useful energy — all three outputs, each over its own hours:
         power   650 × 860 × 24                    = 13 416 000
         heat    325 × 530 × 10                    =  1 722 500
         cooling 250 × 3024 × 14                   = 10 584 000
                                                     ─────────────
                                                     25 722 500 kCal/day
         Annual  = 25 722 500 × 330/10⁶            = 8488.4 Gcal/year

  3.  Gas required:
         input = 25 722 500/0.78                   = 32 977 564 kCal/day
         gas   = 32 977 564/8500                   = 3879.7 Sm³/day

  4.  60 TR VAR on jacket water, COP 0.5:
         heat needed    = 60 × 3024/0.5            = 362 880 kCal/h
         engine shaft   = 650/0.95                 = 684.2 kW
         jacket heat    = 684.2 × 860              = 588 412 kCal/h
         362 880 < 588 412  ⟹  FEASIBLE
```

**Three things this question is really testing.** That EUF is time-weighted, not
averaged. That power runs 24 hours while heat and cooling each run their own
window. And that the "energy loss in the cooling water is the same as the engine
power output" sentence is what lets you size the jacket heat — the shaft power,
found by dividing by the alternator efficiency, not the electrical output.

**State the answer the question asked for:** part 4 wants a **yes/no with numbers**,
not just the two figures.
</details>

<details><summary>N-2 — sawdust briquette hot water boiler, outline</summary>

```
  A_th  = [11.6(45.3) + 34.8(4.4 − 33.3/8) + 4.35(0.1)]/100   = 5.34 kg/kg
  EA    = 12.2/(21 − 12.2) × 100                              = 138.6 %
  AAS   = 5.34 × 2.386                                        = 12.74 kg/kg
  m_dfg = C(44/12) + N₂ in fuel + AAS(0.77) + (AAS − A_th)(0.23) + S(64/32)
                                                              = 13.19 kg/kg

  L1 dry flue gas  13.19 × 0.23 × (235 − 31)/3300 × 100       = 18.75 %
  L2 hydrogen      9(0.044){584 + 0.45(235−31)}/3300 × 100    =  8.10 %
  L3 fuel moisture 0.075{584 + 0.45(204)}/3300 × 100          =  1.54 %
  L4 air humidity  12.74 × 0.0204 × 0.45 × 204/3300 × 100     =  0.723 %
  L5 CO            [%CO/(%CO+%CO₂)] × C × 5654/GCV × 100      =  0.172 %
  L6 bottom ash    0.08 × 800/3300 × 100                      =  1.94 %
  L7 radiation                                                =  0.50 %

  η = 100 − 31.73                                             = 68.28 %

  Mass of hot water × Cp × ΔT = fuel × GCV × η
  m = 375 × 3300 × 0.6828 / [1 × (145 − 110)]                 = 24 142 kg/hr
                                                              = 24.14 m³/hr
```

**Two loss terms you have not drilled**, both simple:

```
    L5 (CO):   %CO/(%CO + %CO₂) × C × 5654 / GCV × 100
               189 ppm = 0.0189 %.   5654 kCal/kg is the heat still locked
               in CO that never got released — the difference between
               burning C to CO and burning it all the way to CO₂.

    L6 (ash):  ash fraction × GCV of ash / GCV of fuel × 100
               unburnt carbon leaving in the bottom ash.
```

**The sting is in the tail.** Six of the twenty marks are the last two lines: the
question does not ask for efficiency, it asks for a **circulation rate in m³/hr**.
An answer stopping at 68.28% loses those marks. `Q = m·Cp·ΔT` on the water side,
with ΔT = 145 − 110, then kg/hr → m³/hr by dividing by 1000.
</details>

<details><summary>N-3 — cooling tower and sump, outline</summary>

```
  CW flow      = 440 × 45                                 = 19 800 m³/hr
  Range        from effectiveness = range/(range+approach)
               0.63 = R/(R+4)   ⟹  R = 4 × 0.63/0.37      = 6.81 °C
  Evaporation  = 0.00085 × 1.8 × 19 800 × 6.81            = 206.3 m³/hr
  COC          = 2000/500                                 = 4
  Blowdown     = E/(COC − 1) = 206.3/3                    = 68.8 m³/hr
```

**Mass flow diagram** — draw it. Hot CW 19,800 in, cold CW 19,800 out,
evaporation 206.3 up, blowdown 68.8 out, makeup in.

```
  Sump volume  = 100 × 15 × 40                            = 60 000 m³
  Swing        = 10 % of full                             =  6 000 m³

  ONE pump:   in 200,  out 206.3 + 68.8 = 275.1
              net = −75.1 m³/hr  ⟹  level falls
              time = 6000/75.1                            = 80 hrs

  BOTH pumps: in 350,  out 275.1
              net = +74.9 m³/hr  ⟹  level rises
              time = 6000/74.9                            = 80 hrs
```

**The point of the question** is that the two pumps in parallel deliver 350, not
400 — parallel pumps on a common head never add linearly, because the extra flow
raises the system resistance. That number is given; using 400 is the trap.

**The near-symmetry (80 and 80) is a coincidence of the numbers**, not a law. Do
not "check" your answer by assuming they should match.
</details>

<details><summary>N-4 — answers</summary>

**(A) 20th N-3 chiller changeover**
```
  Absorption cost/TR-h  = (3024/1.2)/0.80 × 27/9450        = ₹9.00
  Centrifugal cost/TR-h = 0.8 × 8.5                        = ₹6.80
  Yearly saving         = 2.20 × 300 × 7920                = ₹52.27 lakh
  COP of centrifugal    = 3024/(0.8 × 0.875 × 860)         = 5.02
  Tower capacity (sized for VAR) = (3024 + 2520) × 300     = 16 63 200 kCal/h
  New load: VCR (3024 + 0.7 × 860) × 300                   = 10 87 800
            HX  20 000 × 0.5 × (110 − 50)                  =  6 00 000
            total                                          = 16 87 800
  16 87 800 > 16 63 200  ⟹  NOT adequate, by 1.5 %
```

**(B) 24th N-4(D) DRI steel**
```
  Base:       HR = 860/0.2606 = 3300;  SEC_SI = 1.3×1000×6000 + 110×3300
                                              = 8.163 Mcal/t
              ingots = 300 × 0.85 = 255 t;  SEC_SMS = 850 × 3300 = 2.805 Mcal/t
              SEC_plant = (300 × 8.163 + 255 × 2.805)/255       = 12.41 Mcal/t
  Assessment: HR = 3100;  SEC_SI = 7.425;  ingots = 264
              SEC_plant = (300 × 7.425 + 264 × 2.573)/264       = 11.01 Mcal/t
  Coal:       base 390.0 + 137.4 = 527.4 ;  assessment 345.0 + 123.8 = 468.8
              REDUCTION                                         = 58.6 t/day
```

**(C) 24th N-4(C) cement WHRB**
```
  clinker      = 7200 × 0.62/24                            = 186 t/h
  steam (PH)   = 152 × 186 000 × 0.75/(815 − 95)           = 29 450 kg/h
  steam (cool) = 120 × 186 000 × 0.75/(815 − 95)           = 23 250 kg/h
  power = 52 700 × 720 × 0.36 × 0.95 × 0.96/860/1000       = 14.49 MW
  ΔH_R  = 2.22(5.29) + 6.48(1.25) + 7.646(63) − 5.116(22.68) − 0.59(5.92)
                                                           = 382 kCal/kg
```
Note this question supplies three gas temperatures its own model answer never uses.
Say so in one line and move on (Day 13B Rung 162).
</details>

---

# AFTER THE PAPER

## Mark yourself honestly, then fill this in

| Section | Marks | Time taken |
|---|---|---|
| I | /10 | |
| II | /10 | |
| N-1 | /20 | |
| N-2 | /20 | |
| N-3 | /20 | |
| N-4 (which?) | /20 | |
| **Total** | **/100** | |

**Pass is 50.** Mock A was 29/60, which is 48%.

## Then, and this matters more than the score

For **every** mark lost, write one line in the log answering: *was this a concept I
did not know, a method I applied wrongly, arithmetic, units, a lookup, or time?*

**Every concept-level gap goes into `reference/concept-distinctions.md`** — that
file is now the spine of the remaining plan. You named vapour compression vs
absorption; it is entry 1. Whatever this paper turns up becomes entries 14, 15, 16.

Then tell me the score and the gaps, and Day 15 is built from them rather than from
a syllabus.

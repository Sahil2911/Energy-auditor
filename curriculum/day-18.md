# Day 18 — Full Mock 3

**100 marks · 2 hours 30 minutes · open book (guidebooks only) · one sitting.**

**Six days to the exam. This is the dress rehearsal.**

---

## Both checks, written down — because last time only one was run

> ### ✅ Check 1 — Ledger (is anything seen?)
>
> `tools/ledger.py` regenerated 20 Sep and **its blind spot fixed**: the old pattern
> matched *"21st N-1"* but missed *"`papers/21-1.pdf`, question N-1"*, which is the
> form both mocks use. It was therefore blind to the very files it existed to guard.
> Now 48 questions are tracked and every question below was looked up individually.
>
> **Nothing in this paper appears in `question-bank/used-ledger.md`.**

> ### ✅ Check 2 — Data-item prerequisites (is everything reachable?)
>
> Skipped entirely for Mock 2, which is how six unreachable air-preheater marks got
> in. Run properly this time, part by part:
>
> | Question | Every part maps to |
> |---|---|
> | **L-1** aluminium furnace | Day 1 direct efficiency · **Rung 164** hold the service constant |
> | **L-2** BP turbine vs PRDS | Day 4 Rungs 24–27 |
> | **N-1** compressor + chiller | Day 9 Rungs 88–93 (isothermal) · Day 11 (COP) · **Rung 163** (condenser duty) · Day 9 (the 102 constant) |
> | **N-2** hot water startup | Day 1 (direct method) · Day 5 (`m·Cp·ΔT`) · pipe annulus geometry |
> | **N-3** two-unit power plant | Day 3 (all seven losses incl. CO and ash) · **Rung 168** (ash) · Day 12 Rungs 123–124 (heat rate bases) |
> | **N-4(A)** cement raw mill fan | **Rung 137B** (hot-duct pitot, negative static) · Day 9 (fan static efficiency, 102) · Day 8 (affinity laws) |
> | **N-4(B)** textile coal vs biomass | Day 13 Rung 148 (bone-dry basis) · Rung 147 (thermic fluid) · Day 1 (wet steam) · **Rung 164** |
> | **N-4(C)** 500 MW reheat turbine | Day 4 (isentropic efficiency) · Day 12 (turbine, gross, net heat rate) |
>
> **Every data item in every question has a taught use.** Two judgement calls, both
> flagged in the paper where they occur: N-3's bottom:fly ash ratio needs a weighted
> GCV, and N-4(C) asks for a quantity that **cannot be calculated** from the data
> given — BEE's own key says so and awards marks for saying it.
>
> **Deliberately excluded:** the 25th N-4(B), which turns on feedwater-heater TTD
> and DCA. Those appear in `concept-distinctions.md` and Day 17 Rung 174, but never
> as a curriculum rung with worked numbers. Under the new rule that is not enough
> for a 20-mark question.

---

## Structure

| Section | Content | Marks | Time |
|---|---|---|---|
| I | 10 brief questions — **9 real, 1 on the air preheater** | 10 | 10 min |
| II | 2 short numericals | 10 | 10 min |
| III | 4 long numericals, **N-4 a choice of three** | 80 | 100 min |
| — | The nine-item checking pass | — | 10 min |

### The one thing to get right

Mock 2 lost **five marks you could have taken** because Section III ran 129 minutes
and N-3 never got its last two parts. **Day 17 Rung 170 is under test here:**

> **25 minutes maximum on any long question. Then stop, whatever state it is in.**
>
> And Rung 171: **read every sub-part before calculating.** Star the one-liners.
> Mark which parts do not depend on the ones above them. Do the stars first.

**Write your four start times on the answer sheet before you begin.** If it is
21:00 and you began N-1 at 20:35, you are past the bell — move.

---

# SECTION I — Brief Questions (10 × 1 = 10 marks)

State True or False, with one line of reason.

1. Current THD is the ratio of the root-mean-square value of the harmonic currents
   to the square of the fundamental current.
2. Both rotary hearth and walking beam-type furnaces are continuous furnaces.
3. % Oxygen or CO₂ in flue gas is not required to calculate boiler efficiency by
   the direct method.
4. In the reheat cycle of a thermal power plant, partially expanded steam extracted
   from the turbine at various points is used to heat the condensate and feed water
   through HP/LP heaters on its way back to the boiler.
5. The difference between GCV and NCV of hydrogen fuel is zero.
6. In an integrated steel plant, pig iron is produced from the blast furnace.
7. The copper loss in a transformer is the power consumed to sustain the magnetic
   field in the transformer core.
8. In an extraction back pressure cogeneration system, the higher the steam flow
   through the turbine extractions, the lower is the energy utilisation factor.
9. NPSH **required** of a centrifugal pump increases with flow.
10. In a regenerative air preheater, a rise in the flue gas oxygen content measured
    across the preheater indicates air leaking from the air side into the gas side.

---

# SECTION II — Short Numericals (2 × 5 = 10 marks)

### L-1 — `papers/21-1.pdf`, question L-1

In the cast house of an **aluminium smelting plant** there are two billet casting
machines, each served by a 40-tonne holding-cum-melting furnace. One line has a
**fuel-oil fired** furnace, the other an **electric** furnace fed from the captive
power plant.

**Evaluate which is more economical on operating energy cost in ₹/tonne.**

| | |
|---|---|
| Specific oil consumption | 26 litre/T |
| Cost of furnace oil | ₹38/litre |
| Calorific value of FO | 10,000 kCal/kg |
| Efficiency of FO fired furnace | 65 % |
| Efficiency of electric furnace | 90 % |
| Cost of electricity from CPP | ₹3.75/kWh |
| Density of furnace oil | 0.95 kg/litre |

### L-2 — `papers/22-1.pdf`, question L-2

A process plant imports **25 TPH of steam at 20 bar(g)** and reduces it to
**5 bar(g) through a PRDS**. It also runs a **motor-driven gas compressor drawing
900 kW**. An audit suggests installing a **back-pressure steam turbine instead of
the PRDS** to drive the compressor.

**Calculate the steam required for the back-pressure turbine and the hourly
monetary saving.**

Turbine power generation per unit of inlet steam: 0.045 kWh/kg steam ·
Power cost ₹8.0/kWh · Import steam cost ₹3500/MT

---

# SECTION III — Long Numericals (4 × 20 = 80 marks)

**N-1, N-2 and N-3 compulsory. For N-4, answer any ONE.**

### N-1 (20 marks) — `papers/22-1.pdf`, question N-2

**(a)** A two-stage reciprocating belt-driven air compressor — motor input power,
specific power consumption, and the effect of reducing discharge pressure to
6 kg/cm²g.

**(b)** A 160 TPH process gas stream cooled 55 → 35 °C by cooling water, to be
re-schemed as an **air-fin fan cooler followed by a water-cooled chiller** taking
it to 30 °C, worth ₹450 lakh/year of process benefit.

**Open the paper and work it there. Do not read past the question.**

> Part (b) has four sub-parts and ends in a **recommendation**. The question says
> *"as an energy auditor economically evaluate the new proposal"* — so the last
> line of your answer is a verdict, not a number.

### N-2 (20 marks) — `papers/20-1.pdf`, question N-2

A **pressurised hot water circulation system** for process heating. After each
weekend the whole system — water **and the steel piping** — is raised from 50 °C
to 140 °C at start-up.

**Open the paper and work it there.**

> Two parts: the start-up heating time, and the % reduction in start-up load and
> fuel saving if the starting temperature were 60 °C.

### N-3 (20 marks) — `papers/21-1.pdf`, question N-4(C)

A coal-based power plant with **two 200 MW units** on the same coal. Ultimate
analysis, flue gas analysis and heat rates given.

**Open the paper and work it there.**

> Four parts: Unit 1 boiler efficiency (10 marks), which unit is more efficient,
> the coal difference per day, and the station net heat rate.
>
> **Two notes you may need.** The ash loss needs a **weighted** calorific value —
> bottom and fly ash have different GCVs and are given in a 1:4 ratio. And the two
> units' heat rates are quoted **on different bases**; read the labels carefully
> before comparing anything.

### N-4 — answer any ONE (20 marks)

| Option | Paper | Topic |
|---|---|---|
| **(A)** | `papers/21-1.pdf`, N-4(A) | Cement raw mill and raw mill fan — specific power, fan efficiency from a pitot traverse, and a VFD retrofit |
| **(B)** | `papers/25-1.pdf`, N-4(D) | Composite textile mill — stenter on a coal-fired boiler, converted to a biomass thermic fluid heater |
| **(C)** | `papers/22-1.pdf`, N-4(A) | 500 MW-class reheat turbine — isentropic efficiency, HP/IP/LP powers, turbine and net heat rate |

---

*Stop. Finish everything. Run the nine-item checking pass. Record your times.*

---

# ANSWERS AND MARKING

<details><summary>SECTION I</summary>

1. **True.** As BEE states it. *(Physically THD is normally defined as the RMS of
   the harmonics over the fundamental, not its square — but answer the paper as
   printed; this exact wording has been marked True.)*
2. **True.** Both move the charge continuously through the furnace — a rotary hearth
   carries it round on a turntable, a walking beam lifts and steps it along. The
   contrast is with **batch** furnaces, where the charge sits still.
3. **True.** The direct method is `output ÷ input` — steam flow, fuel flow, two
   enthalpies. Flue gas composition belongs to the **indirect** method.
4. **False.** That describes the **regenerative** cycle. **Reheat** takes the steam
   *back to the boiler* to be re-superheated between turbine stages. Two different
   cycles, both present on a large unit, and the paper swaps their names.
5. **False — hydrogen has the largest gap of any fuel.** GCV − NCV is the latent
   heat of the water formed from the fuel's hydrogen; pure hydrogen produces the
   most water per kg of anything, so the gap is maximal (~18%). Zero is true only
   for a fuel with **no** hydrogen, such as carbon or CO.
6. **True.** Blast furnace → pig iron (hot metal), then BOF/EAF → steel.
7. **False.** That is the **iron** (core) loss — hysteresis and eddy currents,
   constant whenever energised. **Copper loss is I²R in the windings and varies as
   load².** Day 17 Rung 181.
8. **False.** More steam through the extractions means **more useful process heat**
   for the same fuel, so EUF **rises**. The turbine gives up some power, but power
   and heat count equally in EUF.
9. **True.** NPSH*required* is a property of the pump and rises with flow, because
   higher velocity at the impeller eye means a bigger local pressure drop. NPSH
   *available* meanwhile **falls** with flow, as friction in the suction line grows
   — the two curves close on each other, which is why cavitation appears at high
   flow.
10. **True.** The air side is at fan discharge pressure and the gas side is under
    ID-fan draft, so leakage runs air → gas. Leaked air is 21% O₂ and flue gas is
    not, so the leak shows as a **rise in O₂ across the preheater** — which is
    exactly what `AL% = 100(O₂_out − O₂_in)/(21 − O₂_out)` measures. Day 17
    Rung 176.

</details>

<details><summary>SECTION II</summary>

**L-1 — aluminium furnace. The invariant is the useful heat in the metal.**

```
   FO route, cost first:
        26 litre/T × ₹38                                  = ₹988 per tonne

   Useful heat actually delivered to the metal:
        26 litre × 0.95 kg/litre × 10 000 kCal/kg × 0.65   = 1,60,550 kCal/T

   Electric route must deliver that SAME heat, at 90 %:
        1,60,550/(0.90 × 860)                              = 207.43 kWh/T
        207.43 × ₹3.75                                     = ₹777.86 per tonne

   ADVANTAGE of electric heating                           = ₹210.14 per tonne
```

**Electrical heating is more economical**, by about 21%.

> **This is Rung 164 in its cleanest form.** The service is 1,60,550 kCal of heat
> *in the metal*. Neither furnace's efficiency belongs in the other's arithmetic —
> the 65% appears only in sizing the service, the 90% only in what electricity it
> takes to deliver it.
>
> Note also **why** electricity wins despite costing far more per kCal: the furnace
> efficiencies are 65% against 90%, and electric melting puts its heat directly
> into the charge instead of up a flue.

**L-2 — back-pressure turbine replacing the PRDS**

```
   Steam through the turbine = 900 kW / 0.045 kWh per kg    = 20 000 kg/h = 20 TPH
   Saving  = power no longer bought = 900 × ₹8              = ₹7200 per hour
```

**Why the steam is free.** The plant was *already* letting 25 TPH down from 20 to
5 bar through a PRDS — throwing the pressure drop away across a valve. The turbine
takes the same let-down and extracts work from it on the way. The steam still
arrives at the process at 5 bar with almost all its heat.

> **The trap is the ₹3500/MT import steam cost.** It is there to tempt you into
> charging the 20 TPH against the saving. **Do not** — that steam was being imported
> and let down anyway. Only if the turbine needed steam *over and above* the
> existing let-down would it cost anything. 20 < 25, so it does not.

</details>

<details><summary>N-1 — compressor and chiller re-scheme</summary>

**(a) Compressor**

```
   Isothermal power = P₁ × Q_f × ln(r) / 36.7
        P₁ = 1.033 kg/cm²a,  Q_f = 11.67 × 60 = 700.2 m³/h
        r  = (7 + 1.033)/1.033                            = 7.776
        iso = 1.033 × 700.2 × ln(7.776)/36.7              = 40.4 kW

   Shaft power   = 40.4/0.60                              = 67.33 kW
   Motor input   = 67.33/(0.90 × 0.97)                    = 77.13 kW
   Specific power= 77.13/700.2                            = 0.1102 kW per m³/h

   At 6 kg/cm²g:  r = 6.808 → iso 37.8 → shaft 63.0 → motor 72.17 kW
   REDUCTION                                              = 4.96 kW
```

**36.7 is `3600/98.067`** — the same family as 102 and 367 (Day 9). Dropping one
bar of discharge pressure saves 6.4% of the compressor's power: the standard
finding, and the reason pressure setting is the first thing an air audit checks.

**(b) Air-fin cooler plus chiller**

```
   i)   existing CW = 160 × 0.5 × (55 − 35)/(42 − 34)      = 200 m³/hr

   ii)  total duty  = 160 000 × 0.5 × (55 − 30)/10⁶        = 2.00 Gcal/h
        air-fin     = 160 000 × 0.5 × (55 − 35)/10⁶        = 1.60 Gcal/h
        chiller     = (2.00 − 1.60) × 10⁶/3024             = 132 TR

   iii) condenser duty = 132 × (1 + 1/4.2)                 = 163 TR
                       = 163 × 3024/10⁶                    = 0.49 Gcal/h
        CW for the chiller = 0.49 × 10⁶/(1.0 × 5)/1000     = 98 m³/hr

   iv)  chiller  = 132 × 3024/4.2/860/0.94                 = 117.6 kW
        air-fin fan = 300 × 100/(102 × 0.70 × 0.95)        = 442 kW
        CT pump and fan                                    = 11 kW
        TOTAL                                              = 570.6 kW

   cost = 570.6 × 9 × 8000/10⁵                             = ₹410.8 lakh/yr
   benefit                                                 = ₹450 lakh/yr
   NET                                                     = ₹39.2 lakh/yr → VIABLE
```

> **Part (iii) is Rung 163 for the third time in three papers**, and BEE writes the
> general form outright: **`condenser duty = TR × (1 + 1/COP)`**. At COP 4.2 the
> multiplier is 1.238.
>
> **Part (iv) is Rung 173.** `102` is `1000/9.81` and needs **m³/s and mmWC** — the
> 300 is m³/s, the 100 is mmWC. Say the units before you substitute.
>
> **And read the margin:** the air-fin fan draws 442 kW against the chiller's 118.
> The fan, not the chiller, is the expensive half of the new scheme. Saying that is
> the recommendation the question asks for.
</details>

<details><summary>N-2 — hot water start-up</summary>

**Both the water and the steel pipe must be heated. The steel is the part people
forget.**

```
   Water:  V = π/4 × 0.1² × 2000                           = 15.71 m³
           m = 15.71 × 1000                                = 15 708 kg

   Steel:  V = π/4 × (0.108² − 0.1²) × 2000                = 2.614 m³
           m = 2.614 × 8000                                = 20 910 kg

   Start-up load = 15 708 × 1 × 90  +  20 910 × 0.12 × 90
                 = 14,13,720  +  2,25,828                  = 16,39,548 kCal

   Boiler at 90 % of 6,00,000                              = 5,40,000 kCal/h
   TIME = 16,39,548/5,40,000                               = 3.04 hours ≈ 3 hr 2 min
```

**Part 2 — starting from 60 °C instead of 50 °C:**

```
   New load = 15 708 × 80 + 20 910 × 0.12 × 80             = 14,57,376 kCal
   Reduction = (16,39,548 − 14,57,376)/16,39,548           = 11.11 %
   Fuel saved = 1,82,172/(10 000 × 0.80)                   = 22.8 kg per start-up
```

> **The steel is 20.9 tonnes against 15.7 tonnes of water** — *more* mass than the
> water it carries. Its low specific heat (0.12) still leaves it at 14% of the
> start-up load. Omit it and you under-read the time by 25 minutes.
>
> **The checking-pass items from Rung 165 apply directly:** two masses to compute,
> two to sum. Count the lines against the parts. And the **total must exceed its
> largest component** — 16.4 lakh is bigger than 14.1 lakh ✓.
>
> Note the 11.11% reduction is exactly 10/90 — the temperature rise fell from 90 °C
> to 80 °C and *everything* else is linear in ΔT. A one-line sanity check.
</details>

<details><summary>N-3 — two-unit power plant</summary>

**Part 1 — Unit 1 boiler efficiency, indirect method (10 marks)**

```
   A_th = [11.6(40) + 34.8(2.5 − 7.5/8) + 4.35(0.5)]/100   = 5.206 kg/kg
   EA   = 3/(21 − 3) × 100                                 = 16.67 %
   AAS  = 5.206 × 1.1667                                   = 6.073 kg/kg
   m_dfg= 0.40(44/12) + 0.012 + 6.073(0.77)
          + (6.073 − 5.206)(0.23) + 0.005(64/32)           = 6.365 kg/kg

   L₁ dry flue gas   6.365 × 0.24 × (170 − 30)/4000        = 5.35 %
   L₂ hydrogen       9(0.025)[584 + 0.45(140)]/4000        = 3.64 %
   L₃ fuel moisture  0.133[584 + 0.45(140)]/4000           = 2.15 %
   L₄ air humidity   0.0199 × 6.073 × 0.45 × 140/4000      = 0.19 %
   L₅ CO   [0.015/(0.015+7)] × 0.40 × 5654/4000            = 0.12 %
   L₆ ash  0.35 × 260/4000              ← weighted GCV     = 2.28 %
   L₇ radiation (given)                                     = 0.45 %

   η = 100 − 14.18                                          = 85.8 %
```

**The weighted ash GCV:** bottom and fly ash are 1:4, at 500 and 200 kCal/kg.

```
        GCV_ash = (1 × 500 + 4 × 200)/5                     = 260 kCal/kg
```

Use 500 alone and L₆ becomes 4.4%; use 200 alone and it becomes 1.75%. **The ratio
is given because it is needed.**

**Part 2 — which unit is more efficient?**

**Read the labels.** Unit 1 is quoted as a **turbine** heat rate; Unit 2 as a
**unit** heat rate. Different quantities — convert before comparing:

```
   Unit 1 unit heat rate = 2450/0.858                       = 2855 kCal/kWh
   Unit 2 unit heat rate (as given)                         = 2790 kCal/kWh
```

**Unit 2 is more efficient — 2790 against 2855.** *(And lower heat rate is better:
Day 12's direction rule. If you want it unambiguous, convert both to efficiency —
860/2855 = 30.1% against 860/2790 = 30.8%.)*

**Part 3 — coal difference per day**

```
   At 85 % load: generation = 200 000 × 0.85 × 24           = 40,80,000 kWh/day
        Unit 1 = 2855 × 40,80,000/4000/1000                 = 2911.7 TPD
        Unit 2 = 2790 × 40,80,000/4000/1000                 = 2845.8 TPD
        DIFFERENCE                                           = 65.9 TPD
```

*(BEE's key works it at both 75% and 85% and awards marks for either — 58.1 TPD at
75%. Say which load factor you used.)*

**Part 4 — station net heat rate**

```
   Station gross HR = (2855 + 2790)/2                       = 2822 kCal/kWh
   Net = gross/(1 − APC) = 2822/0.90                        = 3136 kCal/kWh
```

**Net is always worse than gross** — Day 12 Rung 124.
</details>

<details><summary>N-4 — answers</summary>

**(A) 21st N-4(A) — cement raw mill and fan**
```
   a) SPC of mill = 2294 kW/260 TPH                         = 8.8 kWh/t
   b) SPC of fan  = 1450 kW/260 TPH                         = 5.58 kWh/t
   c) ρ = 1.35 × (10 323 − 850)/10 323 × 273/(273 + 70)     = 0.986 kg/m³
      v = 0.86 √(2 × 9.81 × 14.5/0.986)                     = 14.6 m/s
      A = π(3.5)²/4 = 9.62 m² → flow                        = 140.4 m³/s
      η_static = 140.4 × (30 + 850)/(102 × 1450 × 0.95)     = 87.9 %
   d) affinity: P₂ = 1450 × (40/50)³ = 742.4 kW
      SAVING                                                 = 707.6 kW
```
**The static pressure is −850 mmWC and it is printed with the sign.** Subtract it.
Rung 137B, and the third sitting in which it appears.
*(BEE's key prints the fan SPC as 5.77; 1450/260 = 5.58. Their arithmetic, not
yours.)*

**(B) 25th N-4(D) — textile, coal boiler vs biomass thermic fluid**
```
   bone dry = 1250 × 0.94                                    = 1175 kg/h
   wet inlet = 1175/(1 − 0.65)                               = 3357 kg/h
   evaporated = 3357 − 1250                                  = 2107 kg/h
   Q_evap = 2107 × [540 + (78 − 32)]                         = 12,34,786 kCal/h
   Q_stenter = 12,34,786/0.48                                = 25,72,470 kCal/h

   h_steam = 0.95 × 477 + 184 = 637.15 ; condensate 87
   steam = 25,72,470/(637.15 − 87)                           = 4676 kg/h
   boiler out = /0.95 ; boiler in = /0.72 ; coal = /4200      = 895 kg/h
   COAL COST = 0.895 × 7000                                  = ₹6268/hr

   TFH: out = 25,72,470/0.94 ; in = /0.70 ; biomass = /3800   = 1029 kg/h
   BIOMASS COST = 1.029 × 4000                               = ₹4115/hr

   SAVING = 2153 ₹/hr × 7200 h                               = ₹155 lakh/year
```
**Rung 148 (bone-dry basis) into Rung 164 (hold the service constant).** The drying
duty of 25,72,470 kCal/h is the invariant; the two fuel systems compete to deliver
it, each with its own efficiency *and its own distribution loss*.

*(BEE's key shows 25,72,296 in one line and 25,67,490 in the next — a typo. Their
final 4675 kg/h matches the first.)*

**(C) 22nd N-4(A) — 500 MW reheat turbine**
```
   i)   η_HP = (813 − 735)/(813 − h_s) = 0.796
        h_s = 813 − 78/0.796                                  = 715 kCal/kg
   ii)  LP exhaust = 49 + 0.98(610 − 49)                      = 599 kCal/kg
        η_LP = (741 − 599)/(741 − 559)                        = 78 %
   iii) HP = 684 000(813 − 735)/860/1000                      = 62.03 MW
        IP = 635 000(834 − 741)/860/1000                      = 68.67 MW
        LP = 545 000(741 − 599)/860/1000                      = 90.13 MW
        total 220.8 MW → generator × 0.98 × 0.97              = 209.9 MW
   iv)  turbine HR = [684(813 − 241) + 635(834 − 735)]/209.9  = 2163 kCal/kWh
        station gross HR — **CANNOT BE CALCULATED**, because boiler
        efficiency is not given
   v)   net HR = gross/(1 − 0.06), once gross is assumed
        at 85 % boiler: 2545 → 2707 ; at 88 %: 2458 → 2615 kCal/kWh
```
> **Part (iv) is the most instructive answer in any of these papers.** BEE's key
> says outright: *"SGHR cannot be calculated since boiler efficiency not given"* —
> and then awards full marks to any candidate who assumed 85–88% and said so.
>
> **Saying what is missing beats inventing it.** Write the sentence, state your
> assumption, carry it through. That is what an auditor does with incomplete data,
> and it is what the examiner is looking for.
</details>

---

# AFTER THE PAPER

| Section | Marks | Time started | Time finished |
|---|---|---|---|
| I | /10 | | |
| II | /10 | | |
| N-1 | /20 | | |
| N-2 | /20 | | |
| N-3 | /20 | | |
| N-4 (which?) | /20 | | |
| **Total** | **/100** | | |

## The three questions that matter more than the score

- [ ] **Did every long question get opened?** Four start times on the sheet.
- [ ] **Did any question run past 25 minutes?** Which, and what did it cost the next one?
- [ ] **Did I star the one-liners before calculating?** Name one you took early because of it.

Mock 1 was 84 with four seen questions. Mock 2 was 73 with eleven marks unattempted,
six of which were my gap. **Mock 3 is the clean measurement.**

**Then there are five days left.** Tell me the score and the gaps and I will build
the last week from them — it will be revision and the guidebook index, not new
material. Every Book-4 chapter has been taught and every equipment noun in the ten
papers now has a rung behind it.

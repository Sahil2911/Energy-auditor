# Mock 1 Review — Full Paper

**Sat 06 Sep, 10:39 → 13:08. 149 minutes against a 150-minute paper.**

## Score: **≈ 84 / 100.** Pass is 50.

| Section | Score | Notes |
|---|---|---|
| I — True/False | **7 / 10** | Q5, Q8, Q9 |
| II — L-1 boiler efficiency | **5 / 5** | Exact |
| II — L-2 heat pump | **3 / 5** | Compared inputs, not service |
| N-1 — trigeneration | **≈ 12 / 20** | All three components right; the total omitted one |
| N-2 — sawdust briquette boiler | **20 / 20** | Seven losses, including two never drilled |
| N-3 — cooling tower & sump | **20 / 20** | Diagram included |
| N-4(C) — cement WHRB | **17 / 20** | Right number, wrong unit, at the last line |

**And the time.** 149 minutes for a 150-minute paper — **including about 25 minutes
spent on N-4(A) before abandoning it.** The pace question that Mock A left open is
now answered: you can finish this paper, with a false start in it, and still land
inside the bell.

---

## First — "I couldn't understand the refrigeration one" is not what happened

You scored **10 of that question's 20 marks before you stopped**, and both parts
you completed are exactly right:

```
  (a) absorption ₹9.00/TR-h, centrifugal ₹6.80/TR-h
      saving ₹2.20/TR-h × 300 × 7920           = ₹52,27,200/year      ✓ exact
  (b) COP = 300 × 3024/(0.8 × 300 × 0.875 × 860) = 5.023              ✓ exact
```

Part (b) in particular has the motor efficiency in the right place — the same
distinction you got wrong twice in August and have now got right twice running.

**You stalled on one idea in part (c), not on refrigeration.** Here it is.

### What a chiller rejects to the cooling tower

Everything that goes into a chiller must come out at the condenser. That is not a
rule to memorise; it is conservation of energy with nowhere else to go.

```
   heat rejected  =  the heat you removed from the process
                  +  whatever energy you spent removing it
```

So the second term is **different for the two machines**, and that is the whole
question:

```
   Centrifugal (VCR):  spent = compressor SHAFT work
       per TR = 3024 + (0.8 × 0.875) × 860    = 3024 +  602 = 3626 kCal/h

   Absorption (VAR):   spent = GENERATOR heat
       per TR = 3024 + 2520                   = 3024 + 2520 = 5544 kCal/h
```

**An absorption machine throws away about 50% more heat per TR**, because the heat
that drove it has to leave too.

Your line was:

```
   Heat duty of 300 TR chiller = 300 × (3024 + 2520) = 16,63,200 kCal/h
   Total load = 6,00,000 + 16,63,200 = 22,63,200 kCal/h
```

**16,63,200 is the absorption chiller's rejection — the machine being removed.**
You added the new process load to the old chiller. What the question wants is the
*new* chiller plus the new process load, against a tower sized for the *old* one:

```
   Tower capacity (it was sized for the absorption chiller)
              = 5544 × 300                          = 16,63,200 kCal/h

   New load:  centrifugal  3626 × 300               = 10,87,800
              process HX   20 000 × 0.5 × 60        =  6,00,000
                                                      ───────────
                                                      16,87,800 kCal/h

   16,87,800 > 16,63,200  ⟹  NOT adequate, by 1.5 %
```

You had computed the 6,00,000 correctly at the very top of the page. **The one
missing line was `3626 × 300`.** That is the whole gap — not refrigeration.

> **The sentence to carry:** *the tower's capacity is whatever the machine it was
> sized for used to reject; the new load is whatever the new machine rejects, plus
> anything else you connect.* Two different rejection figures, one comparison.

---

## Section I — 7/10

**Q5 — "Raising feedwater temperature increases evaporation ratio without
necessarily improving efficiency."** You said False; it is **True**.

```
   ER = kg steam / kg fuel                    η = ER × (h_steam − h_fw)/GCV
```

Hotter feedwater means **less heat needed per kg of steam**, so the same fuel makes
more kg — ER rises with nothing about the boiler improved. The efficiency formula
compensates through the shrinking `(h_steam − h_fw)`. This is `concept-distinctions`
entry 2, and it is the 25th sitting's favourite trap: **ER is blind to feedwater
temperature and blind to steam wetness.**

**Q8 — pitot in the suction duct of an ID fan.** You said True; it is **False**.
An ID fan *pulls*, so its suction duct is **below** atmospheric. The static reading
is a **draft** and must be subtracted:

```
   ρ = ρ_NTP × (P_bar − P_static)/10334 × 273/(273 + t)
```

Adding it overstates density by ~13% in a kiln duct, and the velocity and every
downstream mass flow with it. Day 13 Rung 137B.

**Q9 — cement denominators.** You said True; the statement is **backwards**.

```
   STEC — THERMAL — per kg of CLINKER          (700–800 kCal/kg)
   SEEC — ELECTRICAL — per tonne of CEMENT     (65–80 kWh/t)
```

The kiln makes clinker, so kiln heat is charged to clinker. The mills make cement,
so mill electricity is charged to cement. **Cement always weighs more than the
clinker in it**, so if your cement tonnage comes out below your clinker tonnage,
you have inverted the factor.

> **Both Q8 and Q9 come from Day 13 and 13B — the chapters that were read rather
> than drilled.** That is not an argument for drilling them: two marks in Section I
> against the hours the five Day 13 drills would have cost is a trade you would
> take again. But it does confirm the qualification recorded when the plan changed:
> **Sections I and II are compulsory and do reach into sector material.** The fix
> is a re-read of the concept lines, not the numericals.

---

## Section II

### L-1 — 5/5, exact

```
   LP:  0.82 = 14(665 − 80)/GCV   ⟹  GCV = 9987.8 kCal/kg
   HP:  η = 14(732 − 105)/9987.8                      = 87.887 %
```

Two boilers, one fuel, one GCV — found from the boiler you know and used on the one
you don't. Clean, and self-corrected on the page (665 struck for 732).

### L-2 — 3/5. The error is worth more than the marks.

Your chain:

```
   diesel required = 24 000 × 40/(0.7 × 9100)          = 150.706 L/day     ✓
   diesel cost                                          = ₹7535.3/day      ✓
   COP = 150.706 × 9100 / (electrical energy input)                        ✗
```

**That numerator is the diesel heater's fuel input, not the heat delivered.**

COP is *useful heat out ÷ electricity in*. The useful heat is what the water
actually receives:

```
   Q = 24 000 L × (60 − 20) °C × 1 kCal/L·°C           = 960 000 kCal/day
```

The 1,371,429 kCal you used is `960 000 / 0.7` — the fuel the *diesel* heater had
to burn **because it wastes 30%**. The heat pump does not have to reproduce that
waste. Making it deliver 1.37 million kCal is asking it to heat the water *and*
recreate the old heater's losses.

```
   electricity = 960 000/2.5 = 384 000 kCal/day  = 446.5 kWh/day
   cost        = 446.5 × 10                      = ₹4465/day
   REDUCTION   = 7535 − 4465                     = ₹3070/day
```

You had ₹1156.58 — about a third of the true saving, because two-thirds of it was
handed back to a heater that no longer exists.

> ### The general rule, and it will recur
>
> **When comparing two ways of doing the same job, hold the SERVICE constant, not
> the input.** The service here is 960,000 kCal of hot water per day. Each option
> then answers: *what does it cost me to deliver that?*
>
> ```
>     WRONG:  both options must consume the same energy
>     RIGHT:  both options must deliver the same output
> ```
>
> The moment you carry one option's *losses* into the other option, you have
> credited the new equipment with the old equipment's inefficiency. Watch for it
> wherever an efficiency or a COP sits between input and output — heater vs heat
> pump, boiler vs electric, VCR vs VAR, throttle vs VSD.

---

## N-1 — trigeneration, ≈ 12/20

Everything computed is right. **One line of addition was never finished.**

```
   (1) EUF = (0.85 × 10 + 0.73 × 14)/24                 = 0.78          ✓

   (2) electrical  650 × 860 × 24                       = 13.416 Gcal   ✓ computed
       heat        325 × 530 × 10                       =  1.7225 Gcal  ✓
       cooling     250 × 3024 × 14                      = 10.584 Gcal   ✓

       your total                                       = 12.307 Gcal   ✗
       actual total (all three)                         = 25.7225 Gcal
```

**The electricity was computed on the line above and then left out of the sum.**
The daily total should be **25,722,500 kCal**, and the annual figure the question
also asks for — `× 330/10⁶` = **8488.4 Gcal/year** — was not reached.

That halved everything downstream:

```
   your gas   = 12.307/(0.78 × 8500)          = 1856.3 Sm³/day
   correct    = 25.7225/(0.78 × 8500)         = 3879.7 Sm³/day
```

Part (4)'s first line is right — `60 × 3024/0.5 = 362 880 kCal/h`. The jacket heat
is `650/0.95 × 860 = 588 412 kCal/h`, so the proposal is **feasible**, and the
question wants that yes/no said out loud.

**This is not a concept error.** It is a total that was never taken, in a question
whose parts you all had. **It is precisely what the checking pass is for**, and the
cheapest possible sanity check would have caught it: a trigeneration plant's daily
useful energy cannot be *less* than its electricity output alone.

> **Add to the checking pass:** when a question asks for a total and you computed
> the parts on separate lines, **count the lines against the parts** before moving
> on. Three components computed, two summed.

---

## N-2 — sawdust briquette boiler, 20/20

All seven losses, in order, including **two you had never drilled**:

```
   L₁ dry flue gas   18.866 %      L₅ CO          0.172 %   ← never drilled
   L₂ hydrogen        8.11  %      L₆ radiation   0.5   %
   L₃ fuel moisture   1.536 %      L₇ bottom ash  1.939 %   ← never drilled
   L₄ air humidity    0.723 %
                                   η = 68.154 %
   Q = 0.682 × 375 × 3300/(145 − 110) = 24 114 kg/hr = 24.114 m³/hr
```

Model answer: η 68.28%, Q 24.142 m³/hr. **You are within 0.2%.**

**And you finished the question.** Six of these twenty marks are the last two lines
— the paper asks for a circulation rate, not an efficiency, and an answer stopping
at 68% loses them. You did not stop.

### One refinement worth 0.13%

Your `m_dfg`:

```
   m_dfg = (AAS + 1) − [M + 9H₂] = 13.746 − 0.471    = 13.276 kg/kg
```

The model gets 13.19. The difference is the **ash**:

```
   m_dfg = (AAS + 1) − M − 9H₂ − ash
         = 13.746 − 0.075 − 0.396 − 0.08            = 13.196 kg/kg   ✓
```

`(AAS + 1)` assumes the whole kilogram of fuel becomes gas. For oil and gas that is
true. **For coal and biomass it is not — the ash stays behind as a solid** and
leaves through the bottom of the furnace, which is exactly the stream L₇ accounts
for. Subtract it.

At 8% ash it costs 0.13 percentage points of efficiency — immaterial here, but on a
30%-ash Indian coal it is worth 0.5% and a mark.

---

## N-3 — cooling tower and sump, 20/20

```
   CW flow    440 × 45                                  = 19 800 m³/hr
   Range      0.63 = R/(R + 4)  ⟹  R = 4 × 0.63/0.37    = 6.81 °C
   Evaporation 0.00153 × 19 800 × 6.81                  = 206.327 m³/hr
   Blowdown   206.327/(4 − 1)                           = 68.776 m³/hr
   Makeup     206.327 + 68.776                          = 275.104 m³/hr

   one pump   6000/(275.104 − 200)                      = 79.889 hrs
   both pumps 6000/(350 − 275.104)                      = 80.111 hrs
```

**Every figure exact, and the mass flow diagram drawn without being asked twice.**
Marks are allocated to that diagram and most candidates skip it.

You used `0.00153` where the model used `0.00085 × 1.8`. They are the same constant
— 0.00085 per °F, 1.8 °F per °C. Knowing that is why you did it in one step.

---

## N-4(C) — cement WHRB, 17/20

```
   ΔH_R = 2.22(5.29) + 6.48(1.25) + 7.646(63)
          − 5.116(22.68) − 0.59(5.92)              = 382.018 kCal/kg   ✓ exact
   clinker = 0.62 × 7200                           = 4464 TPD          ✓
   gas available = (152 + 120) × 4464              = 1214.208 Gcal/day ✓
   recoverable at 75 %                             =  910.656 Gcal/day ✓
   × 0.36 × 0.95 × 0.96 ÷ 860                      =  347.659 ...      ✓ the NUMBER
```

**347.659 is exactly right. The unit is not.** You wrote "MW per day", and that
unit does not exist — MW is already a rate, so "MW per day" is a rate per day,
which is an acceleration of power.

What you computed is **347.659 MWh per day** — an *energy*. The question asks for
**power in MW**:

```
   347 659 kWh/day ÷ 24 h = 14 486 kW = 14.49 MW      ✓ the model answer
```

**One division from full marks**, and the wrong unit in your own handwriting was the
flag. `MW per day` should stop the pen.

> **The check that catches this every time:** before writing the unit, ask *is this
> a stock or a flow?* kWh, kCal, tonnes, rupees are **quantities**. kW, MW, TPH,
> kCal/hr, ₹/day are **rates**. If the question says "MW" and your working has a
> "per day" in it, you are one division from the answer.
>
> A sanity anchor for cement WHR: **~2 MW per 1000 TPD of kiln.** A 7200 TPD kiln
> gives ~14 MW. 347 would have been the whole state's generation.

---

## Error tally

| # | Error | Type | Cost |
|---|---|---|---|
| 1 | Chiller rejection: used the VAR figure for the VCR | **Concept** | ~10 |
| 2 | Heat pump compared to the diesel heater's *input* | **Concept** | 2 |
| 3 | Daily total omitted the electricity already computed | **Method** — checking pass | ~7 |
| 4 | MWh/day reported as MW | **Units** | 3 |
| 5 | T/F 5 — ER vs efficiency | Concept | 1 |
| 6 | T/F 8 — duct draft sign | Concept | 1 |
| 7 | T/F 9 — STEC/SEEC denominators | Concept | 1 |
| — | m_dfg without the ash deduction | Refinement | 0 |

**Three of the seven are the same shape:** something was computed correctly and then
combined with the wrong partner — the wrong chiller's rejection, the wrong heat
duty, the wrong subset of components. **None of them is a failure to know how.**

---

## Verdict

**84/100 on a full paper at full length, inside the time, with a 25-minute false
start in the middle.** Mock A was 29/60.

You are past the question of whether you can pass this paper. What is left is
tightening: one concept (what a chiller rejects), one habit (comparing on service,
not input), one discipline (the checking pass finishing what it starts), and one
reflex (stock vs flow before writing a unit).

**Day 15 is built from exactly those four, and nothing else.**

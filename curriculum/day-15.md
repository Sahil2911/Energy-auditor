# Day 15 — Gap Closure from Mock 1

**Time: 2.5 hours.** Rungs 163–169.

Built from Mock 1's seven errors and nothing else. **84/100 means the syllabus is
done**; this session exists to convert four specific leaks into reflexes.

| What leaked | Where | Rung |
|---|---|---|
| What a chiller rejects to the cooling tower | N-4(A) part c, ~10 marks | 163 |
| Comparing options on input instead of service | L-2, 2 marks | 164 |
| A total taken before all the parts were in it | N-1, ~7 marks | 165 |
| Stock vs flow before writing a unit | N-4(C), 3 marks | 166 |
| Three Section I concepts | Q5, Q8, Q9 | 167 |
| `m_dfg` for an ash-bearing fuel | N-2, refinement | 168 |

---

## Rung 163 — What a chiller rejects, and why the two machines differ

You lost half of N-4(A) to one missing line. This rung makes that line unforgettable.

### The picture

A chiller is a heat pump: it takes heat from a cold place and puts it somewhere
hot. It cannot do that for free, and **whatever it spends to do it also has to
leave with the heat.**

```
        chilled water                              cooling water
        ────────────►  ┌──────────────┐  ────────────────────────►
         picks up      │   CHILLER    │   dumps  (Q_cold + W_spent)
         Q_cold        └──────────────┘
                              ▲
                        energy in: W_spent
```

**Conservation of energy, and nothing subtler:**

```
    Q_rejected = Q_cooling  +  Energy spent doing the cooling
```

Every chiller obeys this. What changes between machine types is **what "energy
spent" is made of.**

### The two machines, per tonne of refrigeration

```
   VAPOUR COMPRESSION — a motor drives a compressor.
   The energy spent is the compressor's SHAFT work.

        per TR = 3024  +  (kW/TR × η_motor) × 860
        at 0.8 kW/TR and 87.5 % motor:
        per TR = 3024  +  0.7 × 860  =  3024 + 602   =  3626 kCal/h
```

```
   VAPOUR ABSORPTION — heat in a generator drives it.
   The energy spent is the GENERATOR heat.

        per TR = 3024  +  3024/COP
        at COP 1.2:
        per TR = 3024  +  2520                        =  5544 kCal/h
```

**5544 against 3626 — an absorption machine dumps about 50% more heat per TR.**

### BEE writes it as one formula, and it is worth memorising in that form

The 21st sitting's N-2 — recovered from the scan on 06 Sep — states the general
case outright:

```
    Condenser duty  =  TR × 3024 × (1 + 1/COP)
```

One expression for both machines. The whole difference is the multiplier:

| Machine | COP | 1 + 1/COP |
|---|---|---|
| Centrifugal | 4.4 | **1.227** |
| Centrifugal | 5.0 | 1.200 |
| Double-effect VAM | 1.2 | **1.833** |
| Single-effect VAM | 0.7 | 2.429 |

**A COP below 1 rejects more than twice the cooling load.** That is the entire
reason absorption retrofits are cooling tower projects.

*(For a VCR quoted in kW/TR rather than COP, convert first — `COP = 3.517/(kW/TR
× η_motor)` — or use the `3024 + shaft kW × 860` form directly. Both give 3626 for
0.8 kW/TR at 87.5% motor.)*

Say why in one sentence: *a VCR's driving energy arrives as a few hundred kCal of
shaft work; a VAR's arrives as two and a half thousand kCal of generator heat, and
all of it has to come back out at the condenser.*

> **Note what does NOT appear in the VCR line: the motor losses.** Those become heat
> in the motor housing, in the plant room air — not in the refrigerant. So the
> cooling tower sees **shaft** power, and `0.8 × 0.875 = 0.7` is the right number.
> The same 87.5% that belongs in the COP belongs here, for the same reason.

### The three consequences, which are the exam questions

**1. Replacing a VAR with a VCR frees tower capacity.**

```
   (5544 − 3626) × 300 TR = 5,75,400 kCal/h freed — about a third of the duty
```

**2. Replacing a VCR with a VAR needs a bigger tower.** Same arithmetic, the other
way. An audit that recommends absorption chillers on waste heat and forgets the
tower has recommended a plant that trips in May.

**3. A VAR's cooling water flow is ~1.5× a VCR's for the same TR**, so the CW pump
power rises even as the chiller power falls. Count it before claiming the saving.

### Now redo the question, and notice which figure goes where

The tower already exists. **Its capacity is whatever the machine it was sized for
used to reject.**

```
   Existing tower (sized for the 300 TR absorption chiller)
        capacity = 5544 × 300                          = 16,63,200 kCal/h

   Proposed new load:
        centrifugal chiller   3626 × 300               = 10,87,800
        process heat exchanger 20 000 × 0.5 × (110−50) =  6,00,000
                                                         ───────────
                                                         16,87,800 kCal/h

   16,87,800  >  16,63,200   ⟹  the tower is NOT adequate, short by 1.5 %
```

**The two 300-TR figures are different numbers and they play different roles.**
5544 × 300 is the *capacity*, because that is what the tower was built to shed.
3626 × 300 is the *new demand*. Using 5544 on both sides — which is what happened
in the mock — compares the old plant to itself and answers nothing.

> **The sentence to write at the top of any tower-adequacy question:**
>
> ```
>     CAPACITY  = what the OLD machine rejected
>     NEW LOAD  = what the NEW machine rejects  +  anything newly connected
> ```

### Interpretation to add, because the marks are there

The changeover *frees* tower duty; the process heat exchanger then consumes more
than was freed. A 1.5% shortfall is marginal — a fan speed increase, a fill
replacement or a modest tower upgrade covers it. **Write that**, rather than a bare
"no". The question asks "whether", so the answer is a judgement with numbers behind
it.

### Self-check

A 500 TR VCR at 0.75 kW/TR with a 90% motor is replaced by a 500 TR double-effect
VAR at COP 1.3. By how much must the cooling tower duty grow?

<details><summary>Answer</summary>

```
   VCR per TR = 3024 + (0.75 × 0.90) × 860 = 3024 + 580.5   = 3604.5
   VAR per TR = 3024 + 3024/1.3            = 3024 + 2326.2  = 5350.2

   Growth = (5350.2 − 3604.5) × 500 = 8,72,850 kCal/h  —  a 48 % increase
```
Nearly half as much tower again. **This is why absorption retrofits are tower
projects as much as chiller projects.**
</details>

---

## Rung 164 — Comparing options: hold the service constant

The L-2 error, and it is a habit rather than a fact.

Two ways of delivering the **same job**. The job is fixed; what varies is what each
option costs to deliver it.

```
     RIGHT:  both options must deliver the same OUTPUT
     WRONG:  both options must consume the same INPUT
```

In the mock the job was **960,000 kCal/day of hot water** — 24,000 litres lifted
40 °C. That number belongs to the *water*, not to any heater.

```
   Diesel heater, 70 % efficient:
        it must BURN 960 000/0.7 = 1 371 429 kCal → 150.7 L → ₹7535/day

   Heat pump, COP 2.5:
        it must SUPPLY 960 000 kCal of heat
        electricity = 960 000/2.5 = 384 000 kCal = 446.5 kWh → ₹4465/day

   REDUCTION = ₹3070/day
```

Feeding 1,371,429 into the heat pump makes it heat the water **and** recreate the
diesel heater's 30% loss. The new equipment gets charged for the old equipment's
inefficiency, and the saving comes out at a third of the truth — ₹1157 against
₹3070.

### The drill: find the invariant first

Before comparing anything, write one line naming **what stays the same**:

| Comparison | The invariant |
|---|---|
| Diesel heater vs heat pump | kCal delivered to the water |
| Absorption vs centrifugal chiller | TR of cooling |
| Throttle vs VSD | m³/hr delivered at the required head |
| Coal vs gas boiler | kg/hr of steam at the required enthalpy |
| Old vs new motor | shaft kW at the driven machine |

**Then ask each option: what do you cost me to deliver that?**

> **The tell that you have got it backwards:** an efficiency or a COP from *one*
> option appearing anywhere in the *other* option's calculation.

---

## Rung 165 — The checking pass has to finish what it starts

N-1 cost about seven marks to a sum that was never completed. Three components were
computed correctly on three separate lines; two of them made it into the total.

```
   electrical  650 × 860 × 24            = 13 416 000     ← computed, then dropped
   heat        325 × 530 × 10            =  1 722 500
   cooling     250 × 3024 × 14           = 10 584 000
                                           ──────────
   written total                         = 12 306 500     ✗
   actual                                = 25 722 500
```

**This is not a knowledge failure.** It is the kind of error the checking pass
exists for and did not catch.

### Two checks, five seconds each

**1. Count the lines against the parts.** If the question names three outputs and
your total has two addends, stop. Literally count them.

**2. Bound the answer before computing it.** A total must be **at least as large as
its largest component**. The electricity alone was 13.4 Gcal; a total of 12.3 Gcal
is impossible, and the impossibility is visible without any arithmetic.

> **Add both to the checking pass, at the front:**
>
> ```
>   ☐ Every quantity the question named — did I produce it?
>   ☐ Every total — is it ≥ its largest part?
>   ☐ Every part I computed — did it reach the total?
>   ☐ Units on every final answer
>   ☐ The question's actual wording — did I answer THAT?
> ```

The last two are already habits. The first three are the new ones, and all three
would have caught N-1.

---

## Rung 166 — Stock or flow? Decide before writing the unit

`347.659 MW per day` was written on the page. **That unit does not exist.**

```
   STOCK  (a quantity)   kWh, MWh, kCal, Gcal, tonnes, litres, ₹, m³
   FLOW   (a rate)       kW, MW, kCal/hr, TPH, m³/hr, ₹/day, kg/s
```

A stock has no "per time" in it. A flow already has one, so **a second "per day"
on a flow is a mistake, not an emphasis.**

What was computed was `347.659 MWh/day` — a stock per day, which is a flow, but a
flow of *energy per day*, not power. To get power:

```
   347 659 kWh/day ÷ 24 h/day = 14 486 kW = 14.49 MW
```

### The routine

Before writing any unit, ask two questions:

1. **Does the question want a stock or a flow?** "Power output in MW" — flow.
   "Annual energy in Gcal" — stock. "Coal reduction in TPD" — flow.
2. **Is that what I have?** Read your own working: if there is a `/day` in it and
   the answer should be in MW, divide by 24.

**And keep an anchor for each family.** For cement WHR: **~2 MW per 1000 TPD of
kiln capacity.** 7200 TPD → ~14 MW. 347 MW would be a nuclear station.

| Quantity | Sane range |
|---|---|
| Cement WHR power | 2 MW per 1000 TPD |
| Cement STEC | 700–800 kCal/kg clinker |
| Cement SEEC | 65–80 kWh/t cement |
| Boiler efficiency (solid fuel) | 65–85 % |
| Chiller | 0.6–0.9 kW/TR, COP 4–6 |
| Absorption chiller COP | 0.6–0.7 single, 1.1–1.4 double |
| Cooling tower approach | 3–6 °C |
| Power plant net heat rate | 2300–2800 kCal/kWh |
| Stenter drying efficiency | 45–55 % |

**An answer outside its anchor is wrong until proved otherwise.**

---

## Rung 167 — The three Section I concepts

### Q5 — evaporation ratio is blind to feedwater temperature

```
   ER = kg steam / kg fuel                η = ER × (h_steam − h_fw)/GCV
```

Raise the feedwater from 40 °C to 105 °C: each kg of steam now needs **less** heat,
so the same fuel makes **more** kg. **ER rises. The boiler has not changed.**

The efficiency formula does not move, because the `(h_steam − h_fw)` that
multiplies the larger ER is correspondingly smaller.

**ER is blind to three things:** feedwater temperature, steam wetness (carryover
raises the meter reading and lowers the enthalpy per kg), and the GCV/NCV basis —
it never uses a calorific value at all. Use ER for tracking one boiler on one fuel;
use efficiency for anything that compares.

### Q8 — a duct on the suction side of a fan is under draft

An ID fan **pulls**. Everything upstream of it is below atmospheric.

```
   ρ_duct = ρ_NTP × (P_bar ± P_static)/10334 × 273/(273 + t)

           UPSTREAM of a fan (suction)   →  MINUS      kiln, furnace, preheater
           DOWNSTREAM of a fan (discharge) →  PLUS     forced draft, supply ducts
```

**Ask which side of the fan you are on.** Boiler, kiln, preheater and cooler ducts
feeding an ID fan are all suction, all minus. Getting it wrong moves the density
13% and every mass flow after it.

### Q9 — the two cement denominators

```
   The KILN makes clinker  →  kiln heat is charged to CLINKER
        STEC, kCal per kg of clinker,  700–800

   The MILLS make cement   →  mill electricity is charged to CEMENT
        SEEC, kWh per tonne of cement, 65–80
```

**Cement always weighs more than the clinker in it** — gypsum, fly ash, slag are
added. So `cement tonnes = clinker tonnes × factor`, with the factor above 1. If
your cement tonnage comes out below your clinker tonnage, you have inverted it.

---

## Rung 168 — `m_dfg` for an ash-bearing fuel

```
   m_dfg = (AAS + 1) − 9H₂ − M            ← oil, gas: the whole kg becomes gas
   m_dfg = (AAS + 1) − 9H₂ − M − ash      ← coal, biomass: the ash stays behind
```

`(AAS + 1)` counts the air plus **one kilogram of fuel**, assuming all of it leaves
as gas. Ash does not — it drops out of the furnace bottom, which is exactly the
stream the L₇ bottom-ash loss accounts for. Counting it in the flue gas as well is
counting it twice.

At 8% ash it costs 0.13 percentage points of efficiency. On a 30%-ash Indian coal
it costs about half a point and a mark.

---

## Rung 169 — The checking pass, final version

Ten minutes at the end of the paper. **Every item here has cost you marks at least
once.**

```
  ☐ 1. Did I produce every quantity the question NAMED?
  ☐ 2. Is every total ≥ its largest component?
  ☐ 3. Did every part I computed actually reach its total?
  ☐ 4. Stock or flow — does the unit match what was asked?
  ☐ 5. Is every answer inside its sanity anchor?
  ☐ 6. Any inverse quantity — did I convert before comparing?
        (heat rate → efficiency, kW/TR → COP, SEC → output per unit)
  ☐ 7. Any two cases with a different constant — did I convert each before
        differencing?  (Δ(E)/k ≠ Δ(E/k))
  ☐ 8. Did I answer the question's actual WORDING — "whether", "the reduction",
        "the difference", "in m³/hr"?
  ☐ 9. Any leftover data — one line saying why, then move on.
```

Items 1–3 are new after Mock 1. Items 6 and 7 come from Day 12 and Day 13. Item 8
is Trend 2 from the phase-2 checkpoint, still the most expensive of them.

---

# Practice — 45 minutes

Redo, cold, the two parts you did not finish. **They are not new questions.**

| # | Question | Marks | Budget |
|---|---|---|---|
| 73 | 20th N-3, **part (c) only** — tower adequacy | 10 | 15 min |
| 74 | 16th N-2, **parts 2, 3 and 4** — trigeneration | 14 | 20 min |
| 75 | 16th L-1 — heat pump, from scratch | 5 | 8 min |
| 76 | **22nd N-4(D)** — DRI steel, the coal reduction only | 5 | 10 min |

**Drill 76 is new, from the 22nd sitting recovered on 06 Sep.** It is the same DRI
plant as Day 13's Block C with different numbers — you already own the method, so
it tests one thing only: `Δ(E)/k ≠ Δ(E/k)`. The yield runs *backwards* here
(88% → 85%) and the GCV moves further (5000 → 5200), so the trap bites harder:

```
    difference-then-convert    = 50.2 TPD
    convert-then-difference    = 71.7 TPD      ← a 43 % gap
```

<details><summary>Answers</summary>

**73:** capacity 16,63,200; new load 10,87,800 + 6,00,000 = 16,87,800; **NOT
adequate by 1.5%**, recoverable with a modest tower upgrade.

**76:** plant SEC 10.60 → 9.955 Mcal/t. Coal 559.9 → 488.2 TPD, **reduction
71.7 TPD**. (BEE's own method gives 50.2; give 71.7 and note theirs in one line.)

**74:** daily useful energy **25,722,500 kCal**; annual **8488.4 Gcal**; gas
**3879.7 Sm³/day**; VAR needs 362,880 kCal/h against 588,412 available in the
jacket water → **feasible**.

**75:** ₹7535/day vs ₹4465/day, **reduction ₹3070/day**.
</details>

---

## Day 15 checklist

- [ ] **`Q_rejected = Q_cooling + energy spent`**, and know the two forms of "spent"
- [ ] Know VAR rejects ~50% more per TR than VCR, and why
- [ ] **Capacity = what the old machine rejected; new load = what the new one does**
- [ ] Can state the invariant before comparing two options
- [ ] **Never carry one option's efficiency into the other's calculation**
- [ ] Count the lines against the parts before taking a total
- [ ] A total is ≥ its largest component
- [ ] **Stock or flow before writing the unit** — no "MW per day"
- [ ] Know the sanity anchors table
- [ ] ER is blind to feedwater temperature, wetness and GCV basis
- [ ] Suction side → subtract the static pressure
- [ ] STEC per kg clinker, SEEC per tonne cement
- [ ] Subtract the ash from `m_dfg` for coal and biomass
- [ ] **Can run the nine-item checking pass from memory**

**Next: Full Mock 2** — `curriculum/day-16.md`, built entirely from the 21st and
22nd sittings, which were unreadable scans until this week and appear nowhere in
the used-question ledger. **This time "unseen" was checked rather than remembered.**
The target is not the pass mark; it is a clean checking pass.

# The physics behind the parts you skipped

*Rewritten. The first version gave formulas and a slogan. This one derives them.*

---

# § 1 · The first law on a machine that runs in a cycle

**A refrigerating machine returns to the same state every cycle.** Its internal
energy at the end of a cycle equals its internal energy at the start:

```
    ΔU_cycle = 0
```

The first law for that closed system over one complete cycle is therefore

```
    ΔU = ΣQ + ΣW  =  0        ⟹        ΣQ_in + W_in  =  ΣQ_out
```

**Everything that enters must leave. Not as a slogan — as ΔU = 0.**

For a chiller, what enters is the heat picked up in the evaporator, `Q_e`, **plus
whatever you spent to run it**, `P`. What leaves is the heat thrown away at the
condenser, `Q_c`:

```
        ┌──────────────────────────────────────────────────┐
        │                                                  │
   Q_e  │   evaporator  ──►  the machine  ──►  condenser   │  Q_c
  ──────┼──►                      ▲                    ────┼──►
  at    │                         │                        │  at
  7 °C  │                         P                        │  40 °C
        └─────────────────────────┼────────────────────────┘
                                  │  what you paid

                          Q_c  =  Q_e  +  P
```

> **This is the whole of "heat rejection".** It is not a separate topic. It is
> `ΔU = 0` written down for a box you have drawn round the plant.
>
> **And it says the condenser is always the biggest number in the question** —
> bigger than the cooling load, bigger than the power. That is a sanity check you
> now own.

---

# § 2 · The second law: why you must pay at all, and how much

**Clausius' statement:** heat does not flow from cold to hot on its own. So lifting
`Q_e` from 7 °C to 40 °C *requires* a payment. The question is how big.

**Entropy answers it.** For a reversible cycle the entropy taken from the cold
reservoir must equal the entropy dumped to the hot one:

```
    Q_e/T_e  =  Q_c/T_h              (T in KELVIN — always)

    with Q_c = Q_e + P:

    Q_e/T_e = (Q_e + P)/T_h    ⟹    P = Q_e (T_h − T_e)/T_e
```

**Read that.** The payment is proportional to `(T_h − T_e)` — **the temperature
lift** — and inversely proportional to `T_e`.

```
                    Q_e             T_e
    COP_Carnot  =  ─────  =  ───────────────
                     P         T_h  −  T_e
```

### What this gives you, physically

| | Meaning |
|---|---|
| **Lift more, pay more** | Doubling `T_h − T_e` doubles the work for the same cooling |
| **Cold is expensive** | Small `T_e` in the numerator — a freezer costs far more per TR than a comfort chiller |
| **COP can exceed 1, easily** | You are not *making* the heat, you are *moving* it. A COP of 5 breaks no law |

**Check it on the 18th's two chillers:**

```
    Ice plant:   T_e ≈ −12 °C = 261 K,  T_h ≈ 40 °C = 313 K
                 Carnot COP = 261/52                       = 5.02
                 actual     = 3.516/1.52                   = 2.31   → 46 % of Carnot

    Pre-cooler:  T_e ≈  +5 °C = 278 K,  T_h ≈ 40 °C = 313 K
                 Carnot COP = 278/35                       = 7.94
                 actual     = 3.516/0.80                   = 4.39   → 55 % of Carnot
```

**Real machines run at 40–60% of Carnot.** If a question's implied COP comes out
above its Carnot bound, you have made an error — that is a check no formula sheet
gives you.

---

# § 3 · The vapour-compression chiller — you pay in *work*

```
    P is electrical work into the compressor shaft.
    Q_c = Q_e + P = Q_e + Q_e/COP = Q_e (1 + 1/COP)
```

**At COP 4.4 the multiplier is 1.227.** You pay only 23% extra on top of the cooling
load, because work is an efficient currency — every joule of it goes straight into
the refrigerant.

### ⚠️ Shaft work, not motor input — and now you know why

**The condenser only sees energy that crossed into the refrigerant.** The motor's
own I²R and iron losses never enter the gas; they warm the motor and the plant room.

```
    1.728 kW/TR   what the motor draws from the grid
    × 0.88        motor efficiency
    = 1.52 kW/TR  what the shaft delivers INTO the refrigerant   ← use this
```

**That is why the 18th's key uses 1.52 and not the 1.728 it computed two lines
above.** It is a control-volume decision, not a rounding choice: **draw the boundary
round the refrigerant, and the motor losses fall outside it.**

---

# § 4 · The absorption chiller — you pay in *heat*, and that changes everything

**A VAR has no compressor.** It has a generator, where steam or hot water boils
refrigerant out of solution. So it touches **three** temperatures, not two:

```
     Q_g in at T_g  (steam, ~175 °C)
            │
            ▼
     ┌──────────────┐
     │     VAR      │────► Q_rejected at T_h (~40 °C)   condenser + absorber
     └──────▲───────┘
            │
     Q_e in at T_e  (~7 °C)
```

### Why its COP is near 1 — derive it, do not memorise it

**Think of the VAR as two machines bolted together:**

```
   ①  A HEAT ENGINE between T_g and T_h, producing notional work
          W = Q_g (1 − T_h/T_g)                          ← Carnot efficiency

   ②  A HEAT PUMP driven by that work, lifting Q_e from T_e to T_h
          Q_e = W × T_e/(T_h − T_e)                      ← Carnot COP

   Multiply:
          Q_e            (        T_h )        T_e
   COP = ────  =  ( 1 − ─── )  ×  ─────────
          Q_g            (        T_g )    T_h − T_e
```

**You pay the Carnot penalty twice.** That single fact is the entire reason a VAR's
COP is around 1 while a compression chiller's is around 5.

| Driving heat | T_g | Ideal COP | Real machine |
|---|---|---|---|
| Engine jacket water, 90 °C | 363 K | **1.17** | ~0.6–0.7 |
| Hot water / low-pressure steam, 120 °C | 393 K | **1.73** | ~0.7 single-effect |
| Steam at 8.5 bar(g), ~175 °C | 448 K | **2.56** | **~1.2 double-effect** |

> **Notice what the table says.** A VAR's COP is not a property of the machine alone
> — **it is set by the temperature of the heat you feed it.** That is why
> double-effect machines, which use higher-pressure steam and a second generator
> stage, reach 1.2 while jacket-water machines struggle past 0.7.
>
> **And it explains the paper's numbers:** the 21st's double-effect on 8.5 bar(g)
> steam at COP 1.2 is realistic. The 20th's hot-water machine at COP 1.65 is
> generous — but **use the number the paper gives you** and move on.

### Now the rejection, and why it is so much larger

**Same first law, ΔU = 0 — but now the payment is a *heat* stream, and all of it
must leave:**

```
    Q_rejected  =  Q_e  +  Q_g  =  Q_e (1 + 1/COP)
```

**The algebra is identical to the compression chiller. The physics is not.**

```
    2400 TR = 72,57,600 kCal/h of cooling, both machines.

    VCR, COP 4.4 — paid in WORK:
         you spend    72,57,600/4.4 =  16,49,455 kCal/h of electricity
         you reject   72,57,600 + 16,49,455 =  89,07,055 kCal/h     (× 1.227)

    VAR, COP 1.2 — paid in HEAT:
         you spend    72,57,600/1.2 =  60,48,000 kCal/h of steam heat
         you reject   72,57,600 + 60,48,000 = 1,33,05,600 kCal/h    (× 1.833)

    ADDITIONAL burden on the cooling tower   =  43,98,545 kCal/h
    Cooling water at ΔT = 8 °C:  43,98,545/(1000 × 1 × 8) = 549.8 m³/hr
```

> **The reason in one sentence:** *a compression chiller is paid a small amount of
> high-quality work; an absorption chiller is paid a large amount of low-quality
> heat — and every kilocalorie of that heat has to leave through the same cooling
> tower as the cooling load itself.*
>
> **That is why swapping to absorption means a bigger tower and more CW pumping**,
> and it is the single most repeated HVAC idea in these ten papers.

---

# § 5 · The reciprocating engine — the first law again, then *quality*

## The split, and why it is roughly thirds

```
    ┌──────────────────────────────────────────────────────┐
    │  fuel chemical energy  19,19,646 kCal/h    (100 %)    │
    └───┬──────────────┬─────────────────┬─────────────────┘
        │              │                 │
        ▼              ▼                 ▼
   shaft work     jacket heat       exhaust gas       (+ radiation, small)
   5,37,501       5,56,697          8,25,448
     28 %           29 %              43 %
```

**Why only ~28–40% to the shaft:** an internal-combustion engine is a heat engine,
and the second law caps it. Idealised, the Otto cycle gives
`η = 1 − 1/r^(γ−1)` — compression ratio and γ, nothing else. Real gas engines reach
35–42%; this one is quoted at 28%.

**Why the jacket takes ~29%:** peak gas temperature is over 2000 K against a cylinder
wall held near 400 K. That gradient drives a large conductive flux, and the wall
must be cooled or it fails. **The coolant leaves at 85–95 °C** because that is what
the engine's materials and the pressurised circuit allow.

**Why the exhaust takes the rest:** the gas is thrown out mid-expansion at
**400–500 °C.** The paper gives 28% and 29%; **it never states 43% — you get it by
subtraction**, because the three must total 100.

```
    CHECK, free and worth doing:
        28 % of 19,19,646 = 5,37,501        625 kW × 860 = 5,37,500   ✓
```

## ⚠️ Now the part that actually matters — the two heat streams are not equal

**They are nearly the same size in kilocalories. They are completely different in
usefulness.** Energy is conserved; **availability is not.**

The maximum work obtainable from heat `Q` at temperature `T`, rejected to ambient
`T₀`, is its **exergy**:

```
    Exergy  =  Q ( 1 − T₀/T )              T, T₀ in Kelvin
```

With ambient at 30 °C = 303 K:

| Stream | kCal/h | Factor `1 − T₀/T` | Work-equivalent |
|---|---|---|---|
| Shaft power | 5,37,501 | **100 %** | 5,37,501 |
| Jacket water, 90 °C | 5,56,697 | **16.5 %** | 91,978 |
| Exhaust gas, 450 °C | 8,25,448 | **58.1 %** | 4,79,414 |

> **The jacket and the exhaust carry almost the same heat and differ by 5× in
> worth.** That is the whole engineering content of a trigeneration question, and no
> energy balance alone will tell you.

**Which is why each stream gets the duty it is fit for:**

```
    jacket water, 90 °C   →  hot water, or a single-effect VAM
                             (its 16 % availability cannot raise steam)

    exhaust gas, 450 °C   →  steam in an HRSG, or a DOUBLE-effect VAM
                             (58 % availability — a real driving potential)

    shaft work            →  electricity: sell it, or drive a compression
                             chiller at COP 5 rather than a VAM at COP 1
```

**The 20th's question follows exactly that logic**, and now you can reconstruct it
rather than remember it:

```
    Jacket 29 %:   Q_e = Q_g × COP = 5,56,697 × 1.65     ⟹  303.8 TR
                                     ─────────────
                                         3024

    Exhaust 43 %, of which 20 % is taken for hot water:
                   8,25,448 × 0.20 = 1,65,090 kCal/h
                   m = 1,65,090/(1 × (60 − 30))          ⟹  5503 kg/hr
```

> **⚠️ Which way does COP point?** `COP = Q_e/Q_g` always. So:
> ```
>     given the DRIVING HEAT, cooling  =  Q_g × COP        ← the 20th
>     given the COOLING, driving heat  =  Q_e / COP        ← the 21st
> ```
> **You met both directions in two days.** Write `COP = cooling/heat in` at the top
> of the page and read off whichever you need.

---

# § 6 · Why cogeneration actually saves fuel — and why costing every service is physics

**The economics question is not accounting. It is a primary-energy comparison**, and
if you set it up as one the arithmetic follows by itself.

**The grid electricity you displace was made in a condensing power station at about
33% efficiency** — you spent five days proving it, gross heat rates near 2600 kCal/kWh
against 860. **Every kWh you *don't* import saves three kWh of fuel somewhere.**

```
    SEPARATED SYSTEM — three plants, three fuels
        625 kW from the grid          5,37,501/0.33   = 16,28,791 kCal/h
        303.8 TR from a VCR at 4.4    242.6 kW /0.33  =  6,32,707
        hot water from an 85 % boiler 1,65,090/0.85   =  1,94,224
                                              TOTAL   = 24,55,722 kCal/h

    COMBINED — one gas engine doing all three          = 19,19,646 kCal/h

    PRIMARY ENERGY SAVED                               =  5,36,076 kCal/h  ( 21.8 % )
```

> **That is the physical reason the money works.** Not "the chilling comes free" —
> **the separated system burns 22% more fuel to deliver the identical three
> services**, because it throws away the engine's jacket and exhaust heat *and*
> suffers the power station's condenser loss as well.

**So when you cost it, you must price every service the new plant delivers**, for
the same reason: **you are comparing two ways of delivering one fixed set of
outputs.** Drop a service and you are no longer comparing like with like.

```
    Existing:  power     625 × 9.25                        = ₹5781/hr
               cooling   303.8 × 11.25                      = ₹3418/hr
               hot water 5503 × 30/500 = 330 kg stm × 2.85  = ₹ 941/hr
                                                     TOTAL  = ₹10,140/hr
    Trigeneration: gas    213.3 × 45                        = ₹9598/hr
    Saving ₹542/hr × 7500 h                                 = ₹40.6 lakh/yr
```

**Priced on electricity alone the engine looks absurd — ₹9598 to replace ₹5781.**
It is not a trick of accounting; **it is that the electricity-only comparison
ignores two of the three products.**

**Same principle, other way up, in the 22nd N-2(b):** the benefit is fixed at ₹450
lakh/yr, so you must total **every** kW the scheme adds — chiller 117.6 **plus** fan
442 **plus** cooling tower 11 = 570.6 kW → ₹410.8 lakh → net ₹39.2 lakh.
**Count only the chiller and you have changed the system boundary mid-question.**

---

# § 7 · The ice plant — where the energy actually goes, and why pre-cooling wins

## Latent heat dominates, and the numbers say so

```
    Cool water 30 → 0 °C    16500 × 1   × 30  =   4,95,000 kCal   ( 26 % )
    FREEZE at 0 °C          16500 × 80        =  13,20,000 kCal   ( 70 % )
    Sub-cool ice 0 → −8 °C  16500 × 0.5 × 8   =      66,000 kCal   (  4 % )
                                       TOTAL  =  18,81,000 kCal/day
```

**Freezing is 70% of the duty** and happens at a single temperature — the phase
change absorbs 80 kCal/kg with no temperature drop at all. **Note also `Cp_ice =
0.5`, half of water's**, because the hydrogen-bond network in ice has fewer degrees
of freedom available to store energy.

## Why pre-cooling with a *second* chiller saves energy

**This is § 2 used in anger, and it is the real content of part (e).**

The ice plant chiller must evaporate below −8 °C to freeze and sub-cool. **Every
kilocalorie it removes is lifted across ~52 K**, whether that kilocalorie is taking
water from 30 °C to 12 °C or freezing it.

**But water from 30 to 12 °C does not need a −12 °C evaporator.** A separate chiller
with its evaporator at +5 °C does the same job across a lift of only ~35 K:

```
    Carnot COP at −12 °C evaporator = 261/52 = 5.02     actual 2.31  (1.52 kW/TR)
    Carnot COP at  +5 °C evaporator = 278/35 = 7.94     actual 4.39  (0.80 kW/TR)
```

**Moving the same heat at a smaller lift costs less work. That is the entire
saving** — `P = Q(T_h − T_e)/T_e`, with a smaller bracket and a larger denominator.

```
    Pre-cool duty  = 16500 × 1 × (30 − 12)/(24 × 3024)     =   4.09 TR
    Water chiller  = 0.8 × 4.09 × 24                       =   78.5 kWh/day
    Ice chiller now  25.92 − 4.09 = 21.83 TR
                   = 21.83 × 1.728 × 24                    =  905.2 kWh/day
    Auxiliaries, unchanged                                 =  189.8 kWh/day
                                                    TOTAL  = 1173.5 kWh/day
    Was 1265 → per tonne of output 1173.5/15 = 78.2 against 84.33
                                             ⟹ saving 6.1 kWh/tonne
```

**The auxiliaries did not change and still belong in the total** — you are comparing
two *totals*, and a term omitted from one side is an error even when it cancels.

## Part (f), and the shortcut the physics hands you

```
    Q_condenser  =  Q_e  +  P  =  TR × 3024  +  TR × (kW/TR)_shaft × 860
```

**Both terms are proportional to TR.** So the fractional reduction needs no
kilocalories at all:

```
    reduction  =  1 − 21.83/25.92  =  15.8 %
```

> **Whenever every term in an expression is proportional to one quantity, a
> percentage change is just the ratio of that quantity.** Worth ten seconds of
> recognition and it removes two lines of arithmetic under time pressure.

---

# § 8 · The three metrics, and what BEE means by each

**They are one number wearing three hats.**

```
    COP  =  Q_e/P             dimensionless, both in the same units

    kW/TR  =  P/Q_e  in practical units
           =  3.516/COP                since 1 TR = 3024 kCal/h = 3.516 kW

    EER    =  cooling in Btu/h per watt of input  =  3.412 × COP
```

**Where 3.516 comes from — derive it, never memorise it:**

```
    1 TR  =  3024 kCal/h  =  3024/860  kW  =  3.516 kW
```

> **⚠️ The 18th's "EER" is numerically the COP.** BEE computes
> `3024/(1.52 × 860) = 2.313`, which is `3.516/1.52` — **a dimensionless ratio of
> cooling to input.** The true Btu/Wh figure would be `3.412 × 2.313 = 7.89`.
> **Use BEE's own definition when BEE sets the question**, and state which you used.
>
> **And 3.516 is not 3.413.** `3.516 kW/TR` comes from `3024/860`; `3.412 Btu/Wh` is
> a British-unit conversion. Similar digits, unrelated jobs.

---

# The physics on one page

```
 1.  ΔU = 0 round a cyclic machine  ⟹  Q_rejected = Q_cooling + what you paid
     The condenser is ALWAYS the largest number in the question.

 2.  Entropy sets the price:  P = Q_e (T_h − T_e)/T_e   ⟹  COP_Carnot = T_e/(T_h − T_e)
     Pay for the LIFT. Real machines run at 40–60 % of Carnot.
     An implied COP above its Carnot bound means you have erred.

 3.  VCR pays in WORK  (small, high quality)  →  reject × (1 + 1/COP), 1.227 at 4.4
     VAR pays in HEAT  (large, low quality)   →  reject × (1 + 1/COP), 1.833 at 1.2
     A VAR's COP = (1 − T_h/T_g) × T_e/(T_h − T_e) — the Carnot penalty twice.
     Its COP is set by the TEMPERATURE of the driving heat, not by the machine.

 4.  Condenser sees SHAFT work. Motor losses fall outside the refrigerant boundary.

 5.  Engine: shaft ≈ 28 %, jacket ≈ 29 %, exhaust = the rest by subtraction.
     Equal kCal are NOT equal worth:  exergy = Q(1 − T₀/T)
     jacket 90 °C → 16 %   ·   exhaust 450 °C → 58 %   ·   work → 100 %
     Match each stream to a duty its temperature can actually drive.

 6.  Cogeneration saves fuel because the separated system also pays the power
     station's condenser loss. Price EVERY service — you are comparing two routes
     to one fixed set of outputs.

 7.  Phase change dominates any freezing duty (80 vs 30 kCal/kg here).
     Pre-cooling works because the same heat crosses a SMALLER LIFT.

 8.  1 TR = 3024 kCal/h = 3.516 kW.  kW/TR = 3.516/COP.  BEE's "EER" here = COP.
```

# Monday 21 — Cogeneration, Turbines and the Heat Rate Ladder

**Every cogeneration, turbine and heat-rate question in all ten sittings.**
Nothing curated away. Part A is the bridge the topic needs; Part B is the
complete inventory, in run order.

> **The honest arithmetic first.** The topic holds **19 twenty-mark questions,
> three five-markers, one 12-mark part and twelve True/False statements** — about
> **419 marks** of past paper, across the 16th to the 25th. Worked once each at
> exam pace that is **close to eight hours**, not three and a half.
>
> **Nothing is dropped to make it fit.** Instead: **two pairs are the same question
> twice** (marked ⇄ — solve one, read the other's key), and **five of the six
> gas-engine questions are also chiller questions**, so Tuesday picks them up at no
> extra cost. What is left for Monday is Groups 1 and 2 — **the ladder and the
> turbine** — which is where both Mock 3 stalls were.
>
> **A cut line is marked** at the 3½-hour point. Below it is the rest, each item
> with a slot. You decide where to stop; I am not deciding it for you.

| | | Time |
|---|---|---|
| **A** | The heat rate ladder — read, then the six self-checks | 45 min |
| **B · Group 1** | The ladder at station level — 7 questions | 117 min |
| **B · Group 2** | Turbine heat rate from steam — 5 questions in 3 sittings | 75 min |
| ✂️ | **— 3 h 57 min —** | |
| **B · Group 3** | Cogeneration proper: EUF, heat-to-power, steam rate — 5 | 112 min |
| **B · Group 4** | Gas turbine & engine cogeneration, trigeneration — 6 | → **Tuesday** |
| **B · Group 5** | One loose condensing-turbine question | 25 min |
| **B · Group 6** | Twelve True/False, all sittings | 15 min |

---

# PART A — The heat rate ladder

## The question a heat rate actually answers

Forget the formula for a moment. An auditor standing in a power station wants to
know one thing:

> **How much fuel does one unit of electricity cost me?**

That is all a heat rate is — **kCal in, per kWh out**. It is the plant's price tag,
written in heat instead of rupees.

But "in" and "out" are not obvious. **Where do you stand when you measure?**

## Three places to stand, three heat rates

```
        ┌──────────────────────────────────────────────────────────┐
        │                                                          │
 fuel ──┼──►[ BOILER ]──steam──►[ TURBINE + GENERATOR ]──► gross kWh┼──► net kWh
        │                                                    │     │       ▲
        └────────────────────────────────────────────────────┼─────┘       │
                                                             │             │
                                                       auxiliaries ────────┘
                                                    (fans, pumps, mills)

        ├──── 3. NET HEAT RATE ──────────────────────────────────────────────┤
        ├──── 2. GROSS HEAT RATE ────────────────────────────┤
                         ├──── 1. TURBINE HEAT RATE ─────────┤
```

**Each heat rate is a different box drawn around the same plant.**

| | Box drawn around | Input counted | Output counted |
|---|---|---|---|
| **1. Turbine heat rate** | turbine + generator | heat **in the steam** | gross kWh |
| **2. Gross (unit) heat rate** | boiler + turbine + generator | **fuel** | gross kWh |
| **3. Net (station) heat rate** | the whole station | fuel | kWh **leaving the fence** |

**Moving from 1 to 2 pushes the input boundary left**, so the boiler's losses come
inside the box. **Moving from 2 to 3 pushes the output boundary right**, so the
station's own consumption comes out of the answer.

**Both moves make the number bigger.** That is the ladder.

## Rung 1 → 2: why you divide by boiler efficiency

Boiler efficiency says what fraction of the fuel reached the steam:

```
    heat in the steam = fuel energy × η_boiler
```

Turn it round to get the fuel from the steam:

```
    fuel energy = heat in the steam / η_boiler
```

Both heat rates have **the same kWh underneath**, so divide both sides by it and
the relationship passes straight through:

```
    ┌──────────────────────────────────────┐
    │   GROSS HR  =  TURBINE HR / η_boiler │
    └──────────────────────────────────────┘
```

**A 2500 turbine heat rate on an 85% boiler is a 2941 gross heat rate.** The 441
difference is the boiler's losses, charged to every kWh.

## Rung 2 → 3: why you divide by (1 − APC)

The station burns coal to run its own fans, pumps and mills — **8 to 10%** of what
it makes. The fuel does not change; **the electricity you can sell shrinks:**

```
    net kWh = gross kWh × (1 − APC)
```

Same fuel on top, smaller number underneath:

```
    ┌──────────────────────────────────────┐
    │   NET HR  =  GROSS HR / (1 − APC)    │
    └──────────────────────────────────────┘
```

## The ladder, and its sanity check

```
     TURBINE HEAT RATE          e.g.  2500
             │  ÷ η_boiler  (0.85)
             ▼
     GROSS (UNIT) HEAT RATE           2941
             │  ÷ (1 − APC)  (0.92)
             ▼
     NET (STATION) HEAT RATE          3197
```

> **Every step divides by a number below 1, so every step goes UP.**
>
> ```
>         turbine  <  gross  <  net        ALWAYS
> ```
>
> **If your gross comes out below your turbine heat rate, you multiplied.** That
> single inequality catches the error before it reaches the next part.

**And the efficiency that goes with each:**

```
    η = 860 / heat rate        — but WHICH heat rate?

    860/turbine HR  →  the TURBINE CYCLE's efficiency
    860/gross HR    →  the PLANT's efficiency          ← this is "plant efficiency"
    860/net HR      →  efficiency of exported power
```

**`860/2450` on a turbine heat rate is not a plant efficiency.** It is the cycle's,
and it leads nowhere — which is exactly where Mock 3's N-3 stopped.

## What goes into "heat in the steam" — and the reheat term

Single-reheat units heat the steam **twice**: once to raise main steam, once to
re-superheat the cold reheat on its way back. **Both count.**

```
                 MS flow (h_MS − h_feedwater)  +  RH flow (h_HRH − h_CRH)
    Turbine HR = ──────────────────────────────────────────────────────────
                                GENERATOR output, kW
```

**Two things people drop here:**

1. **The reheat term.** On the 22nd's turbine it is `635 × (834 − 735)` — 62,865
   Mcal/h, **14% of the total**. Leaving it out understates the heat rate.
2. **The denominator is the generator, not the turbine shaft.** 220.7 MW at the
   coupling becomes 209.8 MW at the terminals after gearbox and generator. **Heat
   rate is always per kWh you can actually sell.**

## ⚠️ The basis trap — read the label before comparing

Papers quote one unit as a *turbine* heat rate and another as a *unit* heat rate,
in the same table, without warning.

```
    Unit 1: turbine heat rate 2450,  boiler 85.8 %
    Unit 2: unit heat rate    2790
```

**Compare 2450 with 2790 and Unit 1 looks better. It is not.** Climb Unit 1 to the
same rung first:

```
    Unit 1 gross = 2450/0.858                  = 2855
    Unit 2 gross                               = 2790     ⟹ Unit 2 wins
```

> **Two labels to check every time:** *turbine* or *unit/gross* or *net*? And
> **lower is better** — heat rate is an inverse quantity. If you want it
> unambiguous, convert both to efficiency (30.1% vs 30.8%) and compare those.

## Where the ladder does NOT apply: back-pressure cogeneration

A back-pressure set sends its exhaust to a **process**, not a condenser. Its heat
rate looks catastrophic — **30,000–35,000 kCal/kWh** — because the box counts all
the fuel against the electricity and **ignores the steam that left usefully**.

**That is a defect of the measure, not the machine.** For cogeneration use:

```
    EUF  =  (power + useful process heat) / fuel energy      typically 70–85 %

    Heat-to-power ratio  =  useful heat (kW_th) / power (kW_e)

    Steam rate  =  kg of steam per kWh generated
```

> **Judge a condensing plant on heat rate. Judge a cogeneration plant on EUF.**
> Using heat rate on a back-pressure set is the mistake the 22nd sitting tests as a
> True/False, and using EUF on a condensing plant flatters it.

---

## ⚠️ 860 or 3600? — the constant follows the units

The efficiency formula is **not** `860/HR`. It is:

```
    η  =  (energy in one kWh)  /  (heat rate)
```

**One kWh is 860 kCal *and* 3600 kJ — the same energy in two currencies.** So:

```
    heat rate in kCal/kWh   →   η = 860 / HR
    heat rate in kJ/kWh     →   η = 3600 / HR
```

`860 × 4.186 = 3600`. They are one formula, not two.

> **This is not a pedantic point — BEE got it wrong in a printed answer.** The
> 16th sitting's N-4(A) and the 18th's N-4(C) are **the same question**, same data,
> and the 18th's official answer is right while the 16th's is wrong. You will solve
> it once in Group 2 and read both keys. The difference is this constant.

**The same 860 read backwards.** When a gas turbine or gas engine is given by its
**efficiency** rather than by its fuel flow, invert it:

```
    heat rate  =  860 / η        e.g.  28 % engine →  860/0.28  =  3071 kCal/kWh
```

That is rung 1 climbed from the other end, and the 18th, 20th and 21st sittings all
open a question with it.

## ⚠️ The 860 audit — run it before you write the constant

**860 converts between kW and kCal/h. It does nothing else.** So before writing it,
ask what unit the expression is *already* in:

| What you have written | Already in | 860? |
|---|---|---|
| `steam kg/hr × Δh kCal/kg` | kCal/hr | **no** |
| `fuel kg/hr × GCV kCal/kg` | kCal/hr | **no** |
| `generator output kW` | kW | **× 860** |
| `TR × 3024` | kCal/hr | **no** |

> **A heat rate's numerator is a heat flow, never a power.** So in a heat rate built
> from steam or from fuel, **860 never appears in the numerator** — only in the
> efficiency at the end, where it sits on the kWh.

**Where it legitimately appears mid-calculation:** an EUF, where power and process
heat must be brought to one currency —
`EUF = (kW × 860 + steam kCal/h) / fuel kCal/h`. **The 860 goes on the power, not
on the steam.**

**The failure is silent and enormous.** An already-thermal numerator multiplied by
860 comes out 860 times too big — `2133` becomes `18,34,294`, which looks like a
different species of error rather than one stray constant.

## ⚠️ Which efficiency does "overall" mean? — always gross

```
    860 / turbine HR  =  turbine CYCLE efficiency      ← a different question
    860 / GROSS HR    =  OVERALL / PLANT efficiency    ← this one
    860 / net HR      =  efficiency of EXPORTED power  ← a different question
```

**Overall efficiency is fuel-in against what the plant *made*.** A 60 MW set made
60 MW; the 6 MW its auxiliaries ate was still generated. **A plant does not become
less efficient for consuming some of its own output.**

**BEE names the other two when it wants them.** Unqualified **"overall"** or
**"plant"** means gross.

> ### The route with no rung to pick
> ```
>     η = (generator kW × 860) / (fuel kg/hr × GCV)
> ```
> **Output over input, no heat rate involved.** Two lines, cannot be got wrong.
> Use it whenever you are unsure which rung is meant — and note the 860 sits on the
> kW, so the audit above passes.

## Condenser heat load — what the turbine could not use

**Start from the machine, not the formula.** Steam arrives at the condenser having
already given the blades everything it could. The condenser's job is to turn it back
into water so the feed pump can send it round again.

```
                 ┌──────────────────────────┐
   exhaust steam │                          │  condensate
   ─────────────►│        CONDENSER         ├──────────────►
   h = 554       │                          │  h_f = 45.5
                 └────────────┬─────────────┘
                              │  heat thrown away
                              ▼   to cooling water
```

**The load is simply what the steam still had, minus what the water leaves with:**

```
    Q_condenser  =  steam flow × (h_exhaust  −  h_condensate)
                 =  231000 × (554 − 45.5)   =  11,74,63,500 kCal/hr
```

> **Two numbers off the table, and no dryness fraction anywhere.** This is the form
> to use, and it is why part (d) of the 19th N-4(A) never depended on part (c).

### The route through the dryness fraction — the same thing, spelt out

BEE's key writes it as:

```
    Q = steam flow × h_fg × x  =  231000 × 571.6 × 0.889  =  11,73,83,200 kCal/hr
```

**These are not two methods. They are one identity.** By definition:

```
    h_exhaust = h_f + x·h_fg      ⟹      x·h_fg = h_exhaust − h_f
                                                = 554 − 45.5 = 508.5
```

So `571.6 × 0.889 = 508.1 ≈ 508.5` — the tiny gap is only BEE rounding x to three
places. **Use the subtraction; it is shorter and carries no rounding.**

> **When you are forced through x:** if the question gives you the dryness fraction
> and the latent heat but *not* the exhaust enthalpy, multiply. If it gives you the
> exhaust enthalpy, subtract. **Never compute x just to multiply it back out.**

### ⚠️ What the condensate enthalpy is — and is not

**The steam leaves as saturated water at the condenser's own pressure**, not at
feedwater temperature.

```
    h_condensate = h_f at condenser conditions   = 45.5 kCal/kg   ← use this
    h_feedwater  = 130 kCal/kg                   ← NOT this
```

**130 is where the water gets to after the feed heaters**, downstream of the
condenser. Using it would charge the condenser with heat that the *heaters* add,
and understate the load by `231000 × 84.5 = 1,95,19,500` — about 17%.

**The same trap in the other direction:** do not use `h_exhaust − h_feedwater` for
the *boiler* either. Each box takes the enthalpies at its own two ports.

### The three ways a paper asks for it

| Given | Use |
|---|---|
| exhaust enthalpy + condensate enthalpy | `m (h_exh − h_f)` ← **default** |
| dryness fraction + latent heat | `m · x · h_fg` |
| cooling water flow and rise | `m_cw × Cp × ΔT` |

**The third is the auditor's field method**, and papers use it to go the other way
— from the load to the cooling water the plant must circulate:

```
    m_cw  =  Q / (Cp × ΔT)  =  11,74,63,500 / (1000 × 8)  =  14,683 m³/hr
```

*(ρCp for water = 1000 kCal per m³ per °C. A condenser's CW rise is typically
**8–10 °C**; the 24th N-3 states it as 45 m³ of CW per tonne of steam, which is the
same fact in different clothing.)*

### Sanity: the condenser is the biggest heat flow in the plant

**About half the fuel's heat leaves through the condenser.** Check it here:

```
    Fuel in     = 41758 × 4240        = 17,70,53,920 kCal/hr
    Condenser   =                       11,74,63,500 kCal/hr   =  66 %
    Electricity = 60000 × 860         =  5,16,00,000 kCal/hr   =  29 %
```

**Two thirds of the fuel goes to the cooling tower.** That is not a fault in the
plant — it is the Rankine cycle, and it is why a back-pressure set that *uses* its
exhaust reaches an EUF of 0.79 while this machine sits at 0.29.

> **The order-of-magnitude check:** the condenser load should come out **roughly
> twice the electrical output in heat terms**, and always larger than it. If yours
> is smaller than `kW × 860`, you have lost a factor of ten or used the wrong
> enthalpy.

## The two ways a heat rate can be built

Every heat rate question in these ten papers builds the numerator one of two ways.
**Recognising which one you are in decides the whole answer.**

```
    FROM FUEL          coal kg/h × GCV                 → gives GROSS directly
                       ────────────────────
                          gross kW

    FROM STEAM         MS(h_MS − h_fw) + RH(h_HRH − h_CRH)   → gives TURBINE
                       ──────────────────────────────────
                            generator kW
```

**From fuel lands you on rung 2. From steam lands you on rung 1.** If a question
gives you both — as the 19th N-4(A) does — you can compute the gross heat rate
twice and they must agree. **That is the single most valuable check in this topic.**

## Self-checks — do these before Part B

**1.** Turbine heat rate 2100, boiler 88%, auxiliary power 7%. Gross and net?

<details><summary>Answer</summary>

```
    Gross = 2100/0.88            = 2386 kCal/kWh
    Net   = 2386/0.93            = 2566 kCal/kWh
    2100 < 2386 < 2566 ✓
```
</details>

**2.** A plant reports a net heat rate of 3000 and 10% auxiliary power. Its boiler
runs at 87%. What is the turbine heat rate?

<details><summary>Answer</summary>

Climb **down** the ladder — multiply instead of divide:
```
    Gross   = 3000 × 0.90        = 2700
    Turbine = 2700 × 0.87        = 2349 kCal/kWh
    2349 < 2700 < 3000 ✓
```
</details>

**3.** Unit A: turbine heat rate 2300, boiler 84%. Unit B: net heat rate 3050 with
9% auxiliary power. Which is more efficient?

<details><summary>Answer</summary>

Put them on the same rung. Gross is the easiest common ground:
```
    A gross = 2300/0.84          = 2738
    B gross = 3050 × 0.91        = 2776
    ⟹ A is better (2738 < 2776), by about 1.4 %
```
As efficiencies: 31.4% vs 31.0%.
</details>

**4.** Why is a back-pressure turbine's heat rate around 34,000, and is that bad?

<details><summary>Answer</summary>

Because heat rate charges **all** the fuel to the electricity and counts **none** of
the process steam, which is most of the useful output. **It is not bad** — the same
plant has an EUF of 75–85%, far above a condensing plant's 36%. Wrong measure, not
a wrong machine.
</details>

---

**5.** A turbine heat rate is quoted as 7400 kJ/kWh. What is the turbine cycle
efficiency?

<details><summary>Answer</summary>

```
    η = 3600/7400 = 48.6 %
```
Not `860/7400 = 11.6 %`, which is absurd on its face — no turbine cycle is 12%.
**If an efficiency comes out under 20% or over 55%, you used the wrong constant.**
</details>

**6.** A gas engine runs at 32% efficiency. Its heat rate?

<details><summary>Answer</summary>

`860/0.32 = 2688 kCal/kWh`. And the check: `860/2688 = 32%` ✓.
</details>

---

# PART B — the complete inventory

**Every question on this topic in `papers/`, in run order.** Twenty-mark questions
get **25 minutes, hard stop**; five-markers get **7 minutes**. Write the start time
next to each.

**Status column:** ⭐ = do this one first · ⚠️ = you ran out of time on it in Mock 3
· ⇄ = twin of another question, solve one and read the other's key · 🅣 = Tuesday
picks it up.

---

# GROUP 1 · The ladder at station level — 105 min

*Fuel in, kWh out. These are the rungs themselves.*

## 1.0 · 16th S-3 — `papers/16.pdf` — warm-up — 3 min

Condenser back pressure 82 mmHg, atmospheric pressure 755 mmHg. **Condenser
vacuum?**

<details><summary>Check</summary>

```
    Vacuum = atmospheric − absolute = 755 − 82 = 673 mmHg
```
**Three minutes, and it is the same step 1.5 asks for inside a 20-marker.** Note
the barometric pressure is 755 here, not 760 — **use the number the question
gives you**, not the one you remember.
</details>

## 1.1 · 19th L-1 — `papers/19-1.pdf` — 5 marks — 7 min

Plant A: gross unit heat rate 2400 kCal/kWh, auxiliary power 10%.
Plant B: net heat rate 2500. **Which is more efficient?**

<details><summary>Check</summary>

**The whole question is one rung.** A is quoted gross, B is quoted net — you cannot
compare them as printed.

```
    A net = 2400/(1 − 0.10) = 2666.7 kCal/kWh
    B net = 2500                        ⟹ B is more efficient
```

**Five marks for climbing one rung.** Note that A's *gross* number is the smaller
of the two printed figures — reading the labels is the entire exam question.
</details>

## 1.2 · 25th L-2 — `papers/25-1.pdf` — 5 marks — 7 min

Assessment year: gross heat rate 2300, APC 9%. Baseline net heat rate 2600.
Baseline generation 5000 MU. 1 kgoe = 10,000 kCal; 1 ESCert = 1 TOE.
**Find the reduction in net heat rate and the ESCerts earned.**

<details><summary>Check</summary>

```
    Assessment net = 2300/0.91           = 2527.47 kCal/kWh
    Reduction      = 2600 − 2527.47      = 72.53 kCal/kWh
    ESCerts        = 5000×10⁶ × 72.53 / 10⁷  = 36,264
```

**Watch the 10⁷:** 10,000 kCal per kgoe × 1000 kg per tonne. **Say that in a line**
— it is where the marks are, and it is the step most candidates fumble.
*(Set B prints APC 8%, giving 2500 and a 100 kCal/kWh reduction. Same method.)*
</details>

## 1.3 · 19th N-4(A) — `papers/19-1.pdf` — 20 marks — 25 min ⭐

A 60 MW captive power plant. Coal flow **and** steam conditions are both given.
Find coal consumption, gross and net heat rate, dryness of exhaust steam,
condenser heat load, specific coal consumption and overall efficiency.

### ⭐ The ladder, checked against itself

**This is the one question in the whole set that closes the ladder on itself.**
Both routes from Part A are open to you:

```
    FROM STEAM:   231000 × (793 − 130) / 60000  = 2553  ← turbine heat rate
                  2553 / 0.865                  = 2951  ← climb to gross

    FROM FUEL:    41758 × 4250 / 60000          = 2951  ← gross, directly
```

**2951 both ways.** Two independent routes, one answer.

> **If you do nothing else today, do this reconciliation.** It is what turns the
> ladder from something you remember into something you own — and it is the exact
> join you could not make in Mock 3.

<details><summary>Full check</summary>

```
    Coal                = 41,758 kg/hr
    Gross heat rate     = 2951 kCal/kWh
    Net heat rate       = 2951/(1 − 0.10)          = 3279 kCal/kWh
    Dryness of exhaust  = (554 − 45.5)/571.6        = 0.890
    Condenser load      = 11,74,63,500 kCal/hr
    Specific coal       = 0.696 kg/kWh
    Overall efficiency  = 860/2951                 = 29.1 %
```
**Overall efficiency uses the gross, not the turbine, heat rate.** `860/2553`
would give 33.7% — a number that belongs to the turbine cycle and to nothing else.
</details>

## 1.4 · 21st N-4(C) — `papers/21-1.pdf` — 20 marks — 25 min ⚠️

Two units in one station. Unit 1 is quoted by **turbine** heat rate, Unit 2 by
**unit** heat rate. Which is more efficient, the excess coal the worse one burns at
85% load, and the station's net heat rate.

<details><summary>Check</summary>

**The basis trap, full size.** 2450 against 2790 flatters Unit 1; they are on
different rungs.

```
    Unit 1 gross = 2450/0.858 = 2855
    Unit 2 gross              = 2790      ⟹ Unit 2 is the better unit
    Excess coal at 85 % load  ≈ 65.9 TPD          (BEE prints 64.08)
    Station gross ≈ 2821   →  station net ≈ 3136  (BEE prints 3135)
```
**The small gaps are rounding in BEE's intermediate steps.** State your rounding in
one line and the marks are yours either way.
</details>

## 1.5 · 24th N-4(A) — `papers/24-1.pdf` — 20 marks — 25 min

**Two independent halves.** (i) A 500 MW unit improves back pressure from 0.14 ata
to 0.11 ata; design turbine heat rates 2040 and 2000. Condenser vacuum at each,
improvement in gross heat rate, coal saved per day at 74% load. (ii) A 1000 MW
station's annual coal, FO and HSD — find generation, gross and net heat rate.

<details><summary>Check</summary>

```
(i) Vacuum = barometric − absolute
    0.14 ata × 760 = 106.4 mmHg  →  760 − 106.4 = 653.6 ≈ 654 mmHg
    0.11 ata × 760 =  83.6 mmHg  →  760 −  83.6 = 676.4 ≈ 676 mmHg
    Gross HR  = 2040/0.87 = 2344.8   and   2000/0.87 = 2298.9
    Improvement                                      = 46 kCal/kWh
    Coal saved = 500000 × 0.74 × 46 / 5500 = 3093 kg/h = 74.2 T/day

(ii) Units   = 1000 × 0.76 × 7200 / 1000      = 5472 MU
     Gross HR = (4045400×10³×5500 + 3500×10³×10200)/5472×10⁶ = 4073 kCal/kWh
     Net HR   = 4073/0.92                                     = 4427 kCal/kWh
```

**Three traps, all deliberate:**
1. **The HSD is excluded.** 150 MT for earthmoving equipment is not heat into the
   plant. Putting it in the numerator is the error the question is hunting.
2. **Turbine efficiency 93% and alternator 96% are never used** in part (i). BEE
   supplies them as distractors. **Unused data is not a sign you went wrong.**
3. **4073 is a gross heat rate**, and it is enormous — that is a lignite-class
   plant, not an error.

*BEE prints 650 and 674 mmHg for the vacuums, having converted through
1.0332 kg/cm² and then used 760 rather than 735.6 mmHg per kg/cm². Within 0.6%;
the marks are in `vacuum = barometric − absolute`, so state your conversion.*
</details>

## 1.6 · 17th N-4(A) — `papers/17.pdf` — 20 marks — 25 min

A 110 MW unit, **design versus actual**. Actual steam flow to the turbine, specific
steam consumption, **% increase in gross unit heat rate compared to design**, and
the extra monthly coal at 80% PLF.

<details><summary>Check</summary>

**This runs the ladder in both directions in one question.** Actual is built from
steam upward; design is given as a turbine heat rate and climbed.

```
    Generator input = 110/0.96                = 114.58 MW
    Turbine output  = 114.58 + 4.42 (gearbox) = 119 MW
    Steam flow      = 119000×860/(810 − 550)  = 3,93,615 kg/hr
    SSC             = 393615/110000           = 3.58 kg/kWh
    Coal            = 393615×(810 − 135)/(0.875×3800) = 79,907 kg/hr
    Specific coal   = 0.726 kg/kWh
    ACTUAL unit HR  = 0.726 × 3800            = 2758.8 kCal/kWh
    DESIGN unit HR  = 2362.5/0.875            = 2700    kCal/kWh
    % increase      = (2758.8 − 2700)/2700    = 2.17 %
```

> **Note what is compared with what.** The design figure given is a *turbine* heat
> rate (2362.5); the actual is computed as a *unit* heat rate. **Comparing them as
> printed gives 16.8% and is wrong.** Climb the design figure to rung 2 first. This
> is the basis trap again, and it is worth 6 of the 20 marks.

**The gearbox loss is added, not subtracted** — it sits between the turbine and the
generator, so the turbine must produce *more* than the generator delivers.
</details>

---
# GROUP 2 · Turbine heat rate from steam — 75 min

*Enthalpy in, kWh out. Cylinder by cylinder.*

## 2.1 · 16th N-4(A) ⇄ 18th N-4(C) — `papers/16.pdf`, `papers/18-1.pdf` — 20 marks — 25 min ⭐

**The same question in two sittings.** 150 bar / 550 °C reheat unit, HP and LP
cylinders, isentropic efficiency 0.9 each. Generator efficiency is **95% in the
16th and 96% in the 18th** — the only difference in the data.

Find: power at the generator, turbine heat rate, turbine cycle efficiency, dryness
of LP exhaust *(16th only)*, specific steam consumption.

**Solve it once with the 16th's data. Then read both official keys.**

<details><summary>Check — and BEE's error</summary>

```
    h₂  = 3450 − 0.9(3450 − 3050)          = 3090 kJ/kg   (cold reheat, actual)
    h₄  = 3560 − 0.9(3560 − 2300)          = 2426 kJ/kg   (LP exhaust, actual)

    Turbine output = 228000 × [(3450−3090) + (3560−2426)] / 3600
                   = 228000 × 1494 / 3600  = 94,620 kW = 94.62 MW
```

| | 16th (η_gen 95%) | 18th (η_gen 96%) |
|---|---|---|
| Generator | **89.89 MW** | **90.83 MW** |
| Turbine heat rate | **7431 kJ/kWh** | **7354 kJ/kWh** |
| Cycle efficiency | **48.4 %** | **48.95 %** |
| Specific steam consumption | **2.54 t/MWh** | **2.51 t/MWh** |
| Dryness of LP exhaust | (2426 − 191.9)/(2584.9 − 191.9) = **0.934** | — |

> ### ⚠️ BEE's 16th-sitting answer is wrong, and the 18th's is right
>
> The 18th prints the line correctly:
> ```
>     228(3450−3090) + 228(3560−2426)/3600 = 94.62 MW      ✓
> ```
> The 16th prints the same line with **860** in place of 3600, and then reports
> **75.73 MW** — a figure that follows from neither constant. Everything
> downstream inherits it: 71.5 MW at the generator, 9342 kJ/kWh, and a cycle
> efficiency of 38.5%.
>
> **And the 16th's final line gives the game away.** It reads `860/9342 = 38.5%`.
> But `860/9342` is **9.2%**. The 38.5% comes from `3600/9342` — the *right*
> constant, written as the wrong one. The 18th does it properly and in full:
> `860/(7354/4.18) = 48.95%` — convert kJ to kCal first, *then* use 860.
>
> **Nine BEE model-answer errors found so far.** In the exam, work the chain your
> own way, state the constant you used in one line, and you are covered whichever
> key the examiner holds.

**The kJ tell:** every enthalpy here is four digits (3450, 2426). Water is
4.186 kJ/kg°C, so anything in the 2000–3600 range is kJ, not kCal. **Spot the
currency before you pick the constant.**
</details>

## 2.2 · 22nd N-4(A) — `papers/22-1.pdf` — 20 marks — 25 min ⚠️

A 500 MW-class reheat unit. HP, IP and LP cylinder powers, LP isentropic
efficiency, generator output, turbine heat rate, station gross heat rate.

<details><summary>Check — and the three fixes</summary>

```
    h₂ₛ (HP exhaust, actual)      = 715 kCal/kg
    LP exhaust = 49 + 0.98(610 − 49)        = 599 kCal/kg
    η_LP                                     = 78.0 %
    HP 62.03 MW · IP 68.67 MW · LP 89.99 MW  = 220.7 MW at the coupling
    Generator                                = 209.8 MW
    Turbine heat rate                        = 2165 kCal/kWh
    Station gross heat rate    ⟹  CANNOT BE CALCULATED
```

**Three fixes, all from Mock 3:**

1. **A reheat unit has two heat inputs.** Main steam *and* cold-to-hot reheat.
   The reheat term here is ~14% of the numerator; dropping it understates the
   heat rate and loses 4 marks.
2. **The denominator is the generator, not the coupling.** 220.7 MW becomes
   209.8 MW after gearbox and generator. Heat rate is per kWh you can sell.
3. **Say "cannot be calculated."** Boiler efficiency is not given, and BEE's own
   key says so — awarding the marks for stating it with a reasonable assumption of
   85–88%. **Naming the missing datum beats inventing it.**

**The check that proves your cylinders:** 209.8 MW against a 210 MW nameplate.
If your three cylinder powers do not sum to about the rated output, one of them
is wrong — and you know it before the examiner does.
</details>

## 2.3 · 23rd N-4(B) ⇄ 25th N-4(B) — `papers/23-1.pdf`, `papers/25-1.pdf` — 20 marks — 25 min

**Near-twins — same steam data, three small changes.** A 500 MW unit with six
feedwater heaters. Turbine cycle heat rate, unit gross heat rate, then the
**heat-rate penalty from TTD and DCA deviations** across the heater train.

| | 23rd | 25th |
|---|---|---|
| Generator output | 501,700 kW | 501,000 kW |
| Boiler efficiency | 87 % | 88 % |
| Net heat rate & plant efficiency at 6% APC | **asked** | not asked |

**Solve the 23rd** — it is the longer version and contains the 25th.

<details><summary>Check</summary>

```
23rd:   Turbine HR = [1561000(806.47 − 246) + 1413000(844.27 − 730.71)] / 501700
                   = 2063.7 kCal/kWh
        Unit gross = 2063.7/0.87            = 2372.1
        Net        = 2372.1/(1 − 0.06)      = 2523.5
        Efficiency = 860/2523.5             = 34.1 %

25th:   same numerator / 501000             = 2066.6 kCal/kWh
        Unit gross = 2066.6/0.88            = 2348.4
```

**The ladder, all three rungs, in eight marks.** `2064 < 2372 < 2524` ✓

**The reheat term is the second bracket** — 1413 TPH of cold reheat raised from
730.71 to 844.27 kCal/kg. It is 19% of the numerator here. Drop it and the heat
rate comes out near 1740, which is below any real unit and should stop you.

**Then part (c), twelve marks, is bookkeeping, not engineering:**
```
    every 0.56 °C of TTD deviation  →  0.014 % on heat rate
    every 0.56 °C of DCA deviation  →  0.005 % on heat rate
```
For each of the six heaters, take (actual − design), divide by 0.56, multiply by
the factor. **Build a six-row table and sign every row** — a heater running hotter
than design on TTD *hurts*. The marks are in the table's completeness, not in any
one row, so **fill every row even where the deviation is zero**.

*Two sittings, one method, 40 marks of the paper set for 25 minutes of work.
It is the best return on the day.*
</details>

---
# ✂️ — 3 h 45 min — stop here if the day is full

*Everything above is the spine of the topic and both Mock 3 stalls. Everything
below is the rest of it, and it is all assigned a slot — nothing is being dropped.*

---

# GROUP 3 · Cogeneration proper — EUF, heat-to-power, steam rate — 85 min

*The ladder is the wrong tool here. These four questions are why Part A ends where
it does.*

## 3.1 · 22nd L-2 — `papers/22-1.pdf` — 5 marks — 7 min

25 TPH of steam is let down from 20 to 5 bar(g) through a PRDS. Replace the PRDS
with a **back-pressure turbine** driving a 900 kW gas compressor. Steam rate
0.045 kWh/kg.

<details><summary>Check</summary>

```
    Steam needed = 900/0.045   = 20,000 kg/hr = 20 TPH
    Saving       = 900 kW × ₹8 = ₹7200/hr
```
**The point in one line:** a PRDS throws away a pressure drop that a turbine could
have been paid for. The steam still arrives at 5 bar(g) either way — **the service
is held constant** and only the route changes. That is the whole idea of
cogeneration, priced.
</details>

## 3.2 · 19th N-1 — `papers/19-1.pdf` — 20 marks — 25 min ⭐

A back-pressure steam turbine cogeneration plant: 91 TPH at 180 bar / 550 °C down
to 2 bar. Electrical output, boiler fuel, **EUF**, and **heat-to-power ratio**.

<details><summary>Check</summary>

```
    Actual exhaust h = 3420 − 0.9(3420 − 2430)      = 2529 kJ/kg
    Turbine power    = 91000 × (3420 − 2529)/3600   = 22.52 MW
    Electrical       = 22.52 × 0.97 × 0.98          = 21.4 MW
    Coal             = 91000(3420 − 504.7)/(4.18 × 4500 × 0.80) = 17.6 TPH

    EUF = [21400 × 860  +  91000(2529 − 504.7)/4.18] / (17600 × 4500)
        = (1,84,04,000 + 4,40,69,689) / 7,92,00,000  = 0.79

    Heat-to-power = 91000(2529 − 504.7)/4.18 / 21400 = 2059 kCal/kWh
                                                     = 2.39 kW_th/kW_e
```

**Three things to fix in your head here:**

1. **The useful heat is measured from the feedwater, not from zero.** `(2529 −
   504.7)`, not `2529`. The process gets the *rise*, and the condensate comes back.
2. **Both terms of the numerator must be in the same currency.** Power × 860 puts
   kWh into kCal; steam enthalpy ÷ 4.18 puts kJ into kCal. **Mixing them is the
   single most common way to lose this question.**
3. **0.79 against a condensing plant's 0.36.** That contrast *is* the answer to
   "why cogenerate", and a line saying so is usually worth a mark.
</details>

## 3.3 · 24th N-2 — `papers/24-1.pdf` — 20 marks — 30 min ⭐

**The most complete cogeneration question in the ten sittings.** A 4000 TCD sugar
plant with a 13 MW back-pressure turbine; replace two old bagasse boilers with one
80 TPH high-pressure boiler. **Eight parts**: power generation, export, bagasse
consumption, bagasse saved, heat-to-power ratio of the cogen **and** of the sugar
plant, steam rate, and EUF — each for present *and* proposed.

<details><summary>Check</summary>

```
    Plant load      = 29 × 4000/24                        = 4833 kW

PRESENT (42 kg/cm²g, boiler 67 %)
    Potential       = 72000(812 − 676)/860                = 11,386 kW
    Gross gen       = 11386 × 0.90 × 0.96                 = 9837 kW
    Export          = 0.94 × 9837 − 4833                  = 4414 kW
    Steam rate      = 72000/9837                          = 7.32 kg/kWh
    Bagasse         = 77000(815 − 95)/(2270 × 0.67)       = 36.45 TPH
    kW_th           = 72000(676 − 95)/860                 = 48,642 kW
    H:P cogen       = 48642/9837                          = 4.94
    H:P sugar plant = 48642/4833                          = 10.06
    EUF             = (9837×860 + 72000×581)/(36.45×10³×2270) = 60.8 %

PROPOSED (85 kg/cm²g, boiler 74 %)
    Gross gen       = 72000(823 − 676)/860 × 0.92 × 0.96  = 10,869 kW
    Export          = 0.94 × 10869 − 4833                 = 5384 kW
    Additional export                                     = 970 kW
    Steam rate      = 72000/10869                         = 6.62 kg/kWh
    Bagasse         = 77000(823 − 105)/(2270 × 0.74)      = 32.91 TPH
    Bagasse saved                                         = 3.54 TPH
    EUF                                                   = 67.5 %
```

**What this question is really teaching:**

- **The process steam does not change.** 72 TPH at 676 kCal/kg before and after.
  **The service is held constant** and only the pressure it was generated at
  changes — so all the gain is in the extra enthalpy drop the turbine gets to use.
- **Two heat-to-power ratios, and they are different questions.** The cogen's
  (4.94) is heat per kW *generated*; the sugar plant's (10.06) is heat per kW
  *consumed by the process*. **Read which one is asked.**
- **Steam rate goes DOWN as the plant gets better** — 7.32 → 6.62 kg/kWh. It is an
  inverse quantity, like heat rate and kW/TR. *(`reference/reciprocal-traps.md`)*
- **Raising boiler pressure raises boiler efficiency too** here, 67% → 74%. Both
  effects are in the bagasse saving; do not attribute all of it to the turbine.

*BEE's printed EUF for the present system is 60.95%, using 36.35 TPH where the
same answer computed 36.45 two lines earlier. Use your own consistent figure.*
</details>

## 3.4 · 17th N-3 — `papers/17.pdf` — 20 marks — 25 min

A **double-extraction condensing** turbine in a continuous process plant. EUF as
operating, then the effect of installing a VAM that raises the 9 kg/cm²a
extraction.

<details><summary>Check</summary>

```
    EUF, existing case                              = 75.8 %
    Extra steam to the VAM at 9 kg/cm²a             = 5400 kg/hr
    Every 12 kg/hr of extra extraction  →  1 kW     ⟹ +450 kW at the turbine
```

**Double extraction means three steam paths**, not two: first extraction, second
extraction, and what goes on to the condenser. **Draw the schematic before writing
anything** — the mass balance is where this question is won.

**The 12 kg/hr per kW is a steam rate in disguise.** More extraction at an
intermediate pressure means *more* power, not less, because that steam was going to
expand through those stages anyway — you are only changing where it leaves.

🅣 *Tuesday revisits the VAM side of this question with the chillers.*
</details>

## 3.5 · 22nd N-1 — `papers/22-1.pdf` — 20 marks — 25 min 🅣

Biogas-fired 40 bar/350 °C boiler → back-pressure turbine at 8 bar → process
(**nil condensate return**) plus a 2000 TR absorption chiller → cooling tower.

<details><summary>Check</summary>

```
    Generator heat  = 900 × 860/(0.97 × 0.98 × 0.85)  = 9,57,909 kCal/h
    Steam to turbine = 9,57,909/(720 − 660)            = 15.96 TPH
    Chiller heat    = 2000 × 3024/0.8                  = 75,60,000 kCal/h
    Steam to chiller = 75,60,000/(660 − 100)           = 13.5 TPH
    Steam to process = 15.96 − 13.5                    = 2.46 TPH
    Mixed condensate = (13.5×100 + 2.46×30)/15.96      = 89.2 °C
    Biogas          = 15960(720 − 89.2)/(0.75 × 7000)  = 1917.6 Sm³/hr
    VAM rejection   = 2000×3024 + 13500(660 − 100)     = 1,36,08,000 kCal/h
    CT flow         = 1,36,08,000/(3 × 1000)           = 4536 m³/hr
    CT pump         = (4536/3600) × 15 × 9.81/(0.75 × 0.93) = 265.8 kW
```

**"NIL CONDENSATE" is the question.** The process returns nothing, so the mixing
temperature uses 30 °C makeup for that share, not 100 °C. **Read the schematic
labels — they carry data.**

🅣 *Tuesday does the chiller-rejection half properly. Today, do parts (i)–(iv) and
leave (v) for Tuesday if time is short.*
</details>

---
# GROUP 4 · Gas turbine & engine cogeneration, trigeneration — → TUESDAY 🅣

*Six questions. **Five of the six have an absorption chiller in them**, so Tuesday
gets them almost free once the VAM is on the table. They are listed here in full so
the topic's inventory is complete, with the one line each that makes them work.*

| | Question | Marks | What it turns on |
|---|---|---|---|
| **4.1** | **18th N-3** — 20 MW GT + 70 TPH waste heat boiler, petrochemical | 20 | `HR = 860/η` |
| **4.2** | **21st N-3** — 5 MW GT cogen + 12 TPH WHRB vs grid + gas boiler | 20 | evaporation ratio → ₹/kWh |
| **4.3** | **25th N-3(i)** — topping-cycle GT, HRSG exit 135 → 95 °C | 12 | EUF before/after |
| **4.4** | **16th N-2** — gas engine trigeneration, two operating modes | 20 | time-weighted EUF |
| **4.5** | **20th N-4(D)** — hospital, 700 kW gas engine + single-effect VAM | 20 | `HR = 860/η`, then jacket heat |
| **4.6** | **22nd N-4(B)** — commercial building, 850 kW gas engine + WHRB + VAM | 20 | grid vs cogen at ₹10.35/kWh |

<details><summary>4.1 · 18th N-3 — check</summary>

```
    GT generator heat rate = 860/0.28              = 3071 kCal/kWh
    Gas rate               = 3071/13000            = 0.236 kg gas/kWh
    Exhaust gas            = (60 + 1) kg per kg of gas fired
    WHB efficiency = 48000(665 − 105) / (16000 × 0.236 × 61 × 0.3 × 515)
                                                   = 75.5 %
```
**The air-to-fuel ratio is how you get the exhaust mass flow** — 60:1 means
61 kg of gas leaves per kg of fuel burnt. Without that line there is no denominator.

*BEE takes the exhaust heat as `m Cp × 515`, i.e. against a 0 °C datum, not
against the 30 °C ambient. Using 485 gives 80.2%. **State your datum in one line.***

Part (c) then compares supplementary firing in the WHB at 77% against a separate
82% gas boiler — **hold the steam duty constant** and compare only the gas.
</details>

<details><summary>4.2 · 21st N-3 — check</summary>

```
    Existing: 3,60,00,000 kWh × ₹9                      = ₹3240 lakh
              ER = 8700 × 0.83/(665 − 85)               = 12.45 kg steam/Sm³
              steam at ₹964/T                           = ₹1079.7 lakh
                                                   total = ₹4319.7 lakh/yr
    Proposed: gas for 4500 kW at HR 3050 = 1577.58 Sm³/hr → ₹1514.5 lakh
              + depreciation ₹500 + O&M ₹200 lakh        = ₹2214.5 lakh
              effective electricity cost                 = ₹6.15/kWh
```
**Depreciation on a ₹30 crore investment is an operating cost here** — BEE puts it
in the annual comparison rather than only in a payback. Follow the question's own
framing.
</details>

<details><summary>4.3 · 25th N-3(i) — check</summary>

```
    Power        = 1500 × 3.044                          = 4566 kW
    Heat at 135 °C exit = 16.35 × 3600 × 0.265 × (520 − 135) × 0.80
                                                         = 48,04,153 kCal/h
    Steam        = 48,04,153/(663 − 105)                 = 8609.6 kg/h = 8.61 TPH
    Heat at  95 °C exit                                  = 53,03,286 kCal/h
    Steam                                                = 9504 kg/h = 9.50 TPH
    Additional steam                                     = 0.89 TPH

    Fuel input   = 1500 × 9600/860                       = 16,747 kW
    EUF          = (4566 + 4804153/860)/16747            = 60.6 %
    EUF improved = (4566 + 5303286/860)/16747            = 64.1 %
```
**Everything goes into kW before the EUF** — power is already kW, steam heat is
kCal/h ÷ 860, fuel is Sm³/h × LHV ÷ 860. **One currency, then divide.**

**The 16.35 kg/s is the tell** that this is an exhaust-side calculation, not a
fuel-side one: the HRSG sees gas, not gas fuel.
</details>

<details><summary>4.4 · 16th N-2 — check</summary>

```
    Average EUF = (0.85 × 10 + 0.73 × 14)/24             = 0.78
    P_el = 650 kW · Q_heat = 325 × 530 = 1,72,250 kCal/h
                    Q_cool = 250 × 3024 = 7,56,000 kCal/h
```
**A time-weighted average, not a plain one.** The plant runs 10 hours in heating
mode and 14 in cooling mode, so the EUFs weight by hours. Writing `(0.85+0.73)/2`
is the error the question is built around.

Then: daily useful energy in Gcal, daily gas from the average EUF, and whether a
60 TR hot-water VAM at COP 0.5 fits inside the jacket heat.
**"The energy loss in the flue gas and that in the cooling water is the same as the
engine power output"** — that sentence is the jacket-heat data, written as prose.
</details>

<details><summary>4.5 · 20th N-4(D) — check</summary>

```
    Heat rate    = 860/0.28                              = 3071 kCal/kWh
    Gas          = 625 × 3071/9000                       ≈ 213 Sm³/hr
    Jacket heat  = 29 % of engine heat input
    TR from VAM  = jacket heat × COP 1.65 / 3024
    Hot water    = 20 % of exhaust heat / (60 − 30)
```
**Same `860/η` opening as 4.1.** Then three separate heat streams out of one
engine — shaft, jacket, exhaust — each with its own percentage. **Tabulate the
engine's heat balance before answering any part.**
</details>

<details><summary>4.6 · 22nd N-4(B) — check</summary>

Commercial building: 1000 kW total load, 15,12,000 kCal/h of cooling, centrifugal
chillers at 0.45 kW/TR, grid at ₹10.35/kWh — against an 850 kW gas engine with a
WHRB and a steam absorption chiller.

**The comparison must hold both services constant** — the same 1000 kW *and* the
same 500 TR — or the cogeneration case is being flattered. *(`reference/concept-distinctions.md`)*
</details>

---

# GROUP 5 · One loose turbine question — 25 min

## 5.1 · 20th N-4(C) — `papers/20-1.pdf` — 20 marks — 25 min

A biomass power plant: 33.6 TPH at 63 kg/cm²g, 450 °C expanding to a condenser.
**What does raising the inlet temperature to 475 °C earn per year?**

<details><summary>Check</summary>

```
    Power at 450 °C                                      = 8020 kW
    h₂ at 475 °C                                         = 572.8 kCal/kg
    Power at 475 °C                                      = 8253 kW
    Steam rate      = 33600/8253                         = 4.07 kg/kWh
    Additional power                                     = +233 kW
    Additional biomass                                   = +196 kg/hr
    Net annual benefit                                   = ₹59.98 lakh/yr
```
**This is not a cogeneration question** — it is a condensing set, so there is no
EUF and no heat-to-power ratio. **It earns its place here because the extra fuel
must be netted off the extra power**, and forgetting that is the whole trap: the
answer is not `233 kW × hours × tariff`.
</details>

---

# GROUP 6 · The True/False bank — 15 min

**Every Section I statement on this topic across the ten sittings, with BEE's own
answer.** Cover the right-hand column, read the twelve, then check.

| Sitting | Statement | BEE |
|---|---|---|
| 19th S-9 | Heat rate reduces when the condenser inlet **cooling water temperature increases** | **FALSE** |
| 25th #9 | Heat rate can be improved by **decreasing** the condenser cooling water temperature | **TRUE** |
| 22nd #4 | Turbine cycle efficiency rises as condenser inlet CW temperature **falls** | **TRUE** |
| 24th #5 | Increasing the condenser **vacuum** will **increase** the heat rate | **FALSE** |
| 20th #10 | The **gross** heat rate does **not** include auxiliary consumption | **FALSE** ⚠️ |
| 21st #4 | In the **reheat** cycle, partially expanded steam is extracted at various points to heat condensate and feedwater | **FALSE** |
| 19th S-10 | A cogeneration system in a **cement plant** is a **topping** cycle | **FALSE** |
| 22nd #8 | In extraction back-pressure cogeneration, **higher** extraction flow gives a **lower** EUF | **FALSE** |
| 24th #8 | For a 20 MW cogen plant, a **back-pressure** turbine has a **lower steam rate** (kg/kWh) than an extraction-condensing turbine | **FALSE** |
| 25th #2 | Isentropic efficiency of a back-pressure turbine is **higher** if extraction temperature exceeds the steam temperature at back-pressure condition | **FALSE** |
| 25th #6 | **Lower** TTD and DCA in the feedwater heaters give **higher** cycle efficiency | **TRUE** |
| 22nd #6 | 3440 kCal/hr of waste heat into a heat pump plus a 1.5 kW compressor develops 6.6 kW | **FALSE** — `3440/860 + 1.5 = 5.5` |

### ⚠️ The one that catches everybody — 20th #10

> *"The gross heat rate of the power plant does not include auxiliary
> consumption."* **BEE says FALSE.** Read that twice, because the instinct is to
> say true.

**It hinges on which side of the fraction you are thinking about.**

```
                      fuel heat                              fuel heat
    GROSS HR  =  ──────────────────          NET HR  =  ─────────────────────
                  GROSS generation                       generation SENT OUT
                        ▲                                        ▲
             the auxiliaries are fed                 the auxiliaries have been
             out of THIS number, so it                subtracted, so this one
             INCLUDES their kWh                       EXCLUDES them
```

**The auxiliaries are inside the gross figure, not outside it.** Gross generation is
everything the machine made — including the kWh the mills and fans then ate. It is
the *net* heat rate that has taken them out.

So **"gross does not include auxiliary consumption" is false**: gross includes them;
net is the one that does not. The rung that *excludes* auxiliaries is rung 3, and
that is precisely why net is the bigger number.

### And the three chains that answer the rest

**1 · Cooling water → heat rate.** *Colder CW → better vacuum → lower back
pressure → bigger enthalpy drop → more kWh per kg of steam → lower heat rate.*
**Four of the twelve statements are this one chain**, written forwards and
backwards. Learn it once.

*Careful with the word "vacuum":* higher vacuum means **lower** absolute pressure,
which is **better**. Vacuum and pressure move opposite ways, and the 24th's
statement is built on that reversal.

**2 · Topping or bottoming.** A **topping** cycle burns fuel to make power *first*
and uses the rejected heat second. A **bottoming** cycle takes heat that a process
has already used — a cement kiln's preheater exhaust — and makes power from it.
**A cement waste-heat plant is bottoming**, which is why the 19th's statement is
false.

**3 · Back-pressure versus extraction-condensing, on steam rate.** A back-pressure
set drops the steam only as far as the process pressure, so each kg does **less**
work, so it needs **more** kg per kWh. **Its steam rate is higher, not lower** — the
24th's statement inverts it. *(The 24th N-2 sugar plant gives the real figure:
7.32 kg/kWh on a back-pressure set, against about 4 on a condensing one.)*

> **And the fourth idea, which has no chain — it is just a definition.**
> **Reheat** sends steam *back to the boiler* to be re-superheated.
> **Regenerative** bleeds steam *to the feedwater heaters*.
> Different hardware, different purpose. The 21st swaps the two names and asks you
> to notice.

---

# Before you close the book

Write these five lines on the exam card from memory. If any one of them needs the
file to reconstruct, you have found tomorrow's first twenty minutes.

```
   1.   turbine  <  gross  <  net              always
   2.   gross = turbine / η_boiler ;  net = gross / (1 − APC)
   3.   η = 860/HR  (kCal)   or   3600/HR  (kJ)   — check the currency
   4.   engine or GT given by efficiency:  HR = 860/η
   5.   back-pressure set:  EUF, heat-to-power, steam rate — never heat rate
```

**And the one check that is worth more than the five lines:** when a question gives
you both fuel and steam, compute the gross heat rate both ways and make them agree.

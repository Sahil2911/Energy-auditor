# Monday 21 — Cogeneration, Turbines and the Heat Rate Ladder

**2 hours 20 minutes.** Part A is the bridge that was missing. Part B is five
questions, each on a timer.

| | | Time |
|---|---|---|
| **A** | The heat rate ladder — read and work the self-checks | 40 min |
| **B1** | 19th N-4(A), 60 MW captive plant — **the ladder's demonstration** | 25 min |
| **B2** | 21st N-4(C), two 200 MW units — **finish what you started** | 25 min |
| **B3** | 22nd N-4(A), 500 MW reheat turbine — **finish parts (iv) and (v)** | 25 min |
| **B4** | 17th N-3 *or* 20th N-4(C) — whichever appeals | 25 min |

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

# PART B — Five questions, each on a timer

**25 minutes each, hard stop.** Write the start time next to each.

---

## B1 · 19th sitting N-4(A) — `papers/19-1.pdf` — 20 marks

> *"A 60 MW captive power plant (CPP) of a chemical plant has a coal fired Boiler,
> condensing steam Turbine and Generator…"*

**Do this one first.** It is the cleanest demonstration of the ladder in the whole
set — it gives you enough to compute the heat rate **both ways**, and they agree
exactly.

Six parts: gross heat rate, net heat rate, dryness fraction, condenser heat load,
specific coal consumption, overall efficiency.

<details><summary>Answer</summary>

**First, the coal**, from the boiler's direct efficiency:

```
    0.865 = 231 000 × (793 − 130)/(q × 4240)
    q = 231 000 × 663/(0.865 × 4240)              = 41 758 kg/hr
```

```
  a) GROSS HR  = 41 758 × 4240/60 000             = 2951 kCal/kWh
  b) NET HR    = 41 758 × 4240/54 000             = 3279 kCal/kWh
                 (= 2951/(1 − 0.10), the ladder's second step ✓)
  c) dryness   x = (554 − 45.5)/571.6             = 0.890
  d) condenser load = 231 000 × (554 − 45.5)      = 1,17,46,350 kCal/hr
  e) specific coal = 41 758/60 000                = 0.696 kg/kWh
  f) overall efficiency = 860/2951                = 29.1 %
```

### ⭐ The ladder, checked against itself

The same data gives the turbine heat rate directly:

```
    Turbine HR = 231 000 × (793 − 130)/60 000     = 2553 kCal/kWh
    ÷ boiler efficiency 0.865                     = 2951 kCal/kWh
```

**2951 — identical to the gross heat rate computed from coal.** Two independent
routes, one answer. **If you do nothing else today, do this reconciliation**; it is
what makes the ladder yours rather than remembered.

*Sanity: 2951 gross is a bit poor for a modern unit (2300–2600), which fits a 60 MW
captive plant rather than a utility station. The 0.696 kg of coal per kWh at GCV
4240 is the same fact in another dress.*
</details>

---

## B2 · 21st sitting N-4(C) — `papers/21-1.pdf` — 20 marks

> *"A coal-based power plant has two units each of 200 MW…"*

**You stopped at the line `Unit-1 Unit Heat rate =`.** Now finish it. Part 1 (the
boiler efficiency) you already did well — your ash split into fly and bottom at
their own calorific values was better than my own key.

<details><summary>Answer — parts 2, 3, 4</summary>

```
  1) Boiler efficiency (yours, with the ash added to m_dfg)   ≈ 85.8 %

  2) Unit 1 is quoted as a TURBINE heat rate — climb it:
         gross = 2450/0.858                       = 2855 kCal/kWh
     Unit 2 is already a UNIT heat rate           = 2790 kCal/kWh
     ⟹ UNIT 2 IS MORE EFFICIENT (lower heat rate)

  3) At 85 % load, generation = 200 000 × 0.85 × 24 = 40,80,000 kWh/day
         Unit 1 coal = 2855 × 40,80,000/4000/1000  = 2911.7 TPD
         Unit 2 coal = 2790 × 40,80,000/4000/1000  = 2845.8 TPD
         DIFFERENCE                                =   65.9 TPD

  4) Station gross HR = (2855 + 2790)/2            = 2822 kCal/kWh
     Station net HR   = 2822/(1 − 0.10)            = 3136 kCal/kWh
```

*(BEE's key works part 3 at both 75% and 85% load and accepts either — 58.1 TPD at
75%. **Say which load factor you used.**)*

**Interpretation line worth a mark:** Unit 1 burns 66 tonnes a day more for the same
output — about ₹6.3 lakh a day at ₹9500/tonne. That is where the audit
recommendation goes.
</details>

---

## B3 · 22nd sitting N-4(A) — `papers/22-1.pdf` — 20 marks

> *"A thermal power plant is equipped with boiler and reheat steam turbine…"*

**Three fixes from your Mock 3 attempt**, then parts (iv) and (v).

<details><summary>Answer</summary>

```
  i)   h₂s = 813 − (813 − 735)/0.796               = 715 kCal/kg        ✓ you had this

  ii)  ⚠️ LP exhaust is WET. The table's 610 is h_g; apply the dryness:
       h = 49 + 0.98(610 − 49)                     = 599 kCal/kg
       η_LP = (741 − 599)/(741 − 559)              = 78.0 %   (you had 72.0)

  iii) HP = 684 000(813 − 735)/860/1000            = 62.03 MW  ✓
       IP = 635 000(834 − 741)/860/1000            = 68.67 MW  ✓
       LP = 545 000(741 − 599)/860/1000            = 89.99 MW  (you had 83.02)
       turbine total 220.7 MW → generator × 0.98 × 0.97 = 209.8 MW

  iv)  ⚠️ BOTH heat inputs, and the GENERATOR underneath:
       THR = [684(813 − 241) + 635(834 − 735)]/209.8
           = (3,91,248 + 62,865)/209.8             = 2165 kCal/kWh

       Station gross heat rate: **CANNOT BE CALCULATED** — boiler efficiency
       is not given. Write that sentence; BEE's key says the same and awards
       marks for any stated assumption of 85–88 %.
           at 85 %: 2165/0.85                      = 2547
           at 88 %: 2165/0.88                      = 2460

  v)   Net HR = gross/(1 − 0.06)
           from 2547                               = 2710 kCal/kWh
           from 2460                               = 2617 kCal/kWh
```

> **Part (iv) is the most instructive answer in the ten papers.** BEE says a
> quantity cannot be computed from the data given, and rewards the candidate who
> says so and proceeds on a stated assumption. **Naming what is missing is an
> auditor's skill, and it is worth marks.**
</details>

---

## B4 · Choose ONE

### Option A · 17th sitting N-3 — `papers/17.pdf` — 20 marks

> *"In a continuous process industry Steam and Power are supplied through a
> cogeneration plant interconnected with grid…"*

A double-extraction condensing turbine, then a 1200 TR absorption chiller added.
**Three parts: EUF before, net additional annual operating cost, EUF after.**

**This is the question where the ladder does *not* apply** — it is cogeneration, so
the measure is EUF.

<details><summary>Answer — part (i), fully</summary>

```
   Q_thermal = 18 750(697) + 31 250(673) + 18 750(46)
             = 1,30,68,750 + 2,10,31,250 + 8,62,500     = 3,49,62,500 kCal/hr
   P_elec    = 7200 × 860                               = 61,92,000 kCal/hr
   Fuel      = 68 750(745 − 105)/(0.81 × 4000)          = 13 580 kg/hr

   EUF = (3,49,62,500 + 61,92,000)/(13 580 × 4000)      = 75.8 %
```

**Useful pointers for (ii) and (iii):** the VAM needs `1200 × 4.5 = 5400 kg/hr` of
9 bar steam; at a steam rate of 12 kg/kWh that extraction also yields
`5400/12 = 450 kW` of extra power, which displaces grid import at ₹4.25/kWh. The
additional cost is the extra coal for the extra steam, less the grid power saved.

*(Note BEE counts the condensate stream `18 750 × 46` inside "useful thermal". It
is arguable — condensate at 46 kCal/kg is not process heat — but it moves EUF by
under 2 points and the key includes it. **Follow the key and say what you counted.**)*
</details>

### Option B · 20th sitting N-4(C) — `papers/20-1.pdf` — 20 marks

> *"In a particular biomass power plant, 33.6 TPH of steam at 63 kg/cm²g, 450 °C…"*

Five parts at 4 marks each: power at 450 °C, steam rate at 475 °C, additional
power, additional fuel, yearly benefit. **A clean isentropic-efficiency question
with a money answer.**

<details><summary>Answer</summary>

```
  a) 33 600(787.9 − 564.78)/860 × 0.92                  = 8020 kW

  b) at 475 °C the actual outlet comes from η_isen:
     h₂ = 802.4 − 0.79(802.4 − 511.77)                  = 572.8 kCal/kg
     power = 33 600(802.4 − 572.8)/860 × 0.92           = 8253 kW
     steam rate = 33 600/8253                           = 4.07 kg/kWh

  c) additional power = 8253 − 8020                     = 233 kW

  d) extra heat per kg of steam = 802.4 − 787.9 = 14.5 kCal/kg
     extra fuel = 33 600 × 14.5/(0.72 × 3450)           = 196 kg/hr

  e) (233 × 6 − 196 × 3.3) × 8000                       = ₹59.98 lakh/year
```

**Read what happened:** 25 °C more superheat costs 196 kg/hr of biomass and returns
233 kW. The fuel costs ₹647/hr, the power earns ₹1397/hr. **Superheat pays here
because the electricity is worth more than the marginal fuel** — and that is the
whole answer to part (e), in a sentence.
</details>

---

# Before you close the book

- [ ] Can you draw the three boxes and say what each counts?
- [ ] **Can you write the ladder from memory, and say why each step divides?**
- [ ] Turbine < gross < net — can you state it and use it as a check?
- [ ] `860 ÷ which heat rate` gives the plant's efficiency?
- [ ] What two things get dropped from a reheat unit's turbine heat rate?
- [ ] Given a *turbine* heat rate and a *unit* heat rate, what do you do first?
- [ ] Why is heat rate the wrong measure for a back-pressure set, and what replaces it?

**Tomorrow: HVAC, chillers and cooling towers** — `curriculum/revision-plan.md`.
Re-read Rung 163 first; the condenser duty has appeared in three consecutive papers.

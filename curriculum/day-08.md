# Day 8 — Pumps and Pumping Systems

**Time: 3.5 hours. Book-4 Ch 7 (p. 99).**

**Source:** BEE Book 4 Ch 7 —
[4Ch7.pdf](https://beeindia.gov.in/sites/default/files/4Ch7.pdf) (8 pp, free).

Appears in **7 of 8 sittings**. Rungs 73–82.

**Phase 2 begins.** Thermal is behind you. From here the equipment is electrical
and fluid, and your background works for you — expect to move faster.

> **Prerequisite check.** Today's timed question needs the pump chain plus
> three-phase motor input, both taught below. Every sub-part traced. Nothing
> deferred.

---

# Part 1 — What a pump does

## Rung 73 — The job

A pump adds energy to a liquid so it can be moved somewhere it would not go on its
own — up, along a resisting pipe, or into a higher pressure.

That energy shows up in three forms, and Bernoulli says they are interchangeable:

```
    total energy  =  pressure energy  +  potential energy  +  kinetic energy
                          p/ρg              z                   v²/2g
```

Written that way every term has units of **metres**. That is not a coincidence —
it is why pumps are rated in metres of head rather than in pressure.

**Why head, not pressure?** Because a pump is a machine that does a fixed amount
of *work per unit weight* of liquid. Give it water or brine or oil: the same
impeller at the same speed lifts all of them the same **height**. It does not
produce the same **pressure**, because pressure depends on density:

```
    p = ρ · g · H
```

A pump rated 50 m gives 4.9 bar on water (ρ = 1000) but 6.1 bar on brine
(ρ = 1250). **Head is the pump's property; pressure is the fluid's response.**

---

## Rung 74 — Total head, and why it is a difference

The head a pump must deliver is the *difference* between what the system needs at
discharge and what it already has at suction:

```
    H = discharge head − suction head
```

Both measured at the pump flanges, both in metres of the liquid being pumped.

A suction head can be **negative** (a suction *lift*, where the pump draws from
below itself), and then the difference gets larger — subtracting a negative adds.
That is the sign trap in this chapter.

**Drill 48.** Discharge head 55 m, suction head 1 m. Then: discharge 55 m, suction
lift 3 m.

<details><summary>Answer</summary>

```
    Case 1: H = 55 − 1     = 54 m
    Case 2: H = 55 − (−3)  = 58 m
```

A pump lifting from below works harder, as it must.
</details>

---

## Rung 75 — Deriving hydraulic power

**Power is energy per unit time.** So:

```
    Power = (energy per unit weight) × (weight flow per unit time)
          = H × (ṁ · g)
          = H × (Q · ρ · g)
```

With Q in m³/s, ρ in kg/m³, g in m/s², H in m, that gives **watts**:

```
    P_hydraulic (W) = ρ · g · Q · H

    P_hydraulic (kW) = ρ · g · Q · H / 1000
```

This is the **useful** output — the power actually delivered to the liquid.

**The practical form.** Plants quote flow in m³/hr, so convert once:

```
                        Q (m³/hr) × H (m) × ρ (kg/l)
    P_hydraulic (kW) = ────────────────────────────────
                                  367
```

Where does 367 come from? Q/3600 to get m³/s, times 1000 for ρ, times 9.81, over
1000 for kW:

```
    3600 × 1000 / (9.81 × 1000) = 367
```

**So 367 is not a constant to memorise — it is 3600/9.81.** If you forget it,
work in SI and convert at the end.

**Drill 49.** 1700 m³/hr against 54 m of water.

<details><summary>Answer</summary>

```
    SI:        Q = 1700/3600 = 0.4722 m³/s
               P = 1000 × 9.81 × 0.4722 × 54 / 1000 = 250.2 kW

    Shortcut:  P = 1700 × 54 × 1.0 / 367 = 250.1 kW      ✓ same
```

*Anchor:* plant pumps are tens to a few hundred kW. Thousands means a slipped
factor.
</details>

---

## Rung 76 — The efficiency chain

Electricity goes in at the motor terminals; useful work comes out in the liquid.
Two machines sit between, each losing a little:

```
   electrical input ──► [MOTOR] ──► shaft power ──► [PUMP] ──► hydraulic power
                          η_motor                     η_pump
```

Each efficiency is **output ÷ input**, so working backwards you **divide**:

```
    shaft power      = hydraulic power / η_pump
    electrical input = shaft power / η_motor
                     = hydraulic power / (η_pump × η_motor)
```

> **Never multiply.** This is the reciprocal family from
> `reference/reciprocal-traps.md`, and it has already cost marks twice — on the
> steam cost in Day 1 and on the 25th sitting's pump. Input is always **larger**
> than output. If your answer is smaller, you inverted it.

Two efficiencies are quoted, and questions ask for either:

```
    Pump (hydraulic) efficiency = hydraulic power / shaft power
    Overall pump-set efficiency = hydraulic power / electrical input
```

Typical values: pump 65–85%, motor 88–95%, so overall 60–78%.

---

## Rung 77 — Measuring the electrical input

The motor input is measured, not assumed. For a three-phase motor:

```
    P (kW) = √3 × V × I × cos φ / 1000
```

`√3` because the three phases are 120° apart — the line quantities relate to phase
quantities by √3. `cos φ` is the power factor: only the component of current in
phase with the voltage does work.

If motor **losses** are given instead of motor efficiency:

```
    shaft power = electrical input − motor losses
```

**Drill 50.** V = 440, I = 480 A, power factor 0.89, motor losses 19.5 kW.

<details><summary>Answer</summary>

```
    Electrical input = 1.732 × 440 × 480 × 0.89 / 1000 = 325.6 kW
    Shaft power      = 325.6 − 19.5                    = 306.1 kW
```
</details>

---

# Part 2 — How a pumping system behaves

## Rung 78 — Two curves, one operating point

**The pump curve** is what the pump can do: head it can generate against flow.
Centrifugal pumps produce **less head as flow rises** — the curve slopes down.

**The system curve** is what the system demands: head needed to push a given flow.
It has two parts:

```
    H_system = static head + friction head
             = z          + k·Q²
```

- **Static head** — the actual lift, plus any pressure difference. Independent of
  flow; it is there even at zero flow.
- **Friction head** — resistance in pipes, valves, fittings. Grows as **Q²**,
  because friction loss goes with velocity squared.

The system curve therefore starts at the static head and **curves upward**.

**The pump runs where the two curves cross.** Nowhere else. That intersection is
the **operating point**, and it is the single most useful idea in this chapter:

> A pump does not "deliver its rated flow". It delivers whatever flow makes its
> head equal the system's demand. Change either curve and the operating point
> moves.

A pump running far from its **best efficiency point (BEP)** wastes energy even if
it is a good pump — which is why oversizing is the commonest fault an auditor
finds.

---

## Rung 79 — Deriving the affinity laws

Change the impeller speed from N₁ to N₂. What happens?

**Flow.** A centrifugal pump is a volumetric machine — each revolution sweeps a
fixed volume. Twice the speed, twice the sweeps:

```
    Q ∝ N
```

**Head.** Head comes from the velocity the impeller imparts, and kinetic energy
goes as v². Tip speed is proportional to N, so:

```
    H ∝ N²
```

**Power.** Power is the product of the two:

```
    P ∝ Q × H ∝ N × N² = N³
```

```
    Q₂/Q₁ = (N₂/N₁)          H₂/H₁ = (N₂/N₁)²          P₂/P₁ = (N₂/N₁)³
```

**The cube is where all the savings are.** Reduce speed 20% and power falls to
0.8³ = **51%**. That single relationship justifies most variable-speed drive
projects in industry.

The same laws hold for impeller **diameter** trimming, and for fans (Day 9) —
identical physics.

---

## Rung 80 — Throttling versus variable speed

A plant needs less flow. Two ways:

**Throttle a valve.** You add artificial resistance, steepening the system curve.
The operating point slides *up and left* along the pump curve — less flow, but at
**higher head**. The pump is now working against a restriction you deliberately
created, and burning energy to do it.

**Slow the pump.** The pump curve itself moves down. The operating point slides
down the *unchanged* system curve — less flow at **lower head**.

Cut flow by 30%:

| Method | Flow | Head | Power |
|---|---|---|---|
| Throttling | 0.70 | rises | ~0.80 |
| **VSD** | 0.70 | falls | **0.34** |

**A throttle valve is a heater.** The pressure it destroys becomes heat in the
liquid. Every kW of throttling loss is a kW you paid for and threw away.

> **Caveat worth knowing, and worth stating in an exam.** The cube law applies to
> the *friction* part of the system curve. Where **static head is large**, the pump
> must still generate that head at any flow, so speed cannot be reduced as far and
> the savings are smaller. VSDs pay best on **friction-dominated** systems —
> circulation loops, cooling water — and worst on high-lift systems.

---

## Rung 81 — Common findings, and what causes them

| Finding | Cause | Fix |
|---|---|---|
| Throttle valve part-closed | Pump oversized for the duty | Trim impeller, VSD, or smaller pump |
| Pump running far from BEP | Wrong selection, or duty changed | Re-select or trim |
| Low measured efficiency | Wear, internal recirculation, damaged impeller | Overhaul |
| Bypass line open | Poor control practice | Close it, control by speed |
| Two pumps in parallel at low flow | Both far from BEP | Run one |
| Excessive suction losses / cavitation | Blocked strainer, insufficient NPSH | Clear, or re-pipe |

**Oversizing is the root cause of most of them.** Designers add margin on margin —
a safety factor on the flow, another on the head — and the pump arrives too big.
The plant then throttles it for twenty years.

---

## Rung 82 — What an auditor does at a pump

1. **Measure flow** — ultrasonic meter, or from the tank filling rate.
2. **Measure suction and discharge pressures** at the flanges, convert to head.
3. **Measure electrical input** — √3·V·I·cos φ, or a power meter.
4. **Compute all three efficiencies** and compare with the pump curve.
5. **Check the throttle valve position.** A part-closed control valve is a
   measurable, immediate saving.
6. **Plot the operating point** on the pump curve against BEP.
7. **Check whether static or friction dominates** — this decides whether a VSD
   will pay.

**Recommendations, in order of value:** stop throttling (VSD or impeller trim),
correct the pump size, eliminate bypasses, fix worn internals, reduce system
resistance.

---

# Practice

## Timed — 24th sitting, Set B, L-2 (25 min)

`papers/24-2.pdf`, question L-2 — a pump with rated and running conditions,
motor electrical measurements and motor losses. Two parts: hydraulic (pump)
efficiency and overall pump-set efficiency. **5 marks, 8 minutes.**

**Prerequisite check:** Rungs 74–77 cover every part.

<details><summary>Check yourself after attempting</summary>

```
    Q = 1700 m³/hr = 0.4722 m³/s
    H = 55 − 1 = 54 m
    Hydraulic = 1000 × 9.81 × 0.4722 × 54/1000 = 250 kW   (model: 249, using 0.47)

    Motor input  = 1.732 × 440 × 480 × 0.89/1000 = 325.5 kW
    Shaft power  = 325.5 − 19.5 = 306 kW

    (a) Pump efficiency    = 249/306   × 100 = 81.4 %
    (b) Overall efficiency = 249/325.5 × 100 = 76.5 %
```

Note the rated flow of 2124 m³/hr and rated head of 70 m are **not used** — the
pump is running well below its rating, which is itself the finding.
</details>

## Then — 17th sitting L-2 (20 min)

`papers/17.pdf` — a pumping system energy audit. Attempt it cold.

## Log (20 min)

**Record start and finish times for both.** This is the third request; pace under
exam conditions is still unmeasured and is now the largest unknown in the plan.

Log what the checking pass caught — "caught nothing" is information.

---

## Day 8 checklist

**Understanding**
- [ ] Can explain why pumps are rated in head, not pressure
- [ ] Know total head is a difference, and how a suction lift changes the sign
- [ ] Can explain the system curve's two parts and why friction goes as Q²
- [ ] Can explain the operating point and why a pump never simply "delivers rated flow"

**Derivation**
- [ ] Can derive hydraulic power from energy per unit weight
- [ ] Can reconstruct the 367 constant from 3600/9.81
- [ ] **Can derive all three affinity laws** from Q ∝ N and v² for head

**Calculation**
- [ ] Can compute hydraulic power in both SI and the practical form
- [ ] Can compute three-phase motor input and handle motor losses
- [ ] Can distinguish pump efficiency from overall efficiency
- [ ] **Divides by efficiency going backwards, never multiplies**

**Judgement**
- [ ] Can explain why throttling wastes and VSD saves, using the curves
- [ ] Knows the static-head caveat on VSD savings
- [ ] Can list audit measurements and rank recommendations

**Next (Day 9):** fans, blowers and compressed air — the same physics as pumps,
applied to gases, plus the biggest single utility waste in most plants.

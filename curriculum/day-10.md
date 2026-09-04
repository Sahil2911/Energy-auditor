# Day 10 — Motors, Variable Speed Drives and Cooling Towers

**Time: 4 hours. Book-4 Ch 5 (p. 73).**

**Source:** [4Ch5.pdf](https://beeindia.gov.in/sites/default/files/4Ch5.pdf) (free).

**Motors appear in 8 of 8 sittings** — the joint most-examined topic in the paper,
alongside boilers. Cooling towers appear in 5 of 8.

Rungs 95–108. This is your home ground.

> **Prerequisite check.** Today's timed question needs cooling tower theory
> (below), pump power (Day 8) and fan power (Day 9). Every sub-part traced.

---

# Part 1 — Motors

## Rung 95 — Why an induction motor must slip

Stator windings carrying three-phase current produce a magnetic field that rotates
at **synchronous speed**:

```
    N_s = 120 f / P          f = frequency (Hz), P = number of poles
```

At 50 Hz: 2 poles → 3000 rpm, 4 poles → 1500 rpm, 6 poles → 1000 rpm.

The rotor has no electrical connection. Current is *induced* in it by the rotating
field — and induction requires **relative motion**. If the rotor ever reached
synchronous speed, the field would appear stationary to it, no EMF would be
induced, no rotor current would flow, and no torque would be produced.

**So the rotor must always run slower than the field. That difference is slip:**

```
    Slip = N_s − N_actual              % slip = (N_s − N) / N_s × 100
```

Typical full-load slip is 2–5%. A 1500 rpm synchronous motor runs at about 1440–1470.

**And slip is proportional to load.** More torque needed → more rotor current
needed → more relative motion needed. An unloaded motor runs very close to
synchronous; a fully loaded one slips its full nameplate amount.

That relationship is what makes the slip method (Rung 97) work.

---

## Rung 96 — Losses, and why efficiency collapses at low load

| Loss | Depends on | Behaviour with load |
|---|---|---|
| Stator copper (I²R) | current² | **rises with load²** |
| Rotor copper | current² | rises with load² |
| Core (iron) | voltage, frequency | **constant** |
| Friction and windage | speed | **constant** |
| Stray | load | rises |

Two families: **load-dependent** (copper) and **fixed** (core, friction).

Now the consequence. Fixed losses do not shrink when the motor is lightly loaded —
a 100 kW motor delivering 20 kW still has its full core and windage losses, but now
they are spread over a fifth of the output.

```
    Typical efficiency:
      100% load  →  93 %
       75% load  →  93 %      ← flat: this is the design region
       50% load  →  91 %
       25% load  →  83 %
       10% load  →  65 %
```

**Efficiency is flat from about 50% to 100% load, then falls off a cliff.**

> **This is why oversizing wastes.** A motor at 30% load is not "using less
> electricity because it is doing less" — it is doing less *and* doing it badly.
> Power factor collapses too, typically from 0.85 at full load to 0.5 or lower,
> loading the supply with reactive current for no output.

---

## Rung 97 — Three ways to find the loading

You cannot read loading off a nameplate. Three methods, in descending accuracy:

**1. Input power method** — the best, needs a power meter:

```
    % Load = measured input kW / (rated kW / η_rated) × 100
```

The denominator is the input the motor *would* draw at full load.

**2. Current method** — needs only a clamp meter:

```
    % Load = measured current / rated current × 100
```

**Valid only up to about 75% loading.** Below that it overstates, because
magnetising current keeps flowing whatever the load — a motor at zero output still
draws 30–40% of rated current.

**3. Slip method** — needs only a tachometer:

```
    % Load = (N_s − N_measured) / (N_s − N_rated) × 100
```

Straight from Rung 95: slip is proportional to load, so the ratio of actual slip to
full-load slip is the loading.

**Drill 57.** A 7.5 kW motor, 4-pole, 50 Hz. Nameplate full-load speed 1450 rpm.
Measured speed 1480 rpm. Find the loading and the actual output.

<details><summary>Answer</summary>

```
    N_s = 120 × 50 / 4 = 1500 rpm
    % Load = (1500 − 1480) / (1500 − 1450) × 100 = 20/50 × 100 = 40 %
    Output = 0.40 × 7.5 = 3.0 kW
```

*Sanity:* measured speed is nearer synchronous than nameplate, so the motor must be
lightly loaded. 40% fits. ✓ And 40% is in the region where efficiency is beginning
to fall — worth flagging in an audit.
</details>

---

## Rung 98 — Rewinding

When a motor burns out, plants rewind rather than replace. Each rewind typically
costs **1–2 percentage points of efficiency**, because:

- Old windings are burnt out with heat, which can damage the core's inter-laminar
  insulation and raise iron losses
- Rewinders often substitute thinner wire or fewer turns, raising copper losses
- Slot fill and winding geometry rarely match the original

Two or three rewinds and a 93% motor is running at 88–89%. For a motor running
continuously, that is worth more per year than the rewind cost.

**Standard recommendation:** replace rather than rewind for small motors and
continuously-running motors; if rewinding, insist on controlled-temperature burnout
and specify the original wire gauge.

---

## Rung 99 — How a VSD actually works

An induction motor's speed is set by the supply **frequency** (Rung 95). Change
the frequency and you change the speed.

A variable frequency drive does it in three stages:

```
    AC in ──► [RECTIFIER] ──► DC link ──► [INVERTER] ──► variable-frequency AC out
```

The inverter synthesises an AC waveform of any frequency by switching the DC on and
off rapidly (PWM).

**The critical constraint — constant V/f.** Motor flux is proportional to V/f. Drop
the frequency without dropping the voltage and the flux rises, saturating the iron
and overheating the motor. So a VFD reduces **voltage in proportion to frequency**,
holding V/f constant and keeping flux — and therefore available torque — constant.

That is why a VFD produces **constant torque** down to low speed, which is exactly
what centrifugal loads do *not* need — and why the savings are so large.

---

## Rung 100 — When a VSD pays, and when it does not

From Day 8 Rung 79: for centrifugal loads, `P ∝ N³`.

| Speed | Flow | Power |
|---|---|---|
| 100% | 100% | 100% |
| 90% | 90% | **73%** |
| 80% | 80% | **51%** |
| 70% | 70% | **34%** |

**Pays best on:**
- Centrifugal pumps, fans and blowers — the cube law
- Loads that spend most of their time at part flow
- Systems currently controlled by throttling or damping
- **Friction-dominated** systems (Day 8 Rung 80)

**Pays poorly or not at all on:**
- Constant-torque loads — conveyors, positive-displacement compressors, crushers.
  Power there goes as N, not N³, so halving speed halves power at best.
- High **static head** systems, where the pump must generate the lift regardless
- Motors already running near full load most of the time
- Very small motors, where the drive's own 2–4% loss eats the saving

> A VSD is not a universal energy measure. Applied to a constant-torque load
> running at full duty, it *increases* consumption by its own losses. This is a
> favourite True/False.

---

# Part 2 — Cooling towers

## Rung 101 — Cooling by evaporation

A cooling tower rejects heat from circulating water to the atmosphere. It does it
mostly by **evaporation**, not by contact.

Water is broken into droplets over fill material while air is drawn through. A
small fraction evaporates — and evaporation is expensive in energy. Each kilogram
that leaves as vapour carries away about **580 kCal** of latent heat, taken from
the water left behind, which therefore cools.

**The consequence that surprises people: a cooling tower can cool water below the
air temperature.** It is not limited by the dry bulb, because it is not simply
transferring heat to the air.

---

## Rung 102 — Wet bulb temperature is the floor

Wrap a thermometer bulb in a wet wick and blow air over it. Water evaporates,
cooling the bulb, until evaporation and heat gain balance. That equilibrium is the
**wet bulb temperature**, and it is the lowest temperature evaporative cooling can
reach.

- **Dry bulb** — ordinary air temperature
- **Wet bulb** — what evaporative cooling can theoretically achieve
- The gap between them measures how dry the air is. Saturated air: WBT = DBT, and no
  evaporation is possible at all.

> **A cooling tower's performance is set by the weather.** A tower that reaches
> 30 °C on a 25 °C wet-bulb day is performing identically to one reaching 33 °C on
> a 28 °C wet-bulb day. **Always judge a tower against the wet bulb, never against
> an absolute outlet temperature.**

---

## Rung 103 — Range, approach, effectiveness

Three definitions, and everything follows from them:

```
    Range       = T_hot water in  −  T_cold water out
    Approach    = T_cold water out −  T_wet bulb
    Effectiveness = Range / (Range + Approach) × 100
```

- **Range** is set by the *process* — how much heat the plant dumped into the
  water. It is not a tower performance measure at all.
- **Approach** is set by the *tower*. It is the real performance indicator. A good
  tower achieves 3–5 °C; a poor or fouled one 8–10 °C.
- **Effectiveness** combines them: what fraction of the theoretically available
  cooling was actually achieved. Note `Range + Approach` is just
  `T_hot in − T_wet bulb` — the total available driving force.

**Drill 58.** Water in at 35 °C, out at 30 °C, wet bulb 25 °C.

<details><summary>Answer</summary>

```
    Range         = 35 − 30 = 5 °C
    Approach      = 30 − 25 = 5 °C
    Effectiveness = 5/(5+5) × 100 = 50 %
```

An approach of 5 °C is acceptable; 50% effectiveness has room to improve.
</details>

---

## Rung 104 — Deriving the evaporation loss

How much water evaporates? Start from the heat removed.

Cooling `m` kg/hr of water through a range of ΔT removes `m × 1 × ΔT` kCal/hr. If
**all** of it were evaporative, at 580 kCal/kg:

```
    Evaporation = m × ΔT / 580 = 0.001724 × m × ΔT
```

The standard formula is:

```
    Evaporation loss (m³/hr) = 0.00085 × 1.8 × circulation rate (m³/hr) × Range (°C)
                             = 0.00153 × m × ΔT
```

The **1.8** converts the range from °C to °F — the constant 0.00085 is per degree
Fahrenheit.

Compare the two: 0.00153 / 0.001724 = **0.89**. So the formula says about **89% of
the cooling is evaporative**, with the remaining 11% being sensible heat picked up
by the air. That is the physical content of an otherwise arbitrary-looking
constant.

**Rule of thumb worth carrying:** about **1% of the circulating water evaporates per
5.5 °C of range.**

---

## Rung 105 — Cycles of concentration, blowdown and makeup

Evaporation removes **pure water** and leaves the dissolved solids behind. So the
circulating water steadily concentrates. Left alone it would scale the tower and
the heat exchangers.

So some water is deliberately discharged — **blowdown** — and replaced with fresh
**makeup**.

**Cycles of Concentration** is how many times the salts have concentrated:

```
    COC = concentration in circulating water / concentration in makeup water
```

Now derive the relationships from two balances.

**Salt balance** — salts enter in makeup, leave in blowdown:

```
    M × c_makeup = B × c_circulating        ⟹    M = B × COC
```

**Water balance** — makeup replaces what evaporates and what is blown down:

```
    M = E + B
```

Substituting:

```
    B × COC = E + B      ⟹      B (COC − 1) = E

              E                          COC
    B  =  ─────────           M  =  E × ───────
            COC − 1                     COC − 1
```

**Why raising COC saves water:**

| COC | Blowdown | Makeup |
|---|---|---|
| 3.5 | 0.400 E | 1.400 E |
| 5.0 | **0.250 E** | **1.250 E** |
| 8.0 | 0.143 E | 1.143 E |

Going from 3.5 to 5 cycles cuts blowdown by **38%** and total makeup by 11%. The
limit is set by water chemistry — push COC too high and you scale.

**Drift** (windage) is water carried out as droplets. Modern drift eliminators keep
it to 0.02% or less, and questions often say "ignore drift".

---

## Rung 106 — What an auditor checks at a cooling tower

1. **Measure wet bulb**, hot and cold water temperatures. Compute range, approach,
   effectiveness.
2. **Compare approach to design** at the same wet bulb. A widening approach means
   fouled fill, poor distribution or reduced airflow.
3. **Check the fan** — power, blade pitch, whether it could be slowed at night or
   in winter.
4. **Check COC** and whether water treatment allows raising it.
5. **Check distribution** — blocked nozzles leave dry patches on the fill and
   destroy performance.
6. **Check for short-circuiting** of air, and for recirculation of the tower's own
   humid exhaust back into its inlet.

**Common recommendations:** clean or replace fill, fix nozzles, raise COC with
better treatment, fit a VSD or two-speed fan (the cube law applies — Rung 100),
and optimise the number of cells running.

---

# Practice

## Timed — 17th sitting N-1 (35 min)

`papers/17.pdf` — a 3000 Million kCal/hr cooling tower before and after
refurbishment. Effectiveness rises 60% → 70%, COC rises 3.5 → 5. Find:

1. Reduction in pump and fan power
2. Reduction in makeup water in kL/day

**Prerequisite check:** effectiveness and COC → Rungs 103–105 · pump power →
Day 8 Rung 75 · fan power → Day 9 Rung 84. **All parts covered.**

Approach: use effectiveness to get the new cold water temperature, then the new
range, then evaporation, then makeup at each COC.

## Then — 24th sitting Set B, L-2 (15 min)

`papers/24-2.pdf` — the pump efficiency question still outstanding from Day 8. It
also exercises Rung 97's input-power method.

## Log

Record start and finish times. Your three data points so far are all at or inside
budget — keep the run going.

---

## Day 10 checklist

**Motors**
- [ ] Can explain why an induction motor must slip
- [ ] Can compute synchronous speed from poles and frequency
- [ ] Know which losses are fixed and which vary with load
- [ ] Can explain why efficiency and power factor collapse below ~50% load
- [ ] Can use all three loading methods, and know the current method's 75% limit
- [ ] Know what rewinding costs and what to specify
- [ ] Can explain V/f control and why it must be constant
- [ ] Can say when a VSD pays and when it makes things worse

**Cooling towers**
- [ ] Can explain evaporative cooling and why it beats the dry bulb
- [ ] Know the wet bulb is the floor, and judge towers against it
- [ ] Can compute range, approach and effectiveness, and know which measures the tower
- [ ] **Can derive the evaporation loss** and explain the 89%
- [ ] **Can derive B = E/(COC−1) and M = E·COC/(COC−1)** from the two balances
- [ ] Can explain why raising COC saves water and what limits it
- [ ] Can list audit checks and recommendations

**Next (Day 11):** HVAC, chillers and refrigeration — 7 of 8 sittings, and where
the COP ↔ kW/TR reciprocal trap is waiting.

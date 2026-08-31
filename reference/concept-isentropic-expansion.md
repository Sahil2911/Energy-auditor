# Isentropic Expansion — What Is Actually Happening

The formula is easy to memorise and easy to misapply, because it contains a fact
that feels backwards:

```
    h₂ = h₁ − η_isentropic × (h₁ − h₂s)
```

**A less efficient turbine produces exhaust steam with MORE energy in it.**

That sounds wrong. Losses should mean less, not more. Until that resolves, the
formula stays a rule you obey rather than a thing you know.

---

## 1. Start with the puzzle

Two turbines, identical steam in at 3420 kJ/kg, same exhaust pressure.

| | Ideal turbine | Real turbine (90%) |
|---|---|---|
| Steam in | 3420 kJ/kg | 3420 kJ/kg |
| Work extracted | 990 kJ/kg | 891 kJ/kg |
| **Steam out** | **2430 kJ/kg** | **2529 kJ/kg** |

The worse turbine's exhaust carries **99 kJ/kg more energy**. Where did that
extra energy come from — and why is having more of it a bad thing?

---

## 2. A turbine is a sealed, insulated box

This is the fact everything else hangs on.

Steam enters, shaft work leaves, steam exits. That is all. The casing is lagged,
and steam passes through in milliseconds — far too fast to lose meaningful heat
to the surroundings. Thermodynamically the turbine is **adiabatic**: no heat
crosses the boundary.

So energy in must equal energy out:

```
    h₁  =  h₂  +  work
```

**Every joule that fails to leave as shaft work must leave inside the steam.**
There is nowhere else for it to go.

---

## 3. Now the friction

A real turbine has losses — steam scraping over blades, turbulence in the
passages, leakage around tip clearances, swirl at the exit.

Every one of those is friction, and friction makes **heat**.

In a car brake, that heat escapes to the air. In a turbine it cannot: the box is
sealed and insulated. The friction heat is generated *in the steam* and stays
*in the steam*.

So the 99 kJ/kg is not mysterious extra energy. It is **work that was very nearly
extracted and then rubbed back into the steam as heat before it could reach the
shaft.**

> The exhaust enthalpy is higher precisely *because* the turbine was worse. The
> lost work did not vanish — it was downgraded from work into heat, and the heat
> went home with the steam.

That is the whole idea. The rest is bookkeeping.

---

## 4. What entropy has to do with it

You do not need statistical mechanics. One practical statement is enough:

> **Entropy measures how much of a system's energy is unavailable for work.**

Energy is conserved; its *usefulness* is not. Turning work into heat is a
one-way trip — you can always convert work fully into heat, but never heat fully
back into work. That one-wayness is what entropy counts.

- **A frictionless expansion** wastes nothing. No work is degraded into heat, so
  nothing becomes unavailable. **Entropy stays constant** — *iso-entropic*,
  isentropic.
- **A real expansion** degrades some work into heat. Usefulness is destroyed.
  **Entropy increases.**

So "isentropic" is not a special exotic process. It is simply **the perfect
expansion** — the frictionless limit — used as a yardstick.

Two things follow immediately, and they are worth stating because they are what
the exam actually tests:

1. **η_isentropic can never exceed 100%.** You cannot extract more work than a
   frictionless machine. If you compute 105%, you have inverted something.
2. **h₂ must always lie between h₂s and h₁.** Friction can only add enthalpy
   back, never remove more than the ideal expansion did.

---

## 5. The picture — a Mollier (h–s) chart

Enthalpy up the side, entropy along the bottom. Both expansions start at the
same point and end at the same *pressure*, but not the same state:

```
   h
   │
 3420├──● 1  (180 bar, 550 °C)
   │  │╲
   │  │ ╲
   │  │  ╲          ideal: straight DOWN
   │  │   ╲         (entropy unchanged)
   │  │    ╲
   │  │     ╲   real: down AND RIGHT
 2529├──────┼──● 2  ← actual exhaust   (entropy increased)
   │  │     │
 2430├──────●──┼──   2s  ideal exhaust
   │       ╲ ╲│
   │        ╲ ╲     ← both on the 2 bar line
   └────────────────────────────► s
            s₁    s₂
```

- **Ideal expansion — a vertical line.** Entropy is unchanged, so the point drops
  straight down. Maximum possible enthalpy drop, maximum work.
- **Real expansion — slants down and to the right.** Entropy increases, so the
  endpoint shifts right, and being on the same pressure line it also sits
  *higher*. Smaller drop, less work.

**Isentropic efficiency is the ratio of those two vertical drops:**

```
    η = actual drop / ideal drop = 891 / 990 = 90 %
```

The formula now reads as a sentence rather than a rule: *take the ideal drop,
keep only 90% of it, subtract from where you started.*

---

## 6. The physical consequence, in real numbers

The exhaust is at 2 bar. From steam tables at 2 bar:

```
    hf = 504.7    hfg = 2201.9    hg = 2706.6   kJ/kg
```

Both exhaust enthalpies are below hg = 2706.6, so **the steam is wet** — a
mixture of vapour and droplets. Dryness fraction `x = (h − hf) / hfg`:

| | Enthalpy | Dryness |
|---|---|---|
| Ideal exhaust (2s) | 2430 | **87.4% dry** |
| Actual exhaust (2) | 2529 | **91.9% dry** |

**The real turbine's exhaust is drier than the ideal one's.** The friction heat
boiled off some of the droplets that would otherwise have condensed.

Which reveals a genuine engineering irony: a *less efficient* turbine is
sometimes *kinder to its own blades*, because wet steam erodes the last stages.
Turbine designers watch exit dryness for exactly this reason.

> **A detail worth noticing.** The question gives feedwater enthalpy as
> 504.7 kJ/kg — exactly `hf` at 2 bar. That is not a coincidence. It tells you the
> process condensate returns as saturated liquid at the back-pressure. Data in
> these papers is usually physically consistent, and spotting that is a way to
> check you have understood the plant.

---

## 7. If you prefer an electrical analogy

A battery with internal resistance `r`:

```
    terminal voltage = EMF − I·r
```

The `I·r` is not lost from the universe — it is dissipated as heat **inside the
battery**. The battery gets warm, and you get less voltage at the terminals.

A turbine behaves the same way. The friction is its internal resistance, the
shaft work is the terminal voltage, and the heat stays inside the working fluid.
Isentropic efficiency is the analogue of `terminal voltage / EMF`.

---

## 8. Check yourself

1. A turbine's isentropic efficiency falls from 90% to 80%. Does the exhaust
   enthalpy rise or fall?
2. Someone reports 105% isentropic efficiency. What went wrong?
3. Why is a turbine treated as adiabatic when its casing is obviously warm?
4. Steam in 3200 kJ/kg, isentropic exhaust 2300, η 85%. Actual exhaust?
5. Does the real exhaust in (4) sit above or below the isentropic one, and why?

<details><summary>Answers</summary>

1. **Rises.** Less work extracted, so more energy stays in the steam.
   h₂ = 3420 − 0.80(990) = 2628 kJ/kg, up from 2529.
2. They inverted the ratio — probably ideal drop ÷ actual drop. No real machine
   beats the frictionless limit.
3. The casing loses a trickle of heat, but it is negligible beside the megawatts
   flowing through, and the steam's residence time is milliseconds. Adiabatic is
   an excellent approximation, not a claim of perfect insulation.
4. ideal drop = 900; actual = 0.85 × 900 = 765; h₂ = 3200 − 765 = **2435 kJ/kg**
5. **Above** — 2435 > 2300. Friction returns 135 kJ/kg to the steam as heat.
</details>

---

## The one-sentence version

**A turbine is a sealed box, so any work it fails to extract comes back as heat
in the steam — which is why a worse turbine sends out hotter, drier, higher-enthalpy
exhaust, and why the ideal you measure against is the frictionless, constant-entropy
expansion.**

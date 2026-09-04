# Day 9 — Fans, Blowers and Compressed Air

**Time: 4 hours. Book-4 Ch 6 (p. 87) and Ch 8 (p. 107).**

**Sources:** [4Ch6.pdf](https://beeindia.gov.in/sites/default/files/4Ch6.pdf) ·
[4Ch8.pdf](https://beeindia.gov.in/sites/default/files/4Ch8.pdf) — both free.

Rungs 83–94. Fans appear in 4 of 8 sittings, compressed air in 1 of 8 — but
compressed air questions are large when they come, and the 23rd sitting's is a
full 20-marker.

> **Prerequisite check.** Today's timed question has five sub-parts, every one
> traced to a rung below. Part E needs simple payback, taught in Rung 94.

---

# Part 1 — Fans and blowers

## Rung 83 — A fan is a pump for gas

Everything from Day 8 carries over. A fan adds energy to a fluid so it moves
against resistance. Same curves, same operating point, same affinity laws.

Three differences, and only three:

**1. The fluid is compressible — but barely.** Fans raise pressure so little
(under about 1.2:1) that air density is treated as constant. **Below that ratio you
have a fan; above it you have a compressor**, and compressors need different
physics because compression heats the gas. That is Part 2.

| Machine | Pressure rise | Density treated as |
|---|---|---|
| Fan | up to ~1.1:1 (few hundred mmWC) | constant |
| Blower | 1.1 – 1.2:1 | constant |
| Compressor | above 1.2:1 | variable — heats up |

**2. Pressure is measured in mmWC**, not metres of fluid. A column of air has
negligible weight, so head in metres of air would be a useless number. Instead
the pressure is read against a water column: **1 mmWC = 9.81 Pa**.

**3. Three pressures, not one.**

```
    total pressure = static pressure + velocity pressure
```

- **Static** — the pressure pushing outward on the duct walls
- **Velocity (dynamic)** — the pressure equivalent of the air's motion, ½ρv²
- **Total** — their sum, the full energy the fan added

Which one a question means matters. **Static fan efficiency** uses static
pressure; **total fan efficiency** uses total. Read the wording.

---

## Rung 84 — Fan power, and the constant you already know

From Day 8, power is pressure × volumetric flow:

```
    P (W) = Δp (Pa) × Q (m³/s)
```

Convert mmWC to Pa by multiplying by 9.81, and W to kW by dividing by 1000:

```
                  Q (m³/s) × Δp (mmWC) × 9.81        Q (m³/s) × Δp (mmWC)
    P (kW)  =  ─────────────────────────────  =  ────────────────────────
                            1000                            102
```

**102 is 1000/9.81.**

Now look back at Day 8's pump constant. **367 is 3600/9.81.** They are the same
constant — the only difference is whether Q is in m³/s or m³/hr:

| Q in | Divide by | Which is |
|---|---|---|
| m³/s | **102** | 1000/9.81 |
| m³/hr | **367** | 3600/9.81 |

Neither needs memorising. Both are "convert to Pa, convert to kW."

**Fan efficiency:**

```
                        Q (m³/s) × Δp (mmWC)
    η_fan  =  ────────────────────────────────────  × 100
                   102 × shaft power (kW)
```

**Drill 51.** A double-inlet fan handles 166.6 m³/s per inlet against 491 mmWC
static. Shaft power 2127 kW. Static fan efficiency?

<details><summary>Answer</summary>

```
    Total volume = 166.6 × 2 = 333.2 m³/s   (double inlet — both sides count)
    η = 333.2 × 491 / (102 × 2127) × 100 = 75 %
```

*Anchor:* good fans run 70–85%. Below 60%, look for a system problem, not a fan
problem.
</details>

---

## Rung 85 — Measuring flow in a duct

You cannot put a flow meter in a large duct. So velocity is traversed with a
**pitot tube**, which reads velocity pressure directly:

```
    v = √(2 · Δp_velocity / ρ)          →  in practical units:  v = 4.04 √(Δp_mmWC)
```

The 4.04 is √(2 × 9.81/1.2) for air at standard density — Bernoulli, rearranged.

Velocity varies across the duct — fast in the middle, near zero at the walls — so
you traverse several points on two perpendicular diameters and **average the
velocities** (not the pressures; averaging square roots is not the square root of
the average).

```
    Q = v_average × duct area
```

---

## Rung 86 — Fan laws, and why they are the same as the pump laws

Identical derivation to Day 8 Rung 79, because the physics is identical:

```
    Q ∝ N          Δp ∝ N²          P ∝ N³
```

And the same conclusion: **throttling a damper wastes; slowing the fan saves.**

Fans have one option pumps do not — **inlet guide vanes**, which pre-swirl the air
and are better than a damper but still worse than a VSD.

| Method at 70% flow | Relative power |
|---|---|
| Outlet damper | ~0.85 |
| Inlet guide vanes | ~0.65 |
| **VSD** | **0.34** |

---

## Rung 87 — What an auditor checks on a fan

1. Pitot traverse for flow; manometer for static pressure
2. Motor input by √3·V·I·cos φ
3. Compute efficiency; compare with the fan curve
4. **Check the damper position** — a part-closed damper is immediate savings
5. Check for duct leakage, sharp bends near the fan outlet, and blocked filters

---

# Part 2 — Compressed air

## Rung 88 — Why compressed air is the expensive utility

Compressed air is convenient, safe and everywhere in a plant. It is also **the
most expensive form of energy on site**, and this is the fact examiners want you
to be able to justify.

Compressing air heats it. That heat is then thrown away in the aftercooler, and
the energy is gone. Overall, **only about 10% of the electrical energy going into a
compressor ends up as useful work at the tool.** The rest is heat.

Which makes two things standard exam answers:

- **Leaks are the biggest single loss.** A plant typically leaks 20–30% of its
  compressed air. A 3 mm hole at 7 bar costs roughly 2–3 kW continuously — and a
  leak runs 8,760 hours a year.
- **Never use compressed air where anything else will do** — not for cleaning, not
  for cooling, not for agitation. A blower does the same job at a fraction of the
  energy.

---

## Rung 89 — Free Air Delivery, and why it needs defining

A compressor's output is measured as **Free Air Delivery** — the volume of air it
delivers, *measured at inlet conditions*, not at the compressed pressure.

The definition matters because compressed air occupies less volume. Saying "the
compressor delivers 13 m³/min" is meaningless unless you say at what pressure. FAD
fixes the reference at ambient, so machines can be compared.

**The pump-up test** measures it. Isolate the compressor, empty the receiver, run
the machine, and time how long it takes to raise the receiver pressure:

```
              (P₂ − P₁)     V        (273 + t₁)
    FAD  =  ───────────  ×  ───  ×  ───────────
                 P₀          T       (273 + t₂)
```

- `P₂ − P₁` — pressure rise achieved (absolute)
- `P₀` — atmospheric pressure, which converts to free-air terms
- `V` — total system volume: **receiver plus interconnecting pipework**
- `T` — time taken
- The temperature ratio corrects the air in the receiver back to inlet conditions

**Drill 52.** Receiver 10 m³, pipework 1 m³, 1.0 → 8.5 kg/cm²a in 6 minutes.
Inlet 30 °C, receiver 40 °C, atmospheric 1.0 kg/cm²a.

<details><summary>Answer</summary>

```
    FAD = (8.5 − 1.0)/1.0 × 11/6 × 303/313
        = 7.5 × 1.8333 × 0.968
        = 13.31 m³/min  =  470 CFM   (× 35.31)
```

Against a 500 CFM rating, that is **6% below** — a real but not alarming shortfall,
typical of a worn machine.
</details>

---

## Rung 90 — Loading, unloading, and where the waste hides

A reciprocating compressor cannot modulate smoothly. It runs **loaded**
(compressing) until the receiver reaches its upper pressure, then **unloads** —
still spinning, still drawing power, delivering nothing.

**Unloading power is typically 20–30% of loading power for zero output.** That is
pure waste, and reducing unloaded running is one of the most common compressed-air
recommendations.

```
    Hourly energy = (% loaded × loading kW) + (% unloaded × unloading kW)
```

**Drill 53.** 65% loaded at 82 kW, 35% unloaded at 21 kW, energy at ₹10/kWh.
Hourly consumption and daily cost.

<details><summary>Answer</summary>

```
    Loading   = 0.65 × 82 = 53.30 kWh
    Unloading = 0.35 × 21 =  7.35 kWh
    Hourly    = 60.65 kWh
    Daily     = 60.65 × 10 × 24 = Rs 14,556
```

Note the 7.35 kWh every hour buys **nothing at all**. Over a year at 8,000 hours,
that is ₹588,000 of air not delivered.
</details>

---

## Rung 91 — Isothermal efficiency

How good is a compressor? Compare it against the **best thermodynamically
possible** compression.

The ideal is **isothermal** — compressing so slowly, with such perfect cooling,
that the air never heats up. Any temperature rise is wasted work, so isothermal is
the minimum energy route:

```
    Isothermal power (kW) = P₁ × Q₁ × ln(r) / 36.7
```

with `P₁` in kg/cm²a, `Q₁` = **FAD in m³/hr**, and `r` = compression ratio
`P₂/P₁`.

**36.7 is the same family again** — 1 kg/cm² = 98,067 Pa, so 3600/98.067 = 36.7.
Convert to Pa, convert to kW, exactly as with 102 and 367.

The `ln(r)` comes from integrating `P·dV` at constant temperature — the work to
compress a gas isothermally from V₁ to V₂ is `P₁V₁·ln(V₁/V₂)`.

```
    Isothermal efficiency = isothermal power / actual power × 100
```

**Drill 54.** FAD 13.31 m³/min, P₁ = 1.0 kg/cm²a, P₂ = 8.5, actual loading power
82 kW.

<details><summary>Answer</summary>

```
    Q₁ = 13.31 × 60 = 798.6 m³/hr
    r  = 8.5/1.0 = 8.5,  ln(8.5) = 2.1401

    Isothermal power = 1.0 × 798.6 × 2.1401 / 36.7 = 46.57 kW
    Isothermal efficiency = 46.57 / 82 × 100 = 56.8 %
```

*Anchor:* 55–70% is normal. It looks low because the ideal is unattainable — real
compression always heats the air.
</details>

---

## Rung 92 — Specific power, the number plants actually track

```
    Specific power = actual power (kW) / FAD (m³/min)
```

A single number that lets you compare any two compressors. Typical for a
single-stage reciprocating machine at 7 bar: **6–7 kW per 100 CFM**, or about
**0.10–0.12 kW per m³/hr**.

Rising specific power over time means wear, leaking valves, or a fouled intake
filter.

---

## Rung 93 — Speed change on a belt drive

Reducing compressor speed reduces FAD proportionally (Rung 86 — same affinity
law), which lets a machine run loaded for longer instead of cycling.

For a belt drive, the speeds are inversely proportional to the pulley diameters:

```
    N_motor × D_motor = N_compressor × D_compressor
```

**Drill 55.** Motor 1400 RPM with a 300 mm pulley drives a 600 mm compressor
pulley. Current: 65% loaded, FAD 13.31 m³/min. Required: 50 minutes loaded, 10
unloaded per hour, same air delivered. Find the new compressor speed and motor
pulley diameter.

<details><summary>Answer</summary>

```
    Current compressor speed = 1400 × 300/600 = 700 RPM
    Air delivered now = 0.65 × 60 × 13.31 = 519.1 m³/hr

    New loading fraction = 50/60
    New FAD needed = 519.1 / (50/60 × 60) = 10.38 m³/min

    FAD ∝ speed:  N_new = 700 × 10.38/13.31 = 546 RPM
    New motor pulley = 600 × 546/1400 = 234 mm
```

The plant delivers the same air, running longer at lower output — cutting the
wasteful unloaded hours.
</details>

---

## Rung 94 — Simple payback

```
    Simple payback (years) = investment / annual saving
```

That is all it is: how long until the saving repays the cost. It ignores the time
value of money — which is why Day 13 covers NPV and IRR — but for a small
retrofit it is the standard test, and anything under about two years is normally
approved without argument.

**Drill 56.** After the pulley change: 64 kW loading, 18 kW unloading, 50/10 split.
Pulley and belts cost ₹1.2 lakh, 8,000 operating hours, ₹10/kWh.

<details><summary>Answer</summary>

```
    New hourly = 64 × 50/60 + 18 × 10/60 = 53.33 + 3.00 = 56.33 kWh
    Old hourly = 60.65 kWh
    Saving     = 4.32 kWh/hr

    Annual = 4.32 × 8,000 = 34,533 kWh = Rs 3,45,333
    Payback = 1,20,000 / 3,45,333 = 0.35 year = 4.2 months
```

*Sanity:* a four-month payback on a pulley change is exactly why this measure
appears in every compressed-air audit.
</details>

---

# Practice

## Timed — 23rd sitting N-1 (35 min)

`papers/23-1.pdf` — the reciprocating compressor, **20 marks, 30 minutes**. All
five parts.

**Prerequisite check:** A → Rung 89 · B → Rung 90 · C → Rung 91 · D → Rung 93 ·
E → Rung 94. **Every part covered.**

Every drill above is a piece of this question. Assemble them cold.

## Then — 19th sitting N-2, fan power part (15 min)

`papers/19-1.pdf` — the effluent question from Day 5. You did the heat exchanger
side; **now do the fan and pump power comparison** you deferred.

## Log

**Record start and finish times.** Your one data point so far — 4 minutes against
8 — was useful. Build the picture.

---

## Day 9 checklist

**Fans**
- [ ] Know what separates a fan, blower and compressor, and why
- [ ] Can explain static, velocity and total pressure
- [ ] Can reconstruct 102 as 1000/9.81, and see it is 367's twin
- [ ] Can compute fan efficiency and know the 70–85% band
- [ ] Know how duct flow is measured and why velocities are averaged
- [ ] Can rank damper, guide vanes and VSD by power at part flow

**Compressed air**
- [ ] Can justify why compressed air is the most expensive utility
- [ ] Can define FAD and say why the reference matters
- [ ] Can run a pump-up test calculation including the temperature correction
- [ ] Know unloaded running draws 20–30% of power for zero output
- [ ] Can compute isothermal power and efficiency, and know why 55–70% is normal
- [ ] Can use specific power to compare machines
- [ ] Can work a belt-drive speed change
- [ ] Can compute simple payback

**Next (Day 10):** motors, variable speed drives and cooling towers — motors
appear in 8 of 8 sittings.

# Day 5 — Heat Exchangers

**Time: 4 hours. Book-4 Ch 4 (p. 59).** Appears in **7 of 8 sittings**.

> Book 4 Ch 4 is not among the chapters BEE publishes online, so this is built
> from first principles and from the past papers' own worked answers. Your
> supplied guidebook has the chapter — tab it (**HX**).

**How this day is built.** Nothing is asserted. We start from what a heat
exchanger is and what physically happens inside one; `U` emerges from the
resistance chain, and the LMTD is **derived**, not quoted. Formulas appear only
once you can see where they must come from.

Rungs 35–50.

---

# Part 1 — What a heat exchanger is

## Rung 35 — The problem being solved

Two fluids at different temperatures. You want to move heat from one to the other
**without mixing them** — because they are different substances, at different
pressures, or one is dirty and one is not.

That is the entire job: **a wall with fluid on both sides.** Hot fluid gives heat
to the wall, the wall passes it through, the cold fluid takes it away.

Three things follow immediately, and they turn out to be the whole subject:

1. How much heat can the two fluids give and take? → an **energy balance**
2. How hard is it to push heat through the wall? → the **resistance chain**
3. What is pushing it? → the **temperature difference**

`Q = U · A · ΔT_lm` is nothing more than those three questions answered together.
By Rung 42 you will have built it yourself.

---

## Rung 36 — How heat actually crosses

Three mechanisms exist. In a heat exchanger, two of them matter.

**Conduction** — heat diffusing through a solid, molecule to molecule:

```
    Q = k · A · ΔT / x
```

`k` is thermal conductivity, `x` the thickness. This is what happens **inside the
tube wall**. Steel has k ≈ 45 W/m·K and walls are 1–2 mm, so this step is fast and
usually negligible.

**Convection** — heat carried between a surface and a moving fluid:

```
    Q = h · A · ΔT
```

`h` is the **film coefficient**, and it is the crux of the subject. Right at the
wall the fluid is nearly stationary — a thin, sluggish **boundary layer** that heat
must cross by conduction through the fluid itself. `h` measures how thin and how
conductive that layer is.

What sets `h`:

| Factor | Effect on h |
|---|---|
| Higher velocity | thinner boundary layer → **higher h** |
| Turbulent rather than laminar flow | mixing destroys the layer → **much higher h** |
| Higher fluid conductivity | heat crosses the layer faster → higher h |
| Higher viscosity | thicker layer → lower h |

Which is why water and air are so different:

| Fluid | h (W/m²K) |
|---|---|
| Water, turbulent | 3,000 – 10,000 |
| Steam, condensing | 5,000 – 15,000 |
| Oil | 100 – 400 |
| **Air / gas** | **20 – 100** |

**Gases are 50–100× worse than liquids at getting heat to a wall.** Hold that —
Rung 37 makes it the most important fact in the chapter.

**Radiation** — energy as electromagnetic waves, going as T⁴. Matters in furnaces
at 1300 °C (Day 6). At heat-exchanger temperatures it is negligible.

---

## Rung 37 — Building U from the resistances

Now trace one joule from hot fluid to cold. It must cross **three barriers in
series**:

```
   hot fluid ──► [hot film] ──► [metal wall] ──► [cold film] ──► cold fluid
                    1/hᵢ            x/k              1/hₒ
```

Series resistances **add** — exactly like resistors in a circuit, which is the
useful analogy here. The total resistance to heat flow, per unit area:

```
    R_total = 1/hᵢ + x/k + 1/hₒ
```

Define `U` as the **conductance** — the reciprocal of that total resistance:

```
    1/U = 1/hᵢ + x/k + 1/hₒ  (+ R_f for fouling)
```

**So U is not a property of the exchanger. It is a property of the two fluids,
their velocities, and the wall** — and it is something you build, not look up.

**The consequence that matters: in a series chain, the largest resistance
dominates.**

| Case | hᵢ | hₒ | 1/hᵢ | 1/hₒ | U |
|---|---|---|---|---|---|
| Water–water | 5000 | 3000 | 0.0002 | 0.00033 | **1875** |
| Water–**air** | 5000 | **50** | 0.0002 | **0.02** | **~50** |

In the second row the air film is **100× the other resistance**. Improving the
water side does nothing at all — you would be reducing 0.0002 in a total of
0.0202.

> **This is why air-cooled exchangers have fins.** You cannot make the air film
> much better, so you compensate with *area* on that side. Fins are a response to
> a bad film coefficient.
>
> It is also why plate exchangers beat shell-and-tube for water–water: narrow
> corrugated channels force turbulence at low velocity, raising **both** film
> coefficients.

**Drill 36.** hᵢ = 5000, hₒ = 3000 W/m²K, fouling resistance 0.0002 m²K/W. Find U,
and say what the fouling costs.

<details><summary>Answer</summary>

```
    1/U = 0.000200 + 0.000333 + 0.000200 = 0.000733
    U   = 1364 W/m²K

    clean: 1/U = 0.000533 → U = 1875 W/m²K
```

Fouling costs **27% of U** — one thin film adding a resistance as large as the
entire hot-side film. That is why cleaning is an energy measure.
</details>

---

## Rung 38 — Types, and why each exists

Every design is an answer to "how do I get area and turbulence cheaply, at this
pressure, with this fluid?"

**Shell-and-tube** — a bundle of tubes inside a cylindrical shell. One fluid in
the tubes, the other around them, with baffles forcing cross-flow.

- Handles **high pressure and temperature**; the tubes are strong
- Robust, mechanically cleanable, repairable
- But: bulky, and multi-pass means it is **partly parallel flow** (Rung 44)
- U ≈ 800–1500 water–water

**Plate (PHE)** — thin corrugated plates clamped together, fluids in alternate
narrow channels.

- Corrugations force **turbulence at low velocity** → very high h on both sides
- Nearly **true counterflow**; compact; plates can be added to extend it
- But: gaskets limit pressure and temperature, and narrow channels foul quickly
- U ≈ 2000–6000

**Air-cooled** — process fluid in finned tubes, fans blowing ambient air over.

- No cooling water at all
- But: air's h caps U at 20–60, so it needs **enormous finned area** and
  significant fan power, and can never cool below ambient

**Spiral** — two long plates rolled into a spiral.

- Single passage, self-cleaning; handles slurries and fibrous fluids
- Expensive

> **The 19th sitting's question is exactly this choice** — replace an *air-cooled*
> exchanger with a *water-cooled plate* one. Understanding Rung 37 lets you say
> why: the air film caps U near 50, so the air-cooled unit is huge and its fan
> power large; the plate exchanger's U is two orders higher, so it needs 5.57 m²
> and a pump instead of a fan.

---

# Part 2 — Building the equations

## Rung 39 — How much heat: the energy balance

Neither fluid changes phase (unless told), so each simply warms or cools:

```
    Q = m × Cp × ΔT
```

And since the wall only transfers — it stores nothing:

```
    Q_hot = Q_cold
```

**That is how you find the unknown flow.** Questions give you one complete stream
and only temperatures for the other. Compute Q from the complete one, then work
backwards.

The product `m × Cp` recurs so often it has a name — the **capacity rate**, `C`,
in W/°C or kCal/hr°C. It is how much heat a stream carries per degree. A stream
with a small capacity rate changes temperature a lot; a large one barely moves.

**Drill 37.** Ethyl alcohol, 2.1 kg/s, Cp 2670 J/kg°C, heated 25 → 70 °C. Water
cools 95 → 45 °C, Cp 4190. Find the duty and the water flow.

<details><summary>Answer</summary>

```
    Q = 2.1 × 2670 × 45 = 252,315 W = 252.3 kW

    252,315 = m_w × 4190 × 50   ⟹   m_w = 1.204 kg/s
```

Capacity rates: alcohol 5607 W/°C, water 5046 W/°C. Water's is smaller, so it
changes temperature more (50 vs 45 °C). ✓
</details>

---

## Rung 40 — The driving force, and why one number will not do

Heat crosses the wall because of the temperature difference. For a small patch of
area `dA`:

```
    dQ = U · dA · ΔT          where ΔT = T_hot − T_cold at that point
```

But **ΔT is not the same everywhere.** As the fluids travel, the hot one cools and
the cold one warms, so the gap changes continuously — 25 °C at one end, 20 °C at
the other in Drill 37.

So which ΔT goes in `Q = U A ΔT`?

Not the arithmetic mean. Where the gap is wide, heat crosses fast, so temperatures
change fast, so the gap narrows fast. **The gap closes exponentially, not
linearly** — and averaging an exponential decay arithmetically overstates it.

The correct average must come from integrating along the exchanger. That is
Rung 41.

---

## Rung 41 — Deriving the LMTD

Take a counterflow exchanger. Let `C_h = ṁ_h·c_h` and `C_c = ṁ_c·c_c` be the two
capacity rates, and follow position `x` along the hot fluid's direction.

**Step 1 — how each stream changes across a small element.**

The hot fluid loses `dQ`, the cold gains it. In counterflow the cold fluid travels
the other way, so moving along `+x` its temperature also falls:

```
    dT_h = − dQ / C_h              dT_c = − dQ / C_c
```

**Step 2 — how the gap changes.**

```
    d(ΔT) = dT_h − dT_c = −dQ [ 1/C_h − 1/C_c ]
```

**Step 3 — substitute the rate equation** `dQ = U·ΔT·dA`:

```
    d(ΔT) = −U·ΔT·dA [ 1/C_h − 1/C_c ]

    d(ΔT)/ΔT = −U [ 1/C_h − 1/C_c ] dA
```

**There is the exponential.** The rate of change of the gap is proportional to the
gap itself — the signature of exponential decay.

**Step 4 — integrate end to end.**

```
    ln(ΔT₂/ΔT₁) = −U·A [ 1/C_h − 1/C_c ]
```

**Step 5 — replace the capacity rates.** Over the whole exchanger:

```
    Q = C_h(T_h,in − T_h,out)   ⟹   1/C_h = (T_h,in − T_h,out)/Q
    Q = C_c(T_c,out − T_c,in)   ⟹   1/C_c = (T_c,out − T_c,in)/Q
```

Substituting:

```
    ln(ΔT₂/ΔT₁) = −(U·A/Q) [ (T_h,in − T_h,out) − (T_c,out − T_c,in) ]
                = −(U·A/Q) [ (T_h,in − T_c,out) − (T_h,out − T_c,in) ]
                = −(U·A/Q) [ ΔT₁ − ΔT₂ ]
```

**Step 6 — rearrange.**

```
                    ΔT₁ − ΔT₂
    Q  =  U · A · ─────────────
                   ln(ΔT₁/ΔT₂)
```

That fraction is the **log mean temperature difference**. It was not invented — it
is what falls out when you integrate an exponentially closing gap.

```
    LMTD = (ΔT₁ − ΔT₂) / ln(ΔT₁/ΔT₂)
```

Two consequences worth carrying:

- **LMTD is always smaller than the arithmetic mean.** For 33 and 13: LMTD 21.47
  against arithmetic 23.0. Using the arithmetic mean oversizes the duty and
  undersizes the exchanger.
- **When ΔT₁ ≈ ΔT₂ the log form breaks down** (0/0). Then the two are nearly equal
  anyway and the arithmetic mean is a fine approximation. If ΔT₁/ΔT₂ is within
  about 1.5, the error is under 2%.

**Drill 38.** ΔT₁ = 33 °C, ΔT₂ = 13 °C.

<details><summary>Answer</summary>

```
    LMTD = (33 − 13) / ln(33/13) = 20 / 0.9316 = 21.47 °C
    arithmetic mean = 23.0 °C
```
</details>

---

## Rung 42 — The design equation

Assembling Rungs 37, 39 and 41:

```
    Q = U · A · LMTD              ⟹      A = Q / (U · LMTD)
```

Every symbol is now something you built:

| | is | comes from |
|---|---|---|
| Q | the duty | energy balance, Rung 39 |
| U | conductance of the resistance chain | Rung 37 |
| A | surface area | what you are solving for |
| LMTD | correctly averaged driving force | Rung 41 |

**Match U's units to Q's** — these papers use all three systems:

| U | Q must be in |
|---|---|
| W/m²°C | W |
| kW/m²°C | kW |
| kCal/hr·m²°C | kCal/hr |

**Drill 39.** Q = 252,315 W, U = 950 W/m²°C, LMTD 22.41 °C, correction factor 0.82.

<details><summary>Answer</summary>

```
    corrected LMTD = 0.82 × 22.41 = 18.37 °C
    A = 252,315 / (950 × 18.37) = 14.5 m²
```
</details>

---

# Part 3 — Arrangement, performance, and the real world

## Rung 43 — Flow arrangement, and the temperature cross

**Counterflow** — streams travel opposite ways, so the hot inlet faces the cold
*outlet*:

```
    hot:    80 ────────────────► 38
    cold:   47 ◄──────────────── 25

    ΔT₁ = 80 − 47 = 33        ΔT₂ = 38 − 25 = 13
```

**Parallel flow** — both enter the same end:

```
    hot:    80 ────────────────► 38
    cold:   25 ────────────────► 47

    ΔT₁ = 55        ΔT₂ = 38 − 47 = −9  ← impossible
```

That negative gap is the physics refusing. **The cold stream leaves at 47 °C,
hotter than the hot stream's 38 °C outlet — a temperature cross.** Parallel flow
cannot do it: both streams march toward a common temperature and neither passes
the other.

Counterflow can, because each element of cold fluid meets progressively hotter
hot fluid as it travels. The coldest water meets the coolest effluent; the water
about to leave meets the incoming 80 °C.

> **A free check:** if a question's data shows a temperature cross, the
> arrangement **must** be counterflow. And always draw the two-line diagram before
> reading ΔT₁ and ΔT₂ — five seconds, and it removes a whole class of errors.

Counterflow also gives a **larger LMTD** for the same duty, so **less area**. It
is the default everywhere unless a question says otherwise.

---

## Rung 44 — Correction factor F

A multi-pass shell-and-tube exchanger cannot be pure counterflow — tubes running
back the other way are locally parallel. Its true mean driving force is smaller
than the counterflow LMTD, so:

```
    ΔT_effective = F × LMTD          F ≤ 1, typically 0.75–0.95
```

**F is the penalty for not being pure counterflow.** It is read from charts
indexed by shell and tube passes — and in the exam it is **given**. If you are
given F, use it. If not, the arrangement is true counterflow and F = 1.

An F below about 0.75 signals a badly chosen configuration; designers add shell
passes rather than accept it.

---

## Rung 45 — Effectiveness

Sometimes outlet temperatures are not given, and you are asked what the exchanger
*achieves*. **Effectiveness** is the fraction of the theoretically possible
temperature change actually delivered.

The most the cold stream could ever reach is the hot stream's **inlet**
temperature — an infinitely large exchanger, and no more. So:

```
              actual change        T_c,out − T_c,in
    ε  =  ───────────────────  =  ───────────────────
            maximum possible       T_h,in  − T_c,in
```

Rearranged for the outlet you need:

```
    T_c,out = ε × (T_h,in − T_c,in) + T_c,in
```

ε is dimensionless and **can never exceed 1**. If yours does, the denominator is
wrong.

**Drill 40.** ε = 0.4, hot effluent in at 80 °C, cooling water in at 25 °C.

<details><summary>Answer</summary>

```
    T_c,out = 0.4 × (80 − 25) + 25 = 47 °C
```

Must lie between 25 and 80. ✓
</details>

---

## Rung 46 — NTU, when LMTD cannot start

LMTD needs **all four temperatures**. If you have only the two inlets and the
exchanger's size, LMTD cannot begin — you would need the answer to compute it.

```
    NTU = U·A / C_min          "how thermally large is this exchanger"
    C_r = C_min / C_max        "how mismatched are the streams"
```

`C_min` is the smaller capacity rate — the stream that changes temperature more,
and therefore the one that limits what the exchanger can do.

For counterflow:

```
              1 − exp[−NTU(1 − C_r)]
    ε  =  ────────────────────────────────        then    Q = ε · C_min · (T_h,in − T_c,in)
            1 − C_r·exp[−NTU(1 − C_r)]
```

| You know | Use |
|---|---|
| All four temperatures — find area | **LMTD** |
| Two inlets + area — find outlets or duty | **ε–NTU** |

Two behaviours that appear as True/False:

- **Diminishing returns.** ε climbs steeply to about NTU = 2, then flattens.
  Doubling an already-large exchanger buys almost nothing.
- **C_r = 0** means one stream's temperature does not change — a condenser or
  evaporator. Then ε = 1 − e^(−NTU), the best case.

---

## Rung 47 — Fouling

Deposits add a resistance term to the chain of Rung 37, so U falls, so duty falls.

The auditor back-calculates U from measurements and compares with design:

```
    U_actual = Q / (A × LMTD)          R_f = 1/U_actual − 1/U_clean
```

| Symptom | Why |
|---|---|
| Outlet temperature drifting from design | less heat transferred |
| Rising pressure drop | deposits narrowing passages |
| U_actual below U_design | the direct measurement |
| Approach temperature widening | streams no longer pulled together |

Causes: hardness scale, biological growth, corrosion products, process deposits.
Prevention: water treatment, adequate velocity (low velocity lets solids settle),
periodic cleaning.

---

## Rung 48 — Approach temperature: where the money is

The **approach** is the smallest temperature difference in the exchanger. As it
shrinks, LMTD shrinks, and area explodes. On the 25th sitting's duty (1156 kW,
U = 2.8 kW/m²°C):

| Approach | LMTD | Area |
|---|---|---|
| 7 °C | 7.49 | **55 m²** |
| 5 °C | 5.48 | 75 m² |
| 3 °C | 3.48 | 119 m² |
| 1 °C | 1.44 | **286 m²** |

Tightening from 7 °C to 1 °C multiplies the exchanger — and its cost — by five,
for the same heat.

> **The central economic trade-off of heat exchanger design.** As approach → 0,
> area → ∞. Nothing recovers heat perfectly at any price.

For an auditor: a *widening* approach over time is fouling. A proposed recovery
scheme demanding a very tight approach will have poor payback, because area cost
dominates.

---

## Rung 49 — Selection, in one table

| Type | U | Choose when | Avoid when |
|---|---|---|---|
| Shell-and-tube | 800–1500 | High P/T, dirty service, need mechanical cleaning | Space is tight |
| Plate | 2000–6000 | Water–water, close approach, compact | High P/T, fouling duty |
| Air-cooled | 20–60 | No cooling water available | Close approach to ambient needed |
| Spiral | 1500–3000 | Slurries, fibrous fluids | Cost-sensitive |

---

## Rung 50 — What an auditor does at a heat exchanger

1. **Measure all four temperatures and both flows.** Check `Q_hot ≈ Q_cold` within
   a few percent. A large mismatch means a faulty instrument, not a faulty
   exchanger.
2. **Back-calculate U** and compare with design. A shortfall is fouling.
3. **Check the approach** — widening over time means fouling.
4. **Check pressure drop** both sides against design.
5. **Check the arrangement** — is it truly counterflow? A wrongly connected
   exchanger loses duty for nothing.
6. **Look for bypass** — flow going around through an open valve.

Recommendations: clean, treat the water, correct the flow arrangement, add
surface where the approach permits, recover the heat elsewhere if it does not.

---

# Practice

## Worked — 19th sitting N-2 (40 min)

`papers/19-1.pdf` — hot effluent to a plate heat exchanger.

> **Prerequisite check:** the fan and pump power parts need Day 9. **Attempt the
> heat exchanger parts only.**

```
    Heat duty  = 63,450 × 1 × (80 − 38)     = 26,64,900 kCal/hr     (Rung 39)
    Air mass   = 2,664,900 / (0.24 × 30)    = 3,70,125 kg/hr        (Rung 39)
    Water out  = 0.4 × (80 − 25) + 25       = 47 °C                 (Rung 45)
    Water flow = 2,664,900 / (47 − 25)      = 1,21,132 kg/hr        (Rung 39)

    counterflow:   hot  80 ──► 38                                   (Rung 43)
                   cold 47 ◄── 25
    ΔT₁ = 33,  ΔT₂ = 13,  LMTD = 21.47 °C                           (Rung 41)

    Area = 2,664,900 / (22,300 × 21.47) = 5.57 m²                   (Rung 42)
```

**The order works for nearly every question in this chapter:** duty → energy
balance for the unknown → temperatures → LMTD → area.

Now answer in words:

1. Why is the air-cooled exchanger's U so much lower?
2. Why does the plate exchanger need only 5.57 m²?
3. Where is the temperature cross, and what does it prove?
4. Which saving is larger — the smaller exchanger, or the fan replaced by a pump?

<details><summary>Answers</summary>

1. The **air-side film coefficient** dominates the resistance chain (Rung 37);
   air is ~50 W/m²K against water's thousands.
2. U is roughly 500× higher, and area scales as 1/U for the same duty and LMTD.
3. Cold water leaves at 47 °C, above the effluent's 38 °C outlet. It **must** be
   counterflow (Rung 43).
4. **Fan replaced by pump** — moving air costs far more than moving water for the
   same heat, because of that same poor film coefficient.
</details>

## Timed — 18th sitting L-2 (30 min)

`papers/18-1.pdf` — shell-and-tube, 5 marks, 8 minutes. Every piece is a drill
above. **Prerequisite check: fully covered.**

Record start and finish times.

## Log (20 min)

- **What the checking pass caught** — "caught nothing" is information
- Whether every term in every ratio had a written unit
- Whether the two-line diagram was drawn before reading ΔT₁, ΔT₂

---

## Day 5 checklist

**Understanding**
- [ ] Can say what a heat exchanger is and the three questions its equation answers
- [ ] Know what a film coefficient is and what makes it large or small
- [ ] Can build U as resistances in series and say which dominates
- [ ] Know why air-cooled exchangers are finned and plate exchangers are corrugated
- [ ] Can justify shell-and-tube vs plate vs air-cooled

**Derivation**
- [ ] Can explain why the mean must be logarithmic
- [ ] **Can reproduce the LMTD derivation** — six steps, Rung 41
- [ ] Know when the log form breaks down and what to do

**Calculation**
- [ ] Can use Q_hot = Q_cold to find an unknown flow
- [ ] Draw the diagram and read ΔT₁, ΔT₂ off the *ends*
- [ ] Can find area, matching U's units to Q's
- [ ] Know F ≤ 1, given when needed, 1 for true counterflow
- [ ] Can apply effectiveness and check 0 ≤ ε ≤ 1
- [ ] Know when ε–NTU replaces LMTD

**Judgement**
- [ ] Can identify a temperature cross and say what it proves
- [ ] Can back-calculate U to assess fouling
- [ ] Can explain why area explodes as approach shrinks
- [ ] Can list what an auditor measures

**Next (Day 6):** furnaces, waste heat recovery and insulation.

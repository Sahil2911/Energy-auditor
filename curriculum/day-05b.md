# Day 5B — Heat Exchangers, Properly

**Time: 3 hours.**

> **Why this exists.** Day 5 taught you how to *calculate* a heat exchanger and
> almost nothing about how one *behaves*. LMTD and `A = Q/(U·LMTD)` are two
> formulas, and a paper that appears in 7 of 8 sittings deserves more than that.
> The criticism was correct.
>
> Rungs 43–49 are the engineering underneath.

---

## Rung 43 — What U actually is

`U` is treated like a given constant. It is not — it is the **sum of resistances
in series**, and knowing what is in it tells you what to fix.

Heat crossing from hot fluid to cold passes through four obstacles:

```
   hot fluid │ film │  metal wall  │ film │ cold fluid
             │      │              │      │
   resistance:  1/hᵢ  +   x/k   +  1/hₒ  +  R_f (fouling)
```

```
    1/U  =  1/hᵢ  +  x/k  +  1/hₒ  +  R_f
```

- `hᵢ`, `hₒ` — **film coefficients**, how well each fluid carries heat to the
  wall. Set by velocity, viscosity and conductivity.
- `x/k` — conduction through the metal. Usually negligible; steel is thin and
  conductive.
- `R_f` — fouling: scale, biofilm, deposits.

**The critical consequence: series resistances mean the WORST one dominates.**

| Case | hᵢ | hₒ | U |
|---|---|---|---|
| Water–water | 5000 | 3000 | ~1875 |
| Water–**air** | 5000 | **50** | **~50** |

Add a gas to one side and U collapses to roughly the gas-side film coefficient.
Improving the water side is then pointless — you are polishing the resistance
that isn't the problem.

> **This is why air-cooled exchangers have fins.** You cannot raise the air film
> coefficient much, so you raise the *area* on that side instead. Fins are a
> response to a bad film coefficient, not decoration.

**Typical U values (W/m²K) — worth recognising for sanity checks:**

| Type | U |
|---|---|
| Plate heat exchanger, water–water | 2,000 – 6,000 |
| Shell-and-tube, water–water | 800 – 1,500 |
| Shell-and-tube, water–oil | 100 – 400 |
| Air-cooled (finned) | 20 – 60 |
| Steam–water | 1,000 – 3,000 |

The 25th sitting's 2.8 kW/m²°C = 2,800 W/m²K — a plate exchanger, consistent.
The 19th's 22,300 kCal/hr·m²°C ≈ 25,900 W/m²K is unrealistically high; the papers
sometimes use generous numbers. Use the value given, but know the real range.

**Drill 36.** hᵢ = 5000, hₒ = 3000, fouling resistance 0.0002 m²K/W. Find U, and
say what fouling costs.

<details><summary>Answer</summary>

```
    1/U = 1/5000 + 1/3000 + 0.0002 = 0.000200 + 0.000333 + 0.0002 = 0.000733
    U   = 1364 W/m²K

    clean (no fouling): 1/U = 0.000533 → U = 1875 W/m²K
```

Fouling costs **27% of U** — from one thin film. That is why cleaning schedules
are an energy measure, not just maintenance.
</details>

---

## Rung 44 — Fouling, quantified

Fouling adds resistance, so U falls, so for fixed area the duty falls. The
auditor's method is to **back-calculate U from measurements and compare to
design**:

```
    U_actual = Q / (A × LMTD)          then    fouling factor R_f = 1/U_actual − 1/U_clean
```

What it looks like in a plant, and the standard answer to "what would you check":

| Symptom | Why |
|---|---|
| Outlet temperature drifting from design | less heat transferred |
| Rising pressure drop | deposits narrowing the passages |
| U_actual falling below U_design | the direct measurement |
| Approach temperature widening | the exchanger can no longer pull the streams together |

Causes: hardness scale, biological growth, corrosion products, process
deposits. Prevention: water treatment, adequate velocity (low velocity encourages
settling), and periodic cleaning.

---

## Rung 45 — Approach temperature: where the money is

The **approach** is the smallest temperature difference in the exchanger —
typically the gap at the "tight" end.

It matters because as approach shrinks, LMTD shrinks, and **area explodes**.

Using the 25th sitting's duty (1,156 kW, U = 2.8 kW/m²°C):

| Approach | LMTD | Area needed |
|---|---|---|
| 7 °C | 7.49 | **55 m²** |
| 5 °C | 5.48 | 75 m² |
| 3 °C | 3.48 | 119 m² |
| 1 °C | 1.44 | **286 m²** |

Going from a 7 °C approach to 1 °C multiplies the exchanger — and its cost — by
**five**, for the same heat.

> **This is the central economic trade-off of heat exchanger design.** A tight
> approach recovers more heat but needs disproportionately more surface. As
> approach → 0, area → ∞. Nothing recovers heat perfectly, at any price.

For an energy auditor the practical reading works the other way round: if an
existing exchanger shows a *widening* approach over time, it is fouling. If a
proposed heat recovery scheme demands a very tight approach, its payback will be
poor because the area cost dominates.

---

## Rung 46 — Temperature cross, and why counterflow really wins

Day 5 said counterflow beats parallel flow. Here is the sharp version.

Look at the 19th sitting's exchanger:

```
    hot effluent:   80 ──────────────► 38
    cooling water:  47 ◄────────────── 25
```

**The cold stream leaves at 47 °C — hotter than the hot stream leaves (38 °C).**

That is a **temperature cross**, and it is *impossible* in parallel flow. In
parallel flow both streams march toward a common temperature and neither can pass
the other; the best you could ever get is both ending at the same value.

Counterflow can do it because each bit of cold fluid meets progressively hotter
hot fluid as it travels. The coldest water meets the coolest effluent; the
warmest water — about to leave — meets the incoming 80 °C.

Consequences worth stating in an exam:

- Counterflow achieves a **higher cold outlet** for the same inlets
- It gives a **larger LMTD** for the same duty, so **less area**
- Multi-pass shell-and-tube is partly parallel, which is exactly why F < 1 — the
  correction factor is the penalty for not being pure counterflow

> If a question's data shows a temperature cross, the arrangement **must** be
> counterflow. That is a free check on your reading of the problem.

---

## Rung 47 — Effectiveness–NTU: when LMTD cannot be used

LMTD needs **all four temperatures**. Sometimes you only have the two inlets and
are asked what the exchanger will *do* — a performance prediction rather than a
sizing. LMTD cannot start, because you would need the answer to compute it.

The ε–NTU method exists for exactly that case.

**Two dimensionless groups:**

```
    NTU  =  U·A / (m·Cp)_min          "how big is the exchanger, thermally"

    C_r  =  (m·Cp)_min / (m·Cp)_max   "how mismatched are the two streams"
```

`m·Cp` is the **capacity rate** — how much heat a stream carries per degree.
The stream with the *smaller* capacity rate changes temperature more, and it is
the one that limits performance. That is why `min` appears in both groups.

Then effectiveness is a function of those two, from charts or formulas. For
counterflow:

```
              1 − exp[−NTU(1 − C_r)]
    ε  =  ────────────────────────────────
            1 − C_r · exp[−NTU(1 − C_r)]
```

And once you have ε:

```
    Q = ε × (m·Cp)_min × (T_h,in − T_c,in)
```

**Which method when:**

| You know | Use |
|---|---|
| All four temperatures — find area | **LMTD** |
| Two inlets + area — find outlets or duty | **ε–NTU** |

Two behaviours worth knowing, because they are True/False material:

- **NTU has diminishing returns.** ε rises steeply to about NTU = 2, then flattens.
  Doubling a large exchanger buys very little. Same message as Rung 45 from the
  other direction.
- **C_r = 0** means one stream's temperature does not change at all — a condenser
  or evaporator, where the fluid changes phase. Then ε = 1 − e^(−NTU), the best
  case.

---

## Rung 48 — Types, and why you would pick one

| Type | U | Strengths | Weaknesses |
|---|---|---|---|
| **Shell-and-tube** | 800–1500 | High pressure/temperature, robust, cleanable | Bulky, F < 1, more area |
| **Plate (PHE)** | 2000–6000 | Very high U, compact, near-true counterflow, easy to extend | Gasket limits on P and T, fouls in dirty service |
| **Air-cooled** | 20–60 | No water needed | Huge area, fan power, limited by ambient |
| **Spiral** | 1500–3000 | Handles slurries, self-cleaning | Costly |

The 19th sitting's question is exactly this choice: replace an **air-cooled**
exchanger with a **water-cooled plate** one. Now you can say *why* — the air-side
film coefficient caps U at ~50, so the air-cooled unit needs a large finned
surface and a big fan; the plate exchanger's U is two orders higher, so it needs
5.6 m² instead, and a pump draws far less power than the fan it replaces.

**That is what the question is really testing**, and it is invisible if you only
know the two formulas.

---

## Rung 49 — What an auditor actually does at a heat exchanger

The exam's "suggest measures" sub-parts want this list:

1. **Measure all four temperatures and both flows.** Check the heat balance —
   `Q_hot` should equal `Q_cold` within a few percent. A large mismatch means a
   faulty instrument, not a faulty exchanger.
2. **Back-calculate U** and compare with design. A shortfall is fouling.
3. **Check the approach.** Widening over time means fouling.
4. **Check pressure drop** on both sides against design.
5. **Check the arrangement** — is it truly counterflow? A wrongly connected
   exchanger loses duty for nothing.
6. **Look for bypass** — flow going around the exchanger through an open valve.

Typical recommendations: clean, treat the water, correct the flow arrangement,
add surface where the approach permits, recover the heat elsewhere if the
approach does not.

---

## Practice (45 min)

**19th sitting N-2** (`papers/19-1.pdf`) — the air-cooled to plate exchanger
replacement, heat exchanger parts only.

You did the numbers on Day 5. Now answer in words, in your own notes:

1. Why is the air-cooled exchanger's U so much lower?
2. Why does the plate exchanger need only 5.57 m² when the air-cooled one is huge?
3. Where is the temperature cross, and what does it tell you about the arrangement?
4. What are the two energy savings in the replacement — and which is larger?

<details><summary>Answers</summary>

1. The **air-side film coefficient** dominates. Series resistances mean the worst
   one governs; air is around 50 W/m²K against water's thousands.
2. Its U is roughly 500× higher, and area scales as 1/U for the same duty and
   LMTD.
3. Cold water leaves at 47 °C, hotter than the effluent's 38 °C outlet. It
   **must** be counterflow — parallel flow cannot cross.
4. **Fan power replaced by pump power** (the larger saving — moving air is far
   more energy-intensive than moving water for the same heat), and a smaller
   exchanger. The question quantifies the first.
</details>

---

## Day 5B checklist

- [ ] Can write U as resistances in series and say which one dominates
- [ ] Know why air-cooled exchangers are finned
- [ ] Can recognise a plausible U for each exchanger type
- [ ] Can back-calculate U to assess fouling
- [ ] Can explain why area explodes as approach shrinks
- [ ] Can identify a temperature cross and say what it proves
- [ ] Know when LMTD applies and when ε–NTU is needed
- [ ] Know NTU has diminishing returns, and what C_r = 0 means
- [ ] Can justify plate vs shell-and-tube vs air-cooled
- [ ] Can list what an auditor measures at an exchanger

**Next (Day 6):** furnaces, waste heat recovery and insulation.

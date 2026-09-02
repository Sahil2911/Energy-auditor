# Day 5 — Heat Exchangers

**Time: 4 hours. Book-4 Ch 4 (p. 59).**

Appears in **7 of 8 sittings**. Rungs 35–49, in one session.

> Book 4 Ch 4 is not among the chapters BEE publishes online, so this is built
> from first principles and from the past papers' own worked answers. Your
> supplied guidebook has the chapter — tab it (**HX**).

> **Structure.** Rungs 35–42 are how to calculate an exchanger. Rungs 43–49 are
> how one behaves — what U is made of, where the money is, and what an auditor
> measures. Do not stop at 42: the calculation rungs alone will get you through a
> sizing question and leave you unable to answer "why", which recent papers ask.

---

## Before you start — the three-line rule

Heat exchanger questions mix **W, kW, kJ and kCal** freely. The 18th sitting's
question is in watts; the 19th's is in kCal/hr.

From `reference/unit-discipline.md`: **no unit conversion inside a fraction bar.**
Each term on its own line, unit written beside it, convert there, divide once at
the end.

This is the chapter where that rule earns its keep.

---

# Part 1 — How to calculate an exchanger

## Rung 35 — Heat duty, and the balance that unlocks everything

A heat exchanger moves heat from a hot stream to a cold one. Neither stream
changes phase (unless told otherwise), so for each:

```
    Q = m × Cp × ΔT
```

**The key fact: whatever the hot side loses, the cold side gains.**

```
    Q_hot = Q_cold
```

That single equation is how you find the *unknown* flow rate. Almost every
question gives you everything about one stream and only temperatures for the
other. Compute Q from the complete stream, then work backwards.

**Drill 30.** Ethyl alcohol, 2.1 kg/s, Cp 2670 J/kg°C, heated 25 → 70 °C. Water
cools 95 → 45 °C, Cp 4190. Find the heat duty and the water flow.

<details><summary>Answer</summary>

```
    Q = 2.1 × 2670 × (70 − 25) = 252,315 W = 252.3 kW

    252,315 = m_w × 4190 × (95 − 45)
    m_w = 252,315 / 209,500 = 1.204 kg/s
```

*Sanity:* water has a higher Cp and a larger ΔT, so it needs less mass flow than
the alcohol. 1.2 < 2.1 ✓
</details>

---

## Rung 36 — Why a single ΔT will not do

The obvious formula would be `Q = U × A × ΔT`. The trouble is that **ΔT changes
continuously along the exchanger.**

At the inlet end the streams may be 33 °C apart; at the outlet end only 13 °C.
Which do you use? Neither — and the arithmetic mean is wrong too, because heat
transfer is exponential, not linear. The gap closes fastest where it is widest.

The correct average is **logarithmic**, and it is always *smaller* than the
arithmetic mean.

```
              ΔT₁ − ΔT₂
    LMTD  =  ───────────
              ln(ΔT₁/ΔT₂)
```

**Drill 31.** ΔT₁ = 33 °C, ΔT₂ = 13 °C. LMTD, and compare to the arithmetic mean.

<details><summary>Answer</summary>

```
    LMTD = (33 − 13) / ln(33/13) = 20 / 0.9316 = 21.47 °C
    arithmetic mean = (33 + 13)/2 = 23.0 °C
```

LMTD is lower, as it must be. Using 23 would overstate the duty and undersize the
exchanger.
</details>

---

## Rung 37 — Getting ΔT₁ and ΔT₂ right — the real trap

**Match the ends of the exchanger, not the labels of the streams.**

**Counterflow** — the streams run in opposite directions, so the hot inlet faces
the cold *outlet*:

```
    hot:    80 ────────────────► 38
    cold:   47 ◄──────────────── 25

           ΔT₁ = 80 − 47 = 33        ΔT₂ = 38 − 25 = 13
            (hot in, cold out)        (hot out, cold in)
```

**Parallel flow** — both enter the same end:

```
    hot:    80 ────────────────► 38
    cold:   25 ────────────────► 47

           ΔT₁ = 80 − 25 = 55        ΔT₂ = 38 − 47 = −9  ✗ impossible
```

That negative gap is the point: **parallel flow cannot lift the cold stream above
the hot outlet.** Counterflow can, which is why it is used almost everywhere and
why it is the default unless a question says otherwise.

> **Always write the little two-line diagram before computing.** It takes five
> seconds and removes the whole class of end-matching errors.

---

## Rung 38 — Correction factor F

The clean LMTD formula assumes pure counterflow. A **shell-and-tube** exchanger
with multiple passes is partly counterflow and partly parallel, so its true mean
temperature difference is smaller. A correction factor accounts for it:

```
    Corrected LMTD = F × LMTD          (F ≤ 1, typically 0.75–0.95)
```

F comes from charts in the guidebook, indexed by the number of shell and tube
passes. **In the exam it is normally given.** If you are given F, use it. If you
are not, it is a true counterflow arrangement and F = 1.

**Drill 32.** LMTD 22.41 °C, correction factor 0.82.

<details><summary>Answer</summary>

0.82 × 22.41 = **18.37 °C**
</details>

---

## Rung 39 — Area

```
    Q = U × A × LMTD_corrected        ⟹      A = Q / (U × LMTD_corrected)
```

`U` is the overall heat transfer coefficient — how good the exchanger is per unit
area per degree. **Watch its units**, they vary by paper:

| Unit | Then Q must be in |
|---|---|
| W/m²°C | W |
| kW/m²°C | kW |
| kCal/hr·m²°C | kCal/hr |

**Drill 33.** Q = 252,315 W, U = 950 W/m²°C, corrected LMTD 18.37 °C.

<details><summary>Answer</summary>

A = 252,315 / (950 × 18.37) = **14.5 m²**
</details>

**Drill 34.** Q = 26,64,900 kCal/hr, U = 22,300 kCal/hr·m²°C, LMTD 21.47 °C.

<details><summary>Answer</summary>

A = 2,664,900 / (22,300 × 21.47) = **5.57 m²**

A plate heat exchanger — very high U, so very little area. That is their whole
advantage.
</details>

---

## Rung 40 — Effectiveness

Sometimes you are not given outlet temperatures at all. **Effectiveness** is the
fraction of the theoretically possible temperature change that is actually
achieved.

The most the cold stream could *ever* be heated to is the hot stream's inlet
temperature. So:

```
                actual temperature change      T_c,out − T_c,in
    ε  =  ────────────────────────────────  =  ───────────────────
              maximum possible change          T_h,in  − T_c,in
```

Rearranged to give the outlet you need:

```
    T_c,out = ε × (T_h,in − T_c,in) + T_c,in
```

**Drill 35.** Effectiveness 0.4, hot effluent in at 80 °C, cooling water in at
25 °C. Water outlet?

<details><summary>Answer</summary>

```
    T_c,out = 0.4 × (80 − 25) + 25 = 0.4 × 55 + 25 = 47 °C
```

*Sanity:* ε must lie between 0 and 1, so the outlet must fall between 25 and
80 °C. 47 does. ✓
</details>

> ε is dimensionless and can never exceed 1. If yours does, you have used the
> wrong temperature difference underneath.

---

## Rung 41 — Fouling, and why U falls

Scale, biofilm and deposits build an insulating layer on the tubes. `U` drops, so
for the same area the duty falls — or you need a bigger ΔT to shift the same heat.

Symptoms an auditor looks for, and the standard exam answer to "what would you
check":

- Outlet temperature drifting away from design over months
- Rising pressure drop across the exchanger
- The calculated U falling below its design value

The fix is cleaning, and the calculation is: compare **U actual** (back-calculated
from measured duty, area and LMTD) against **U design**.

```
    U_actual = Q / (A × LMTD)
```

---


---

# Part 2 — How an exchanger behaves

Everything above sizes a heat exchanger. None of it says what U *is*, why
counterflow really wins, or what you would recommend after measuring one. Recent
papers ask exactly those things.

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


---

## Putting it together (40 min)

**19th sitting N-2** (`papers/19-1.pdf`) — hot effluent to a plate heat exchanger.

> **Prerequisite check:** the fan and pump power parts need Days 8–9. **Attempt
> the heat exchanger parts only** — heat duty, air mass, water outlet, water flow,
> LMTD and area. The power comparison is deferred to Day 9.

```
    Heat duty  = 63,450 × 1 × (80 − 38)     = 26,64,900 kCal/hr
    Air mass   = 2,664,900 / (0.24 × 30)    = 3,70,125 kg/hr
    Water out  = 0.4 × (80 − 25) + 25       = 47 °C
    Water flow = 2,664,900 / (47 − 25)      = 1,21,132 kg/hr

    counterflow:   hot  80 ──► 38
                   cold 47 ◄── 25
    ΔT₁ = 33,  ΔT₂ = 13,  LMTD = 21.47 °C

    Area = 2,664,900 / (22,300 × 21.47)     = 5.57 m²
```

**The order works for nearly every heat exchanger question in this paper:** duty
first, then the energy balance for the unknown flow, then temperatures, then
LMTD, then area.

Now answer these in words — this is what Part 2 was for:

1. Why is the air-cooled exchanger's U so much lower?
2. Why does the plate exchanger need only 5.57 m² when the air-cooled one is huge?
3. Where is the temperature cross, and what does it prove?
4. What are the two savings in the replacement, and which is larger?

<details><summary>Answers</summary>

1. The **air-side film coefficient** dominates. Series resistances mean the worst
   one governs; air is ~50 W/m²K against water's thousands.
2. Its U is roughly 500× higher, and area scales as 1/U for the same duty and LMTD.
3. Cold water leaves at 47 °C, hotter than the effluent's 38 °C outlet. It **must**
   be counterflow — parallel flow cannot cross.
4. **Fan power replaced by pump power** (the larger — moving air costs far more
   than moving water for the same heat), and a smaller exchanger.
</details>

---

## Block C — Timed question (30 min)

**18th sitting L-2** (`papers/18-1.pdf`) — shell-and-tube, 5 marks, 8 minutes.
Every piece is a drill above.

> **Prerequisite check:** fully covered. The 25th sitting N-1, set here
> previously, needed pump power, fan power and chiller SEC for 14 of its 20
> marks — it now appears on Day 11, after HVAC.

Record start and finish times.

## Block D — Log (20 min)

Tag every lost mark. Log explicitly:

- **What the checking pass caught.** "Caught nothing" is information too.
- Whether every term in every ratio had a written unit.
- Whether the two-line flow diagram was drawn before computing LMTD.

---

## Day 5 checklist

**Calculation (Rungs 35–42)**

- [ ] Can use Q_hot = Q_cold to find an unknown flow
- [ ] Can explain why the mean must be logarithmic
- [ ] Draw the two-line diagram and read ΔT₁, ΔT₂ off the *ends*
- [ ] Know F ≤ 1, given when needed, 1 for true counterflow
- [ ] Can find area, matching U's units to Q's
- [ ] Can apply effectiveness and check 0 ≤ ε ≤ 1

**Behaviour (Rungs 43–49)**

- [ ] Can write U as resistances in series and say which dominates
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

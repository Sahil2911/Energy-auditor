# Day 5 — Heat Exchangers

**Time: 3.5 hours. Book-4 Ch 4 (p. 59).**

Appears in **7 of 8 sittings**. Rungs 35–42.

> Book 4 Ch 4 is not among the chapters BEE publishes online, so the theory here
> is built from first principles and from the past papers' own worked answers.
> Your supplied guidebook has the chapter — tab it (**HX**).

---

## Before you start — the three-line rule

Heat exchanger questions mix **W, kW, kJ and kCal** freely. The 18th sitting's
question is in watts; the 19th's is in kCal/hr.

From `reference/unit-discipline.md`: **no unit conversion inside a fraction bar.**
Each term on its own line, unit written beside it, convert there, divide once at
the end.

This is the chapter where that rule earns its keep.

---

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

## Putting it together (40 min)

**19th sitting N-2** (`papers/19-1.pdf`) — hot effluent to a plate heat exchanger.
Do only the heat exchanger parts; the fan and pump power come on Day 9.

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

Notice the shape: **duty first, then the energy balance for the unknown flow,
then temperatures, then LMTD, then area.** That order works for nearly every
heat exchanger question in this paper.

---

## Block C — Timed questions (55 min)

1. **18th sitting L-2** (`papers/18-1.pdf`) — shell-and-tube, 5 marks, 8 minutes.
   Every piece is a drill above.
2. **25th sitting N-1** (`papers/25-1.pdf`) — pharmaceutical chilled water system,
   20 marks, 30 minutes. Recent, and unseen.

**Record start and finish times for both.** Speed is now tracked.

## Block D — Log (20 min)

Tag every lost mark. Then log, explicitly:

- **What the checking pass caught.** If nothing, write "caught nothing" — that is
  information too.
- Whether every term in every ratio had a written unit.
- Whether the two-line flow diagram was drawn before computing LMTD.

---

## Day 5 checklist

- [ ] Can compute heat duty and use Q_hot = Q_cold to find an unknown flow
- [ ] Can explain why the mean must be logarithmic, not arithmetic
- [ ] Draw the two-line diagram and read ΔT₁, ΔT₂ off the *ends*
- [ ] Know why counterflow beats parallel flow
- [ ] Know F ≤ 1, is given when needed, and is 1 for true counterflow
- [ ] Can find area, matching U's units to Q's
- [ ] Can apply effectiveness and sanity-check 0 ≤ ε ≤ 1
- [ ] Can back-calculate U to assess fouling
- [ ] Both timed questions done, times recorded, checking pass logged

**Tomorrow (Day 6):** furnaces, waste heat recovery and insulation.

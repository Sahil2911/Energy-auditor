# Diagnostic — Electrical and Fluid Systems

**Scheduled after Day 10. 30 marks, 45 minutes.**

Covers Days 8, 9 and 10 — pumps, fans, compressed air, motors, VSDs and cooling
towers. Book-4 chapters 5, 6, 7 and 8.

> **Prerequisite check — data-item level.** Every quantity in both numericals maps
> to a taught rung. Section III uses cooling tower effectiveness and approach
> (Rung 103), the evaporation formula (104), COC and blowdown (105), and a sump
> mass balance. Nothing orphaned.

## Rules

- **One sitting, timer visible, guidebooks only.** No notes, no reference files
  from this repository.
- Formula → substitute → evaluate.
- **Sanity sentence on every final answer.**
- **Run the checking pass** before stopping, and record what it caught.
- **Record start and finish times.**

---

# SECTION I — True or False (5 × 1 = 5 marks, 5 minutes)

1. A centrifugal pump rated for 50 m of head will develop the same discharge
   pressure whether it is pumping water or brine.

2. Reducing a centrifugal pump's speed to 70% reduces its power consumption to
   approximately 34% of the original.

3. In a heat exchanger where water flows on one side and air on the other,
   increasing the water velocity is the most effective way to raise the overall
   heat transfer coefficient.

4. An induction motor running at exactly its synchronous speed would produce no
   torque.

5. A cooling tower achieving a cold water temperature of 30 °C on a day with a
   wet bulb of 25 °C is performing worse than one achieving 32 °C on a day with a
   wet bulb of 28 °C.

   *(Corrected: the original answer key marked this False on the claim that both
   approaches were 5 °C. They are 5 °C and 4 °C. The answer is **True**.)*

---

# SECTION II — Short Numerical (5 marks, 8 minutes)

**16th sitting L-2** — `papers/16.pdf`

> A pump draws water through a 150 mm diameter pipe with a suction head of **3 m
> below the pump centre line**. The actual power input to the motor is 16.7 kW at
> a motor efficiency of 90%. The discharge pressure is 4.5 kg/cm² and the water
> velocity in the pipe, by ultrasonic meter, is 1 m/s.
>
> Find the pump efficiency.

---

# SECTION III — Long Numerical (20 marks, 30 minutes)

**24th sitting N-3** — `papers/24-1.pdf`

A steam turbine power plant with an induced draft cooling tower. Steam to
condenser 440 T/hr; 45 m³ of circulating water per tonne of steam condensed.

Two makeup pumps of 220 m³/hr each in parallel: **one alone delivers 200 m³/hr,
both together deliver 350 m³/hr.** One runs continuously; the second starts when
the sump falls below 90% of full and stops when it is full again.

Circulating water TDS 2,000 ppm; makeup water TDS 500 ppm. Tower effectiveness
63%, approach 4 °C. Sump 100 m × 15 m × 40 m, with continuous blowdown.

Calculate:

- **(a)** Evaporative loss and blowdown in m³/hr, and **draw the mass flow diagram**
  with all flows and losses — *10 marks*
- **(b)** For how many hours does only one makeup pump run? — *5 marks*
- **(c)** For how many hours do both pumps run? — *5 marks*

> Part (a) explicitly asks for a **diagram**. Draw it — marks are allocated to it,
> and a labelled sketch of flows in and out is the fastest way to see parts (b)
> and (c).

---

*Stop. Finish everything, run the checking pass, then continue.*

---

# ANSWERS

## Section I

<details><summary>Answers with reasons</summary>

1. **False.** Head is the pump's property; pressure is the fluid's response.
   `p = ρgH`, so 50 m gives 4.9 bar on water and 6.1 bar on brine. (Day 8, Rung 73)

2. **True.** `P ∝ N³`, and 0.7³ = 0.343. (Day 8, Rung 79)

3. **False.** The resistances are in series and the **air film dominates** — it can
   be 100× the water-side resistance. That is why such exchangers are finned: you
   add area on the air side because you cannot fix its film coefficient.
   (Day 5, Rung 37)

4. **True.** Current is induced by relative motion. At synchronous speed the field
   appears stationary to the rotor, no EMF is induced, no rotor current flows, and
   no torque is produced. (Day 10, Rung 95)

5. **True.** Judge a tower against the **wet bulb**, never an absolute temperature —
   and doing so here gives approaches of **5 °C and 4 °C**. The second tower has the
   tighter approach and is therefore the better performer, so the first *is* performing
   worse. (Day 10, Rung 102)

   > **Answer key error, found by the student.** This was originally marked False on
   > the assertion that both approaches were 5 °C. 32 − 28 = 4. The intended question
   > needed 33 °C against a 28 °C wet bulb; the numbers as written make the statement
   > true. She answered False first, then struck it out and wrote True — which means
   > she computed both approaches rather than pattern-matching the rule.
</details>

## Section II

<details><summary>Pump efficiency</summary>

```
    Flow:   Q = π/4 × 0.15² × 1 = 0.01767 m³/s  (= 63.6 m³/hr)        [1]

    Head:   discharge 4.5 kg/cm² = 45 m
            suction is 3 m BELOW the pump — a lift, so −3 m
            H = 45 − (−3) = 48 m                                       [1]

    Hydraulic power = 1000 × 9.81 × 0.01767 × 48 / 1000 = 8.32 kW      [1]

    Shaft power = 16.7 × 0.90 = 15.03 kW                               [1]

    Pump efficiency = 8.32 / 15.03 × 100 = 55.4 %                      [1]
```

> **The second trap.** Dividing hydraulic power by the *motor input* of 16.7 kW
> gives 49.8% — that is the **overall pump-set efficiency**, not the pump
> efficiency. The question asks for the pump. The motor efficiency must be applied
> first. The two answers differ by exactly the motor efficiency: 49.8/55.4 = 0.90.

**The sign is the whole question.** Reading the suction as +3 gives H = 42 m and
an efficiency of 48.5% — plausible-looking and wrong.

*Sanity:* 55% is poor for a pump (65–85% is normal) — which is presumably the
point of the question.
</details>

## Section III

<details><summary>Cooling tower and sump</summary>

**(a)**

```
    CW flow  = 440 × 45                         = 19,800 m³/hr

    Effectiveness = Range/(Range + Approach)
    0.63 = R/(R + 4)   ⟹   R = 0.63 × 4/0.37    = 6.81 °C

    Evaporation = 0.00085 × 1.8 × 19,800 × 6.81 = 206.3 m³/hr

    COC = 2000/500                              = 4
    Blowdown = E/(COC − 1) = 206.3/3            = 68.8 m³/hr

    Makeup = E + B                              = 275.1 m³/hr
```

Mass flow diagram: 19,800 m³/hr circulating; 206.3 evaporating from the tower;
68.8 leaving as blowdown; 275.1 entering as makeup.

**(b)** One pump delivers 200 m³/hr against a 275.1 m³/hr demand:

```
    Deficit    = 275.1 − 200 = 75.1 m³/hr
    Sump       = 100 × 15 × 40 = 60,000 m³,  10% = 6,000 m³
    Time to fall to 90% = 6,000 / 75.1 = 79.9 hours
```

**(c)** Both pumps deliver 350 m³/hr:

```
    Surplus = 350 − 275.1 = 74.9 m³/hr
    Time to refill 6,000 m³ = 6,000 / 74.9 = 80.1 hours
```

*Sanity:* the two periods are nearly equal because the deficit and surplus are
nearly equal — the pumps are well matched to the duty. Worth stating.

**Note the parallel-pump trap:** two 220 m³/hr pumps do not deliver 440 together.
They deliver 350, because adding a pump in parallel raises the system resistance
and both slide back along their curves. The question hands you the real figures —
use them, not the ratings.
</details>

---

# SCORING

| Section | Marks | Yours |
|---|---|---|
| I — True/False | 5 | |
| II — Pump efficiency | 5 | |
| III — Cooling tower | 20 | |
| **Total** | **30** | |

**Pass equivalent: 15/30.**

| Score | Reading | Action |
|---|---|---|
| 24+ | Strong — Phase 2 secure | Proceed to Day 12 |
| 15–23 | Passing, gaps identified | Proceed; re-drill where tags concentrate |
| Under 15 | Phase 2 not holding | Repair before Day 12 |

## Diagnostics to record

- **Start and finish times**
- Every lost mark tagged: concept / method / arithmetic / units / reading / time
- **What the checking pass caught** — "caught nothing" is information
- Whether the mass flow diagram was drawn before calculating (b) and (c)

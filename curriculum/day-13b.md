# Day 13B — Buildings and Building Cooling Load

**Time: 1.5 hours. Book-4 Ch 14 (p239).** Rungs 154–162.

> **Why this session exists.** Chapter 14 was the last Book-4 chapter with no
> lesson behind it. It appears in **2 of 8** machine-readable sittings (17th and
> 23rd) — but when it appears it is a **full 20-mark N-3/N-4 option**, and it is
> the *easiest* twenty marks in the book, because the physics is `U·A·ΔT` which
> you have used since Day 5. Leaving it uncovered would have been leaving free
> marks on the table.
>
> This also closes chapter coverage at **15 of 15**.

> **Prerequisite check — data-item level.** The timed question (23rd N-4(A)) uses
> every item it supplies except two: the motor efficiency of 90% in part B, and the
> outdoor WBT of 26 °C. Both are genuinely unused in BEE's own model answer. See
> Rung 162 — this is the second over-supplied question in two days, and knowing
> that is now part of the skill.

---

## Rung 154 — What "cooling load" actually means

On Day 11 you sized chillers in TR and computed kW/TR. **Where did the TR come
from?** Somebody counted the heat leaking into the space. That count is the
cooling load, and it is what an energy auditor recomputes when a client asks
"is my chiller oversized?" or "will insulation pay?".

A conditioned room is a box that heat gets into by every route physics allows:

```
                         ☀ sun through glass
                         │
      ┌──────────────────▼──────────────────┐
  →   │  people  lights  computers          │  ← conduction through roof
 air  │                                     │  ← conduction through walls
 leaks│         25 °C, 50 % RH              │  ← conduction through windows
      └─────────────────────────────────────┘
```

The auditor's job is to list every arrow, put a number on it, and add them up. The
list is always the same eight items, and **an examiner marks the list, not the
arithmetic** — so learn the list.

| | External (comes from outside) | Internal (generated inside) |
|---|---|---|
| 1 | Conduction through **walls** | 5. **People** — sensible + latent |
| 2 | Conduction through **roof** | 6. **Lighting** |
| 3 | Conduction through **windows** | 7. **Equipment** |
| 4 | **Solar radiation** through glass | 8. **Infiltration** — sensible + latent |

Write those eight rows down the left of your page *before* you calculate anything.
That is your answer's skeleton, and it earns marks even where a number goes wrong.

---

## Rung 155 — Sensible and latent, and why the split matters

Two kinds of heat enter the room, and they are not interchangeable:

- **Sensible heat** changes the air's *temperature*. A thermometer sees it.
- **Latent heat** changes the air's *moisture*. A thermometer does not see it; the
  coil still has to remove it, by condensing the water out.

Only three of the eight items have a latent part: **people** (they sweat and
breathe), **infiltration** (outdoor air is more humid), and any wet process in the
room. Walls, roofs, glass, lights and computers are purely sensible — they add no
water.

So your answer table has **two number columns**, and you total both:

```
    Total cooling load = Σ sensible + Σ latent
```

> **Why an examiner cares.** The sensible/latent split sets the coil's design
> condition. A room full of people needs a colder coil than its temperature alone
> suggests, because the coil must also get below the dew point. Getting the split
> right, not just the total, is what separates a 16 from a 20.

---

## Rung 156 — CLTD: conduction with the sun's memory built in

You know conduction:

```
    Q = U × A × ΔT
```

For a wall in the sun, what is ΔT? Not simply (36 − 25). A dark roof at noon has a
surface far hotter than the air, **and** the heat it absorbed at noon does not
arrive inside until 3 pm, because the slab has thermal mass.

Rather than make you solve a transient conduction problem, ASHRAE pre-computed the
answer and published it as an **equivalent** temperature difference — one that,
used in the plain steady formula, gives the right instantaneous load:

```
    CLTD = Cooling Load Temperature Difference
    Q = U × A × CLTD
```

**CLTD is not a temperature difference you can measure.** It is a lookup that
already contains the solar absorption, the surface film, the thermal lag and the
time of day. It is *always* given in the question. Never try to derive it, and
never substitute (T_out − T_in) for it.

Look at the values the 23rd sitting gives and read them physically:

| Surface | CLTD | Why |
|---|---|---|
| Wall | 12 °C | Vertical, part-shaded, heavy |
| **Roof** | **42 °C** | Horizontal, full sun all day, dark |
| Window | 8 °C | Thin, so almost no lag — near the real air ΔT |

**The roof dominates.** 42 against 12 is why "insulate the roof" is the standard
first recommendation for an Indian commercial building, and why the payback part
of the question is always about the roof.

> **The net-area trap.** Windows are set *into* walls. Wall area for conduction is
> **gross wall − window area**. The 23rd sitting gives wall 45 m² and window 15 m²,
> and the model answer uses **30 m²**. Count the window's heat once, not twice.

---

## Rung 157 — Solar gain through glass: a different mechanism

Glass does two things at once and they are counted separately:

1. It **conducts** — that is the `U × A × CLTD` row, already handled.
2. It **transmits** sunlight straight through, which becomes heat when it lands on
   the floor. Conduction has nothing to do with this.

For the transmitted part:

```
    Q_solar = A_glass × SC × SCL
```

- **SCL**, Solar Cooling Load factor (W/m²) — how much solar energy the glass
  passes at that orientation and hour. Given.
- **SC**, Shading Coefficient — a **dimensionless multiplier ≤ 1** comparing this
  glass to plain 3 mm clear glass. SC = 0.84 means it passes 84% of what clear
  glass would; tinted or low-e glass runs 0.3–0.5, and an internal blind lowers it
  further.

**Both glass rows appear in the table.** The 23rd sitting's window contributes 360 W
by conduction and **6300 W** by solar transmission — seventeen times more. Solar
gain through glass is usually the second-largest single item after the roof.

---

## Rung 158 — Internal gains: people, lights, equipment

**People.** A seated adult emits ~130 W, split ~80 sensible / ~50 latent. Both are
given.

```
    sensible = N × sensible/person × CLF
    latent   = N × latent/person              ← NO CLF
```

**Why no CLF on latent?** The **Cooling Load Factor** accounts for *storage*: heat
radiated to the walls and furniture is absorbed and released later, so not all of
it hits the coil this hour. Moisture cannot be stored in a wall — it goes straight
into the air and straight to the coil. **So CLF applies to sensible gains only.**
Applying it to the latent row is the most common single error on this question.

**Lighting.** Two multipliers, and both are physically real:

```
    Q_light = (W/m² × floor area) × ballast factor × CLF
```

- **Ballast factor** (~1.2 for fluorescent): the control gear burns real watts on
  top of the lamp's rating, and they all end up as heat in the room.
- **CLF**: some of the lamp's output is radiant and reaches the coil later.

*(An LED retrofit removes the ballast factor and cuts the lamp watts — which is why
lighting upgrades in air-conditioned buildings save twice: once at the meter, once
at the chiller. Worth one sentence in any answer.)*

**Equipment.** `W/m² × floor area`. Sensible only. No factors.

---

## Rung 159 — Infiltration: the two constants, derived

Air leaks in around doors and windows. It arrives hot and humid and has to be
brought to room condition.

**First, the flow.** "Air changes per hour" means the room's whole volume is
replaced that many times an hour:

```
    V̇ (m³/s) = (room volume × ACH) / 3600
```

**Then, two loads.** Both are `flow × property × difference`:

```
    Q_sensible = 1210 × V̇ × (T_out − T_in)            watts
    Q_latent   = 3010 × V̇ × (W_out − W_in)            watts, W in g/kg
```

Those constants are not arbitrary — check them:

```
  1210 :  ρ × Cp of air = 1.2 kg/m³ × 1005 J/kg·K ≈ 1210 J/m³·K       ✓
          so 1210 × (m³/s) × (K) = J/s = W

  3010 :  ρ × h_fg = 1.2 kg/m³ × 2500 kJ/kg ÷ 1000 (g→kg)
                   = 1.2 × 2500 = 3000 J per m³ per g/kg              ✓
```

**1210 is `ρCp` and 3010 is `ρh_fg`.** Both are supplied in the question, so you do
not need to memorise them — but recognising what they are tells you instantly which
one multiplies temperature and which multiplies humidity. That is the only decision
in this rung, and it is a 2-mark decision.

> **Humidity units.** The question gives 19 and 11 **grams** of water per kg of dry
> air. Do not convert to kg — 3010 is already built for g/kg. If you divide by 1000
> you will report a latent load a thousand times too small.

---

## Rung 160 — From load to power: the shortcut that always works

Once you have a cooling load in watts and a COP, the electrical power is:

```
                cooling load (W)
    Power (W) = ─────────────────
                      COP
```

That is just the definition of COP from Day 11, rearranged. Nothing else needed.

BEE's model answers take a longer route — watts → TR → kCal/hr → ÷COP → ÷860 → kW.
**It gives the same answer, and here is why:**

```
    1 TR = 3516 W  =  3024 kCal/h
    1 kW = 1000 W  =   860 kCal/h

    3516/3024 = 1.1627         1000/860 = 1.1628      ← the same ratio
```

The TR cancels itself out. So `W ÷ 3516 × 3024 ÷ COP ÷ 860 × 1000` is exactly
`W ÷ COP`. Use whichever you like — but **know they must agree**, and if they don't,
you have dropped a factor.

Then the money, straight from Day 13 Rung 150:

```
    annual saving ₹ = power saved (kW) × operating hours × tariff
    simple payback  = investment / annual saving
```

---

## Rung 161 — Worked: the roof insulation payback (23rd N-4(A) part B)

Roof U improves from 0.363 to 0.300 W/m²K. Cost ₹40,000. COP 3.75, 6000 h/yr,
₹10/kWh.

```
  old roof gain = 0.363 × 400 × 42        = 6098.4 W
  new roof gain = 0.300 × 400 × 42        = 5040.0 W
  load saved                              = 1058.4 W

  power saved   = 1058.4 / 3.75           = 282.2 W = 0.282 kW
  annual saving = 0.282 × 6000 × 10       = ₹16 920
  payback       = 40 000 / 16 920         = 2.36 years
```

**Only the roof row changes.** Every other item in the table is untouched by roof
insulation, so recomputing the whole 32 kW load is wasted time — compute the *delta*
and you are done in four lines.

> **The unused 90%.** The question supplies "efficiency of the motor coupled with
> the compressor: 90%", and BEE's model answer never uses it. Dividing by 0.9 would
> give 0.3136 kW, ₹18,817/yr and a **2.13-year** payback — arguably more correct,
> since the electricity meter sees motor input, not shaft power (the Day 11
> COP-vs-kW/TR basis warning, exactly). **Write the model answer's number, then add
> one line:** *"including 90% motor efficiency, payback = 2.13 years."* You cannot
> lose marks for the sentence, and you may gain one.

---

## Rung 162 — What to do when data is left over

Two questions in two days have supplied data their own model answers never use —
the cement WHRB's gas temperatures, and this motor efficiency. So the rule needs
stating properly:

**"Unused data is a tell" is a check on *my* curriculum, not a law about BEE's
papers.** If I set you a question and something is left unused, it usually means I
have not taught a step. In the real exam it more often means the paper included
context, or a route the setter considered and dropped.

**What to do in the exam, in order:**

1. Finish every part the question explicitly asks for.
2. Look at what is left over. Ask once: *is there a named quantity here I have not
   produced?* If yes, that is a missed step — go back.
3. If not, write **one line** saying why it is not needed, or how it would change
   the answer if used.
4. Move on. **Do not spend a second minute on it.**

Never let leftover data stop you finishing. A complete answer with one unused input
scores far better than an incomplete answer hunting for a use.

---

# Block C — Timed question (30 minutes)

**23rd sitting, N-4(A)** — `papers/23-1.pdf`, both parts, 20 marks.

Build the eight-row table first. Then fill it.

<details><summary>Model answer — open only after you have finished and timed yourself</summary>

**External**

```
  wall     = 0.35  × (45 − 15) × 12   =   126.0 W      ← net wall area
  roof     = 0.363 × 400      × 42    =  6098.4 W
  windows  = 3.00  × 15       ×  8    =   360.0 W
  solar    = 15 × 0.84 × 500          =  6300.0 W
```

**Internal**

```
  people  sensible = 30 × 80 × 0.9    =  2160.0 W
          latent   = 30 × 50          =  1500.0 W     ← no CLF
  lighting = 21 × 400 × 1.2 × 0.9     =  9072.0 W
  equipment= 6.3 × 400                =  2520.0 W

  infiltration flow = (400 × 3.9 × 0.25)/3600 = 0.11 m³/s
          sensible = 1210 × 0.11 × (36 − 25) =  1464.1 W
          latent   = 3010 × 0.11 × (19 − 11) =  2648.8 W
```

**Totals**

| # | Component | Sensible W | Latent W |
|---|---|---|---|
| 1 | Wall conduction | 126.0 | |
| 2 | Roof conduction | 6098.4 | |
| 3 | Window conduction | 360.0 | |
| 4 | Solar through glass | 6300.0 | |
| 5 | People | 2160.0 | 1500.0 |
| 6 | Lighting | 9072.0 | |
| 7 | Equipment | 2520.0 | |
| 8 | Infiltration | 1464.1 | 2648.8 |
| | **Total** | **28 100.5** | **4148.8** |

```
    Total cooling load = 28 100.5 + 4148.8 = 32 249 W  ≈ 32.25 kW  ≈ 9.2 TR
```

**Part B** — as Rung 161: **₹16,920/year, payback 2.36 years** (2.13 years if the
90% motor efficiency is applied).

**Sanity check:** 9.2 TR for a 400 m² office is 43 m² per TR. Indian design practice
is 30–40 m²/TR for offices, so this building is at the light end — consistent with
its modest 30 occupants.

</details>

---

# Drill

| # | Question | Paper | Marks | Budget |
|---|---|---|---|---|
| 72 | Building heat gain / cooling load | 17th sitting | 20 | 30 min |

---

## Day 13B checklist

- [ ] **Can write the eight-row load table from memory**, before calculating
- [ ] Know which three items have a latent part, and that lights and walls do not
- [ ] Know CLTD is a lookup containing solar and thermal lag, never `T_out − T_in`
- [ ] **Use net wall area** (gross − windows)
- [ ] Know glass appears twice: conduction *and* solar transmission
- [ ] **Apply CLF to sensible gains only** — never to the latent row
- [ ] Know the ballast factor is real extra watts, and why LEDs save twice
- [ ] Can compute infiltration flow from ACH, and know 1210 = ρCp, 3010 = ρh_fg
- [ ] **Know `power = load ÷ COP`** and why the TR route gives the same answer
- [ ] Can compute a delta-load payback without redoing the whole table
- [ ] Know what to do with leftover data — one line, then move on

**Next:** the **sector & systems diagnostic** — 40 marks, 2 long questions,
60 minutes, covering Days 11–13B. Then Day 14, Full Mock 1, under exam conditions.

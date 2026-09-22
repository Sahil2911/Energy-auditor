# Review — Monday 1.4 · 21st sitting N-4(C), two-unit coal power station

**04:55 → 05:32 = 37 minutes** against a 25-minute budget. Both times written —
**good, keep doing that.** The overrun is entirely in part 1, which is fair: a full
indirect-method boiler efficiency is a 10-mark part and you worked all seven losses.

## Score: 10.5 / 20

| | Part | Marks | You | |
|---|---|---|---|---|
| 1 | Unit 1 boiler efficiency (indirect) | 10 | **86.176 %** *(BEE 85.88)* | **8.5** |
| 2 | Which unit is more efficient | 2 | "Unit 1" | **0** |
| 3 | Difference in coal per day, 75% load | 5 | two TPH figures, no difference | **2** |
| 4 | Station net heat rate | 3 | 6258.03 | **0** |

---

# ✅ First — the thing you did right, and it is yesterday's lesson

**Twice in part 1 you wrote a loss, saw it was absurd, and went back.**

```
    L2 = [584 + 9(0.025)(0.24)(140)]/4000   = 14.789    "impossible"
    ⟹  L2 = 9(0.025)[584 + 0.24(140)]/4000  =  3.474    ✓ structure correct

    L3 = [584 + (0.133)(0.24)(140)]/4000    = 14.711    "impossible"
    ⟹  L3 = 0.133[584 + 0.24(140)]/4000     =  2.054    ✓ structure correct
```

**That is exactly the discipline the last review asked for**, and you applied it
unprompted, twice, on the same page. **The bracket fix is also right**: the mass of
water multiplies the *whole* bracket, because every kilogram of it must be both
evaporated (584) and superheated (Cp ΔT). Writing `584 + m·Cp·ΔT` charges the
latent heat once for the fuel instead of once per kilogram of water — which is why
it came out at 14%.

> **The alarm fired twice and you acted twice. Hold on to that.** The rest of this
> review is about the one place it did not fire.

---

# Part 1 — 8.5/10. The method is complete; one constant is the wrong substance

**Everything structural is right:**

```
    TA    = 11.6(0.40) + 34.8(0.025 − 0.075/8) + 4.35(0.005)  = 5.206  ✓
    EA    = 3/(21 − 3)                                        = 16.667 % ✓
    AAS   = 5.206 × 1.16667                                   = 6.075  ✓
    m_dfg = AAS + 1 − (M + 9H₂ + ash)                         = 6.367  ✓
    L5 CO = (0.015 × 0.40)/(0.015 + 7) × 5654/4000            = 0.121 % ✓
    L6 ash: fly 0.35×⅘×200/4000 = 1.40 · bottom 0.35×⅕×500/4000 = 0.875
            total                                             = 2.275 % ✓
```

**The CO conversion deserves a mention:** the paper gives *150 ppm* and you used
*0.015%*. `150/10000 = 0.015`. Silently correct, and it is a step many candidates
get wrong.

## ⚠️ The one error: Cp changes substance partway down the loss list

You used **0.24 for every loss**. The data table says *"Specific Heat of **Flue
Gas** = 0.24"* — **that is the gas**, and it applies to L1 only.

**L2, L3 and L4 are not about flue gas. They are about water vapour.**

```
    L1   dry flue gas                  →  Cp = 0.24   ← the table's value
    L2   H₂ burnt to water             →  Cp = 0.45   ← WATER VAPOUR
    L3   moisture in the fuel          →  Cp = 0.45   ← WATER VAPOUR
    L4   moisture in the air           →  Cp = 0.45   ← WATER VAPOUR
```

**Ask one question at each loss: what substance am I heating?** The 584 in L2 and
L3 is water's latent heat — the presence of that number *tells you* the stream is
water, so the Cp beside it must be water vapour's.

| | You (0.24) | Correct (0.45) |
|---|---|---|
| L2 H₂ | 3.474 | **3.639** |
| L3 fuel moisture | 2.054 | **2.151** |
| L4 air moisture | 0.102 | **0.190** |
| **η_boiler** | **86.176 %** | **85.83 %** *(BEE 85.88)* |

> **This one has been here before.** It is Day 3's Rung 13 — *"Cp flue gas vs
> vapour confused"* was the first concept error logged in this whole programme, on
> 31 August. **It has regressed.** Put the two numbers on the exam card as a pair:
>
> ```
>     0.23–0.24  →  DRY FLUE GAS        (L1 only)
>     0.45       →  WATER VAPOUR        (L2, L3, L4 — wherever 584 appears)
> ```

**Why it matters beyond 0.35 points:** the boiler efficiency is the denominator of
part 2 and therefore of parts 3 and 4. Your 86.176% gives Unit 1 a gross heat rate
of 2843 where BEE gets 2853 — and the *coal difference* in part 3 moves from
56.5 TPD to 47.7, a 16% swing from one constant.

---

# ⚠️ Part 2 — 0/2. You climbed the rung correctly and then named the wrong winner

**The hard part was right:**

```
    Unit 1 is quoted as a TURBINE heat rate (2450) — rung 1
    Unit 2 is quoted as a UNIT heat rate    (2790) — rung 2
    Unit 1 gross = 2450/0.862 = 2842.2      ⟹ now both on rung 2  ✓
```

**That is the basis trap, and you saw straight through it.** In Mock 3 this is the
step that stopped you. It no longer does.

**Then:**

> *"∴ Unit 1 HR > Unit 2 HR ∴ Unit 1 is more efficient"*

**The premise is true and the conclusion is backwards.** BEE's key says it in as
many words: *"Heat rate of unit 1 is higher than heat rate of unit 2, hence unit 2
is more efficient."*

### Heat rate is an inverse quantity. Lower is better.

```
    heat rate  =  kCal of fuel  PER  kWh produced
                  ───────────
                  the COST side is on top
```

**It is a price, not a score.** More fuel per unit is worse, exactly as ₹ per kg is
worse when it is higher. The same family as **kW/TR** and **specific energy
consumption** — all three read backwards. *(`reference/reciprocal-traps.md`)*

> ### The fix that makes the inversion impossible
>
> **Do not conclude on the heat rate. Convert to efficiency and conclude on that.**
>
> ```
>     Unit 1:  860/2842.2  =  30.25 %
>     Unit 2:  860/2790    =  30.82 %     ⟹  Unit 2   ← higher is better, always
> ```
>
> **Two extra divisions, and the sentence writes itself in the direction your
> intuition already runs.** Efficiency behaves the way you expect; heat rate does
> not. When a question asks *which is better*, spend the ten seconds.

---

# Part 3 — 2/5. Two rates computed, and the question's actual demand left blank

**Unit 2 is right:**
```
    200000 kW × 2790/4000 = 139.5 TPH  →  × 0.75 = 104.625 TPH  ✓
```

**Unit 1 has a digit transposition:**
```
    200000 × 2842.227/4000  =  142.111 TPH     ← you wrote 141.211
                             × 0.75 = 106.583  ← you wrote 105.908
```
**142.111 became 141.211** — the `2` and the `1` swapped. Nothing conceptual, and
nothing a recheck would miss: your own Unit 2 line is 139.5, so Unit 1 at a 2%
higher heat rate must land near 142, not 141.

## ⚠️ But the marks went elsewhere: you never answered the question

**The question asks for the *difference* of coal consumed *per day*.** You produced
two hourly rates and stopped.

```
    Difference = (106.583 − 104.625) TPH × 24 h  =  47.0 TPD
    BEE, using 2852.8                            =  56.5 TPD at 75 % load
                                                 =  64.1 TPD at 85 % load
```

*(BEE prints both loads and the note says marks were awarded for either. The
question body specifies 75%, so 75% is the safe answer — but say which you used.)*

> ### Read the last noun of the question before you stop
>
> ```
>     "the DIFFERENCE of coal consumed PER DAY between unit 1 & unit 2"
>                ▲                        ▲
>          a subtraction            × 24, not per hour
> ```
> **Three of the five marks were in two arithmetic steps you did not take** — after
> doing all the hard work that made them possible. **When you finish a part, reread
> the question and check that the thing on your page is the thing it named.**

---

# ⚠️ Part 4 — 0/3. Heat rates cannot be added

```
    You wrote:   NHR = (2842.227 + 2790)/(1 − 0.1)  =  6258.03 kCal/kWh
```

### Why this cannot be right, before any formula

**A heat rate is a ratio — fuel per unit of output.** Ratios do not add. Put two
identical cars in a garage and the garage does not do 30 km/litre because each does
15. **Adding two heat rates describes a station that burns both units' fuel to make
one unit's electricity.**

### The general form, which always works

```
                        total heat into the station
    Station gross HR = ─────────────────────────────
                        total kWh out of the station

                       HR₁ × kWh₁  +  HR₂ × kWh₂
                     = ──────────────────────────     ← a GENERATION-WEIGHTED average
                            kWh₁  +  kWh₂
```

**Here both units are 200 MW at the same load**, so the weights are equal and it
collapses to the plain average:

```
    Station gross = (2842.2 + 2790)/2       = 2816.1   (BEE: 2821.4)
    Station net   = 2816.1/(1 − 0.10)       = 3129     (BEE: 3135)
```

> **Keep the general form, not the shortcut.** If the units were 200 MW and 500 MW,
> or at different loads, the plain average would be wrong too. **The weights are
> the generations.**

## And this is the one place the alarm did not fire

**6258 kCal/kWh implies a plant efficiency of `860/6258 = 13.7%`.**

**No thermal power station has ever run at 14%.** A coal unit is 28–36%; even a
1900s engine beat 14%. The number was as impossible as the 14.789 you rejected
twice on the previous page — **and this time it went down unchallenged.**

> ### Why it slipped past, and the guard
>
> The two you caught were **percentages**, where you have a strong instinct: a
> single boiler loss of 14% is visibly wrong. **You have no equally strong instinct
> for kCal/kWh** — 2800 and 6258 are both just four-digit numbers.
>
> **So give heat rate a range, the way you already have one for losses:**
> ```
>     turbine heat rate     2000 – 2600
>     gross / unit          2300 – 3000
>     net / station         2600 – 3300
>     ANY of them > 4000    ⟹  something is wrong, unless it is a
>                               back-pressure cogen set (30,000+)
> ```
> **And the free check:** every heat rate has an efficiency. `860/answer`. If it is
> not between 25% and 40% for a condensing plant, stop.

---

# What to carry into 1.5 (24th N-4(A))

1. **`0.24 dry flue gas · 0.45 water vapour.`** On the card as a pair. Wherever 584
   appears, the Cp beside it is 0.45.
2. **Conclude on efficiency, never on heat rate.** `860/HR` for both, then compare.
3. **Heat rates are averaged by generation, never added.**
4. **`860/answer` on every heat rate you produce.** 25–40% or start again.
5. **Reread the question's last noun before moving on** — *difference*, *per day*,
   *per tonne*, *annual*. This cost 3 marks today and it is the cheapest of all the
   fixes.

**1.5 is the natural next one:** it is the ladder again (2040/0.87 and 2000/0.87),
it asks for a *coal saving per day* — the same last-noun discipline — and it hides
two unused numbers to see whether you will force them in.

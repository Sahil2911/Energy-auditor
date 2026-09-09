# Day 17 — Triage and Units

**Time: 2 hours.** Rungs 170–174.

Built from Mock 2's error tally, which is short and lopsided:

```
   ~11 marks   never attempted        ← Rungs 170–171
     6 marks   unit conversions        ← Rungs 172–173
     4 marks   Section I directions    ← Rung 174
```

**Only four marks were concept losses.** This session is a clock and a units habit.
There is no new engineering in it.

---

## Rung 170 — Marks per minute, and the twenty-five minute rule

You spent 129 minutes on Section III against a 100-minute budget and still left a
question eleven marks short. **The paper was not too hard. The order was wrong.**

### The arithmetic that settles it

Every question part has a rate: marks available ÷ minutes to earn them. Look at
what was on the table at minute 120 of Mock 2:

| Available work | Marks | Minutes | **Marks/min** |
|---|---|---|---|
| N-3 A(iv) — one multiplication on a number already computed | 3 | ~1 | **3.0** |
| N-3 B(i) — one subtraction over another, four table values | 3 | ~1 | **3.0** |
| N-3 A(v) — %O₂ from EA, then the leakage formula | 3 | ~4 | 0.75 |
| The 26th minute of a question already 25 minutes deep | ~1 | 1 | **~0.5–1.0** |

**A(iv) and B(i) were worth six marks in about three minutes.** That is five times
the rate of grinding on a question you are already deep inside.

> ### The rule
>
> **At 25 minutes on a long question, stop where you are and move on.** Mark the
> page, leave a gap, return only if time remains after every question has been
> opened.
>
> **Corollary — never spend a 26th minute on a question while an untouched part of
> another sits at three marks.**

### Why 25

100 minutes ÷ 4 long questions. If every question gets its 25, all four get opened
and the cheap parts of all four get taken. Mock 2's actual split was roughly
32 / 32 / 33 / 32 — four questions each slightly over, and the fourth paid for it.

**The 25 is not a target to hit.** Most questions will finish inside it. It is a
ceiling that stops one question eating another's marks.

---

## Rung 171 — Read all the parts first, and take the one-liners

The other half of the same fix, and it costs ten seconds per question.

**When you turn to a long question, read every sub-part before you start
calculating.** You are looking for two things:

1. **One-liners** — a part that needs one operation on something the earlier parts
   already produced, or one lookup straight from the data table.
2. **Dependencies** — which parts need which, so you know what is lost if you
   abandon early.

Mock 2's N-3, read that way:

```
   A(i)   dry flue gas loss at design       — needs work, feeds (iii)
   A(ii)  same at operating                 — needs work, feeds (iii)
   A(iii) the increase                      — subtraction of (i) and (ii)
   A(iv)  × 7000 h × ₹9500/T                — ONE-LINER, needs only (iii)   ★
   A(v)   %O₂ from EA, then leakage         — independent of all the above
   B(i)   (294−40)/(315−40)                 — ONE-LINER, straight off the table ★
   B(ii)  actual air from measured O₂       — independent
```

**Two starred one-liners and two independent parts.** A(v), B(i) and B(ii) needed
nothing from A(i)–(iv) at all — they could have been done *first*, in any order, in
about six minutes for eight marks.

> **The habit:** before the first calculation, put a **★** against every part you
> can answer in under two minutes, and a **|** against every part that does not
> depend on the ones above it. Do the stars first.

**Self-check — mark up Mock 2's N-1 the same way.**

<details><summary>Answer</summary>

```
   i)   steam to turbine    — needs work
   ii)  steam to chiller    | independent of (i)          ★ two lines
   iii) steam to process    — needs (i) and (ii)
   iv)  biogas              — needs (i),(ii),(iii)
   v)   CT pump power       | independent of (i)(iii)(iv)  ★ needs only (ii)
```

**(ii) and (v) are a self-contained pair worth eight marks and needing nothing from
the rest of the question.** If N-1 had been the one you ran out of time on, those
eight were reachable first.
</details>

---

## Rung 172 — kJ and kCal: which way is bigger

The L-1 loss. `Cp = 2.223 kJ/kg°C` became `2.223 × 4.18` where it needed
`2.223 ÷ 4.186`, and the heat load came out **17.5 times too large**.

### The one fact

```
       1 kCal = 4.186 kJ           a kCal is the BIGGER unit
```

So the **number** runs the other way from the unit:

```
   kJ → kCal :  ÷ 4.186    fewer of the bigger unit   → number gets SMALLER
   kCal → kJ :  × 4.186    more of the smaller unit   → number gets BIGGER
```

**Say it as a sentence, not a rule:** *"It takes 4.186 kJ to make one kCal, so there
are always fewer kCal than kJ."*

### The anchor that makes it unmissable

**Water is 1 kCal/kg°C, and that same water is 4.186 kJ/kg°C.** Put any specific
heat beside water:

| Substance | kJ/kg°C | ÷ 4.186 → kCal/kg°C | Sanity |
|---|---|---|---|
| Water | 4.186 | **1.00** | the definition |
| Thermic fluid | 2.223 | **0.531** | about half of water ✓ |
| Flue gas | 0.96 | **0.23** | the 0.23 you use every boiler question ✓ |
| Air | 1.005 | **0.24** | the 0.24 from Day 13B's 1210 ✓ |
| Steel | 0.50 | **0.12** | |

**Nothing in this paper has a specific heat above water's.** If a kCal/kg°C figure
comes out above 1.0, the conversion is inverted. 2.223 → 9.3 fails that instantly.

> The other unit pairs, same logic — **ask which unit is bigger, then the count
> runs opposite:**
>
> ```
>    1 kWh   = 860 kCal      kWh → kCal : × 860     kCal → kWh : ÷ 860
>    1 TR    = 3024 kCal/hr = 3.517 kW
>    1 kg/cm² = 10 000 mmWC = 0.981 bar
>    1 bar   = 10.2 m of water
> ```

**Added to `reference/reciprocal-traps.md` as entry 12** — the first unit-system
member of the family.

---

## Rung 173 — Say a constant's units before you use it

The N-4(d) loss. You wrote `(1210 × 2) + (3010 × 2) = 8440` and read it as 8.44 kW.

**1210 and 3010 are not watts.** From Day 13B Rung 159:

```
    1210  =  ρ × Cp  of air        J per m³ per K
    3010  =  ρ × h_fg of water     J per m³ per (g/kg)
```

Neither is a quantity of anything until it is multiplied by **a volume flow** and
**a difference**:

```
    Q_sensible = 1210 × V̇ (m³/s) × ΔT (K)              → J/s = W
    Q_latent   = 3010 × V̇ (m³/s) × Δ(g/kg)             → W
```

`1210 × 2` has units of J per m³ — it is a heat *density*, not a heat *rate*. The
`2` was an air change number, which is dimensionless per hour, and the m³/s never
entered.

### The routine, and it takes five seconds

**Before using any tabulated constant, say its units out loud, then check that what
you multiply by cancels them into the answer you want.**

```
    want:  W  =  J/s
    have:  1210 J/(m³·K)  ×  V̇ m³/s  ×  ΔT K   →   J/s   ✓
           1210 J/(m³·K)  ×  2                  →   J/(m³·K)   ✗ not watts
```

**And the cross-check you already had:** the same 1210 appeared four lines earlier
multiplied by `0.729 m³/s` and `12 K`. **A constant does not change its meaning
between two lines of the same question.** If it needed a flow and a ΔT at line 4,
it needs them at line 9.

> The same discipline covers every constant in the formula sheet: **367** is
> `3600/9.81` and needs m³/h × m; **102** is `1000/9.81` and needs m³/s × mmWC;
> **860** is kCal per kWh; **3024** is kCal/hr per TR. None of them is a quantity
> on its own.

---

## Rung 174 — Four directions from Section I

All four Mock 2 misses are "which way does it move?" questions. Reason each from
the physics rather than recalling a sentence.

### Dew point and moisture run **together**, not opposite

Dew point is the temperature at which the air would become saturated.

```
    more moisture  →  saturation reached sooner on cooling  →  HIGHER dew point
    less moisture  →  must cool further to condense         →  LOWER dew point
```

So *"lower dew point ⟹ higher moisture"* is **False**. A useful anchor: dew point
can never exceed dry bulb, and it equals dry bulb at 100% RH.

### The ID fan is always the bigger machine

Follow the mass through a balanced-draft boiler:

```
    FD fan  →  combustion AIR only, at ambient temperature
                         ↓ + fuel mass, + air in-leakage, + heated to 150–200 °C
    ID fan  →  everything the FD sent, PLUS all of that, at a much larger volume
```

So the FD fan's flow capacity is **Lower**. Three separate reasons stack the same
way — mass added, leakage added, volume expanded by temperature — and no mechanism
runs the other way.

### Lower TTD = better condenser

Terminal temperature difference is the gap between condensing steam and the cooling
water leaving. Squeeze it and more heat crossed for the same driving temperature —
so the heat transfer rate is **Higher**.

**Same family as three others you already own:**

| Quantity | Small is | Because |
|---|---|---|
| Cooling tower **approach** | good | closer to the wet bulb |
| Heat exchanger **approach** | good | more surface used |
| Condenser **TTD** | good | tighter to the cooling water |
| Feedwater heater **TTD / DCA** | good | less bled steam for the same duty |

**All four are "how close did you get to the theoretical limit". Smaller is always
better; it just costs surface.**

### Only C, H and S burn

```
    A_th = [11.6 C + 34.8 (H₂ − O₂/8) + 4.35 S] / 100
                            ↑
              the fuel's own oxygen is SUBTRACTED
```

Fuel-bound oxygen is already oxidised — it releases nothing, and it *reduces* the
air required, which is what the minus sign says. Nitrogen passes through inert.
**So "oxygen and nitrogen do not contribute to calorific value" is True** — and you
have been using the fact, in that minus sign, since Day 2A.

---

# Practice — 50 minutes

**Two of these are the parts you did not reach. Do them first.**

| # | Question | Marks | Budget |
|---|---|---|---|
| 77 | **22nd N-3, parts A(iv), A(v), B(i), B(ii) only** | 11 | 12 min |
| 78 | **21st N-4(B) part (d) only**, from the 42.8 kW | 6 | 6 min |
| 79 | 22nd L-1 — thermic fluid, **from scratch, watching the Cp** | 5 | 8 min |
| 80 | 21st L-2 — EPI, **from scratch, watching the denominator** | 5 | 6 min |
| 81 | **21st N-3** — 5 MW gas turbine cogen and payback, **timed, hard stop at 25 min** | 20 | 25 min |

**Drill 81 is the rule under test.** Set a timer. When it reads 25:00, stop mid-line
if you have to, and record what was left unfinished. That is the skill.

<details><summary>Answers</summary>

**77:** A(iv) 0.870 × 7000 × 9500 = **₹578 lakh/yr**. A(v) 25% EA → 4.2% O₂,
44.8% EA → 6.5% O₂ via `O₂ = 21 × EA/(1 + EA)`; leakage
`(6.5 − 4.2)/(21 − 6.5) × 100` = **15.86%**. B(i) `(294 − 40)/(315 − 40) × 100`
= **92.4%**. B(ii) actual air = A_th × (1 + EA) from the measured O₂.

**78:** 42.8/(3.5 × 0.95) = 12.88 kW → × 8 × 300 × 7.5/10⁵ = **₹2.32 lakh/yr**.

**79:** Q = 60 × 826 × (2.223/4.186) × 20 = **5,26,383 kCal/hr**; oil **₹4606/hr**,
briquettes **₹1772/hr** → briquettes. *(BEE's key uses Cp 2.233 and gets 5,28,750,
₹4626 and ₹1779. Note the discrepancy in one line.)*

**80:** 9,98,736/10,000 = **99.87 ≈ 100 kWh/yr/m²**; **40 Wh/h/m²**.

**81:** existing ₹4319.7 lakh/yr; proposed fuel ₹1514.5 + 500 + 200 = ₹2214.5 lakh;
cogen electricity ₹6.15/kWh.
</details>

---

## Day 17 checklist

**Triage**
- [ ] **25 minutes maximum on any long question**, then move on
- [ ] Never a 26th minute while an untouched part sits at three marks
- [ ] **Read every sub-part before calculating**; star the one-liners
- [ ] Mark which parts are independent of the ones above them
- [ ] Do the stars first

**Units**
- [ ] **A kCal is bigger than a kJ, so there are fewer of them** — kJ ÷ 4.186
- [ ] Water is 1 kCal/kg°C — **nothing here has a higher specific heat**
- [ ] Say a constant's units before using it, and check they cancel
- [ ] **1210 and 3010 need a flow AND a difference** before they are watts
- [ ] A constant means the same thing on line 9 as on line 4

**Directions**
- [ ] Dew point and moisture move **together**
- [ ] **The ID fan is always bigger** — mass, leakage and temperature all stack
- [ ] Small approach / TTD / DCA = **good**, in every context
- [ ] Only **C, H and S** burn; fuel oxygen is subtracted in `A_th`

**Next: Full Mock 3.** From the remaining unseen questions in the 21st and 22nd,
plus the two the question bank reclassified on 06 Sep. **The score is not the
measure — finishing all four long questions is.**

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

# Part 2 — The air preheater (the part that was never taught)

> **This section exists because she was right.** Mock 2's N-3 asked for **APH
> leakage** and **APH effectiveness**, and neither appears anywhere in the
> curriculum. Day 6 Rung 62 teaches *combustion air preheat on a furnace
> recuperator* — a different device in a different context. Day 5 Rung 45 teaches
> effectiveness generically but never applies it to an APH, and the **leakage
> formula appears nowhere at all.**
>
> **Six of the eleven marks I called a triage loss were unreachable.** Rungs
> 175–178 close that, and Drill 77 below is only fair once they are read.

## Rung 175 — What an air preheater is, and why it is not a recuperator

The last heat exchanger on a boiler's back end. Flue gas leaves the economiser at
300–400 °C — still far too hot to send up a stack — so it passes through an **air
preheater**, giving that heat to the incoming combustion air.

```
   furnace ─► superheater ─► economiser ─► AIR PREHEATER ─► ID fan ─► stack
                                 │             ▲   │
                            feedwater      cold air  hot air (250–300 °C)
                                               │      └────► to the burners
                                            FD fan
```

**It is the same idea as Day 6's recuperator** — Rung 62's `1% fuel saving per
20 °C of air preheat` applies here unchanged — but the hardware differs, and the
difference is the whole of Rung 176.

| | **Recuperative** (tubular / plate) | **Regenerative** (Ljungström, rotary) |
|---|---|---|
| How | Gas and air on opposite sides of a fixed wall | A rotating matrix soaks up heat in the gas stream, gives it up in the air stream |
| Size | Large — gas-to-gas U is poor | Compact for the same duty |
| **Leakage** | **In principle none** — a solid wall separates them | **Unavoidable** — the seals slide |
| Typical use | Small and medium boilers | Large utility boilers |

**On a regenerative APH the air side is at fan discharge pressure and the gas side
is under ID-fan draft.** A pressure difference across a sliding seal leaks, always.
That leak is not a defect to be eliminated; it is a design parameter to be
*measured*, and 5–15% is normal.

---

## Rung 176 — Why leakage matters, and the formula derived

**Leaked air short-circuits the furnace.** It crosses from the air side straight
into the gas side without ever reaching a burner. So it:

- **does nothing for combustion** — it never sees fuel;
- **loads the ID fan** with mass it did not need to move;
- **loads the FD fan too**, which must supply the leak on top of the real air;
- **cools the flue gas**, which makes the exit temperature *look* better than the
  boiler deserves — a false economy that hides a real loss.

### The measurement, and where the formula comes from

You cannot weigh the leak. But leaked air is 21% O₂, and flue gas is not — so
**the leak announces itself as a rise in %O₂ across the preheater.**

Take **100 moles of flue gas entering** the APH at `O₂_in`, and let **L moles of
air** leak in. Oxygen is conserved:

```
     oxygen in the gas    +    oxygen in the leaked air   =  oxygen in the gas out

        100 × O₂_in       +          L × 21              =  (100 + L) × O₂_out
```

Expand and collect the L terms:

```
        100·O₂_in + 21L = 100·O₂_out + L·O₂_out
        L(21 − O₂_out)  = 100(O₂_out − O₂_in)
```

```
                       O₂_out − O₂_in
        AL %  =  100 × ────────────────
                        21 − O₂_out
```

**That is it — a single oxygen balance.** Note the family resemblance to the excess
air formula: both are "how much 21% air got added", and both put the *unknown* air
over `21 minus the measured O₂`.

**Worked, 22nd sitting N-3 A(v).** The question gives *excess air*, not O₂, so
invert the excess-air formula first:

```
        EA = O₂/(21 − O₂)        ⟹        O₂ = 21 × EA/(1 + EA)

        25.0 % EA  →  21 × 0.250/1.250  =  4.2 % O₂    (APH inlet)
        44.8 % EA  →  21 × 0.448/1.448  =  6.5 % O₂    (APH outlet)

        AL = 100 × (6.5 − 4.2)/(21 − 6.5)  =  230/14.5  =  15.86 %
```

**Check it forwards:** 100 mol at 4.2% O₂ plus 15.86 mol of air at 21% gives
`(4.2 + 15.86 × 0.21)/1.1586 = 6.50%` ✓.

> **15.86% is high.** Above ~12% an auditor calls for seal adjustment. The cost is
> not subtle: that leaked air is pumped twice, by the FD fan and again by the ID
> fan, and it is 15% extra mass through a fan whose power goes as flow.

---

## Rung 177 — APH effectiveness, and why it is measured on the air side

This is **Day 5 Rung 45's effectiveness**, unchanged — actual heat transferred over
the maximum thermodynamically possible — applied to the air:

```
                    actual air temperature RISE
        ε  =  ──────────────────────────────────────────
              maximum possible rise (air in → gas in)

                 T_air,out − T_air,in
           =  ─────────────────────────
                 T_gas,in − T_air,in
```

The air can never leave hotter than the gas entered, so ε ≤ 1 — the same bound as
every effectiveness on Day 5.

**Worked, 22nd N-3 B(i):**

```
        design     (316 − 36)/(356 − 36)  = 280/320  = 87.5 %
        operating  (294 − 40)/(315 − 40)  = 254/275  = 92.4 %
```

### Why the air side and not the gas side

You could write the same ratio on the gas side — `(T_gas,in − T_gas,out)/(T_gas,in
− T_air,in)`. **Do not.** Rung 176 is the reason: **leakage cools the gas**. Cold
air dumped into the gas stream drops the measured gas outlet temperature without a
single extra joule reaching the air. Gas-side effectiveness therefore *rises* when
the seals get worse, which is exactly backwards.

**The air side cannot be faked.** Air that leaked across never reached the burners,
so it never appears in the air outlet measurement.

> **Read the 22nd's numbers with that in mind.** Effectiveness *rose* from 87.5% to
> 92.4% while leakage was 15.86% and the gas exit temperature *rose* from 145 °C to
> 165 °C. A "better" preheater on a boiler burning more coal. The three numbers only
> reconcile once you know what leakage does.

---

## Rung 178 — The cold end, and why exit gas temperature has a floor

If the APH is free money, why not cool the flue gas to 60 °C?

**Because of sulphur.** Fuel sulphur burns to SO₂, a little of it oxidises further
to SO₃, and SO₃ plus water vapour is sulphuric acid. That acid has a **dew point of
120–150 °C** — far above the water dew point — and below it, it condenses on the
coldest metal in the plant, which is the APH's cold end.

```
        acid dew point ≈ 120–150 °C   on sulphur-bearing fuel
                        ≈  50–60 °C   on natural gas (no sulphur)
```

So the exit gas temperature is not an efficiency target to be minimised. **It is a
floor set by the fuel**, and the standard rules follow from it:

- Coal and furnace oil: hold exit gas at **~150–170 °C**.
- Natural gas: can go far lower — which is why condensing economisers exist on gas.
- A cold-end that keeps corroding means the fuel's sulphur, not the design.

**This is the same fact as Day 6's "exhaust of furnace-oil systems is limited to
about 170 °C"** — the 16th sitting asks it directly as a short question. One cause,
two chapters.

---

## Rung 178B — What an auditor checks on an APH

1. **O₂ before and after** — leakage, by Rung 176. Rising over months means seals.
2. **Air in/out and gas in/out temperatures** — effectiveness, by Rung 177.
3. **Gas exit temperature against the acid dew point** — too low is corrosion, too
   high is loss.
4. **Draft loss across the APH** — rising means fouling or ash plugging.
5. **FD and ID fan powers** — a leaking APH shows up in both.

---

# Part 3 — The rest of the coverage audit

**Her question prompted a full sweep of every equipment noun in the ten papers
against the curriculum.** The air preheater was the serious gap. Three more turned
up, all lighter, and all closed here rather than left to be discovered in an exam.

## Rung 179 — Screw compressors (in 6 of 10 papers; Day 9 taught reciprocating only)

**The assessment arithmetic is identical** — FAD, specific power, isothermal
efficiency, leakage test — so nothing you learned on Day 9 is wasted. What differs
is **part-load behaviour**, and that is where the audit findings are.

| | **Reciprocating** | **Screw** |
|---|---|---|
| Mechanism | Piston, positive displacement in pulses | Two meshing helical rotors, continuous |
| Delivery | Pulsating — needs a receiver | Smooth |
| Typical size | Up to ~100 kW | 20 kW to several MW — **the industrial default** |
| Specific power at 7 bar | 6–7 kW/100 CFM | 5.5–6.5 kW/100 CFM |
| Part load | **Load/unload only** (Day 9 Rung 91) | Load/unload, **slide valve**, or **VFD** |
| Unloaded power | ~25–35 % of full load | **~25–40 %** of full load |
| Maintenance | Valves, rings — frequent | Bearings, oil — infrequent |

**The part-load story is the exam story.** A screw compressor's slide valve
modulates capacity by shortening the effective rotor length — but its power does
**not** fall proportionally:

```
    100 % capacity → 100 % power
     70 % capacity →  ~82 % power        ← the penalty
     50 % capacity →  ~70 % power
      0 % capacity (unloaded) → 25–40 %
```

**So a screw running at 50% on the slide valve is worse than one cycling load/
unload**, and much worse than a VFD, which follows capacity nearly linearly. The
standard finding — *"replace slide-valve modulation with a VFD, or with proper
sequencing of multiple machines"* — comes straight from that table.

> Day 9 Rung 91's load/unload arithmetic transfers unchanged. The only new fact is
> that **a screw has a third option and its middle setting is a trap.**

## Rung 180 — Condensate recovery (asked in the 25th; taught nowhere)

Steam condenses at the process and leaves as **saturated water at the steam
pressure**. Throwing it away wastes four things at once, and candidates usually
name only one:

```
   1. HEAT      condensate at 8 bar is ~175 °C carrying ~176 kCal/kg
                against 30 °C makeup — about 20–25 % of the steam's total heat
   2. WATER     the mass itself, which must be replaced
   3. TREATMENT demineralised water costs money to make
   4. BLOWDOWN  makeup carries dissolved solids; more makeup raises boiler TDS,
                which forces more blowdown, which wastes more heat again
```

**The 25th sitting's True/False — "the only reason for installing condensate
recovery is to reduce makeup water" — is False**, and item 1 is why: the heat is
the larger prize, and item 4 is the one almost nobody says.

```
    fuel saving %  ≈  (condensate returned, kg) × (h_cond − h_makeup)
                      ────────────────────────────────────────────────
                        (steam raised, kg) × (h_steam − h_makeup)
```

Every degree of feedwater temperature is worth roughly **1% of fuel per 6 °C** —
the same order as Day 6's air preheat rule, from the same arithmetic.

> **Where you have already used this:** Mock 2's N-1 turned on it. The process
> returned **NIL CONDENSATE**, so its share of the feedwater arrived as 30 °C
> makeup instead of 100 °C return, and the mixed temperature fell to 89.2 °C. You
> got that right. This rung is the general case of the thing you already did.

## Rung 181 — Transformer losses (Section I fodder, two sittings)

Two losses, and the exam swaps their names:

```
   IRON (core, no-load)  — hysteresis + eddy currents in the core
                           CONSTANT whenever energised, load or no load
   COPPER (I²R, load)    — resistance of the windings
                           varies with the SQUARE of load
```

**The 21st sitting states "copper loss is the power consumed to sustain the
magnetic field" → False.** That is the iron loss. *(You got this one right.)*

**Maximum efficiency occurs where copper loss = iron loss**, which is typically
40–60% of rating — so a transformer loaded at 25% is running badly, and the fix is
to consolidate loads onto fewer transformers and switch the rest off.

## Rung 182 — Naming, not concepts

- A **jigger** is the dyeing machine in Day 13 Rung 146's liquor-ratio question —
  fabric passes back and forth through a bath. The 23rd sitting names it; the
  curriculum did not. **Same question, same arithmetic.**
- A **stenter** (Day 13 Rung 148) is sometimes written **"stenter frame"** or
  **"tenter"**. Same machine.
- **Thermopack** = thermic fluid heater (Day 13 Rung 147). The 21st N-4(D) uses the
  trade name without explanation.

---

# Practice — 50 minutes

**Two of these are the parts you did not reach. Do them first.**

| # | Question | Marks | Budget |
|---|---|---|---|
| 77 | **22nd N-3, parts A(iv), A(v), B(i), B(ii) only** — now reachable, after Rungs 175–178 | 11 | 12 min |
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

**Air preheater** *(new — this was missing from the curriculum)*
- [ ] Know an APH from a furnace recuperator, and recuperative from regenerative
- [ ] Know **why a regenerative APH must leak** — a sliding seal between a
      pressurised air side and a drafted gas side
- [ ] Know leaked air **short-circuits the furnace**: no combustion benefit, both
      fans loaded, gas artificially cooled
- [ ] **Can derive `AL% = 100(O₂_out − O₂_in)/(21 − O₂_out)`** from an oxygen balance
- [ ] Can invert the excess air formula: **`O₂ = 21 × EA/(1 + EA)`**
- [ ] **Effectiveness is measured on the AIR side**, and why the gas side lies
- [ ] Know the acid dew point sets a **floor** on exit gas temperature

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

**The rest of the coverage audit**
- [ ] Screw vs reciprocating: **same assessment maths, different part-load options**
- [ ] Know a screw's slide valve at 50 % capacity still draws ~70 % power
- [ ] **Condensate recovery saves four things**, and heat is the biggest
- [ ] Iron loss is constant and magnetic; **copper loss is I²R and varies as load²**
- [ ] Jigger, thermopack, stenter frame — names for machines already taught

**Directions**
- [ ] Dew point and moisture move **together**
- [ ] **The ID fan is always bigger** — mass, leakage and temperature all stack
- [ ] Small approach / TTD / DCA = **good**, in every context
- [ ] Only **C, H and S** burn; fuel oxygen is subtracted in `A_th`

**Coverage note.** With Rungs 175–182, every equipment noun appearing in the ten
papers now has curriculum behind it. That sweep should have happened before Mock 2,
not after it.

**Next: Full Mock 3.** From the remaining unseen questions in the 21st and 22nd,
plus the two the question bank reclassified on 06 Sep. **The score is not the
measure — finishing all four long questions is.**

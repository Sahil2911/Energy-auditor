# Day 3 — The Indirect Method: All Seven Losses

**Time: 3.5 hours. Book-4 Ch 1 (p. 1).**

This is **the most-examined calculation in Paper 4** — present in all eight
readable sittings. Today it becomes routine.

Same rung format. Rungs 12–19 continue from Day 2B.

---

## Readiness check (10 min)

Before starting, answer these from memory. If any is shaky, revisit that rung
first — today builds directly on them.

1. A fuel is 45% carbon. How much **air** does that carbon need, per kg of fuel?
2. Flue gas O₂ reads 5%. Excess air?
3. Why 23% in one calculation and 21% in the other?
4. A fuel is 6% hydrogen. How much **water** does 1 kg produce?
5. What does `m_dfg = (AAS + 1) − 9·H₂ − moisture` say in words?
6. Why does a gas boiler show lower GCV efficiency than an oil boiler?

<details><summary>Answers</summary>

1. 0.45 × 11.6 = **5.22 kg air**
2. 5/(21−5) × 100 = **31.3%**
3. 23% is oxygen by **mass** (for air quantities); 21% is by **volume** (what an
   analyser reads)
4. 9 × 0.06 = **0.54 kg water**
5. Everything in (air + fuel) comes out; subtract the water formed from hydrogen
   and the fuel's own moisture, and what remains is dry gas
6. Gas has far more hydrogen (~23% vs ~11%), so it makes more water, and
   vaporising that water carries latent heat up the stack
</details>

---

## Rung 12 — What the method actually claims

Fuel releases a fixed amount of heat. Call it 100%. Some reaches the steam; the
rest escapes by a handful of identifiable routes.

```
    η = 100 − (L1 + L2 + L3 + L4 + L5 + L6 + L7)
```

Every loss has the same shape:

```
    loss % = (heat carried away by that route) / GCV × 100
```

So you are always doing the same thing — computing a quantity of heat, then
expressing it as a fraction of the fuel's energy. Seven variations on one idea.

**Two families:**

| Family | Losses | Heat mechanism |
|---|---|---|
| **Sensible** — something hot leaves | L1, L4 | `m × Cp × ΔT` |
| **Latent + sensible** — water leaves as vapour | L2, L3 | `m × [584 + Cp·ΔT]` |
| **Chemical** — fuel never released its energy | L5, L7 | unburnt fuel value |
| **Surface** | L6 | usually given |

Recognising which family a loss belongs to tells you its formula shape before you
look it up.

---

## Rung 13 — L1, dry flue gas

Hot gas leaves the stack. You computed its mass on Day 2B.

```
    L1 = m_dfg × Cp × (Tg − Ta) / GCV × 100
```

Pure `m·Cp·ΔT`. Cp for flue gas is **0.24** in most papers (sometimes 0.23 or
0.29 — use what the question gives).

**Usually the largest loss**, because m_dfg is large and mostly nitrogen you never
wanted. Reducing it means either less excess air or a lower stack temperature —
which is exactly what an economiser or air preheater does.

> ⚠️ **Cp here is flue gas — 0.24, not 0.45.** 0.45 belongs to superheated steam
> and is used in L2–L4. L1 heats *gas*; L2–L4 heat *water vapour*. Substituting
> the vapour value nearly doubles L1 and the answer still looks plausible. See
> the specific-heat card in `reference/formula-sheet.md` §1.

**Sanity anchor: typical L1 is 5–12%.** Above about 15%, suspect either a wrong
Cp or a genuinely terrible boiler.

**L1 is a ratio, and GCV is in the denominator.** A low-GCV fuel shows a *higher*
percentage loss for the same absolute heat up the stack. Paddy husk (GCV 3500)
gives L1 = 8.5% while natural gas (GCV 13,000) gives 6.4% — even though husk's
flue gas mass is three times smaller. Small numerator over small denominator can
still be large. Never judge a loss by the size of m_dfg alone.

---

## Rung 14 — L2, water made from hydrogen

Hydrogen burns to water. 1 kg of H₂ makes 9 kg of water (Day 2B, Rung 9). That
water leaves as vapour, carrying:

- **584 kCal/kg** to vaporise it (latent heat), plus
- `Cp_steam × ΔT` to superheat it to stack temperature

```
    L2 = 9·H₂ × [584 + Cp_s × (Tg − Ta)] / GCV × 100
```

> ⚠️ **Cp_steam is not a fixed number in these papers.** The 18th sitting *gave*
> 0.45 in the question data. The 24th did not, and its model answer used **0.43**,
> noting "value referred from the guidebook."
>
> **Rule: use the value the question gives. Only go to the guidebook if it is
> silent.** Do not carry 0.45 in your head as universal.

---

## Rung 15 — L3, moisture already in the fuel

Identical to L2 in mechanism — water leaving as vapour — but this water was
*already in the fuel*, not made by burning. So no factor of 9; just the moisture
fraction:

```
    L3 = M × [584 + Cp_s × (Tg − Ta)] / GCV × 100
```

Same bracket as L2. Only the mass differs. Matters for coal (5–10%) and biomass
(10–15%); zero for oil and gas.

---

## Rung 16 — L4, moisture in the combustion air

Air is humid. That moisture is dragged through and heated. No latent heat — it was
already vapour — so it is just sensible heat:

```
    L4 = AAS × humidity factor × Cp_s × (Tg − Ta) / GCV × 100
```

Humidity factor is typically **0.025 kg/kg dry air**. Always small — a few tenths
of a percent. Do not skip it; it is worth a mark.

---

## Rung 17 — L5, incomplete combustion

From Day 2A: carbon burnt to CO releases 2,430 kCal/kg instead of 8,084 — energy
left in the gas.

```
    L5 = %CO / (%CO + %CO₂) × C × 5744 / GCV × 100
```

The fraction `%CO/(%CO + %CO₂)` is the share of carbon that got it wrong.

> The theoretical shortfall is 8,084 − 2,430 = **5,654**, but BEE's formula uses
> **5,744**. Use 5,744 — it is what the guidebook and the model answers use, and
> the examiner marks against those.

Only appears when the question gives a CO reading. If there is no CO figure, there
is no L5.

---

## Rung 18 — L6, radiation and convection

Heat through the boiler shell into the boiler house.

**Almost always given** (1.2%, 1.6%, 2%…). Measuring it needs surface temperature
surveys, which is not a two-hour-exam activity. Take the given number.

---

## Rung 19 — L7, unburnt carbon in ash

Carbon that left in the ash without burning at all.

```
    L7 = (ash quantity × GCV of ash) / GCV of fuel × 100
```

Needs ash quantity and its calorific value. If the question does not give both,
this loss is not being asked for. Relevant to coal and biomass only.

---

## Blowdown — the trap

Boiler water concentrates dissolved solids, so some is periodically discharged.

```
    Blowdown % = (Feedwater TDS × % makeup) / (Maximum permissible boiler water TDS)
```

> ⚠️ **Blowdown is NOT one of the seven losses.** The indirect method accounts for
> heat leaving in the *flue gas and ash*. Blowdown leaves as hot *water* — a real
> energy loss, but outside this calculation.
>
> The 25th sitting asked exactly this as True/False: *"In indirect method of boiler
> efficiency calculations, blowdown losses are also considered."* **False.**

---

## Rung 20 — The full calculation

Complete worked example: the paddy husk boiler, 24th sitting N-1(c)
(`papers/24-1.pdf`). You already have A_th = 4.27 from Day 2A Drill 4.

Given: C 33.95%, H₂ 5.01%, S 0.09%, O₂ 32.52%, moisture 10.79%, mineral matter
16.73%. GCV 3500. Flue gas O₂ 6%, exit 225 °C, ambient 32 °C. Radiation 1.6%,
humidity factor 0.025. Cp gas 0.24, Cp steam 0.43 (guidebook).

```
    Excess air  = 6/(21−6) × 100          = 40 %
    AAS         = 1.40 × 4.27             = 5.98 kg air/kg husk

    m_dfg       = (5.98 + 1) − 9(0.0501) − 0.1079
                = 6.98 − 0.451 − 0.108    = 6.42 kg/kg

    ΔT = 225 − 32 = 193 °C
    bracket = 584 + 0.43 × 193 = 666.99

    L1 = 6.34 × 0.24 × 193 / 3500 × 100   = 8.40 %
    L2 = 9(0.0501) × 666.99 / 3500 × 100  = 8.59 %
    L3 = 0.1079 × 666.99 / 3500 × 100     = 2.06 %
    L4 = 5.98 × 0.025 × 0.43 × 193 / 3500 × 100 = 0.35 %
    L6 = 1.6 % (given)
                                            ───────
    Total losses                          = 21.0 %
    η = 100 − 21.0                        = 79 %
```

> **Note the m_dfg discrepancy.** Our arithmetic gives **6.42**; the official model
> answer states **6.34** and uses that for L1. Recomputing 6.98 − 0.451 − 0.108
> gives 6.42, so the model answer contains a small slip. With 6.42, L1 = 8.50% and
> efficiency becomes 78.9% instead of 79%.
>
> **This does not matter for marks.** Examiners award the method. Two lessons:
> published model answers are not infallible, and a defensible method with a
> slightly different number is still a full-marks answer. Show your working.

Then parts (d) and (e) reuse Day 1:

```
    ER = 3500 × 0.79 / (665 − 84)          = 4.76
    Steam cost = 6700/4.76 + 550           = Rs 1,958/tonne
```

*Sanity sentence:* the coal boiler came to Rs 3,229/tonne. Husk is cheaper per
tonne of fuel and the boiler is more efficient, so husk steam must cost less. It
does — by about 40%. ✓

---

## Practice (50 min)

**1. 18th sitting N-1** (`papers/18-1.pdf`) — redo the natural gas boiler
unaided, start to finish. You have seen it twice; now produce it cold. Target
20 minutes.

**2. 20th sitting** (`papers/20-1.pdf`) — find the boiler question and attempt
the efficiency part. A fuel you have not met.

For each, write the **sanity sentence** before checking arithmetic.

## Block D — Log (20 min)

Tag every lost mark. Note specifically:

- Any loss whose **formula shape** you could not recall (that is a Rung 12 gap —
  the family table)
- Any place you used a Cp from memory instead of from the question

---

## Day 3 checklist

- [ ] Can state all seven losses and which family each belongs to
- [ ] Can write L1–L4 without looking
- [ ] Know Cp values come from the question first, guidebook second
- [ ] Know blowdown is not one of the seven
- [ ] Know L5 uses 5,744 as BEE specifies
- [ ] Completed the husk calculation end to end
- [ ] Both practice questions attempted with sanity sentences

**Tomorrow (Day 4):** cogeneration and turbines — back-pressure, extraction and
topping cycles, and isentropic efficiency. Appears in 7 of 8 sittings.

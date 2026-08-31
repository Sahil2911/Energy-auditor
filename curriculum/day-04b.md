# Day 4B — Gas Turbine Cogeneration

**Time: 2 hours.**

> **Why this exists.** Day 4 taught *steam* turbine cogeneration and then set a
> **gas** turbine question calling it "different machine, same logic." That was
> wrong, and the failure to start it was the predictable result. Gas turbine
> cogeneration shares almost no formulas with the steam turbine case:
>
> | | Steam turbine | Gas turbine |
> |---|---|---|
> | Efficiency route | isentropic, via enthalpies | **given directly**, via heat rate |
> | Fuel from | boiler heat balance | **gas rate = heat rate / GCV** |
> | Heat recovery | exhaust steam is the product | **separate WHRB on the exhaust** |
> | Needs | steam tables | **air:fuel ratio, exhaust Cp** |
>
> No isentropic efficiency appears anywhere. Rungs 29–33.

---

## Rung 29 — The layout

```
   air ──► compressor ──► combustor ──► gas turbine ──► generator
                              ▲              │
                            fuel             │ exhaust, ~500 °C
                                             ▼
                              Waste Heat Recovery Boiler (WHRB)
                                             │
                                             ▼
                                     process steam
```

Two separate machines with **two separate efficiencies**:

- The **gas turbine** converts fuel to shaft power — typically only 25–30%
- The **WHRB** catches the hot exhaust and makes steam — typically 70–80%

The gas turbine's low efficiency is not a defect. Its exhaust leaves at ~500 °C
carrying most of the fuel energy, and that is precisely what the WHRB harvests.

**Supplementary firing:** extra fuel burnt directly in the WHRB duct when more
steam is needed than the exhaust alone can raise.

---

## Rung 30 — Heat rate, and the reciprocal you already know

For any power-producing machine:

```
    Heat rate (kCal/kWh) = 860 / η
```

Because 1 kWh = 860 kCal. If the machine were perfect it would need exactly
860 kCal per kWh; at efficiency η it needs 860/η.

This is the **efficiency ↔ heat rate** reciprocal pair from
`reference/reciprocal-traps.md`. Higher efficiency, lower heat rate.

**Drill 26.** Gas turbine efficiency 28% on GCV. Heat rate?

<details><summary>Answer</summary>

860 / 0.28 = **3,071.43 kCal/kWh**

*Sanity:* efficiency is low, so heat rate should be high. A good condensing power
plant runs ~2,300–2,500; 3,071 is worse, as expected for a gas turbine alone.
</details>

---

## Rung 31 — Gas rate, then fuel consumption

Heat rate says kCal per kWh. Divide by the fuel's GCV and you get **kg of fuel
per kWh** — the "gas rate":

```
    Gas rate (kg/kWh) = Heat rate / GCV
    Fuel (kg/hr)      = Gas rate × Power (kW)
```

**Drill 27.** Heat rate 3071.43 kCal/kWh, natural gas GCV 13,000 kCal/kg,
generating 16,000 kW.

<details><summary>Answer</summary>

```
    Gas rate = 3071.43 / 13000 = 0.2363 kg/kWh
    Fuel     = 16000 × 0.2363 = 3,780 kg/hr
```
</details>

---

## Rung 32 — How much exhaust, and how hot

The turbine draws in far more air than it needs, for cooling. The question gives
an **air-to-fuel ratio** — 60:1 is typical.

Everything in comes out, so per kg of fuel:

```
    exhaust = air + fuel = 60 + 1 = 61 kg per kg of fuel
```

Same mass-in-equals-mass-out idea as Rung 9, applied to a turbine.

```
    Exhaust mass (kg/hr) = fuel × (A/F + 1)
    Exhaust heat (kCal/hr) = exhaust mass × Cp × T
```

**Drill 28.** Fuel 3,780 kg/hr, A:F = 60:1, exhaust at 515 °C, Cp 0.3.

<details><summary>Answer</summary>

```
    exhaust mass = 3780 × 61 = 230,580 kg/hr
    exhaust heat = 230,580 × 0.3 × 515 = 3,56,25,000 kCal/hr
```
</details>

> ⚠️ **An ambiguity worth knowing.** The model answer uses **515**, not
> (515 − 30), even though ambient is given. Strictly the *available* heat is
> measured above ambient, which would give (515 − 30) = 485 and a WHRB efficiency
> of 80.1% rather than 75.5%.
>
> Follow the model's convention — use the raw exhaust temperature — but **state
> your assumption in one line.** Examiners accept either with the assumption
> written down.

---

## Rung 33 — WHRB efficiency

Heat into the steam, over heat available in the exhaust:

```
                  steam flow × (h_steam − h_feedwater)
    η_WHRB  =  ─────────────────────────────────────────
                        exhaust heat
```

**Drill 29.** 48,000 kg/hr steam at 665 kCal/kg, feedwater 105 kCal/kg, exhaust
heat from Drill 28.

<details><summary>Answer</summary>

```
    steam heat = 48,000 × (665 − 105) = 2,68,80,000 kCal/hr
    η_WHRB     = 26,880,000 / 35,625,000 = 75.4 %
```
</details>

---

## Rung 34 — Supplementary firing economics

The standard part (c): is it cheaper to raise extra steam by supplementary firing
in the WHRB, or in a separate dedicated boiler?

Compare **fuel needed per tonne of steam** by each route:

```
    fuel = steam × (h_steam − h_fw) / (η × GCV)
```

Whichever route has the **higher efficiency** needs less fuel and wins. That is
the whole comparison — no capital cost, no complications.

**Worked, from the 18th sitting:**

```
    Supplementary firing, η = 75.5 + 1.5 = 77 %
        fuel = 10,000 × 560 / (0.77 × 13,000) = 559.44 kg/hr

    Separate boiler, η = 80 % (as the question states)
        fuel = 10,000 × 560 / (0.80 × 13,000) = 538.46 kg/hr

    Saving = 20.98 kg/hr = 29.97 m³/hr at 0.7 kg/m³
    Yearly = 29.97 × 25 × 8,600 = Rs 64,43,550
```

**The separate boiler wins**, because 80% beats 77% — the claimed 1.5-point
improvement is not enough to close the gap.

> ⚠️ **Model answer error.** The question specifies a separate boiler at **80%**;
> the model answer computes with **85%**, reaching 506.79 kg/hr and Rs 1.61 crore.
> Its conclusion is right; its arithmetic uses a figure its own question does not
> give. **Follow the question, not the model.** This is the fourth such error
> logged — see `reference/precision-and-rounding.md` §4.

---

## The unit rule this chapter demands

Day 4's timed question was lost on exactly one line. Both routes are correct:

```
    all in kCal:   electrical × 860 ...  heat / 4.18 ...  fuel × GCV
    all in kJ:     electrical × 3600 ... heat as-is ...   fuel × GCV × 4.18
```

**What fails is mixing them.** Before writing a ratio with several terms, put a
unit label on every term and check they agree. Ten seconds.

---

## Practice (45 min)

**18th sitting, Set B, N-2** (`papers/18-2.pdf`) — the question you could not
start. All three parts, 25 minutes. Every piece is now a drill above.

Then re-do **19th N-1 part (c)** only, with the unit labelling rule. Target: 0.79.

---

## Day 4B checklist

- [ ] Can draw the gas turbine + WHRB layout and name both efficiencies
- [ ] Know heat rate = 860/η and why it is a reciprocal
- [ ] Can go heat rate → gas rate → fuel consumption
- [ ] Can get exhaust mass from the air:fuel ratio
- [ ] Can compute WHRB efficiency and state the ΔT assumption
- [ ] Can decide a supplementary-firing question on efficiency alone
- [ ] Unit-labelled every term before writing a multi-term ratio

**Next (Day 5):** heat exchangers — LMTD, correction factors, effectiveness–NTU.

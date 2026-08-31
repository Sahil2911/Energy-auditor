# Day 4 — Cogeneration and Turbines

**Time: 3.5 hours. Book-4 Ch 3 (p. 43).**

**Source:** BEE Book 4 Ch 3, *Energy Performance Assessment of Cogeneration and
Turbines* — [4Ch3.pdf](https://beeindia.gov.in/sites/default/files/4Ch3.pdf)
(9 pp, free). Read §3.3 and the worked example in §3.6.

Appears in **7 of 8 sittings**. Rungs 21–28.

---

## Readiness check (5 min)

1. `η = 100 − (losses)` — which method, and why does it exist?
2. 1 kWh equals how many kCal?
3. Why did the husk boiler show a higher L1 percentage than the gas boiler?

<details><summary>Answers</summary>

1. Indirect method — a heat balance. It names each loss, so an auditor knows what
   to fix.
2. **860 kCal.**
3. L1 is a ratio with GCV underneath. Husk's GCV is 3.7× smaller, which outweighs
   its 3× smaller flue gas mass.
</details>

---

## Rung 21 — What cogeneration is

**One fuel, two useful outputs: power *and* useful heat.**

A conventional power plant burns fuel, makes steam, expands it through a turbine
to a condenser, and throws the condenser heat away — roughly 60% of the fuel
energy, dumped into cooling water at 35 °C, too cold to be useful.

Cogeneration refuses that. Instead of expanding steam all the way down to vacuum,
you stop the expansion at a pressure the *process* can use — 2, 5, 10 kg/cm² —
and send the exhaust to the process instead of to a condenser.

You get less power per kg of steam. But the heat that would have been thrown away
now does useful work. Overall fuel utilisation rises from ~35% to 75–85%.

**Topping vs bottoming cycle:**

| | Sequence | Typical |
|---|---|---|
| **Topping** | Fuel → **power first**, then heat from the exhaust | Gas turbine + waste heat boiler; steam turbine + process steam |
| **Bottoming** | Fuel → **high-temperature process first**, then power from waste heat | Cement kiln or glass furnace exhaust → waste heat boiler → turbine |

Topping is far more common and is what the papers usually set.

---

## Rung 22 — Three turbine types

| Type | Exhaust goes to | Power per kg steam | Used when |
|---|---|---|---|
| **Back-pressure** | Process, at useful pressure | Low | Process heat demand is steady |
| **Condensing** | Condenser, under vacuum | High | Power is the objective |
| **Extraction-condensing** | Some bled to process, rest to condenser | Adjustable | Both demands vary |

**Back-pressure gives least power per kg of steam** — you stopped the expansion
early. That is the deliberate trade: less power, but the exhaust heat is used
rather than dumped.

---

## Rung 23 — Isentropic efficiency

The single most examined idea in this chapter.

> 📖 **For the intuition rather than the rule**, read
> `reference/concept-isentropic-expansion.md`. It explains why a *less* efficient
> turbine sends out exhaust with *more* energy in it — which is the part of this
> formula that resists memorisation until it clicks.

An **ideal** turbine expands steam with no losses — an isentropic (constant
entropy) expansion. From the steam tables or Mollier chart, that ideal exhaust
enthalpy is `h₂s`.

A **real** turbine has friction and turbulence. It extracts less work, so the
steam leaves with *more* enthalpy than ideal: `h₂ > h₂s`.

```
                       actual heat drop      h₁ − h₂
    η_isentropic  =  ────────────────────  =  ─────────
                       ideal heat drop       h₁ − h₂s
```

Rearranged — and this is the form the exam wants:

```
    h₂ = h₁ − η_isentropic × (h₁ − h₂s)
```

**Read that carefully.** You take the *ideal* drop, keep only η of it, and
subtract from inlet. A 90% efficient turbine achieves 90% of the ideal drop.

*Sanity:* h₂ must always lie **between** h₂s and h₁. If your actual exhaust
enthalpy comes out below the isentropic value, you have inverted the formula.

**Drill 21.** Inlet 3420 kJ/kg, isentropic exhaust 2430 kJ/kg, isentropic
efficiency 90%. Find actual exhaust enthalpy.

<details><summary>Answer</summary>

```
    ideal drop  = 3420 − 2430 = 990 kJ/kg
    actual drop = 0.90 × 990  = 891 kJ/kg
    h₂ = 3420 − 891 = 2529 kJ/kg
```

Check: 2529 sits between 2430 and 3420. ✓
</details>

---

## Rung 24 — Units: the trap in this chapter

Boiler questions run in **kCal**. Turbine questions often run in **kJ**, because
steam tables are published that way. Mixing them is the classic fatal error here.

```
    1 kCal = 4.18 kJ
    1 kWh  = 860 kCal = 3600 kJ
```

**Power from a turbine:**

```
    if enthalpies in kJ/kg:    P (kW) = m (kg/s) × Δh (kJ/kg)
                                      = m (kg/hr) / 3600 × Δh

    if enthalpies in kCal/kg:  P (kW) = m (kg/hr) × Δh (kCal/kg) / 860
```

Both say the same thing. **Decide which system you are in at the start of the
question and stay there.**

**Drill 22.** 91 TPH of steam, actual heat drop 891 kJ/kg. Turbine output in MW?

<details><summary>Answer</summary>

```
    m = 91,000 kg/hr = 25.28 kg/s
    P = 25.28 × 891 = 22,522 kW = 22.52 MW
```
</details>

---

## Rung 25 — From turbine shaft to switchboard

The turbine's mechanical output passes through a gearbox and a generator, each
losing a little:

```
    Electrical output = turbine power × η_gearbox × η_generator
```

**Drill 23.** 22.52 MW at the shaft, gearbox 97%, generator 98%.

<details><summary>Answer</summary>

22.52 × 0.97 × 0.98 = **21.41 MW**
</details>

These efficiencies **multiply** — never add or average them.

---

## Rung 26 — Fuel to feed the boiler

Straight back to Day 1. The boiler must supply steam at h₁ from feedwater at h_fw:

```
    fuel (kg/hr) = m × (h₁ − h_fw) / (GCV × η_boiler)
```

With enthalpies in kJ and GCV in kCal, divide by 4.18 to reconcile:

```
    fuel = m × (h₁ − h_fw) / (4.18 × GCV × η_boiler)
```

**Drill 24.** 91,000 kg/hr steam, h₁ 3420 kJ/kg, feedwater 504.7 kJ/kg, coal GCV
4500 kCal/kg, boiler 80%.

<details><summary>Answer</summary>

```
    fuel = 91,000 × (3420 − 504.7) / (4.18 × 4500 × 0.80)
         = 265,292,300 / 15,048
         = 17,630 kg/hr = 17.63 TPH
```
</details>

---

## Rung 27 — Energy Utilisation Factor

The measure that makes cogeneration look good, because it counts **both** outputs:

```
                 electrical output + useful heat output
    EUF  =  ───────────────────────────────────────────
                    total fuel energy input
```

Useful heat is what the process actually receives — the exhaust steam enthalpy
above feedwater:

```
    useful heat = m × (h₂ − h_fw)
```

**Drill 25.** 21.41 MW electrical, 91,000 kg/hr exhaust at 2529 kJ/kg, feedwater
504.7 kJ/kg, fuel 17,600 kg/hr at 4500 kCal/kg. Find EUF.

<details><summary>Answer</summary>

```
    electrical  = 21,400 × 860              = 1,84,04,000 kCal/hr
    useful heat = 91,000 × (2529 − 504.7)/4.18 = 4,40,69,689 kCal/hr
    fuel input  = 17,600 × 4500             = 7,92,00,000 kCal/hr

    EUF = (18,404,000 + 44,069,689) / 79,200,000 = 0.79
```

79% against a condensing plant's ~35%. That is the whole case for cogeneration.
</details>

---

## Rung 28 — Heat-to-power ratio, and why back-pressure heat rate looks terrible

**Heat-to-power ratio** — how much process heat accompanies each unit of power:

```
    Heat:power = useful heat (kCal/hr) / electrical output (kW)     kCal/kWh
```

From Drill 25: 44,069,689 / 21,400 = **2,059 kCal/kWh**. It tells you whether a
site's heat and power demands match what the plant produces.

**Now a result that looks alarming and is not.** BEE's own worked example gives a
back-pressure cogeneration plant an overall heat rate of **34,000 kCal/kWh**,
against ~3,000 for a condensing plant.

Ten times worse — and yet the back-pressure plant is the efficient one.

The resolution: **heat rate charges all the fuel against power alone.** A
back-pressure turbine makes little power per kg of steam, so heat rate looks
dreadful. But its exhaust heat is not wasted — it runs the process.

> **Heat rate is the wrong metric for a cogeneration plant. EUF is the right one.**
> This is a favourite True/False and short-answer topic. Be able to state it.

---

## The checking pass — now mandatory

From `reference/precision-and-rounding.md` §5. At the end of every question:

1. Re-add every sum
2. Re-read each constant against the data table — **and check kJ vs kCal**
3. Verify nothing below a correction uses the old value
4. Say the sanity sentence for the final answer

Four missed slips over four sessions. This is worth more marks now than more theory.

---

## Block C — Timed question (50 min)

**19th sitting N-1** (`papers/19-1.pdf`) — steam turbine cogeneration with a
back-pressure turbine, 20 marks, 25 minutes. It is the source of every drill
above, so you have already done the pieces; assemble them cold.

Then **18th sitting N-2 Set B** (`papers/18-2.pdf`) — a gas turbine cogeneration
system. Different machine, same logic.

## Block D — Log (25 min)

Tag every lost mark. Note specifically:

- Any place kJ and kCal were mixed
- Whether the isentropic formula was applied in the right direction
- Whether the checking pass caught anything — **and log what it caught**

---

## Day 4 checklist

- [ ] Can explain cogeneration and why EUF beats heat rate for it
- [ ] Know topping vs bottoming, and the three turbine types
- [ ] Can apply `h₂ = h₁ − η(h₁ − h₂s)` and sanity-check that h₂s < h₂ < h₁
- [ ] Know 1 kCal = 4.18 kJ, 1 kWh = 860 kCal = 3600 kJ
- [ ] Can compute turbine power in either unit system
- [ ] Know gearbox and generator efficiencies multiply
- [ ] Can compute EUF and heat-to-power ratio
- [ ] Can explain why a back-pressure plant's 34,000 kCal/kWh is not bad news
- [ ] Both timed questions done, checking pass applied to each

**Tomorrow (Day 5):** heat exchangers — LMTD, correction factors, and
effectiveness–NTU. 7 of 8 sittings.

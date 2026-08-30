# Day 2 — Fuels, Combustion and Carbon Accounting

**Time: 3.5 hours. Book-4 Chapter 1 (p. 1) / Book-2 Chapter 1.**

> **Change of order.** This was originally Day 3, with the indirect method on
> Day 2. That was backwards — you cannot compute the indirect method without
> stoichiometry first. Combustion now comes before the losses that depend on it.

Goals:
1. Go from an **ultimate analysis** to theoretical air, excess air and dry flue
   gas mass — the three quantities every indirect-method question needs.
2. Master the **carbon balance** and CO₂ emission calculation.
3. Finish the natural-gas half of the question you could not complete on Day 1.

---

## Block A — Concept (50 min)

### A1. The ultimate analysis

Every solid or liquid fuel question opens with a table like this:

| Constituent | % by weight |
|---|---|
| Carbon | 84 |
| Hydrogen | 11 |
| Nitrogen | 0.5 |
| Oxygen | 0.5 |
| Sulphur | 4 |

That is a **mass** breakdown of 1 kg of fuel. Everything today flows from it.

Three of those burn and release heat — **carbon, hydrogen, sulphur**. Nitrogen
passes straight through. Oxygen already in the fuel is a *credit*: it is oxygen
you do not have to supply from air.

### A2. Theoretical air

The minimum air for complete combustion:

```
    A_th = { 11.6·C + 34.8·(H₂ − O₂/8) + 4.35·S } / 100     kg air / kg fuel
```

with C, H₂, O₂, S as **percentages** from the ultimate analysis.

Where the constants come from — worth knowing so you never misremember them:

| Reaction | Mass ratio | × (1/0.23) for air |
|---|---|---|
| C + O₂ → CO₂ | 32/12 = 2.67 kg O₂ per kg C | **11.6** |
| 2H₂ + O₂ → 2H₂O | 8 kg O₂ per kg H₂ | **34.8** |
| S + O₂ → SO₂ | 32/32 = 1.0 kg O₂ per kg S | **4.35** |

Air is 23% oxygen by mass, so each oxygen requirement is divided by 0.23 to get
the air requirement. That is the only trick.

**The `O₂/8` term.** Oxygen already present in the fuel is bound to hydrogen in
the ratio 8:1 by mass (2H₂ + O₂ → 2H₂O gives 8 kg O₂ per 1 kg H₂). So `O₂/8` is
the hydrogen already spoken for. Subtract it — it will not burn for you.

### A3. Excess air from flue gas oxygen

Real boilers supply more air than theoretical, and the leftover O₂ shows up in
the flue gas. Working backwards:

```
    % EA = [ %O₂ / (21 − %O₂) ] × 100
```

21 is the percentage of oxygen in air **by volume** — flue gas analysers read by
volume, which is why 21 appears here and 23 appeared above. Do not mix them up.

Then:

```
    AAS = (1 + EA/100) × A_th          kg air / kg fuel
```

### A4. Mass of dry flue gas

Everything that goes up the stack, minus the water vapour. Two accepted routes:

**Route 1 — constituent by constituent:**

```
    m_dfg = C×(44/12) + N₂_fuel + S×(64/32)
            + (AAS × 0.77)                    ← nitrogen from air
            + (AAS − A_th) × 0.23             ← unburnt excess oxygen
```

**Route 2 — the shortcut:**

```
    m_dfg = (AAS + 1) − 9·H₂ − moisture
```

Everything in (air + fuel) goes out; subtract the water formed from hydrogen
(9 kg H₂O per kg H₂) and any fuel moisture, and what remains is dry.

Both appear in model answers and both earn full marks. Route 2 is faster; Route 1
is safer when the question gives you an odd constituent. **Learn Route 2, keep
Route 1 as a check.**

### A5. The carbon balance and CO₂ — this is what you missed

Here is the whole idea, and it is simpler than it looks.

**Every carbon atom in the fuel leaves as CO₂.** Not some of it — all of it,
under complete combustion. Carbon does not accumulate in the boiler.

So the carbon flow *in* equals the carbon flow *out*:

```
    C in fuel (kg/hr)  =  fuel rate × carbon fraction
```

Now convert carbon to CO₂ by molecular weight:

```
    C   +   O₂   →   CO₂
    12  +   32   →   44
```

**1 kg of carbon produces 44/12 = 3.67 kg of CO₂.**

Put together:

```
    CO₂ (kg/hr) = fuel rate (kg/hr) × carbon fraction × 3.67
```

> **You have already met 3.67 today.** Look back at Route 1 in A4: the first term
> is `C × (44/12)`. Same number, same chemistry — that term *is* the CO₂ in the
> flue gas. The dry flue gas mass and the CO₂ emission are two uses of one fact.
> If you had spotted that on Day 1 you would have had the emission calculation
> already.

**Only carbon counts.** Hydrogen becomes H₂O. Sulphur becomes SO₂. Nitrogen
passes through. None of them is CO₂. When a question asks for CO₂, look at the
carbon row of the ultimate analysis and ignore everything else.

**Why natural gas is cleaner — two compounding effects:**

1. Lower carbon fraction (73% vs 84%), so less CO₂ per kg burnt
2. Higher GCV (13,000 vs 10,000 kCal/kg), so you burn fewer kg for the same heat

The second effect is the larger one, and it is the one candidates forget.

---

## Block B — Guided practice (60 min)

### B1. Finish Day 1's question (35 min)

Return to the 18th sitting, N-1 — the natural gas boiler in `papers/18-1.pdf`.
You correctly found the furnace oil requirement. Now do the natural gas side.

Given for natural gas: C 73%, H₂ 23%, N₂ 3%, O₂ 1%, GCV 13,000 kCal/kg, flue gas
O₂ 4%, exit gas 180 °C, ambient 30 °C, Cp gas 0.29, Cp vapour 0.45, radiation and
moisture loss 1.2%.

**Step 1 — theoretical air**

```
    A_th = 11.6 × 0.73 + 34.8 × (0.23 − 0.01/8)
         = 8.468 + 34.8 × 0.22875
         = 16.43 kg air / kg gas
```

(No sulphur in natural gas, so the 4.35·S term vanishes.)

**Step 2 — excess air**

```
    % EA = 4 / (21 − 4) × 100 = 23.5 %
    AAS  = 1.235 × 16.43 = 20.29 kg air / kg gas
```

**Step 3 — dry flue gas**

```
    m_dfg = (0.73 × 44/12) + 0.03 + (20.29 × 0.77) + (20.29 − 16.43) × 0.23
          = 2.677 + 0.03 + 15.62 + 0.888
          = 19.22 kg / kg gas
```

**Step 4 — the two losses**

```
    L1 = 19.22 × 0.29 × (180 − 30) / 13000 × 100  =  6.43 %

    L2 = 9 × 0.23 × [584 + 0.45 × (180 − 30)] / 13000 × 100
       = 2.07 × 651.5 / 13000 × 100
       = 10.37 %
```

L2 is large because natural gas is 23% hydrogen — it makes a lot of water, and
the latent heat goes up the stack. **This is why gas boilers show lower GCV
efficiency than oil boilers despite burning cleaner.** Worth remembering as a
True/False trap.

**Step 5 — efficiency, indirect method**

```
    η = 100 − (6.43 + 10.37 + 1.2) = 82 %
```

**Step 6 — fuel rates**

```
    NG = 8000 × (665 − 90) / (0.82 × 13000) = 431.52 kg/hr
    FO = 8000 × (665 − 90) / (0.84 × 10000) = 547.62 kg/hr   ← you had this
```

**Step 7 — CO₂, the part you were missing**

```
    CO₂ from NG = 431.52 × 0.73 × 3.67 = 1156.1 kg/hr
    CO₂ from FO = 547.62 × 0.84 × 3.67 = 1688.2 kg/hr
    Increase    = 1688.2 − 1156.1      =  532.1 kg CO₂/hr
```

**Step 8 — green power to offset it**

```
    Green energy = 532.1 × 720 / 0.80 = 4,78,890 kWh per month
```

Read that last step carefully. Every kWh of wind displaces 0.80 kg of CO₂, so you
divide the excess CO₂ by 0.80 to get kWh. Multiply by 720 hours for the month.
Dividing when you should multiply is the classic slip here — check by asking
whether the answer should be bigger or smaller than the CO₂ figure.

### B2. Your turn (25 min)

**24th sitting N-1, parts (c), (d), (e)** — the paddy husk boiler from Day 1's
worked example, in `papers/24-1.pdf`. You did (a) and (b) on Day 1. Now finish it.

Paddy husk ultimate analysis: moisture 10.79, mineral matter 16.73, C 33.95,
H₂ 5.01, N₂ 0.91, S 0.09, O₂ 32.52. Flue gas O₂ 6%, exit 225 °C, ambient 32 °C,
radiation 1.6%, humidity factor 0.025, GCV 3500 kCal/kg.

Watch for: this fuel has **moisture and sulphur**, unlike natural gas, so you get
extra loss terms. The model answer is in the paper.

---

## Block C — Timed question (55 min)

**18th sitting, Set A, L-1** (`papers/18-1.pdf`) — 5 marks, 8 minutes.

> The LP and HP boilers both have 83% efficiency on furnace oil, GCV
> 10,000 kCal/kg. LP: steam enthalpy 666 kCal/kg, feedwater 95 °C. HP: steam
> enthalpy 737 kCal/kg, feedwater 105 °C. The cost of steam from the LP boiler is
> Rs 3000/tonne. Find the cost of steam from the HP boiler.

This is pure Day 1 material — evaporation ratio and nothing else. It should take
under eight minutes. If it doesn't, tell me, because that changes the plan.

Then, with the remaining time, attempt **17th sitting N-1** — a cooling tower and
CW pump question (`papers/17.pdf`). It is outside today's topic on purpose: I want
to see how you handle an unfamiliar system, not whether you memorised today.

## Block D — Log (25 min)

Mark both against the model answers. Tag every lost mark: **concept / method /
arithmetic / units / lookup**.

For the 17th N-1, note separately what you *could not start* versus what you
started and got wrong. Those are different failures and need different fixes.

---

## Homework before Day 3

1. Memorise the three combustion constants — 11.6, 34.8, 4.35 — and be able to
   say where each comes from. Reconstructing beats remembering.
2. Memorise **3.67 kg CO₂ per kg carbon**, and that it is the same 44/12 in the
   dry flue gas formula.
3. Tab the combustion section (**CA**) and the loss formulas (**BE**). Both sit
   in Book 4 Chapter 1, which starts at **p. 1** — you have the chapter pages in
   `reference/guidebook-index.md`, now fill in the **lookup table** rows, which
   are the ones that actually cost you time in the hall.
4. Write out both m_dfg routes from memory and check them against A4.

## Day 2 checklist

- [ ] Can go from ultimate analysis → A_th → EA → AAS → m_dfg unaided
- [ ] Understand why 23% appears in A_th and 21% in excess air
- [ ] Can calculate CO₂ from any fuel and know why only carbon matters
- [ ] Finished the 18th N-1 end to end
- [ ] Attempted the 24th N-1 (c)(d)(e)
- [ ] Both timed questions done and marked
- [ ] Errors tagged in `log/study-log.md`

**Tomorrow:** the indirect method in full — all seven losses, not just the two
you met today, and the sequencing that lets you compute a boiler efficiency from
nothing but a flue gas analysis.

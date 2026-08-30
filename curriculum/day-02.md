# Day 2 — Fuels, Combustion and Carbon Accounting

**Time: 3.5 hours.**

**Source:** BEE Book 2 Chapter 1, *Fuels and Combustion* —
[beeindia.gov.in/sites/default/files/2Ch1.pdf](https://beeindia.gov.in/sites/default/files/2Ch1.pdf)
(26 pp, free). Read §1.6–1.9 alongside Block A. Book 4 Ch 1 (p. 1) for the
assessment procedure.

> **Rewritten 30 Aug.** The first version gave formulas without the physics
> behind them. That was a teaching fault, not a consequence of the missing
> guidebook. This version builds every formula from what is physically
> happening, and cites the official chapter it comes from.

Goals:
1. Understand **what combustion actually is** and where the heat comes from.
2. Derive theoretical air, excess air and dry flue gas mass rather than
   memorising them.
3. Master the **carbon balance** and CO₂ emissions.
4. Understand **why the indirect method exists** — the bridge to Day 3.

---

## Block A — Concept (75 min)

### A1. What burning actually is

Combustion is **rapid oxidation of fuel, releasing heat**. Only three things in
any fuel actually burn:

| Reaction | Heat released |
|---|---|
| C + O₂ → CO₂ | **8,084 kCal/kg of carbon** |
| 2H₂ + O₂ → 2H₂O | **28,922 kCal/kg of hydrogen** |
| S + O₂ → SO₂ | **2,224 kCal/kg of sulphur** |
| 2C + O₂ → 2CO (incomplete) | only 2,430 kCal/kg of carbon |

Read the last row carefully. Carbon burnt to CO instead of CO₂ releases 2,430
instead of 8,084 — **a loss of 5,654 kCal for every kg of carbon that gets it
wrong.** That is the entire reason CO in flue gas is a loss term, and why an
analyser reading CO is reporting money going up the stack.

Hydrogen is by far the most energetic per kg — but it produces **water**, and
that will cost you later. Hold that thought until A7.

### A2. Why air, and what nitrogen does to you

You need oxygen, but you get it from air, which is only **20.9% oxygen** — the
rest is essentially nitrogen.

Nitrogen does not burn. It is a **thermal diluent**: it enters cold, absorbs heat
from the flame, and leaves hot up the stack. Every kg of nitrogen you drag
through the furnace carries heat out of it.

That single fact drives most of this paper:

- It is why **excess air is expensive** — more air means more nitrogen heated and
  discarded
- It is why the **dry flue gas loss (L1)** is usually the largest loss
- It is why nitrogen dominates the flue gas mass, as you will see in A5

At high flame temperatures some nitrogen also oxidises to NOₓ — a pollutant, not
an energy term, but it is why you cannot simply raise flame temperature freely.

**Two different percentages for air, and they trip people up:**

| Basis | Oxygen | Nitrogen | Used for |
|---|---|---|---|
| By **mass** | 23% | 77% | Theoretical air, flue gas mass |
| By **volume** | 21% | 79% | Excess air from an O₂ analyser |

Flue gas analysers measure by volume, so 21 appears in the excess air formula.
Mass balances use 23. Using the wrong one is a silent error that produces a
plausible-looking wrong answer.

### A3. The three T's

Good combustion needs all three:

- **Temperature** — high enough to ignite and sustain
- **Turbulence** — fuel and air genuinely mixed
- **Time** — long enough to finish burning before the gas leaves

Fail any one and you get unburnt carbon and CO. This is the qualitative half of
the subject and it appears in True/False questions and in "suggest improvements"
sub-parts. Worth being able to state.

### A4. From ultimate analysis to theoretical air

The **ultimate analysis** is a mass breakdown of 1 kg of fuel:

| Constituent | % by weight |
|---|---|
| Carbon | 84 |
| Hydrogen | 11 |
| Nitrogen | 0.5 |
| Oxygen | 0.5 |
| Sulphur | 4 |

Now build the air requirement from the chemistry rather than memorising it.

**Step 1 — oxygen needed per kg of each element**, straight from molecular
weights:

| Reaction | Mass ratio | O₂ per kg |
|---|---|---|
| C + O₂ → CO₂ | 12 → 32 | 32/12 = **2.67** |
| 2H₂ + O₂ → 2H₂O | 4 → 32 | 32/4 = **8.0** |
| S + O₂ → SO₂ | 32 → 32 | **1.0** |

**Step 2 — convert oxygen to air.** Air is 23% O₂ by mass, so divide by 0.23:

| Element | O₂ per kg | ÷ 0.23 → air per kg |
|---|---|---|
| Carbon | 2.67 | **11.6** |
| Hydrogen | 8.0 | **34.8** |
| Sulphur | 1.0 | **4.35** |

Those are the three constants. You never have to memorise them — 32/12/0.23 and
8/0.23 and 1/0.23 regenerate them in seconds.

**Step 3 — the oxygen credit.** Oxygen already in the fuel is oxygen you need not
supply. It is bound to hydrogen in the mass ratio 8:1 (from 2H₂ + O₂, where 8 kg
of O₂ serves 1 kg of H₂). So `O₂/8` is hydrogen already spoken for — subtract it.

```
    A_th = { 11.6·C + 34.8·(H₂ − O₂/8) + 4.35·S } / 100     kg air / kg fuel
```

### A5. Excess air — the central trade-off

Theoretical air is the *minimum*. In a real furnace, mixing is imperfect, so at
exactly theoretical air some fuel would never meet oxygen and would leave unburnt.
So you supply extra.

But every extra kg of air is extra nitrogen heated and thrown away. That gives
the trade-off that governs boiler operation:

```
   too little air  →  unburnt carbon, CO, soot        (lost fuel)
   too much air    →  nitrogen heated and discarded   (lost heat)
```

There is an optimum in between, and finding it is what combustion tuning *is*.

**Measuring it.** You cannot easily measure the air going in, but you can measure
the oxygen coming out — whatever was not consumed. Working backwards:

```
    % EA = [ %O₂ / (21 − %O₂) ] × 100
    AAS  = (1 + EA/100) × A_th
```

Why `21 − %O₂` in the denominator: of the 21% oxygen that entered, `%O₂` survived
unused, so `21 − %O₂` was consumed. The ratio of surviving to consumed is the
ratio of excess air to theoretical air.

**Sanity anchor:** 4% O₂ ≈ 23% excess air; 6% ≈ 40%; 8% ≈ 62%. If your excess air
comes out negative or above ~150%, re-read the question.

### A6. Mass of dry flue gas

Everything leaving up the stack, minus the water. **Route 1**, constituent by
constituent:

```
    m_dfg = C×(44/12)              ← CO₂ formed
          + N₂ in fuel
          + S×(64/32)              ← SO₂ formed
          + AAS × 0.77             ← nitrogen from air
          + (AAS − A_th) × 0.23    ← unused excess oxygen
```

Note what dominates: for the natural gas case you will do in Block B, nitrogen
from air is 15.6 of 19.2 kg — **over 80% of the flue gas mass is nitrogen you
never wanted.** That is A2 made numerical.

**Route 2**, the shortcut — mass in equals mass out:

```
    m_dfg = (AAS + 1) − 9·H₂ − moisture
```

Air plus 1 kg of fuel goes in; subtract the water formed (9 kg of H₂O per kg of
H₂, from 2H₂ + O₂ → 2H₂O) and any fuel moisture. What's left is dry.

Both earn full marks. Learn Route 2, keep Route 1 as a check.

### A7. Why the indirect method exists — the bridge to Day 3

Here is the idea Day 3 is built on, and it is worth getting now.

The **direct method** you learnt on Day 1 asks: how much heat reached the steam,
divided by how much heat the fuel held? Simple, but it tells you *nothing about
where the losses went*. An auditor cannot act on it.

The **indirect method** asks the complementary question: where did all the heat
go? Track every loss, and whatever is left must have reached the steam.

```
    η = 100 − (sum of all losses)
```

This is just a **heat balance** — energy in equals energy out, so accounting for
the leaks tells you the yield. Its value is that each loss is separately
identified, so you know what to fix. That is why BEE requires it for audits and
why Paper 4 examines it rather than the direct method.

**Where the heat actually goes:**

| Loss | Physically what happens |
|---|---|
| L1 dry flue gas | Hot gas — mostly nitrogen — leaves up the stack |
| L2 hydrogen | H₂ burns to water; the water is vaporised and the latent heat leaves as steam |
| L3 fuel moisture | Water already in the fuel is boiled off and lost |
| L4 air moisture | Humidity in the combustion air is heated and lost |
| L5 CO | Carbon burnt to CO instead of CO₂ — 5,654 kCal/kg forgone (A1) |
| L6 radiation | Heat through the boiler shell to the boiler house |
| L7 unburnt ash | Carbon leaving in the ash, never burnt at all |

You already have the physics for L1 (A2 — nitrogen carries heat out) and for L5
(A1 — incomplete combustion). Day 3 does all seven in full.

**Now the hydrogen point from A1 pays off.** Natural gas is ~23% hydrogen against
furnace oil's ~11%. Hydrogen releases the most heat per kg — but it makes water,
and vaporising that water consumes ~584 kCal/kg of latent heat which goes
straight up the stack. So:

> **A gas boiler shows lower efficiency on GCV than an oil boiler, despite gas
> burning cleaner.** In Block B you will compute L2 = 10.37% for natural gas
> against roughly 6–7% for oil. That difference is entirely hydrogen.

This is also the **GCV vs NCV** distinction. Gross calorific value counts the
latent heat of that water as if recoverable; net calorific value does not. Indian
practice and this exam use **GCV** unless a question says otherwise — which is
why L2 must be subtracted explicitly.

---

## Block B — Guided practice (60 min)

### B1. Finish Day 1's question (35 min)

The 18th sitting N-1 (`papers/18-1.pdf`) — the natural gas boiler you could not
complete. You now have every tool.

Natural gas: C 73%, H₂ 23%, N₂ 3%, O₂ 1%. GCV 13,000 kCal/kg. Flue gas O₂ 4%,
exit 180 °C, ambient 30 °C. Cp gas 0.29, Cp vapour 0.45. Radiation + air moisture
1.2%.

**Step 1 — theoretical air** (A4)

```
    A_th = 11.6 × 0.73 + 34.8 × (0.23 − 0.01/8)
         = 8.468 + 34.8 × 0.22875
         = 16.43 kg air / kg gas
```

No sulphur in natural gas, so that term vanishes.

**Step 2 — excess air** (A5)

```
    % EA = 4 / (21 − 4) × 100 = 23.5 %
    AAS  = 1.235 × 16.43 = 20.29 kg air / kg gas
```

Matches the anchor in A5: 4% O₂ ≈ 23% excess air. ✓

**Step 3 — dry flue gas** (A6)

```
    m_dfg = (0.73 × 44/12) + 0.03 + (20.29 × 0.77) + (20.29 − 16.43) × 0.23
          = 2.677 + 0.03 + 15.62 + 0.888
          = 19.22 kg / kg gas
```

Nitrogen from air is 15.62 of 19.22 — **81% of the flue gas.** A2, in numbers.

**Step 4 — the two losses**

```
    L1 = 19.22 × 0.29 × (180 − 30) / 13000 × 100  =  6.43 %
    L2 = 9 × 0.23 × [584 + 0.45 × (180 − 30)] / 13000 × 100  =  10.37 %
```

L2 exceeds L1. For a gas boiler the water from hydrogen costs more than the whole
stack loss — exactly as A7 predicted.

**Step 5 — efficiency** (A7)

```
    η = 100 − (6.43 + 10.37 + 1.2) = 82 %
```

**Step 6 — fuel rates**

```
    NG = 8000 × (665 − 90) / (0.82 × 13000) = 431.52 kg/hr
    FO = 8000 × (665 − 90) / (0.84 × 10000) = 547.62 kg/hr   ← you had this
```

**Step 7 — CO₂**

Every carbon atom leaves as CO₂. From C + O₂ → CO₂, 12 → 44, so **1 kg of carbon
gives 44/12 = 3.67 kg CO₂**:

```
    CO₂ (kg/hr) = fuel rate × carbon fraction × 3.67

    NG:  431.52 × 0.73 × 3.67 = 1156.1 kg/hr
    FO:  547.62 × 0.84 × 3.67 = 1688.2 kg/hr
    Increase                  =  532.1 kg CO₂/hr
```

**Only carbon makes CO₂.** Hydrogen → H₂O, sulphur → SO₂. And note 3.67 is the
same 44/12 from Route 1 in A6 — that term *is* the CO₂ in the flue gas.

Gas wins on CO₂ twice over: less carbon per kg (73 vs 84%), and fewer kg burnt
because GCV is higher (13,000 vs 10,000). The second effect is the larger.

**Step 8 — green power offset**

```
    Green energy = 532.1 × 720 / 0.80 = 4,78,890 kWh/month
```

*Sanity sentence:* each kWh displaces only 0.8 kg CO₂, so the kWh figure must
exceed the CO₂ figure. 478,890 > 383,112. ✓

### B2. Your turn (25 min)

**24th sitting N-1 (c)(d)(e)** — the paddy husk boiler (`papers/24-1.pdf`). You
did (a) and (b) on Day 1.

Husk: moisture 10.79, mineral matter 16.73, C 33.95, H₂ 5.01, N₂ 0.91, S 0.09,
O₂ 32.52. Flue gas O₂ 6%, exit 225 °C, ambient 32 °C, radiation 1.6%, humidity
factor 0.025, GCV 3500.

This fuel has **moisture and sulphur**, so extra loss terms appear. Predict before
calculating: with 32.5% oxygen already in the fuel, will theoretical air be high
or low compared with the natural gas case?

---

## The sanity sentence — required from today

Every final answer gets one written line first:

> *"This should be larger/smaller than X, because…"*

From physics, in words, **before** checking arithmetic. Three seconds, and it
catches the inversion that cost you marks on Day 1. See
`reference/reciprocal-traps.md`.

Write it on the script — examiners award marks for interpretation, and the model
answers state exactly this reasoning before calculating.

---

## Block C — Timed question (45 min)

**17th sitting N-1** (`papers/17.pdf`) — a cooling tower and CW pump system,
20 marks, 25 minutes.

Deliberately outside today's topic. I want to see how you approach an unfamiliar
system, not whether you absorbed today's material. Read it, decide what physics
applies, attempt what you can.

## Block D — Log (20 min)

Mark against the model answers. Tag each lost mark: **concept / method /
arithmetic / units / lookup**.

For the 17th N-1, separate **could not start** from **started and got it wrong** —
different failures, different fixes.

Log separately any **inversion you caught yourself**. That is the check working.

---

## Homework before Day 3

1. Read BEE Book 2 Ch 1 §1.6–1.9
   ([2Ch1.pdf](https://beeindia.gov.in/sites/default/files/2Ch1.pdf)) — the source
   for Block A.
2. Be able to *derive* 11.6, 34.8 and 4.35, not recall them.
3. Know why 23% appears in theoretical air and 21% in excess air.
4. Memorise 3.67 kg CO₂ per kg carbon, and its link to 44/12.
5. Tab **CA** (combustion) and **BE** (losses); fill the lookup rows in
   `reference/guidebook-index.md`.

## Day 2 checklist

- [ ] Can explain what nitrogen does and why excess air costs money
- [ ] Can derive A_th from molecular weights unaided
- [ ] Know why 23% vs 21%, and when each applies
- [ ] Can compute m_dfg by both routes
- [ ] Can calculate CO₂ and explain why only carbon counts
- [ ] Can explain why the indirect method exists and what a heat balance is
- [ ] Can say why a gas boiler shows lower GCV efficiency than an oil boiler
- [ ] 18th N-1 finished end to end
- [ ] 24th N-1 (c)(d)(e) attempted
- [ ] 17th N-1 attempted under time
- [ ] Sanity sentence written on every answer

**Tomorrow:** the indirect method in full — all seven losses with the physics of
each, blowdown, and computing efficiency from nothing but a flue gas analysis.

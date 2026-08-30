# Day 2B — What Comes Out, and Where the Heat Goes

**Time: 3 hours.**

**Source:** BEE Book 2 Ch 1 §1.6–1.9
([2Ch1.pdf](https://beeindia.gov.in/sites/default/files/2Ch1.pdf))

Day 2A worked out what goes *in* — the air. Today: what comes *out*, and why
that matters. Same one-rung-at-a-time approach.

**Prerequisite:** every box on the Day 2A checklist. If any is unticked, go back.
Today builds directly on it.

---

## Rung 9 — The mass of the flue gas

Nothing disappears. Everything that enters the furnace leaves it. So:

```
    mass out  =  mass in  =  air supplied + fuel
```

For our furnace oil at 4% O₂ (Day 2A, Drill 5): AAS = 16.95 kg air per kg fuel.

```
    total gas out = 16.95 + 1 = 17.95 kg per kg of fuel
```

That is the whole idea. The rest is bookkeeping.

**Why "dry" flue gas?** Some of that stream is water vapour — from burning
hydrogen, and from any moisture in the fuel. Water is treated separately because
it carries **latent heat**, which behaves differently from ordinary hot gas. So we
subtract it:

```
    m_dfg = (AAS + 1) − 9·H₂ − moisture
```

**Where does 9·H₂ come from?** From 2H₂ + O₂ → 2H₂O: 4 kg of hydrogen makes 36 kg
of water, so **1 kg of hydrogen makes 9 kg of water.**

For our oil (H₂ = 0.11, no moisture):

```
    water formed = 9 × 0.11 = 0.99 kg
    m_dfg = 17.95 − 0.99 = 16.96 kg dry gas / kg fuel
```

**Drill 6.** Natural gas, H₂ = 23%, AAS = 20.29 kg/kg. Find m_dfg.

<details><summary>Answer</summary>

```
    total  = 20.29 + 1 = 21.29
    water  = 9 × 0.23  = 2.07
    m_dfg  = 21.29 − 2.07 = 19.22 kg / kg gas
```

Over 2 kg of water per kg of fuel. Remember that number — Rung 11 explains why it
costs you.
</details>

---

## Rung 10 — CO₂

Every carbon atom that enters leaves as CO₂. Carbon does not accumulate.

```
    C + O₂ → CO₂
    12 → 44           ⟹   1 kg carbon makes 44/12 = 3.67 kg CO₂
```

Same move as Rung 1, different direction: there we asked what carbon *needs*,
here we ask what it *becomes*.

```
    CO₂ (kg/hr) = fuel rate × carbon fraction × 3.67
```

**Only carbon.** Hydrogen makes water, sulphur makes SO₂, nitrogen passes
through. When asked for CO₂, read the carbon row and ignore the rest.

**Drill 7.** A boiler burns 550 kg/hr of furnace oil (84% carbon). CO₂ per hour?

<details><summary>Answer</summary>

550 × 0.84 × 3.67 = **1,696 kg CO₂/hr**
</details>

**Drill 8.** Same boiler switches to natural gas (73% carbon) and, because the
GCV is higher, burns only 432 kg/hr. CO₂ now?

<details><summary>Answer</summary>

432 × 0.73 × 3.67 = **1,157 kg CO₂/hr** — a drop of about a third.

Gas wins twice: less carbon per kg (73 vs 84%), *and* fewer kg burnt. The second
effect is the larger one.
</details>

---

## Rung 11 — Where the heat goes

Now the idea the whole of Day 3 rests on.

Burning the fuel releases a fixed amount of heat. Not all of it reaches the steam.
Ask the simple question: **where does the rest go?**

**Loss 1 — the hot gas leaves.** You calculated m_dfg in Rung 9: about 17 kg of
gas per kg of fuel, mostly nitrogen you never wanted, leaving at 180–250 °C when
it entered at ambient. Heating that much gas costs real energy:

```
    L1 = m_dfg × Cp × (T_gas − T_ambient) / GCV × 100
```

That is just `m·Cp·ΔT` — heat needed to warm a mass — expressed as a percentage
of the fuel's energy. `Cp` for flue gas is 0.24–0.29 kCal/kg°C.

**Loss 2 — the water leaves as steam.** Rung 9 showed hydrogen makes 9 kg of water
per kg of hydrogen. That water is produced as **vapour**, and turning water into
vapour costs about **584 kCal/kg of latent heat**. That heat goes up the stack and
is never recovered:

```
    L2 = 9·H₂ × [584 + Cp_steam × (T_gas − T_ambient)] / GCV × 100
```

The bracket has two parts: 584 to vaporise it, plus Cp×ΔT to superheat the vapour
to stack temperature.

**Now the payoff.** Natural gas is 23% hydrogen against oil's 11%. Twice the
hydrogen, twice the water, twice this loss. Which is why:

> **A gas boiler shows lower efficiency on GCV than an oil boiler, even though gas
> burns cleaner.** Not a flaw in the boiler — a property of the fuel.

This is also what **GCV vs NCV** means. Gross calorific value counts that latent
heat as though it were available; net calorific value does not. This exam uses
**GCV**, which is why L2 must be subtracted explicitly.

**The method in one line.** Account for every loss, and whatever remains reached
the steam:

```
    η = 100 − (all losses)
```

That is the **indirect method** — a heat balance. Its value over the direct method
is that each loss is named separately, so an auditor knows what to fix. Day 3 does
all seven.

---

## Putting it together (45 min)

Now — and only now — watch the pieces combine. This is the 18th sitting N-1
(`papers/18-1.pdf`), the question that stopped you.

Natural gas: C 73%, H₂ 23%, N₂ 3%, O₂ 1%. GCV 13,000. Flue gas O₂ 4%, exit
180 °C, ambient 30 °C. Cp gas 0.29, Cp vapour 0.45. Radiation + air moisture 1.2%.
Steam load 8 TPH at 665 kCal/kg, feedwater 90 °C.

Each step names the rung it uses. Nothing here is new.

| | Step | Rung |
|---|---|---|
| 1 | `A_th = 11.6×0.73 + 34.8×(0.23 − 0.01/8) = 8.468 + 7.96 = 16.43` | 2A-7 |
| 2 | `EA = 4/(21−4)×100 = 23.5%`  →  `AAS = 1.235 × 16.43 = 20.29` | 2A-8 |
| 3 | `m_dfg = (20.29+1) − 9×0.23 = 21.29 − 2.07 = 19.22` | 9 |
| 4 | `L1 = 19.22 × 0.29 × (180−30) / 13000 × 100 = 6.43%` | 11 |
| 5 | `L2 = 9×0.23 × [584 + 0.45×150] / 13000 × 100 = 10.37%` | 11 |
| 6 | `η = 100 − (6.43 + 10.37 + 1.2) = 82%` | 11 |
| 7 | `NG = 8000×(665−90) / (0.82×13000) = 431.52 kg/hr` | Day 1 |
| 8 | `FO = 8000×(665−90) / (0.84×10000) = 547.62 kg/hr` ✓ you had this | Day 1 |
| 9 | `CO₂: NG 431.52×0.73×3.67 = 1156.1;  FO 547.62×0.84×3.67 = 1688.2` | 10 |
| 10 | `Increase = 532.1 kg/hr`  →  `green = 532.1×720/0.80 = 4,78,890 kWh` | — |

Note step 5 exceeds step 4: for a gas boiler the water costs more than the entire
stack loss. Exactly as Rung 11 predicted.

*Sanity sentence for step 10:* each kWh displaces only 0.8 kg CO₂, so the kWh
figure must be **larger** than the CO₂ figure. 478,890 > 383,112. ✓

**Work through it with the paper open.** If a step is unclear, name the step
number — that tells me precisely which rung to rebuild.

---

## Practice (30 min)

**24th sitting N-1, parts (c) and (d)** (`papers/24-1.pdf`) — the paddy husk
boiler. You already found A_th = 4.27 in Day 2A Drill 4, so you are partway there.

Husk: moisture 10.79%, C 33.95%, H₂ 5.01%, N₂ 0.91%, S 0.09%, O₂ 32.52%.
Flue gas O₂ 6%, exit 225 °C, ambient 32 °C, radiation 1.6%, GCV 3500.

**Cp of flue gas = 0.24. Cp of superheated steam = 0.43.**

> These were missing when this practice was first set, which caused a wrong L1.
> They are two different substances: **L1 heats gas (0.24); L2–L4 heat water
> vapour (0.43–0.45).** The 24th paper gives neither — both come from the
> guidebook. See `reference/formula-sheet.md` §1.

Do only these:

1. Excess air and AAS (Rung 2A-8)
2. m_dfg — remember this fuel **has moisture**, so subtract it too (Rung 9)
3. L1 (Rung 11)

Stop there. L2, L3 and the rest come on Day 3.

*Predict first:* husk has 10.79% moisture and only 33.95% carbon. Will its L1 be
higher or lower than the natural gas boiler's 6.43%, and why?

---

## No timed question today

Deliberately. The cooling tower question that was set here originally was a bad
call on a day already carrying too much. It returns on Day 10, where it belongs.

---

## Day 2B checklist

- [ ] Understand mass in = mass out for the furnace
- [ ] Can compute m_dfg and explain why water is separated out
- [ ] Know 1 kg hydrogen makes 9 kg water, and why
- [ ] Can calculate CO₂ and explain why only carbon counts
- [ ] Can explain L1 physically — heating gas you did not want
- [ ] Can explain L2 physically — latent heat leaving as vapour
- [ ] Can say why gas shows lower GCV efficiency than oil
- [ ] Followed all ten steps of the combined example
- [ ] Husk practice parts 1–3 attempted

**Tell me any step number you could not follow.** That is more useful than "I got
lost" — it points at the exact rung.

**Tomorrow (Day 3):** all seven losses, blowdown, and a full efficiency from
nothing but a flue gas analysis.

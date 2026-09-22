# Reciprocal Traps and the Sanity Check

The single most expensive error type in Paper 4 is not arithmetic. It is
**getting a ratio the right way up.** The method is sound, the numbers are
right, and the final line divides where it should multiply.

It costs the whole answer, and it is invisible unless you check.

## Why it happens

Paper 4 is full of quantities that come in reciprocal pairs. Both members of the
pair describe the same physical fact; they just point in opposite directions.
When a question hands you one and asks for something built on the other, the
inversion is easy to miss because *the number looks plausible either way*.

## The pairs — know all of these

| Quantity | Its reciprocal | Relationship |
|---|---|---|
| Evaporation ratio (kg steam / kg fuel) | Specific fuel consumption (kg fuel / kg steam) | SFC = 1 / ER |
| Evaporation ratio | Steam cost | cost ∝ **1 / ER** |
| Boiler efficiency | Fuel required for a given load | fuel ∝ **1 / η** |
| Power plant efficiency | Heat rate (kCal/kWh) | η = 860 / HR |
| COP | kW/TR | kW/TR = 3.517 / COP |
| Gross heat rate | Net heat rate | net = gross / (1 − aux fraction) |
| Efficiency | Specific energy consumption | SEC ∝ 1 / η |

Read the middle column as "the better this gets, the worse that number looks."
Higher ER, higher efficiency and higher COP are all *good*, and each one **drives
its partner down**. If a change improves the plant and your paired number also
rose, you have inverted.

## The check — three seconds, every ratio

Before writing a final answer that came from a ratio, ask:

> **Should this be bigger or smaller than what I started with — and why?**

Answer it in words, from physics, *before* you look at your arithmetic. Then see
whether your number agrees.

Worked example, from the 18th sitting L-1:

- The HP boiler has a lower evaporation ratio (13.13 vs 14.54)
- Lower ER means **more fuel burnt per tonne of steam**
- More fuel per tonne means that steam **costs more**
- LP steam is Rs 3000/tonne, so HP steam must exceed Rs 3000

Any answer below 3000 is wrong before you check a single digit. That one sentence
catches the error every time.

## The inversion-proof method — track real quantities

When a ratio makes you uneasy, stop working in ratios and follow an actual
physical amount through the problem. You cannot invert a quantity you are
literally counting.

Same question, done by tracking one tonne of fuel oil:

```
    1 tonne FO  →  14.54 tonnes of LP steam
    LP steam sells at Rs 3000/tonne
    ⟹ 1 tonne FO is worth 14.54 × 3000 = Rs 43,608

    1 tonne FO  →  13.13 tonnes of HP steam
    ⟹ HP steam costs 43,608 / 13.13 = Rs 3,322/tonne
```

Every line has units you can say out loud. There is no ratio to flip. It takes
perhaps thirty seconds longer and it cannot go wrong in this particular way.

The model answers in `papers/` often give both routes — the ratio method and the
quantity-tracking method — and award full marks for either. **Use ratios when
confident, quantities when not.**

## If you catch yourself mid-question

Good — that is the check working. Note it in the study log as a *caught*
inversion rather than an error. The pattern worth watching is not how many you
make, but whether the ratio you get wrong is one you have already met.

---

## The running list

Every ratio in this paper that can be flipped, and the sentence that settles it.

| # | Where | The ratio | The settling question |
|---|---|---|---|
| 1 | Day 1 | Evaporation ratio q vs 1/q | Does a *better* boiler make more steam per kg fuel, or less? |
| 2 | Day 1 | Steam cost × vs ÷ efficiency | Does *worse* efficiency make steam dearer? Then divide. |
| 3 | Day 3 | Carbon fraction of the fuel | Which fuel is it? Read the row again. |
| 4 | Day 6 | SEC — energy per unit output | Does *more* output at the same energy give a bigger or smaller SEC? |
| 5 | Day 9 | Payback = cost / saving | A bigger saving pays back *sooner*, so saving is on the bottom. |
| 6 | Day 10 | Pump vs overall efficiency | Motor input or shaft power in the denominator? Overall uses motor input. |
| 7 | Day 11 | COP vs kW/TR | They are reciprocals. Higher COP, lower kW/TR. |
| 8 | **Day 13** | **Thermic fluid heater fuel after efficiency improvement** | Same heat duty, better efficiency → **less** fuel. So `new fuel = old × η_old/η_new`. If it went up, you inverted it. |
| 9 | **Day 13** | **Textile liquor-ratio loss margin** | Do losses make the computed bath bigger or smaller? Smaller — so the margin divides. |
| 10 | **Day 13** | **Cement-to-clinker factor** | Cement always weighs *more* than the clinker in it. If cement < clinker, flip it. |
| 12 | **Mock 2** | **kJ ↔ kCal** ⚠️ *the first unit-system member* | A kCal is the **bigger** unit, so there are always **fewer** of them: kJ ÷ 4.186. Anchor: water is 1 kCal/kg°C = 4.186 kJ/kg°C — **nothing in this paper has a specific heat above water's**, so a kCal/kg°C above 1.0 is inverted. |
| 11 | **Day 12** | **Heat rate — comparing two plants** ⚠️ *first uncaught inversion since Day 1* | Heat rate is input per unit output, so **lower is better**. Never answer on the inverse quantity: convert both to efficiency (`860/HR`) and compare those. |

## The general rule behind #5, #7 and #11

Three of these are the same trap wearing different clothes. Each pairs an
**inverse** quantity (input per unit output — lower is better) with a **direct**
one (output per unit input — higher is better):

| Inverse — lower is better | Direct — higher is better | Bridge |
|---|---|---|
| Heat rate, kCal/kWh | Efficiency, % | `η = 860/HR` |
| kW/TR | COP | `COP = 3024/(kW/TR × 860)` |
| Specific energy consumption | Output per unit energy | reciprocal |

Every *other* performance number in this paper — efficiency, COP, evaporation
ratio, effectiveness, EUF, yield — runs the normal way. So "the bigger number
wins" is a heavily reinforced reflex, and on these three it fires and is wrong.

**The habit that removes the risk entirely: never answer a comparison on the
inverse quantity.** Convert both sides to the direct one, then compare. It costs
two divisions and it cannot go wrong.

## A cousin: differencing before converting

Not an inversion, but the same shape of mistake — combining two cases before
putting them on a common footing.

```
    Δ(E)/k  ≠  Δ(E/k)        whenever k differs between the two cases
```

If the two cases quote **different GCVs, tariffs or emission factors**, you must
convert each one *first* and difference afterwards. On the 24th sitting's DRI
question this is worth 40% of the answer. See `concept-distinctions.md` entry 14.

**The pattern to watch is not how many you make** — it is whether the ratio you get
wrong is one you have already met.

---

# ⚠️ A second cousin: intensive quantities do not add

**Heat rate, kW/TR, SEC, evaporation ratio, kWh/tonne — all of them are ratios.**
Two of anything measured in a "per" unit combine by **re-doing the division on the
totals**, never by addition, and only by a plain average when the weights happen to
be equal.

```
    WRONG      station HR  =  HR₁ + HR₂
    WRONG      station HR  =  (HR₁ + HR₂)/2      ← unless the outputs are equal

    RIGHT      station HR  =  total heat in / total kWh out

                            HR₁·kWh₁  +  HR₂·kWh₂
                          = ──────────────────────    ← weighted by GENERATION
                               kWh₁  +  kWh₂
```

**The weights are always the denominator of the ratio**, so:

| Ratio | Weight it averages by |
|---|---|
| heat rate, kCal/kWh | **kWh generated** |
| kW/TR | **TR of cooling** |
| SEC, kWh/tonne | **tonnes produced** |
| evaporation ratio, kg steam/kg fuel | **kg of fuel** |
| specific coal, kg/kWh | **kWh generated** |

**The 21st sitting's N-4(C) is the exam case:** two 200 MW units at the same load,
so the weights *are* equal and the plain average is right — `(2852.8 + 2790)/2 =
2821.4`. **Adding them gives 6258 and an implied plant efficiency of 13.7%.**

> ### The sanity band that catches it
>
> ```
>     turbine heat rate        2000 – 2600 kCal/kWh
>     gross / unit heat rate   2300 – 3000
>     net / station heat rate  2600 – 3300
>     above 4000               ⟹ wrong, unless a back-pressure
>                                 cogeneration set (30,000+)
> ```
>
> **And the free check on any heat rate: `860/answer`.** A condensing plant lands
> between **25% and 40%**. Anything outside that, stop and look again. *(A
> percentage that is obviously wrong gets caught by instinct; a four-digit
> kCal/kWh does not — so give it a band and use it.)*

**Why a car makes it obvious:** two cars each doing 15 km/litre do not make a
garage that does 30. Fuel economy is per-litre; heat rate is per-kWh. **Put the two
fuels over the two distances and divide once.**

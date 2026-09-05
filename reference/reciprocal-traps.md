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

**The pattern to watch is not how many you make** — it is whether the ratio you get
wrong is one you have already met.

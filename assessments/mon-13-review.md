# Review — Monday 1.3 · 19th sitting N-4(A), 60 MW captive power plant

**Started 21:22.** No finish time written — **write both, always**; the clock is
half the assessment and Mock 3 ran 162 minutes.

## Score: 13 / 20

| | Part | Marks | You | |
|---|---|---|---|---|
| a | Gross heat rate | 8 | **2950.899** | ✅ full |
| b | Net heat rate | 3 | **3278.777** | ✅ full |
| c | Dryness fraction of exhaust | 2 | 38.681 % | ❌ |
| d | Condenser heat load | 3 | *skipped* | ❌ |
| e | Specific coal consumption | 2 | **0.696 kg/kWh** | ✅ full |
| f | Overall efficiency | 2 | 26.229 % | ❌ |

**The three you lost are worth 7 marks and took under four minutes each to fix.**

---

# ⚠️ The headline — your alarm fired three times and you wrote the answer down anyway

You wrote, in your own hand:

> *"This is **too high**"* … *"**Too low**"* … *"**Too low**"*

**Three times the sanity check worked perfectly.** You knew 21,20,571 kCal/kWh was
absurd. You knew a 38.7% dryness fraction was absurd. You knew 26.2% was low.

**And all three wrong answers stayed on the page.**

> **The ladder is doing its job. What is missing is the next instruction.**
>
> ```
>     alarm fires  →  STOP  →  go back one line  →  find it  →  rewrite
> ```
>
> **Not "note it and move on."** An answer you have already labelled wrong earns
> zero — the same as a blank — but it has cost you the time as well.
> **Budget two minutes for the recheck the moment you write "too high".**

**The evidence that this is a habit, not an accident:** part (a)'s alarm *did* make
you restart, and the restart was **completely correct**. You already know how to do
this. On (c) and (f) you rang the bell and kept walking.

---

# Part (a) — right in the end, and worth reading for how you got there

**Your second attempt is exactly BEE's method and exactly right:**

```
    η_boiler = Q Δh/(q × GCV)   ⟹  q = 231(793 − 130)/4240      = 41.758 TPH
    GHR      = q × GCV/60000                                     = 2950.899 ✓
```

**Eight marks. Nothing to add.** But the first attempt is worth dissecting, because
both errors in it are general.

```
    You wrote:   HR_turbine = 860 × 554 × 231000 / 60000  = 18,34,294
```

### Error 1 · The 860 does not belong — and here is the test

**860 converts between kW and kCal/h. Nothing else.**

```
    kW  ──× 860──▶  kCal/h            kCal/h  ──÷ 860──▶  kW
```

Your numerator was already `kg/hr × kCal/kg = kCal/hr`. **It was in heat units
before you touched it.** Multiplying by 860 asked it to convert again, and 860
kCal/kWh is what came out — literally, a factor of 860 too big.

> ### The 860 audit — run it before you write the constant
>
> **Ask: what unit is my numerator in right now?**
>
> ```
>     already kCal/h  (mass × enthalpy, or fuel × GCV)  →  NO 860
>     in kW           (a power, an output, a load)      →  × 860
> ```
>
> **A heat rate's numerator is never a power.** So in a heat rate calculation built
> from steam or from fuel, **860 never appears in the numerator** — only in the
> efficiency at the end.
>
> **The one place it does appear:** the 19th N-1 EUF, where power in kW and steam
> heat in kCal/h must be brought to the same currency. There the 860 is on the
> *power*, not on the steam.

### Error 2 · 554 is the exhaust, not the drop

You caught this yourself — **793 is written in above it**. The turbine's heat input
is the heat *the steam carries above the feedwater it came from*:

```
    heat in the steam  =  231000 × (793 − 130)   NOT  231000 × 554
```

**554 is where the steam ends up**, not what it gave up. It belongs to part (c)
and part (d), and to nothing else.

### ⭐ The reconciliation you were one line away from

**Fix those two and your first attempt lands on your second:**

```
    HR_turbine = 231000 × (793 − 130)/60000            = 2553 kCal/kWh
                 ÷ η_boiler 0.865                      = 2951
    GHR from coal (your page 2)                        = 2950.899
```

**The same number, from two sides of the boiler.** That is the check I said was the
session, and you had both halves on the page. **Had you run it, the 18,34,294 could
not have survived thirty seconds.**

> **Add this to the exam card:** *when a question gives me both fuel and steam, I
> get the gross heat rate twice and they must agree.* The 19th, 21st and 17th
> sittings all hand you both.

---

# Part (c) — the formula is right, the letters are swapped

```
    You wrote:   h = h_g + x·h_fg     ⟹   554 = 554 + x(45.5)
    It is:       h = h_f + x·h_fg     ⟹   554 = 45.5 + x(571.6)
                                                x = 508.5/571.6 = 0.889
```

**Read the identity out loud and it cannot go wrong:**

> *"Wet steam is **water, plus the fraction of it that has been boiled**."*
>
> ```
>     h  =  h_f     +     x  ·  h_fg
>           ▲                   ▲
>       start from            add back the
>       SATURATED WATER       latent heat, but only
>       (the bottom)          the fraction x of it
> ```

**h_f, not h_g.** If you start from `h_g` — steam that is *already* fully dry —
there is nothing left to add, which is exactly what your line said: `554 = 554 + …`,
forcing x toward zero.

### ⚠️ The trap in the data table, and it is deliberate

**Look at the two numbers you swapped:**

```
    Condenser temperature                         : 45.5 °C
    Enthalpy of water at that pressure and temp   : 45.5 kCal/kg
```

**They are the same figure.** That is not a coincidence — below 100 °C, water's
enthalpy in kCal/kg is numerically its temperature in °C, because `Cp = 1`. **BEE
prints both and it invites exactly the swap you made**, sliding 45.5 into the h_fg
slot where 571.6 belonged.

> **Label every number before you use it.** `h_f = 45.5`, `h_fg = 571.6`,
> `h_exhaust = 554`. Three labelled lines cost fifteen seconds and would have made
> this unmissable.

**And the sanity range you already half-knew:** a condensing turbine exhausts at
**0.86–0.93** dry. Below 0.85 the blades erode; that is the design limit, not a
number a working plant reports. **0.387 is not slightly low, it is impossible** —
it would mean the condenser is full of water with a little steam in it.

---

# Part (d) — three marks lost to part (c), not to part (d)

```
    Condenser heat load = steam flow × (h_exhaust − h_condensate)
                        = 231000 × (554 − 45.5)       = 11,74,63,500 kCal/hr

    BEE's route         = 231000 × 571.6 × 0.889      = 11,73,83,200 kCal/hr
```

**They are the same calculation** — `x · h_fg` *is* `(554 − 45.5)` by definition.
BEE routes through the dryness fraction; the direct subtraction needs no x at all.

> ### The lesson is about dependency, not about condensers
>
> **You skipped (d) because (c) was broken. But (d) never needed (c).** The direct
> form uses two numbers straight off the table.
>
> **Before abandoning a part, ask whether it truly depends on the part that failed.**
> Here, three marks were sitting in plain sight behind a two-mark error.

---

# Part (f) — the rung error, in mirror image

```
    You wrote:   η = 860/NHR = 860/3278.8 = 26.229 %
    It is:       η = 860/GHR = 860/2950.9 = 29.14 %
```

**This is the Mock 3 error, pointing the other way.** In Mock 3 you took
`860/turbine HR` — one rung too low. Here you took `860/net` — one rung too high.

> ### So the rule needs to be sharper than "860 over a heat rate"
>
> ```
>     "Overall efficiency" / "plant efficiency"   =  860 / GROSS      ← ALWAYS
>
>     860/turbine  =  turbine CYCLE efficiency     (a different question)
>     860/net      =  efficiency of EXPORTED power (a different question)
> ```
>
> **Overall efficiency is fuel-in against what the plant made.** The plant *made*
> 60 MW. The 54 MW that left the fence is a commercial figure, not the machine's
> efficiency — the 6 MW the auxiliaries ate was still generated, and the plant does
> not become less efficient because it used some of its own output.
>
> **BEE names it when it wants the other one.** If a question wants net, it will say
> *"efficiency of power exported"* or *"net efficiency"*. Unqualified **"overall"**
> or **"plant"** means gross. Every time.

**BEE's second route is the one to remember, because it has no rung to pick:**

```
    η = (60000 kW × 860) / (41758 kg/hr × 4240 kCal/kg) = 29.14 %
        ────────────────    ───────────────────────────
        what came out           what went in
```

**Energy out over energy in, with no heat rate in sight.** When you are unsure which
rung a question means, **go back to first principles and divide output by input.**
It cannot be got wrong, and it is two lines.

*(Note where the 860 sits here: on the **kW**, because 60000 is a power. The 860
audit passes.)*

---

# What to carry into 1.4 and 1.5

1. **When the alarm fires, stop.** Two minutes, one line back. This is the whole
   review.
2. **Label every number off the data table before using it** — `h_f = 45.5`,
   `h_fg = 571.6`. The 19th's table is built to punish unlabelled figures.
3. **Overall efficiency = 860/gross.** Or skip the ladder entirely:
   `kW × 860 / (fuel × GCV)`.
4. **Run the 860 audit** before writing the constant: is my numerator already in
   kCal/h, or is it a power?
5. **Reconcile when both routes are open.** 1.4 (21st N-4(C)) gives you two units to
   put on the same rung; 1.6 (17th N-4(A)) gives design against actual. **Both are
   the same skill you just missed.**

**Three of your six parts were fully correct, including the eight-mark one.** The
method is there. **What is missing is not knowledge — it is the discipline of
acting on your own alarm**, and that is a cheaper fix than any concept on the list.

# Review — Thursday's HVAC session

> **Her verdict: "Thursday proved to be very poor."**
>
> **The work says otherwise. The scheduling was poor. The work was not.**

## What is actually on the page — 23:13 to 23:58, 45 minutes

| Question | Parts attempted | Correct |
|---|---|---|
| **21st N-2** — 2400 TR, centrifugal vs VAM | a, b, c | **3 / 3** |
| **22nd N-2(b)** — air-fin cooler + chiller | i, ii | **2 / 2** |
| **20th N-4(D)** — hospital trigeneration | 1 | **1 / 1** |
| **18th N-2** — 25 TPD ice plant | a, b, c, d | **3 / 4** |

**Nine of ten sub-parts correct**, and the tenth is off by 3% on a constant.

```
    21st (a)  50 × 100/(102 × 0.7 × 0.92)              =   76.117 kW   ✓
    21st (b)  2400 × 3024/(4.4 × 0.94 × 860)           = 2040.394 kW   ✓
    21st (c)  2400 × 3024/(1.2 × 479) = 12626 kg/h
              less the 10 TPH available                =    2.626 TPH  ✓
    22nd (i)  m × 1 × (42 − 34) = 160 × 0.5 × (55 − 35) =  200 TPH     ✓
    22nd (ii) 160000 × 0.5 × 5/3024                     =  132.275 TR  ✓
    20th (1)  625 × 860/(0.28 × 9000)                   =  213.294 Sm³/h ✓
    18th (a)  37950/30/15                               =   84.333 kWh/T ✓
    18th (b)  495000 + 1320000 + 66000                  = 18,81,000 kCal ✓
    18th (c)  1881000/(24 × 3024)                       =   25.918 TR  ✓
```

**In 45 minutes, at midnight, after a full day.** That is not a poor performance.
**Do not carry a false verdict into Saturday** — it will make you slow and cautious
on questions you can actually do.

---

# ⭐ The catch that is better than any of the arithmetic

**18th N-2 part (a).** You wrote `37950/(25 × 30) = 50.6`, struck it, and wrote
**84.333**.

```
    "The monthly energy consumption ... in a 25 TPD ice plant is 37,950 kWh.
     The daily OUTPUT of the ice plant is 15 Tonnes of block ice..."

    a) Energy consumption per tonne of ice 'output'
                                            ▲ BEE's own quotation marks
```

**25 is the rated capacity. 15 is the output.** The question puts *'output'* in
inverted commas because that is the whole trap, and the paragraph explains why they
differ — ice is lost pulling blocks out of the cans.

> **Every alarm you have caught so far was arithmetic** — a number too big, a
> fraction above 1. **This one was a reading trap**, with no impossible number to
> warn you. **You caught it anyway.** That is a harder skill and a better one.

---

# ⚠️ The real failure, and it is not ability

## You did the first parts of four questions instead of all parts of one

**Every one of the four stopped exactly where the marks start.**

| | You stopped before | Which is worth |
|---|---|---|
| 21st N-2 | **(d) condenser duty and cooling water** | ~8 of 20 marks |
| 22nd N-2(b) | (iii) onward — the economics | ~12 of 20 |
| 20th N-4(D) | 2, 3, 4 — TR from the VAM, hot water, savings | 18 of 20 |
| 18th N-2 | (e), (f) — pre-cooling savings | ~7 of 20 |

**Opening parts are the cheap ones.** They are also the ones you have already proved
you can do, five days running. **The marks and the learning are both in the back
half**, and you have now skipped the back half four times in one sitting.

## And 21st N-2 (d) is the exact part the question was chosen for

**Chiller heat rejection has cost you marks twice** — Mock 1's N-4(A), and again in
Day 15. **That is why the 21st N-2 was ranked first on Thursday's list**: BEE prints
the general form there, in its own key.

**You did a, b and c — and stopped one line short of it.**

## The start time is the whole story

**23:13.** The plan asked for 3½ hours in the day and got 45 minutes at midnight.
**Nothing about the work was poor; the day simply did not happen.** That is worth
naming plainly, because the fix is scheduling, not study.

---

# The one thing to do before anything else on Friday — 25 minutes

## 21st N-2 part (d), and the formula it teaches

```
    Q_rejected  =  Q_cooling  +  the energy you spent doing it

    condenser duty  =  TR × 3024 × (1 + 1/COP)
```

**Work it for both machines, on the same 2400 TR:**

```
    Centrifugal, COP 4.4:  2400 × 3024 × (1 + 1/4.4)  =  89,07,055 kCal/h
    Absorption,  COP 1.2:  2400 × 3024 × (1 + 1/1.2)  = 1,33,05,600 kCal/h
    ADDITIONAL rejection                              =  43,98,545 kCal/h

    Cooling water = 43,98,545/(1000 × 1 × (42 − 34))   =  549.82 m³/hr
```

> **The multiplier is the whole idea:** `×1.227` at COP 4.4, `×1.833` at COP 1.2.
> **A VAM rejects ~50% more heat for the same cooling**, because the heat that drove
> it has to leave too. That is why swapping to absorption needs a bigger cooling
> tower — and it is the single most repeated HVAC concept in these papers.

**Write the line `Q_rejected = TR × 3024 × (1 + 1/COP)` on the exam card now.**

---

# One constant to fix — 18th N-2 (d)

```
    You:   EER = 3.413 × 25.918 × 24 × 30/(0.85 × 0.88 × 37950)  =  2.244
    BEE:   kW/TR = 44.80/25.92 = 1.728 → × 0.88 = 1.52
           EER  = 3024/(1.52 × 860)                              =  2.313
```

**Your method is right.** The slip is `3.413` where `3.516` belongs.

```
    3.516 kW per TR       =  3024 kCal/h ÷ 860        ← the one you want
    3.413 Btu per Wh      =  a British-unit conversion, unrelated
```

**Two similar-looking numbers, different jobs.** `3024/860 = 3.516` — derive it
rather than remember it, and it cannot be confused.

*(Note also that BEE applies the 88% motor efficiency to get shaft power before the
EER. You did include it — good; that is the part most candidates drop.)*

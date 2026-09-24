# Review — Monday 1.5, 1.6 and 2.1

**Three questions in one sitting.** Scores, then the one concept that went wrong.

| | Question | Time | Score |
|---|---|---|---|
| **1.5** | 24th N-4(A) — 500 MW back pressure + 1000 MW station | 12:38 → 12:55 · **17 min** | **20 / 20** |
| **1.6** | 17th N-4(A) — 110 MW, design vs actual | → 13:43 · ~48 min | **19.5 / 20** |
| **2.1** | 16th N-4(A) — 150 bar reheat cycle | 19:34 → 20:02 · **28 min** | **17 / 20** |

## Monday so far: 80 / 100

```
    1.3   13.0 / 20   ████████████▌
    1.4   10.5 / 20   ██████████▌
    ── the two reviews ──────────────────────────
    1.5   20.0 / 20   ████████████████████
    1.6   19.5 / 20   ███████████████████▌
    2.1   17.0 / 20   █████████████████
```

**The first two: 23.5/40 — 59%. The last three: 56.5/60 — 94%.**

That is not warming up. **Every single fix from the two reviews shows up in the
work**, by name, and I will point at each one below.

---

# 1.5 · 24th N-4(A) — 20/20 in 17 minutes

**Nothing to correct. Four things to notice.**

```
    Vacuum at 0.14 ata = 760 − 760(0.14)         = 653.6 mmHg
    Vacuum at 0.11 ata = 760 − 760(0.11)         = 676.4 mmHg
    GHR  2040/0.87 = 2344.828 · 2000/0.87 = 2298.851 · improvement 45.977
    Coal = 500 × 0.74 × 10³ × 45.977/5500 = 3.093 TPH × 24 = 74.232 TPD
    Units = 1000 × 0.76 × 7200 × 10⁻³            = 5472 million kWh
    GHR   = (40,45,400×10³×5500 + 3500×10³×10,200)/(5472×10⁶) = 4072.624
    NHR   = 4072.624/0.92                        = 4426.766 kCal/kWh
```

**1 · You caught an inverted formula and rewrote it.** The struck-out line reads
`coal qty × GCV / (500 × 0.74)` — fuel over power, upside down. You replaced it with
`kWh × load factor × improvement / GCV`. **That is the third time in three questions
the alarm has fired and you have acted on it.**

**2 · You excluded the HSD, and that was the trap.** 150 MT of diesel for
earthmoving equipment is not heat into the boiler. Putting it in would have been
invisible in the answer — no alarm could catch it — and it is the only part of this
question with no arithmetic check behind it. **You had to know it, and you did.**

**3 · You left the unused data alone.** Turbine efficiency 93% and alternator 96%
appear in part (i) and are never needed. Forcing them in is the commonest way to
lose this question. **Unused data is not evidence you went wrong.**

**4 · Your vacuum figures are better than BEE's.** BEE prints 650 and 674, having
multiplied by 1.0332 and then converted at 760 mmHg per kg/cm² — one conversion too
many. `1 ata = 760 mmHg` gives 653.6 and 676.4. **Yours is the clean reading.** Add
one line saying `1 ata = 760 mmHg` and no examiner can mark it down.

---

# 1.6 · 17th N-4(A) — 19.5/20

**The whole chain is right, and two steps are better than BEE's own key.**

```
    Generator input = 110/0.96                    = 114.583 MW
    Turbine output  = 114.583 + 4.42 (gearbox)    = 119.003 MW
    Steam flow      = 119003 × 860/(810 − 550)    = 393,626 kg/hr
    SSC             = 393.626/110                 = 3.578 kg/kWh
    ACTUAL unit HR  = 393626 × 675/(0.875 × 110000) = 2760.17
    DESIGN unit HR  = 2362.5/0.875                = 2700
    % increase      = 60.17/2700                  = 2.229 %
```

**The gearbox loss is added, not subtracted** — the turbine must make *more* than the
generator delivers. You got the direction right without hesitating.

**And you compared like with like.** The paper gives design as a **turbine** heat
rate (2362.5) and your actual is a **unit** heat rate. You climbed the design figure
to rung 2 before comparing. **Comparing them as printed gives 16.8% and is the whole
trap.** This is the same basis trap as 1.4 part 2 — and here you handled it
completely, including the conclusion.

> **Your 2760.17 is more precise than BEE's 2758.8.** They rounded specific coal to
> 0.726 kg/kWh and multiplied back up. Your 2.229% against their 2.17% is entirely
> that rounding. **Say in one line that you carried full precision and the marks are
> yours.**

## ⚠️ The half mark: two different answers for the last step

```
    Extra coal = 60.171 × 110000 × 0.8/3800 = 1393 kg/hr = 1.393 TPH
                 1.393 × 720 h               = 1002.96 T/month   ← follows
    but you also wrote                          988.56 T/month   ← does not
```

**988.56 = 1.373 × 720.** The `9` and the `7` swapped — **the same digit
transposition as 1.4's `142.111 → 141.211`.** Twice in three questions.

> **It is a copying error, not a thinking error, and it has a mechanical fix:**
> when you carry a number down to a new line, **read it back off the line above
> before you multiply.** Two seconds. Both times the wrong digit was in the
> *second* position, which is exactly where the eye skips.

**Also: leave one answer on the page.** Two candidate figures with neither struck
out invites the examiner to mark the wrong one.

## Time

**~48 minutes if you ran straight through from 12:55.** That is double the budget
for a 20-marker. The work is clean, so this is pace, not confusion — and 1.5 at 17
minutes proves the pace is there when the chain is familiar. **Note where the
minutes went; my guess is the actual-vs-design bookkeeping, which is worth building
a two-column layout for.**

---

# 2.1 · 16th N-4(A) — 17/20

# ⭐ First: you beat the official answer key

```
    Your (a):   89.889 MW
    BEE prints: 71.5 MW, from a turbine output of 75.73 MW
    Correct:    228000 × 1494/3600 = 94.620 MW × 0.95 = 89.889 MW
```

**Your figure is right to three decimals and BEE's is wrong.** The 18th sitting sets
the identical question and prints the identical line correctly — `228(3450−3090) +
228(3560−2426)/3600 = 94.62 MW`. The 16th's key uses **860** where 3600 belongs and
then reports a number that follows from neither.

> **You did not have the 18th's key in front of you.** You derived it. That is the
> single most encouraging thing in three days of work — and it is worth remembering
> in the exam: **a model answer is not always right, and your own consistent chain
> is worth more than a remembered number.**

**And (d) is the third alarm you acted on today:**

```
    x = (2584.9 − 191.9)/(2426 − 191.9) = 1.071     "not possible"
    x = (2426 − 191.9)/(2584.9 − 191.9) = 93.36 %   ✓
```
**A dryness fraction above 1 is impossible and you said so and inverted it.** In 1.3
the same structure went down unchallenged. It no longer does.

**(e)** `228/89.889 = 2.536 t/MWh` ✓

---

## ⚠️ (b) The turbine heat rate — heat IN, not work OUT

```
    You wrote:  228[(3450 − 230) + 0.9(3560 − 2300)]/89.889/4.18 = 2642.046
    Correct:    228[(3450 − 990.3) + (3560 − 3090)]/89.889       = 7431 kJ/kWh
                                                                  = 1775.2 kCal/kWh
```

### The concept, and it is the important part

**Part (a) and part (b) use the same two steam streams and ask opposite questions.**

```
                   ┌────────┐         ┌──────────┐         ┌────────┐
    feedwater ────►│ BOILER ├──3450──►│    HP    ├──3090──►│REHEATER│
       990.3       └────────┘         └──────────┘         └────┬───┘
                                                                │ 3560
                                            ┌──────────┐        │
                        2426 ◄──────────────┤    LP    │◄───────┘
                                            └──────────┘

    (a) WORK OUT — what the steam GAVE UP to the blades
        HP:  3450 − 3090  =  360          ← subtract what comes OUT
        LP:  3560 − 2426  = 1134          ← subtract what comes OUT

    (b) HEAT IN — what was PUT INTO the steam
        boiler:   3450 − 990.3 = 2459.7   ← subtract what went IN
        reheater: 3560 − 3090  =  470     ← subtract what went IN
```

**The reheat term flips between the two.** In (a) it ends at the LP exhaust, 2426.
In (b) it starts at the cold reheat, 3090. **You used the (a) term inside (b)** —
`0.9(3560 − 2300) = 1134` is the LP cylinder's work, not the reheater's duty.

> ### The check that makes it obvious
>
> **Heat in must exceed work out.** Always, by the size of the condenser loss.
>
> ```
>     heat in   2459.7 + 470   = 2929.7 kJ/kg of main steam
>     work out    360  + 1134  = 1494   kJ/kg
>     ratio                    = 51 %   ← the cycle efficiency, near enough
> ```
> **Your bracket came to 4354, which is bigger than either** — because it mixes one
> heat term with one work term and double-counts the reheater. **Any bracket larger
> than `h_MS − h_feedwater + h_HRH − h_CRH` is wrong by construction.**

### And the 230

**990.3 is the only feedwater enthalpy on the page. 230 appears nowhere in the
data.** Whatever its origin — `990.3 kJ/kg` is `236.6 kCal/kg`, so a half-finished
conversion is the likely cause, since you did divide by 4.18 at the end — the rule
is the same:

> **Every number in an expression must be traceable to the data table or to a line
> you wrote.** Before you evaluate, run your finger along the row and name the
> source of each figure. **A number with no parent is always an error.**

**On the 4.18:** dividing kJ by 4.18 to reach kCal and then using 860 is
**correct**, and BEE's 18th-sitting key does exactly that. Keep it — just say which
currency you are in, in one line, before you divide.

## (c) inherits (b)

`860/2642.046 = 32.551%` is arithmetically right on a wrong input. The true figure
is **48.44%**.

> **This is where a band would have caught it.** A *turbine cycle* on 150 bar /
> 550 °C with reheat runs **45–50%**. 32.5% is a *plant* efficiency — you produced a
> number from the wrong rung of the ladder without a fuel input anywhere in sight.
>
> ```
>     turbine CYCLE efficiency      45 – 50 %   (no boiler in the box)
>     PLANT / overall efficiency    28 – 36 %   (boiler included)
> ```
> **There is no fuel in this question at all**, so nothing you calculate can be a
> plant efficiency. That alone rules out 32.5%.

---

# The five things to carry into the rest of the week

1. **Heat in ≠ work out.** For a reheat turbine heat rate: `MS(h_MS − h_fw) +
   RH(h_HRH − h_CRH)`. The reheat term ends where the *heat* was added, not where
   the *work* finished.
2. **Name the parent of every number** before you evaluate. 230 had none.
3. **Read the number back off the line above** when you carry it down. Two
   transpositions in three questions, both in the second digit.
4. **Turbine cycle 45–50%, plant 28–36%.** If there is no fuel in the question, you
   cannot be computing a plant efficiency.
5. **One answer on the page.** Strike the one you have rejected.

**And keep doing the thing you did four times today** — 1.5's inverted formula,
2.1's impossible dryness, and the two you caught in 1.4. **That habit is now worth
more marks than any remaining concept on the list.**

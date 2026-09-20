# Mock 3 Review — Full Paper

**Sat 20 Sep, 16:35 → 19:17. 162 minutes against 150.**

## Score: **≈ 58 / 100.** Pass is 50.

| Section | Score | Time | Note |
|---|---|---|---|
| I — Brief questions | **8 / 10** | 5 min | Q4, Q8 |
| II — L-1 aluminium | **5 / 5** | — | Exact |
| II — L-2 BP turbine | **5 / 5** | 25 min total | **Spotted the decoy** ⭐ |
| N-1 — compressor + chiller | **12 / 20** | 29 min | (a) perfect; (b) stopped after (ii) |
| N-2 — hot water start-up | **≈ 9 / 20** | **16 min** | Two errors, both from rushing |
| N-3 — two-unit power plant | **≈ 8 / 20** | **45 min** | Stopped mid part 2 |
| N-4 — **three** attempted | **≈ 11 / 20** | 42 min | Best was (C) |

---

## The headline is not the score. It is where the 162 minutes went.

```
   Section I        5 min   (budget 10)   ✅
   Section II      25 min   (budget 10)   ✗ 15 over
   N-1             29 min   (budget 25)   ~ 4 over, and you MOVED ON  ✅
   N-2             16 min   (budget 25)   ← the CHEAPEST question got the LEAST time
   N-3             45 min   (budget 25)   ✗✗ 20 over, and still unfinished
   N-4 × three     42 min   (budget 25)   ✗ you answered a question three times
```

**You allocated backwards.** N-2 was the simplest twenty marks on the paper — two
`m·Cp·ΔT` calculations and a division. It got **16 minutes** and came back with two
errors. N-3 was the most expensive — eight loss terms built from an ultimate
analysis — and it got **45 minutes** and still stopped at part 2 of 4.

### What that cost, arithmetically

You answered N-4 **three times**: the textile (18:35–18:56), the cement
(18:56–19:06) and the turbine (19:06–19:17). Only one can be submitted. The other
two cost about **31 minutes for zero marks**.

Spend those 31 minutes on the work you left behind instead:

```
   N-1 (b) parts (iii) and (iv) + recommendation      8 marks   ~10 min
   N-3 parts 2 (conclusion), 3 and 4                 10 marks   ~12 min
   N-2 done at 25 minutes rather than 16              ~6 marks   ~9 min
                                                     ─────────
                                                      24 marks in 31 minutes
```

**That is a paper in the high seventies, from the same knowledge, on the same
day.** The marks were on the table. The clock spent them in the wrong place.

> **Rung 170 held once and broke once.** You left N-1 at 29 minutes — close to the
> ceiling, and you moved. Good. Then N-3 ran 45 and nothing stopped it.
>
> **The rule needs a physical trigger, not an intention.** See Day 19.

---

## Section II — 10/10, and one of these is the best single line of the paper

**L-1 — aluminium furnace, 5/5.** You worked it on a 40-tonne batch basis:

```
   fuel for 40 t = 26 × 0.95 × 10 000 × 40            = 98,80,000 kCal
   useful heat   = 0.65 × that                        = 64,22,000 kCal
   electricity   = 64,22,000/0.90                     = 71,35,556 kCal = 8297.2 kWh
   ₹/tonne: FO 26 × 38 = 988   ·   electric 3.75 × 8297.2/40 = 777.86
```

**Electric wins by ₹210/tonne.** The 40 cancels, so the per-tonne route is two lines
shorter — but you carried the 40 all the way and **remembered to divide it back
out**, which is the part that goes wrong when people do this.

And the structure is Rung 164 exactly: **useful heat is the invariant**, 0.65 sizes
it, 0.90 delivers it, neither efficiency touches the other's arithmetic.

**L-2 — back-pressure turbine, 5/5. You caught the decoy.**

```
   Cost of steam = 20 × 3500 = ₹70,000 per hr        ← written, then STRUCK OUT
   "However, 25 TPH is already available."
   Hourly monetary savings = ₹7200
```

**That struck-out line is worth more than the marks.** The ₹3500/MT was placed to
make you charge 20 TPH of steam against the saving. You wrote it, saw that the
plant was *already* letting 25 TPH down through the PRDS, and cancelled it — with
the reason written next to it. An examiner reading that knows you understood the
scheme, not just the formula.

---

## Section I — 8/10

**Q4 — the reheat cycle.** You said True; it is **False**. What the statement
describes — steam extracted at various points to heat condensate and feedwater
through HP/LP heaters — is the **regenerative** cycle. **Reheat** sends steam back
to the *boiler* to be re-superheated between turbine stages.

```
   REHEAT        turbine → BOILER → turbine     raises the mean temperature of
                                                heat addition, and keeps the LP
                                                exhaust dry
   REGENERATIVE  turbine → FEEDWATER HEATERS    raises feedwater temperature, so
                                                less fuel per kg of steam
```

**Both are on the same 500 MW unit** — which is why the paper can swap their names
and catch people. You met the regenerative side in this very paper's N-4(C), where
feedwater enters at 241 °C.

**Q8 — extraction back-pressure EUF.** You said True; it is **False**.

```
   EUF = (power + useful process heat) / fuel energy
```

More steam through the extractions means **more useful process heat** for the same
fuel. Power falls a little, heat rises more — and **EUF counts them equally**. So
EUF *rises*. This is the Day 4 point about why a back-pressure set's heat rate
looks terrible and its EUF looks excellent: heat rate ignores the heat, EUF does
not.

**Q10 — the air preheater — correct.** The one I wrote to test Rungs 175–178,
taught eleven days ago. Leaked air is 21% O₂, flue gas is not, so the leak shows as
a rise in O₂ across the preheater. **That gap is closed.**

---

## N-1 — 12/20

**Part (a) is 8/8 and contains a genuinely elegant step.**

```
   iso power = 1.033 × 11.67 × 60 × ln(8.033/1.033)/36.7     = 40.424 kW
   motor input = 40.424/(0.6 × 0.9 × 0.97)                   = 77.174 kW
   specific power = 77.174/700.2                             = 0.11 kW per m³/h

   (iii)  kW ∝ ln(r)  ⟹  kW₂ = 77.174 × ln(7.033/1.033)/ln(8.033/1.033)
                            = 72.172 → reduction 5.00 kW
```

**`kW ∝ ln(r)` is the right instinct.** Everything else in the isothermal formula
is unchanged, so the whole chain scales with the log ratio — one line instead of
recomputing four. That is the move of someone who understands the formula rather
than executing it.

**Part (b) stopped after (ii), at 4/12.**

```
   (i)  m_cw × 1 × (42 − 34) = 160 × 0.5 × (55 − 35)  →  200 TPH      ✓
   (ii) chiller = 160 × 0.5 × (35 − 30) × 1000/3024   =  132.275 TR   ✓
        (you first wrote (55 − 35), struck it, corrected to (35 − 30)) ✓
   (iii)(iv) not reached                                                ✗
```

The self-correction on (ii) is the checking pass working. What was left:

```
   (iii) condenser duty = 132 × (1 + 1/4.2) = 163 TR → CW = 98 m³/hr
   (iv)  chiller 117.6 kW + air-fin fan 442 kW + CT 11 kW = 570.6 kW
         cost ₹410.8 lakh vs benefit ₹450 lakh → NET ₹39.2 lakh/yr, viable
```

**Part (iii) is `TR × (1 + 1/COP)` — Rung 163, third paper running.** You have had
it right twice. It was eight marks and about ten minutes away.

---

## N-2 — ≈9/20, and both errors came from 16 minutes

### Error 1 — π r² with the diameter substituted for the radius

```
   Yours:    3.14 × (0.1)² × 2000                    = 62.8 m³
   Correct:  π/4 × (0.1)² × 2000                     = 15.71 m³
```

**0.1 m is the diameter.** The radius is 0.05. Either write `πr²L` with r = 0.05,
or `(π/4)D²L` with D = 0.1 — never `πD²L`. **A factor of exactly 4.**

> **The sanity check that catches it:** a 100 mm pipe is a hand-span across. Two
> kilometres of it holds about 16 m³ — a small road tanker. 62.8 m³ is three
> tankers, from a pipe you could grip.

### Error 2 — the steel pipe was never counted

This is what the question was built around:

```
   Water:  15.71 m³ × 1000                           = 15,708 kg
   Steel:  π/4 × (0.108² − 0.1²) × 2000 × 8000       = 20,910 kg
```

**There is 33% more steel than water**, and it all has to be raised from 50 °C to
140 °C too. Its low specific heat (0.12) still leaves it carrying **14% of the
start-up load**.

```
   Start-up load = 15,708 × 1 × 90  +  20,910 × 0.12 × 90
                 = 14,13,720 + 2,25,828               = 16,39,548 kCal
   Time = 16,39,548/(0.90 × 6,00,000)                 = 3.04 hr
```

You also used the full 6,00,000 kCal/hr rather than **90% of it** — the question
says "if the boiler operates at 90% capacity".

**What you got right:** part 2's insight that the start-up load is **∝ ΔT**, so the
ratio 80/90 gives the new load in one line and the **11.111% reduction is exactly
right** — it is basis-independent, so it survived both errors above. Good
reasoning on a wrong foundation.

*(Fuel saving: 22.8 kg per start-up, not 8.3 — the 11.111% was applied to a load
3.4× too small.)*

---

## N-3 — ≈8/20 in 45 minutes

**The loss inventory is mostly right, and one part of it is better than my own key.**

```
   A_th 5.206 ✓   EA 16.667 % ✓   AAS 6.075 ✓
   L₂ 3.639 ✓   L₃ 2.151 ✓   L₄ 0.190 ✓   L₆ radiation 0.45 ✓
   L₇ fly ash    (0.35 × 4/5) × 200/4000 × 100        = 1.40 %   ✓
   L₈ bottom ash (0.35 × 1/5) × 500/4000 × 100        = 0.875 %  ✓
```

**You split the ash into fly and bottom and costed each at its own GCV.** My answer
key used a single weighted GCV of 260 kCal/kg. **Your way is cleaner and the totals
are identical** — 1.400 + 0.875 = 2.275%, exactly the weighted figure. It also
shows the 1:4 ratio being *used* rather than averaged away.

### Two errors

**m_dfg without the ash deduction.**

```
   Yours:    (AAS + 1 + N₂) − M − 9H₂                 = 6.728 kg/kg
   Rung 168: ... − ASH                                = 6.378 kg/kg
```

`(AAS + 1)` assumes the whole kilogram of fuel leaves as gas. **This coal is 35%
ash** — it drops out of the furnace bottom, which is exactly what your own L₇ and
L₈ account for. Counting it twice inflates L₁ from 5.36% to 5.64%.

Rung 168 was written for you eleven days ago after Mock 1, where at 8% ash it was
worth 0.13 points. **At 35% ash it is worth five times that.**

**L₅ (CO) carries two compounding unit errors.**

```
   Yours:    [0.015/(0.015 + 0.07)] × 0.4 × 565/4000  = 0.997 %
   Correct:  [0.015/(0.015 + 7)]    × 0.4 × 5654/4000 = 0.121 %
```

- **CO₂ is 7%, not 0.07.** Both CO and CO₂ must be in the same units in that ratio;
  you put CO as a percentage (0.015 for 150 ppm) and CO₂ as a fraction.
- **The constant is 5654, not 565.** It is kCal/kg of carbon still locked in CO.

The two errors ran opposite ways and partly cancelled — 8× too large instead of
820×. **A partial cancellation is more dangerous than a clean error**, because the
answer stays plausible.

> **Both errors are Rung 173's routine:** say the units of every term in a ratio
> before you divide, and say the units of every constant before you substitute.

**Corrected, the efficiency is 85.8%** against your 84.66% — so the loss inventory
was fundamentally sound.

**Parts 2, 3 and 4 were not finished.** You computed `η_turbine = 860/2450 = 35.1%`
and `η_unit = 860/2790 = 30.8%` and then stopped at "Unit-1 Unit Heat rate =". One
more line:

```
   Unit 1 unit heat rate = 2450/0.858                 = 2855 kCal/kWh
   vs Unit 2's 2790     ⟹  UNIT 2 is more efficient
   coal difference at 85 % load                       = 65.9 TPD
   station net heat rate = (2855 + 2790)/2/0.90       = 3136 kCal/kWh
```

**Ten marks, and you were one line from the first of them.**

---

## N-4 — three attempted, best ≈11/20

### (C) the reheat turbine — your best, and two specific slips

```
   i)   h₂s = 813 − (813 − 735)/0.796                 = 715.0    ✓
   iii) HP 62.037 MW ✓   IP 68.669 MW ✓
```

**The LP exhaust enthalpy.** You used the table's **610** directly. But 610 is
`h_g` — saturated vapour at the condenser pressure — and the exhaust is **wet**:

```
   h_exhaust = h_f + x(h_g − h_f) = 49 + 0.98(610 − 49)  = 599 kCal/kg
```

**The dryness fraction of 0.98 is given precisely so you apply it.** Unused data is
the tell.

```
   η_LP  = (741 − 599)/(741 − 559)                    = 78.0 %   (you had 72.0 %)
   LP power = 545 000 × 142/860/1000                  = 89.99 MW (you had 83.02)
```

**The turbine heat rate.** Two things:

```
   Yours:    684(813 − 241)/213.723                   = 1831
   Correct:  [684(813 − 241) + 635(834 − 735)]/209.79 = 2165 kCal/kWh
```

- **The reheat term is missing.** The boiler adds heat *twice* — once to raise main
  steam, once to reheat the cold reheat back up. `635 × (834 − 735)` is 62,865
  Mcal/h of it, 14% of the total.
- **The denominator is generator output, not turbine power.** 220.69 MW at the
  shaft becomes 209.79 MW at the terminals after the gearbox and generator. Heat
  rate is always **per kWh sent out**, not per kWh at the coupling.

*(And part (iv) asks for the station gross heat rate, which **cannot be calculated**
— boiler efficiency is not given. BEE's key says so and awards marks for saying it.
That sentence was free.)*

### (A) the cement raw mill — 8/20

```
   a) 2294/260 = 8.823 kWh/t ✓      b) 1450/260 = 5.577 kWh/t ✓
   d) P₂/P₁ = (40/50)³ = 0.512 → savings 48.8 % ✓
```

Part (c), the fan efficiency from the pitot traverse, was **10 marks and was not
done** — you wrote `Q × ΔP/102` and then `= 4.04 √ΔP`, which is the *velocity*
formula, not fan power. Two different uses of the same measurement:

```
   velocity      v = C_p √(2g Δp_dynamic/ρ)      needs the CORRECTED density
   fan power     P = Q × Δp_static/(102 × η)     needs flow and static pressure
```

And part (d) asks for the **saving in fan power consumption** — 48.8% is the ratio;
the answer is `1450 × 0.488 = 707.6 kW`. Stock vs flow, Rung 166.

### (B) the textile stenter — abandoned, and the reason is worth knowing

Two things went wrong before you left it:

- **Stenter output is 1250 kg/hr; you used 1200.** A data misread.
- **The moisture basis.** You wrote `m_in = 1128 × 0.65 = 733.2`. That is **moisture
  regain** — kg of water per kg of bone-dry cloth. The paper gives **moisture
  content** — water as a fraction of the *wet* cloth. So:

```
   bone dry = 1250 × (1 − 0.06)                      = 1175 kg/h
   wet inlet = 1175/(1 − 0.65)        ← DIVIDE       = 3357 kg/h
   evaporated = 3357 − 1250                          = 2107 kg/h
```

**Divide by (1 − moisture), never multiply by moisture.** Rung 148's whole point,
and the same shape as Day 13B's "outlet cloth = bone dry / 0.95".

---

## Error tally

| # | Error | Type | Marks |
|---|---|---|---|
| 1 | **45 min on N-3, 42 min on three N-4s** | **Time / selection** | **~24** |
| 2 | N-2: πD²L for πr²L | Geometry | ~4 |
| 3 | N-2: steel pipe omitted; 90% capacity not applied | **Reading** | ~5 |
| 4 | N-3: m_dfg without the ash — Rung 168 | Method | ~2 |
| 5 | N-3: L₅ with CO₂ as 0.07 and 5654 as 565 | Units | ~1 |
| 6 | N-4(C): h_g used where x·h_fg was required | Method | ~5 |
| 7 | N-4(C): reheat term omitted; turbine power for generator | Method | ~2 |
| 8 | Section I Q4, Q8 | Concept | 2 |

**Two marks of concept loss on a hundred-mark paper.** Everything else is a clock,
a reading, or a substitution.

---

## The trend, stated honestly

| | Score | The asterisk |
|---|---|---|
| Mock 1 | 84 | **Four of eight questions had been assigned before** |
| Mock 2 | 73 | **Six marks were unreachable** — 78% of what was answerable |
| Mock 3 | **58** | Clean paper. **31 minutes spent answering N-4 three times.** |

**The trend is down and it deserves to be taken seriously — but it is not a
knowledge trend.** Concept losses have gone 12 → 4 → 2 across the three papers.
What has grown is time mismanagement, and Mock 3 is the extreme case: a paper where
roughly 24 reachable marks were left on the table while 31 minutes went into work
that could never be submitted.

**Fix the clock and this is a high-seventies paper.** Six days is enough for that,
because it is a habit and not a syllabus.

---

## Verdict

**58/100. Pass is 50.** Section II perfect, N-1(a) perfect, the air preheater item
correct, the ash split better than my own key, the PRDS decoy caught and struck out
with a reason.

**Day 19 is the clock, six specific slips, and the exam-day card. Nothing else.**

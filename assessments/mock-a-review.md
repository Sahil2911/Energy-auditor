# Mock A — Assessment

**Raw: 29 / 60 (48%). On attemptable material: 29 / 50 (58%).**
Pass equivalent is 30/60.

Ten of the sixty marks were not attemptable — a Tutor fault, below.

---

## Section I — 8 / 10

Correct: 1, 2, 3, 6, 7, 8, 9, 10.

Both errors are **concepts covered explicitly**, which makes them the most
important marks lost on the paper.

### Q4 — answered False, correct answer True

> *"For a real steam turbine, the actual exhaust enthalpy is higher than the
> enthalpy after an isentropic expansion to the same pressure."*

This is the sealed-box argument from `concept-isentropic-expansion.md`. A turbine
is adiabatic, so `h₁ = h₂ + work`. Friction returns work to the steam as heat, and
that heat cannot escape — so the real exhaust carries **more** enthalpy than the
ideal one. **h₂ > h₂s, always.**

She requested that explanation herself two sessions ago and worked through it. The
formula `h₂ = h₁ − η(h₁ − h₂s)` was applied correctly in Section II L-2 on the same
paper — so the *procedure* is secure while the *direction* is not.

That distinction matters: a procedure survives until a question is phrased
differently, which is exactly what Section I does.

### Q5 — answered True, correct answer False

> *"A back-pressure plant has a much higher heat rate than a condensing plant,
> which shows it uses fuel less efficiently."*

The first clause is true; the conclusion is false. Heat rate charges **all** the
fuel against power alone, and a back-pressure turbine makes little power per kg of
steam — but its exhaust heat runs the process rather than being dumped. EUF is the
right measure and is far higher.

A **compound statement** where the fact is right and the inference wrong. Section I
uses this shape often; read the second half as a separate claim.

---

## Section II — 9 / 10

### L-1 — 5 / 5

```
    EA   = 8/(21−8) × 100 = 61.538 %
    AAS  = 14 × 1.615 = 22.61 kg/kg
    L1   = 23.61 × 0.24 × 765 / 10,000 × 100 = 43.348 %
```

Exact. Method, substitution and arithmetic all clean.

### L-2 — 4 / 5

Values all correct: h₂ = 2620 kJ/kg, turbine 11.333, electrical 10.773.

**Labelled MWh instead of MW.** Power, not energy. `60,000 × 680 / 3600` gives
kilo**watts** — a rate. The number is right and the division by 3600 was clearly
performed, but it is not shown on the page and the unit is wrong.

This is the third appearance of power-versus-energy confusion, after `21,410 ×
4.18` on Day 4. Watch it: **kW is a rate; kWh is a quantity.**

---

## Section III N-1 — approx 2 / 20

The reverse combustion problem. She wrote:

```
    EA = 3/(21−3) = 0.167
    C + O₂ → CO₂
    TA = 11.6C + 34.8(H₂ − O₂/8)
    AAS = 1.167 TA
    m_fg = 1 + AAS − (9H₂ + M)
```

Every relationship is correctly recalled. But look at the third line: **C and H₂
are what the question asks you to find.** The forward route needs the fuel
composition as an input, and here it is the output.

**This is a problem-recognition failure, not a knowledge gap.** She had every tool
required — 12/44 for carbon from CO₂, 0.77 for nitrogen in air, 0.23 for oxygen, 8
kg O₂ per kg H₂. All are Day 2A rungs. What was missing was seeing that the flue
gas analysis is the *starting point*.

The route, which she could have built:

```
    per 100 kg dry flue gas:
    Carbon from CO₂    = 12 × 12/44        = 3.273 kg
    Air from N₂        = 85 / 0.77         = 110.39 kg
    O₂ supplied        = 0.23 × 110.39     = 25.39 kg
    O₂ consumed        = 25.39 − 3         = 22.39 kg
    O₂ used by carbon  = 3.273 × 32/12     = 8.73 kg
    O₂ left for H₂     = 22.39 − 8.73      = 13.66 kg
    Hydrogen           = 13.66 / 8         = 1.708 kg

    Fuel = 4.98 kg per 100 kg flue gas  →  C 65.7 %, H₂ 34.3 %
    Dry flue gas for 200 kg/hr fuel = 4,016 kg/hr
```

**The trigger to learn:** when the question gives you a *flue gas analysis* and asks
about the *fuel*, every arrow reverses. Ask what each flue gas component can only
have come from — CO₂ can only come from carbon, N₂ can only come from air.

## Section III N-2 — approx 10 / 20

Part B(i) is **correct and complete**:

```
    Q₁ = 5000 × 0.9 × 35        = 1,57,500 kCal/hr        ✓
    m_cw = 157,500/(32−25)      = 22,500 kg/hr            ✓
    LMTD₁ = (58−30)/ln(58/30)   = 42.473 °C               ✓
    Q₂ = 5000 × 0.9 × 50        = 2,25,000 kCal/hr        ✓
    T_out = 25 + 225,000/22,500 = 35 °C                   ✓
    LMTD₂ = (55−15)/ln(55/15)   = 30.786 °C  (wrote 30.768)
    A₂/A₁ = 1.972  →  area up 97.2 %                      ✓ (exact 97.1%)
```

Block diagrams drawn for both cases, as part A required. The 30.768 is a digit
transposition of 30.786 and moves the answer by 0.1 percentage point.

**Parts B(ii) and B(iii) require the chiller COP** — Day 11 material.

---

## Tutor fault — the fourth prerequisite failure

The 17th N-2 asks for the chiller's COP and the resulting load reduction. I
checked that the question was a heat exchanger question and **did not read its
sub-parts** — the exact failure the prerequisite rule was written to prevent, one
session after writing it.

| Day | Question | Untaught | Marks lost |
|---|---|---|---|
| 1 | 18th N-1 | Indirect method | 18/20 |
| 4 | 18th N-2 | Gas turbine cogen | 20/20 |
| 5 | 25th N-1 | Pump, fan, chiller | 14/20 |
| **7** | **17th N-2** | **Chiller COP** | **10/20** |

The rule now reads: **check every sub-part, not the question's topic.** A question
is cleared only when each numbered part has been traced to a taught rung.

---

## Tag distribution

| Tag | Marks | Note |
|---|---|---|
| **Concept** | ~20 | N-1 direction (18), Q4 isentropic (1), Q5 compound statement (1) |
| Units | 1 | MWh for MW |
| Arithmetic | ~0 | 30.768 for 30.786, immaterial |
| Method | 0 | |
| **Curriculum** | 10 | Chiller COP, not taught |

**Almost all of it is one thing: N-1.** Strip that question out and the paper reads
27/30 on everything else — 90%.

Per the Day 7 rubric, "mostly concept means the teaching was too fast". That is
half right here. The individual concepts are secure; what is missing is
**recognising which direction a problem runs**, which is a skill the curriculum has
not taught at all because every worked example so far has run forwards.

---

## Verdict

**29/60 raw, 58% on attemptable material — a pass, narrowly, on the hardest half
of the paper.**

Sections I and II are strong: 17/20 combined, with clean method throughout. The
one long question she could fully attempt, she largely solved. The failure is
concentrated in a single question of a type never met before.

Not a foundation problem. A gap in **question-type coverage**.

---

## Instruction to Tutor

1. **Add reverse/inverse problems to the curriculum.** Every worked example so far
   runs forwards. Build a short reference on inverse problems — flue gas → fuel,
   performance → sizing, output → input — with the recognition triggers.
2. **Re-teach the isentropic direction as a statement, not a formula.** She can
   apply `h₂ = h₁ − η(h₁ − h₂s)` and still answer the True/False wrongly. Add it to
   the anchors: *h₂ is always between h₂s and h₁.*
3. **Compound True/False statements** — teach reading the second clause as a
   separate claim.
4. **Prerequisite rule tightened** to sub-part level, and the fourth breach logged.
5. Proceed to Day 8. The rubric's "30–44: proceed, re-drill where tags
   concentrate" applies, and the tags concentrate on one specific, fixable thing.

## No timing recorded

Start and finish times were not logged per question, so pace under exam conditions
is still unmeasured after being requested twice. **This is now the single most
important missing datum** — a paper that would pass untimed and fail timed looks
identical on paper to one that passes both.

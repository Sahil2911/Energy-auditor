# Assessment — Day 4

*Written retrospectively. This session was assessed in conversation at the time
but never committed — see the record-keeping note in `framework.md`.*

Two questions submitted, then a re-attempt after Day 4B was written.

---

## First attempt

### 19th N-1, steam turbine cogeneration — **15 / 20**

**Time: 21:53 → 22:19, twenty-six minutes** (target 25).

```
    h₂ = 3420 − 0.90(3420 − 2430) = 2529 kJ/kg          ✓
    Turbine = 91,000/3600 × 891 = 22.52 MW               ✓
 a) Electrical = 22.52 × 0.98 × 0.97 = 21.41 MW          ✓
 b) Fuel = 91,000(3420−504.7)/(4.18 × 4500 × 0.8) = 17.63 TPH   ✓
 c) EUF = 0.611                                          ✗  (correct 0.788)
 d) Heat:power = 2058.37 kCal/kWh                        ✓
```

Three of four parts correct. The isentropic step, the efficiency chain (multiplied
correctly for the gearbox and generator), and the kJ-to-kCal reconciliation on the
fuel — which is the conversion most candidates fail — were all clean.

**Part (c) mixed unit systems in a single ratio:**

| Term | Units used |
|---|---|
| Electrical `21,410 × 860` | kCal ✓ |
| Heat `91,000 × 2024.3` | kJ ✗ |
| Fuel `17,630 × 4500 × 4.18` | kJ ✗ |

One term of three in the wrong system. Converting that one term (`21,410 × 3600`)
gives 0.7879 from the same expression.

### 18th N-2, gas turbine cogeneration — not attemptable

**Time: 22:20 → 22:32, twelve minutes, then stopped.**

Part (a) marked "Don't know". Part (b) opened `η_WHB = Q(h₂ − h_fw)/(q × GCV)` and
was abandoned — the right instinct with no route to the exhaust mass.

**Tutor fault — second prerequisite breach.** Day 4 taught *steam* turbine
cogeneration and then set a *gas* turbine question describing it as "different
machine, same logic". They share almost no formulas: no isentropic efficiency,
efficiency given rather than derived, fuel from gas rate rather than a boiler
balance, exhaust mass from an air-to-fuel ratio, and the waste heat boiler as a
second machine with its own efficiency.

**Stopping after twelve minutes was the correct call** — she recognised the tools
were absent rather than grinding.

---

## Re-attempt, after Day 4B

### 18th N-2 — **20 / 20**

**Time: 22:16 → 23:06, fifty minutes.**

```
    Heat rate = 860/0.28 = 3071.43 kCal/kWh      ✓
    Gas rate  = 0.236 kg/kWh, fuel 3776 kg/hr    ✓
    η_WHB     = 75.53 %                          ✓
    Supplementary firing = 559.44 kg/hr          ✓
    Separate boiler @ 80% = 538.46 kg/hr         ✓
    Conclusion: separate boiler economical       ✓
```

**She computed the separate boiler at 80% — the question's figure — not the 85%
the official model answer uses.** The instruction to follow the question over the
model was applied without prompting.

From "cannot begin" to fully correct in one session.

### 19th N-1 part (c) redo

**Time: 23:07 → 23:25, eighteen minutes.** Parts (a) and (b) correct again;
**(c) returned 0.611** — the same unit mix, this time with the fuel deliberately
converted to kJ so that two terms agreed and one did not. Still wrong.

Second occurrence of the same 5 marks.

---

## Tags

| Tag | Marks | Note |
|---|---|---|
| **Units** | 5 | kCal/kJ mixed in one ratio, twice |
| **Curriculum** | 20 | Gas turbine cogeneration not taught |
| Concept, method, arithmetic | 0 | |

## Verdict

Method secure on steam turbine cogeneration. The 5 marks lost twice are a **layout**
problem, not a knowledge gap — both conversions are used correctly elsewhere on the
same page.

## Instruction to Tutor

1. **Day 4B written** — gas turbine cogeneration, Rungs 29–34.
2. **`reference/unit-discipline.md` created** — no unit conversion inside a
   fraction bar; each term on its own line with its unit, convert there, divide once
   at the end. Also separates 4.18 (energy→energy, never applied to a power) from
   860 and 3600 (power→energy rate), since `21,410 × 4.18` was attempted.
3. Speed becomes a tracked metric from Day 5.

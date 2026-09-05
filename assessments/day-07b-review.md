# Day 7B Review — Reverse Calculations from Flue Gas Analysis

**Attempted 05 Sep, deliberately delayed to put a gap between the lesson and the
attempt.** That was a good call — a delayed attempt tests recall, not short-term
memory, and this one held up.

| Question | Marks | Score | Time |
|---|---|---|---|
| Mock A N-1 redo — 25th N-2, reverse combustion | 20 | **19** | 18:10 → 18:39 (29 min) |
| Practice 2 — standard `m_dfg` formula + CO-corrected excess air | — | **✓ method, one slip** | 18:56 → 19:03 (7 min) |

---

## The redo — the chain that was worth 0/20 in Mock A came back complete

Every step of the reverse chain, correct and in order:

```
  Carbon from CO₂       12 × 12/44          =  3.273 kg
  Air from N₂           85 / 0.77           = 110.39 kg
  O₂ supplied           0.23 × 110.39       = 25.39 kg
  O₂ consumed           25.39 − 3           = 22.39 kg
  O₂ used by carbon     12 × 32/44          =  8.727 kg
  O₂ left for hydrogen  22.39 − 8.727       = 13.663 kg
  Hydrogen              13.663 / 8          =  1.708 kg

  Fuel = 3.273 + 1.708 = 4.981 kg per 100 kg of dry flue gas
  ⟹  C 65.71 %,  H₂ 34.29 %
  ⟹  dry flue gas at 200 kg/hr fuel = 200 × 100/4.981 = 4015.3 kg/hr
```

This is the question that cost the entire 20 marks in Mock A. **It now comes back
whole, from a cold start, three days after the lesson.** The Day 7B insertion did
what it was added to do.

One detail worth naming: `O₂ used by carbon` was taken as `12 × 32/44` — straight
from the CO₂ mass — rather than the longer `3.273 × 32/12`. Same answer, one step
fewer, and it shows the reaction is being read rather than recalled.

**Practice 2** applied the standard formula and the **CO-corrected** excess air:

```
  m_dfg = [11(12) + 8(6) + 7(0.5 + 81.5)] / [3(0.5 + 12)] × 0.72
  EA    = (O₂ − CO/2)/(21 − (O₂ − CO/2)) = 5.75/15.25 = 37.71 %   ✓
```

The excess air is exactly right, including the `− CO/2` correction, which most
candidates omit. The `m_dfg` arithmetic reads **14.41**; it should be **14.48**
(754/37.5 = 20.107, × 0.72). A small slip in an otherwise correct substitution —
worth re-checking the division, not re-learning anything.

---

## The question asked: why do the two dry flue gas routes disagree?

She computed the dry flue gas mass two ways and got two answers:

| Route | Result |
|---|---|
| From the flue gas composition — 100 kg dfg per 4.981 kg fuel | **4015.3 kg/hr** |
| From the fuel — `AAS + 1 − 9H₂`, with AAS = TA × (1 + EA) | **4084.4 kg/hr** |

**Neither route is wrong as algebra. The two are the same equation.** Here is the
proof:

```
  Route 1 gives, implicitly, the actual air supplied:
      AAS = 110.39 / 4.981 = 22.164 kg per kg of fuel

  Feed that into Route 2's formula:
      m_dfg = AAS + 1 − 9H₂ = 22.164 + 1 − 9(0.3429) = 20.078 kg/kg
      × 200 = 4015.6 kg/hr          ← identical to Route 1
```

So the routes agree **exactly**. The whole 1.7% gap sits in one number: the
**actual air supplied**.

- Route 1 gets AAS from the **measured nitrogen** — 85 kg of N₂ could only have
  arrived as air, so air = 85/0.77. That is a mass balance. It cannot be wrong.
- Route 2 gets AAS from `theoretical air × (1 + excess air)`, with excess air from
  the shortcut `%O₂/(21 − %O₂)` = **15.10%**.

The true excess air, from the nitrogen balance, is **13.34%**. The shortcut
overstated it, and that is the entire discrepancy.

### Why the shortcut over-reads here — and it is worth understanding

`EA = O₂/(21 − O₂)` quietly assumes that **the dry flue gas contains the same
number of moles as the air that was supplied**, so that the oxygen supplied is 21%
of the dry gas. Check whether that holds:

```
  Air supplied       = 0.7934 kmol O₂ + 3.036 kmol N₂ = 3.829 kmol
  Dry flue gas       = 0.273 CO₂ + 0.094 O₂ + 3.036 N₂ = 3.402 kmol
                                                          ── 11 % fewer
  O₂ supplied as a share of the DRY gas = 0.7934/3.402 = 23.3 %,  not 21 %
```

**Where did the missing 11% of the moles go? Into water, which the dry analysis
throws away.**

```
  C  + O₂ → CO₂       1 mole of gas in, 1 mole out    — mole-neutral
  H₂ + ½O₂ → H₂O      ½ mole of O₂ vanishes from the dry gas
```

Carbon combustion does not change the gas count at all. **Only hydrogen shrinks
it**, and this fuel is **34% hydrogen by mass** — the question calls it
"hydrogen-enriched" and that is not decoration. 15.4 kg of water per 100 kg of dry
flue gas leaves the dry basis, and with it the oxygen that made it.

For an ordinary fuel — coal at 4% H₂, furnace oil at 12% — the shrinkage is 1–4%
and the shortcut is fine, which is why you have used it all curriculum without
trouble. At 34% hydrogen it breaks.

### The rule to carry into the exam

> **When the flue gas composition is given, work from the flue gas. When only the
> fuel's ultimate analysis is given, work from the air. Never cross over
> mid-question.**
>
> The flue-gas route is a **direct mass balance** — nitrogen in, nitrogen out — and
> carries no approximation. The air route needs an excess-air figure, and every
> excess-air formula is an approximation. Given the choice, the measured route wins.
>
> If you compute both and they disagree by a few per cent, **the flue-gas route is
> the one to report**, and one line saying why earns the mark rather than costing it.

**19/20.** The one mark is for reporting 4084 alongside 4015 without resolving
which to trust — and resolving it is what this note now does.

---

## Error tally

| # | Error | Type | Fix |
|---|---|---|---|
| 1 | Two dfg values reported, not reconciled | **Concept** | The rule above — measured route beats derived route |
| 2 | Practice 2: 14.41 for 14.48 | Arithmetic | Re-divide; nothing to re-learn |

---

## Verdict

**The Mock A hole is closed.** Twenty marks that were unreachable in Mock A are now
routine, from cold, three days after the lesson.

The question she raised is a better question than the one the paper asked. Noticing
that two valid methods disagree — and stopping to ask why rather than picking the
one that looks nicer — is the habit that separates an auditor from a calculator.
The answer turned out to be a real limitation of a formula this curriculum has been
using unqualified since Day 2A, and it is now qualified.

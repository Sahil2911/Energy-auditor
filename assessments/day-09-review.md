# Assessment — Day 9

Two questions: the 23rd sitting N-1 (compressed air, 20 marks) and the 19th
sitting N-2 fan/pump comparison deferred from Day 5.

---

## 23rd N-1, compressed air — **20 / 20**

**Time: 15:14 → 15:46, thirty-two minutes** (target 30).

```
    A) FAD                   = 13.311 m³/min            ✓
    B) Daily energy / cost   = 1455.6 kWh / Rs 14,556   ✓
    C) Isothermal power      = 46.572 kW                ✓
       Isothermal efficiency = 56.795 %                 ✓
    D) New motor pulley      = 234 mm                   ✓
    E) Saving 4.317 kWh/hr, payback 4.17 months         ✓
```

**First full-marks long question of the series** — and on a chapter met that same
day, at exam pace, with five sub-parts chaining through each other.

**Fifth reciprocal catch, unprompted.** The payback line was first written
`43.17 × 8000 / 1,20,000`, then reworked to `1,20,000 / (43.17 × 8000)`.

---

## 19th N-2, fan and pump — fan correct, one stream error

**Time: 15:49 → 16:09, twenty minutes.**

**Fan side fully correct:**

```
    Air mass   = 370,125 kg/hr = 102.813 kg/s      ✓
    Air volume = 79.7 m³/s                          ✓
    Fan power  = 79.7 × 30 / 102 = 23.441 kW        ✓
    Annual     = 23.441 × 5000/(0.65 × 0.9) = 2,00,350 kWh   ✓
```

The 102 constant on its first outing, and the efficiency chain divided rather than
multiplied.

**Pump side:**

```
    Written:  m(60 − 30) = 63,450(80 − 38)   →   m = 88,830 kg/hr
```

**60 − 30 is the air's temperature rise, applied to the water stream.** Cooling
water enters at 25 °C and the exchanger's effectiveness of 0.4 fixes its outlet at
47 °C, so ΔT = 22:

```
    m = 26,64,900 / 22 = 1,21,132 kg/hr
    Pump power  9.902 kW, not 7.261
    Annual saving  1,27,004 kWh, not 1,46,565 — overstated by 15 %
```

Everything downstream of the substitution is arithmetically correct.

## The finding

She computed that same 47 °C **correctly on Day 5**, in the guided walkthrough.
Cold, the effectiveness step did not resurface and the air ΔT was the one already
on the page.

A heat exchanger has **four temperatures**, and the wrong pair is always available
and always plausible.

## Tags

| Tag | Note |
|---|---|
| **Concept — stream identity** | Air ΔT applied to the water stream |
| All others | 0 across both questions |

## Verdict

The strongest session so far on the compressed air side. The pump error is narrow
and specific — not a gap in the pump chain, which was executed correctly on the
same page for the fan.

## Instruction to Tutor

Checking pass gains step 4a: **label every ΔT with its stream before
substituting.** Write "air: 60−30" or "water: 47−25" beside the number.

# Assessment — Day 11

**Time: 08:57 → 09:45, forty-eight minutes** for both questions (targets 30 + 15).

---

## 25th sitting N-1, pharmaceutical chilled water — **20 / 20**

**08:57 → 09:29, thirty-two minutes** (target 30).

```
 a) Area = 55.373 m²                                    ✓  (model 55.2)

 b) Chilled water pump  200 × 18/(367 × 0.78)/0.92 = 13.672 kW   ✓
    Condenser pump      600 × 18/(367 × 0.80)/0.92 = 39.984 kW   ✓
    Cooling tower fan   28 × 42.83/(102 × 0.62)/0.92 = 20.612 kW ✓
    Total                                          = 74.268 kW   ✓  (model 74.3)

 c) Chiller SEC = (850/4.4)/(850/3.517) = 0.799 kW/TR   ✓
    System SEC  = (193.2 + 74.268)/241.7 = 1.107 kW/TR  ✓
    Annual      = 4314.6 and 5977.8 kWh/TR              ✓

 d) Annual energy = 1444.734 MWh                        ✓
    Annual cost   = Rs 108.355 lakh                     ✓  (model 108.32)
```

**Full marks on the question that was set — and withdrawn — on Day 5**, where 14 of
its 20 marks were untaught. Every part correct, at exam pace, including the three
separate auxiliary calculations each with its own efficiency chain.

### The interpretation habit has formed

She wrote, unprompted:

> Chiller SEC = 0.799 kW/TR **(good)**
> System SEC = 1.107 kW/TR **(requires improvement)**

That is exactly the judgement the Phase 2 checkpoint flagged as missing, asked for
once at the end of Day 11, and delivered on the first attempt. It is also *correct*
— 0.80 is a respectable chiller, and 1.11 at system level is not.

She also converted both to **kWh/TR annually**, which the question did not ask for
but which is how a plant would actually quote it.

---

## 17th sitting N-2 parts (ii) and (iii) — partially correct

**09:29 → 09:45, sixteen minutes.**

### (ii) COP — correct

```
    Chiller load = 5000 × 0.9 × (55 − 11) = 1,98,000 kCal/hr = 230.2 kW
    Work input   = 60 × 0.87                                 =  52.2 kW
    COP = 230.2 / 52.2 = 4.411                               ✓  (model 4.41)
```

Marked **"(good)"** — again the interpretation, unprompted.

### (iii) Energy saving — the TR reduction is right, the conversion is not

```
    Reduction in load = 5000 × 0.9 × (55 − 40) = 67,500 kCal/hr
                      = 67,500/3024 = 22.321 TR                      ✓

    Hers:  67,500/860 × 600 × 12 = 565.116 MWh                       ✗
    Model: 22.32 × 0.916 × 600 × 12 = 1,47,205 kWh = 147.2 MWh
```

**The 22.321 TR is exactly right.** What follows converts it the wrong way.

`67,500/860 = 78.5 kW` is the **heat no longer being moved** — a thermal quantity.
The question asks for the **energy saved**, which is electrical, and the chiller
does not consume one kW of electricity per kW of cooling. It consumes about a
quarter of that.

The bridge is **kW/TR**:

```
    kW/TR = motor input / TR delivered = 60 / 65.476 = 0.916
    Energy saving = 22.32 TR × 0.916 kW/TR = 20.45 kW
                  × 600 × 12 = 1,47,205 kWh
```

Her answer overstates the saving by **3.8×** — which is `1/0.26`, the reciprocal of
the plant's specific consumption.

### The subtlety worth extracting

Notice the plant has **two different performance numbers**, and they are not the
same reciprocal pair:

| | Basis | Value |
|---|---|---|
| COP = 4.411 | motor **output** (60 × 0.87 = 52.2 kW) | shaft |
| kW/TR = 0.916 | motor **input** (60 kW) | electrical |

`3.517/0.916 = 3.84`, not 4.41 — because one includes the motor loss and the other
does not.

**For an energy saving you always want the electrical basis**, because that is what
the meter records and what the bill charges. So `kW/TR` on motor input is the right
bridge, not COP on shaft power.

This is the same "name which efficiency" issue as the Electrical & Fluids
diagnostic, appearing in a new place: not *which machine*, but *which side of the
motor*.

---

## Tags

| Tag | Note |
|---|---|
| **Concept** | Thermal load reduction converted directly to energy, bypassing kW/TR |
| Method, arithmetic, units, reading | 0 |

## Verdict

**Chapter 9 complete.** The 25th N-1 at full marks closes out a question that has
been open since Day 5, and the auxiliary chain — three machines, six efficiencies —
was executed without a single slip.

The one error is a genuine concept point rather than a slip, and it is specific:
**a reduction in cooling load is not a reduction in electricity until you divide by
the plant's own performance.**

**And the interpretation habit is now established** — three unprompted judgements
across two questions, all correct.

## Instruction to Tutor

1. Add to the anchors: **cooling load ≠ electrical load.** To convert a TR change
   into a kWh change, multiply by kW/TR on an **electrical input** basis — never by
   860 alone, and not by COP on shaft power.
2. Note the COP/kW-TR basis distinction explicitly in Day 11 Rung 113: COP is
   usually quoted on shaft power, kW/TR on motor input, so `3.517/kW-per-TR` will
   not reproduce a quoted COP when motor losses are in play.

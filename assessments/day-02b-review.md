# Assessment — Day 2B practice (paddy husk boiler)

**Task:** 24th sitting N-1, parts 1–3 — excess air, AAS, m_dfg, L1, with a
prediction written first.

**Score: 4 / 5 steps correct.** One error, and it was partly set up by the lesson.

## What was right

```
    Excess air = 6/(21−6) × 100        = 40 %              ✓
    AAS        = 1.4 × 4.27            = 5.978 kg/kg       ✓
    m_dfg      = 6.978 − 9(0.0501) − 0.1079 = 6.4192       ✓
```

Formulas written before substitution throughout, units carried, working laid out
in a chain an examiner could follow. This is exam-ready presentation.

**The m_dfg deserves note.** 6.4192 is arithmetically correct. The official model
answer states **6.34** from the same inputs, which does not reproduce. The student
is right and the published answer is wrong. She was not told this in advance.

## The error

```
    L1 = 6.4192 × 0.45 × (225−32) / 3500 × 100 = 15.929 %     ✗
    Correct, with Cp = 0.24:                    =  8.50 %
```

**0.45 is the specific heat of superheated steam. 0.24 is flue gas.** L1 heats
gas; L2–L4 heat water vapour. Using the vapour value in L1 nearly doubles the
loss.

The arithmetic was flawless — 6.4192 × 0.45 × 193 / 3500 × 100 really is 15.929.
Only the constant was wrong.

**Partly a lesson fault.** The Day 2B practice listed the composition, flue gas
O₂, temperatures, radiation loss and GCV — but **not the Cp values**. The 24th
paper does not give them either; both come from the guidebook. With no value
supplied, the only Cp visible anywhere in the lesson was the 0.45 in the natural
gas worked example. Picking it up was reasonable.

Fixed: Day 2B now states both values and explains the distinction, and
`reference/formula-sheet.md` §1 carries a specific-heat card.

**A sanity check would also have caught it.** A 15.9% dry flue gas loss is very
high; typical L1 is 5–12%. Worth adding L1 to the anchor set.

## The prediction — right answer, incomplete reason

> *"L1 of husk will be higher than natural gas boiler's 6.43% since more excess
> air is required for paddy husk's combustion."*

**Direction correct**: 8.50% > 6.43%. Writing it before calculating is exactly the
habit asked for, and it is now appearing unprompted.

The reasoning is the weaker half. Husk does run more excess air (40% vs 23.5%),
but that is not why L1 is higher — husk's flue gas mass is **three times smaller**
than the gas boiler's (6.42 vs 19.22 kg/kg). On mass alone husk should lose less.

Decomposing `L1 = m_dfg × Cp × ΔT / GCV`:

| Factor | Husk vs NG | Effect on L1 |
|---|---|---|
| m_dfg | 3.0× smaller | pushes L1 **down** |
| GCV | 3.7× smaller | pushes L1 **up**, and dominates |
| ΔT | 1.29× larger (193 vs 150) | pushes L1 up |

Give husk the gas boiler's GCV and its L1 falls to **2.29%**. Give it the gas
boiler's ΔT and L1 is 6.60%. **GCV is the dominant term.**

The physical statement: husk carries little energy per kg, so the same quantity of
stack heat is a much larger *fraction* of it. Loss percentages are always a ratio —
a small numerator over a small denominator can still be large.

## Error tags

| Tag | Note |
|---|---|
| Concept | Cp of flue gas vs vapour not distinguished |
| **Curriculum** | Cp values omitted from the practice data |
| Arithmetic | 0 — every computation correct |
| Units | 0 |

## Verdict

Strong session. The mechanical chain — excess air → AAS → m_dfg → loss — is
solid and correctly executed on a fuel with moisture and fuel-oxygen, which is
harder than the taught example. Presentation is exam-standard. The prediction
habit has stuck.

Two things to sharpen: keeping the two Cp values distinct, and reading a loss
*percentage* as a ratio rather than an absolute quantity.

## Instruction to Tutor

1. Specific-heat card added to the formula sheet; Day 2B practice data corrected.
2. Add L1 to the sanity anchors: **typical L1 is 5–12%.**
3. In Day 3 Rung 13, state explicitly that L1 percentage scales inversely with
   GCV, so low-GCV fuels show high percentage losses at the same absolute loss.
4. Day 3's existing Cp warning (Rung 14) is well aimed — keep it prominent.

# Study Log

Updated daily. The Reviewer reads this before each assessment.

## Progress tracker

| | |
|---|---|
| Curriculum | 16 sessions, ~52 hours |
| Started | 30 August 2026 |
| Curriculum ends | 14 September 2026 |
| **Exam** | **26 September 2026, 14:00–16:30** |
| Days completed | **9 / 16** — through Day 7 (Mock A) |
| Buffer after curriculum | 11 days |

```
Curriculum  [████████                      ]  25%   4/16 sessions
Book-4 ch.  [██                            ]   7%   1/15 chapters (ch.1 COMPLETE)
```

**Days to exam: 26.**

## Chapter coverage

| Ch. | Topic | Day | Status |
|---|---|---|---|
| 1 | Boilers | 1–3 | ✅ complete |
| 2 | Furnaces | 6 | ✅ complete |
| 3 | Cogeneration, turbines | 4, 4B | ✅ complete |
| 4 | Heat exchangers | 5 | ✅ complete |
| 5 | Motors, VSD | 10 | ⬜ |
| 6 | Fans and blowers | 9 | ⬜ |
| 7 | Water pumps | 8 | ⬜ |
| 8 | Compressors | 9 | ⬜ |
| 9 | HVAC | 11 | ⬜ |
| 10 | Financial analysis | 13 | ⬜ |
| 11 | Power plants | 12 | ⬜ |
| 12 | Steel | 13 | ⬜ |
| 13 | Cement | 13 | ⬜ |
| 14 | Buildings | 11 | ⬜ |
| 15 | Textile | 13 | ⬜ |

## Assessment scores

| After day | Assessment | Max | Score | Date |
|---|---|---|---|---|
| 3 | Boiler & combustion diagnostic | 20 | **18** | 30 Aug |
| 7 | Mock A — thermal | 60 | **29** | 30 Aug |
| 10 | Electrical & fluids diagnostic | 30 | — | — |
| 13 | Sector & systems diagnostic | 40 | — | — |
| 14 | Full Mock 1 | 100 | — | — |
| 15 | Full Mock 2 | 100 | — | — |

## Error tally

Running count by error type. This is what tells the tutor what to change.

| Type | Count | Note |
|---|---|---|
| Concept | 1 | Did not know the method |
| Method | 2 | Knew it, applied it wrongly |
| Arithmetic | 0 | Right method, wrong number |
| Units | 0 | kCal/kJ, TPH/kg-hr mix-ups |
| Lookup speed | 0 | Over 60 s to find something in the books |
| Curriculum | 18 + | Marks lost to material not yet taught, or data omitted from a question — a planning fault, not a gap |

---

## Daily entries

Copy this template each day.

### Day N — DD Month

**Planned:** topic
**Hours:** actual vs 3.5 planned
**Covered:**
-

**Timed question:** paper, question, self-marked score /20, time taken

**Errors:**
| # | Error | Type | Fix |
|---|---|---|---|
| 1 | | | |

**Lookups over 60 s:**
-

**Confidence (1–5):**
**Carry-over to tomorrow:**

---

### Day 0 — 30 August 2026

**Setup day.** Repository organised, curriculum built, past papers analysed.

Findings that shaped the plan:
- 18 PDFs are 10 sittings (Set A/B duplicate each other), 8 machine-readable
- Format stable 2015–2025: 10 + 10 + 80 marks
- Paper duration increased from 2 h to 2.5 h for the 26th
- Top recurring topics: boilers 8/8, motors 8/8, HVAC 7/8, pumps 7/8,
  heat exchangers 7/8, power plant heat rate 7/8, cement 7/8

**Action before Day 1:** confirm remaining Paper 4 attempts on the candidate
dashboard (limit is 4 within 6 consecutive exams), and download the 4th-edition
guidebooks if they are not already to hand.

**Next:** Day 1 — exam craft, guidebook indexing, boilers direct method.

---

### Day 1 — 30 August 2026

**Planned:** Exam craft, open-book system, boilers — direct method and
evaporation ratio.

**Covered:** Evaporation ratio learnt and applied correctly.

**Timed question:** 18th sitting Set A, N-1 (20 marks).
Furnace oil requirement calculated correctly at **547.62 kg/hr** — exact to the
model answer. CO₂ emissions for both boilers not attempted.

**Errors:**

| # | Error | Type | Fix |
|---|---|---|---|
| 1 | CO₂ from fuel not calculable | Concept — genuine gap | Day 2 A5, carbon balance |
| 2 | NG branch unreachable | **Curriculum** | Question needed Day 2–3 material; Block C replaced |

**Assessment:** `assessments/day-01-review.md` — 2/20 as marked, but only 2 marks
were reachable with Day 1 material. Every reachable mark was earned.

**Curriculum changes made:**
- Days 2 and 3 swapped — combustion now precedes the indirect method
- Day 1 Block C replaced with a self-contained ER question
- CO₂ carbon balance added to Day 2

**Confidence (1–5):** 4 on evaporation ratio.
**Carry-over:** finish the 18th N-1 in Day 2 Block B1.

**Next:** Day 2 — fuels, combustion and carbon accounting.

---

### Day 1 (continued) — Block C, corrected question

**Timed question:** 18th sitting L-1, LP/HP steam cost. 5 marks.
**Time: 13:27 → 13:34, seven minutes** against an eight-minute target.

**Score: 3/5.**

Ratio derivation fully correct — set η_LP = η_HP, cancelled GCV, obtained
(Q/q)_HP = 0.903 (Q/q)_LP. Verified: ER_LP = 14.536, ER_HP = 13.133, ratio
0.9035.

Final step inverted: multiplied Rs 3000 by 0.903 to get Rs 2709 instead of
dividing to get Rs 3322. Steam cost is inversely proportional to evaporation
ratio.

Also redid the furnace oil calculation correctly at 0.547 TPH.

**Errors:**

| # | Error | Type | Fix |
|---|---|---|---|
| 1 | Steam cost ∝ ER instead of 1/ER | Method | Sanity sentence; quantity-tracking method |

**Caught unprompted:** the crossed-out 1.826 in the furnace oil working is the
exact reciprocal of 0.547 — the same inversion, spotted and corrected. Two
inversions in one hour, one caught, one missed.

**Assessment:** `assessments/day-01-blockC-review.md`

**Curriculum change:** `reference/reciprocal-traps.md` added. From Day 2, every
final answer requires a written sanity sentence.

**Confidence (1–5):** 4 on evaporation ratio, and the algebra is solid. The gap
is verification, not knowledge.

**Next:** Day 2 — fuels, combustion, carbon accounting.

---

### Day 2 — 30 August 2026

**Planned:** Fuels, combustion, carbon accounting.

**Outcome:** Could not follow worked examples B1 or B2. Could not attempt the
Block C question.

**Diagnosis — build fault, not a knowledge gap.** The lesson introduced five new
ideas (theoretical air, excess air, dry flue gas mass, carbon balance, heat
balance) and then required all five simultaneously in an eight-step worked
example. One unclear link makes the whole example unreadable. Compounded by a
deliberately off-topic 20-mark cooling tower question at the end of an already
overloaded day.

**Errors:** none attributable to the student. Tagged **Curriculum**.

**Action taken:**
- Day 2 split into **2A** (combustion air) and **2B** (flue gas, CO₂, heat balance)
- Rewritten rung-by-rung: one idea per rung, each with a drill and a checkable
  answer. Every drill answer verified numerically.
- Combined example moved to the end of 2B, with each step labelled by the rung it
  uses — so a failure points at a specific rung
- Cooling tower question removed to Day 10
- Reviewer trigger added: inability to follow a *worked example* is a build fault,
  never logged as a student gap

**Curriculum now 16 sessions**, ending 14 Sep. Buffer 11 days.

**Next:** Day 2A — combustion air, one rung at a time.

---

### Days 2A & 2B — 30 August 2026

**Both completed.** The rung-by-rung format worked where the combined lesson had
not. No blocking issues reported.

**Covered:** ultimate analysis as kg/kg · oxygen requirements from the reactions ·
the 23% conversion to air · deriving 11.6, 34.8, 4.35 · the O₂/8 fuel-oxygen
credit · theoretical air · excess air from flue gas O₂ · mass in = mass out ·
dry flue gas mass · CO₂ carbon balance · the heat-balance rationale for the
indirect method.

**Chapter 1 (Boilers) now substantially covered** — direct method, evaporation
ratio, combustion, flue gas, CO₂. Remaining: the seven losses (Day 3).

**Note for the Reviewer:** completion was self-reported without drill answers, so
retention is unverified. Day 3 therefore opens with a six-question readiness
check on the 2A/2B rungs. If that check goes badly, the rungs need revisiting
before the losses.

**Next:** Day 3 — the indirect method, all seven losses.

---

### Day 2B practice — paddy husk boiler (submitted 30 Aug)

**4 of 5 steps correct.**

```
    Excess air = 6/(21−6) × 100            = 40 %          ✓
    AAS        = 1.4 × 4.27                = 5.978         ✓
    m_dfg      = 6.978 − 0.451 − 0.108     = 6.4192        ✓
    L1         = 6.4192 × 0.45 × 193/3500  = 15.929 %      ✗  (Cp wrong)
    L1 correct = 6.4192 × 0.24 × 193/3500  =  8.50 %
```

**Notable: the m_dfg of 6.4192 is right and the official model answer's 6.34 is
wrong.** Recomputing from the paper's own inputs gives 6.42.

**Error:** used Cp = 0.45 (superheated steam) in L1, which needs 0.24 (flue gas).
Arithmetic itself was flawless.

**Partly a curriculum fault:** the Day 2B practice data omitted both Cp values.
The 24th paper does not give them either — both come from the guidebook — so the
only Cp visible in the lesson was the 0.45 from the natural gas example.

**Prediction written before calculating, unprompted** — the new habit has stuck.
Direction was right (8.50% > 6.43%). Reasoning was incomplete: attributed it to
excess air, when husk's flue gas mass is actually 3× *smaller*. The dominant term
is GCV — 3500 vs 13,000 — since L1 is a ratio.

| # | Error | Type | Fix |
|---|---|---|---|
| 1 | Cp flue gas vs vapour confused | Concept | Specific-heat card; Day 3 Rung 13 warning |
| 2 | Cp values absent from practice data | Curriculum | Day 2B data corrected |

**Assessment:** `assessments/day-02b-review.md`

**Changes made:** specific-heat card added to formula sheet §1 · Day 2B practice
data corrected · Day 3 Rung 13 gains the Cp warning, the 5–12% sanity anchor for
L1, and an explanation of why low-GCV fuels show high percentage losses.

**Verdict:** the chain excess air → AAS → m_dfg → loss is solid, executed
correctly on a harder fuel than the taught example, with exam-standard
presentation.

---

### Day 3 — 30 August 2026

**Completed.** Both practice questions attempted.

**20th sitting N-1 (5 parts, 20 marks): 18/20.** Strongest session so far.

A_th 16.2 ✓ · excess air 23.5% ✓ · AAS 20.01 ✓ · L1 7.6% ✓ · η 80.96% ✓ ·
steam:fuel 18.651 ✓ · air 127.154 m³/min ✓ · improvement 2.63% ✓ ·
saving 15.686 m³/hr ✓ · yearly Rs 33,54,294 ✓

**More accurate than the official model on parts (c), (d) and (e).** The model
rounded intermediates to 3 s.f. before subtracting, turning a 0.25% input error
into a 9% output error. Its (e) also contradicts itself — "Rs 30,79,296 =
Rs 33.793 lakhs".

**Good exam economy:** started computing L2, spotted that 9.92% was given in the
data table, struck it out and moved on.

**Timing:** parts (c)–(e) in three minutes (23:13→23:16).

**Errors:**

| # | Error | Type | Fix |
|---|---|---|---|
| 1 | m_dfg 19.12 — used 0.21 for H₂ in one line | Arithmetic | none needed, isolated slip |
| 2 | 18th N-1: correct answer reached, then reverted | **Method** | Rule-a-line correction discipline |

**The significant finding.** On the 18th N-1 she initially used efficiency (0.82)
where the carbon fraction (0.73) belongs, caught it unaided, corrected to 1154.66,
and computed 4,80,186 kWh — correct. She then struck out both correct lines and
substituted the values following from the original error. Right answer reached
and discarded.

**Assessment:** `assessments/day-03-review.md`

**Added:** `reference/precision-and-rounding.md` — the subtraction trap, the
15/571 cancellation shortcut, correction propagation, and a running list of errors
found in official model answers.

**Chapter 1 (Boilers) complete.** Direct method, evaporation ratio, combustion,
flue gas, CO₂, all seven losses.

**Next:** Day 4 — cogeneration and turbines.

---

### Day 6 — 24th sitting L-2, re-rolling furnace

**Time: 20:39 → 20:56, seventeen minutes** for a 5-mark question (target 10).

**All final answers correct — full marks.**

```
    η        = 38.302 %                    ✓
    SEC      = 40.429 kg/tonne             ✓
    Cost, FO = Rs 2223.595/tonne           ✓
    Cost, electric = Rs 1788.303/tonne     ✓
    Conclusion: electric furnace economical ✓
```

**Best self-correction yet.** She first wrote SEC as `36000/(1565×0.93)` — the
inversion — then struck it out and wrote `(1565×0.93)/36`. That is the fourth
appearance of the reciprocal family and **the first caught on the first pass,
unprompted**.

**One slip that did not propagate.** `5,985,473.68 / 860 = 6,959.85 kWh/hr` was
written as **695.985** — a factor of ten — and carried into SEC as 19.333 kWh/T
instead of 193.33. But the final cost line reads Rs 1788.303, which requires
193.33 × 9.25. So the arithmetic performed was right; only the two transcribed
intermediates were out by ten.

Lucky rather than caught. The checking pass still is not running.

**The anchor that would have caught it instantly:** heating one tonne of steel to
1250 °C needs 0.13 × 1215 = 157,950 kCal = **~184 kWh, irreducibly**. An answer of
19.3 kWh/tonne is ten times below the thermodynamic minimum.

| # | Error | Type | Fix |
|---|---|---|---|
| 1 | 6959.85 written as 695.985 | Arithmetic | Order-of-magnitude anchors added to the checking pass |

**Added:** `reference/precision-and-rounding.md` §5 now requires an
order-of-magnitude check on every *intermediate*, plus a table of physical
anchors — steel heating energy, ER bands, efficiency bands, L1 bands,
theoretical air, furnace SEC, turbine heat rates, pump power scale.

**Book-4 Chapters 1, 2, 3 and 4 now complete.**

**Next:** Day 7 — consolidation and Mock A, thermal only, 50 marks, timed.

---

### Day 7 — Mock A

**29 / 60 raw (48%). 29 / 50 on attemptable material (58%).** Pass equivalent 30/60.

| Section | Score |
|---|---|
| I — True/False | **8/10** |
| II — Short numericals | **9/10** |
| III — N-1 reverse combustion | ~2/20 |
| III — N-2 heat exchanger | ~10/20 (B(i) correct; B(ii),(iii) untaught) |

**Sections I and II: 17/20 combined.** L-1 exact. L-2 values all correct, labelled
MWh instead of MW.

**N-1 is where the paper was lost.** She recalled every relationship correctly but
wrote `TA = 11.6C + 34.8(H₂ − O₂/8)` — with C and H₂ being precisely what the
question asks for. A problem-recognition failure, not a knowledge gap: all the
tools were Day 2A rungs.

**N-2 part B(i) fully correct**, including both block diagrams and the 97.2% area
increase (exact 97.1%).

**Two Section I errors, both concepts covered explicitly:** the isentropic
direction (she can apply the formula and still misjudge the direction), and a
compound statement whose fact is true and inference false.

**Tutor fault — fourth prerequisite breach.** The 17th N-2's parts (ii) and (iii)
need chiller COP (Day 11). The question's *topic* was checked; its *sub-parts* were
not. Rule tightened to sub-part level.

**Tags:** concept ~20 (almost all N-1), units 1, curriculum 10.
**Strip N-1 out and the rest reads 27/30.**

**Added:** `reference/inverse-problems.md` — the four inverse types in Paper 4,
the recognition trigger, and the anchor-and-chain method.

**Still missing after two requests: per-question timing.** Pace under exam
conditions remains unmeasured, and it is now the most important unknown.

**Next:** Day 8 — pumps and pumping systems. Phase 2 begins.

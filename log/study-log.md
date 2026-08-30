# Study Log

Updated daily. The Reviewer reads this before each assessment.

## Progress tracker

| | |
|---|---|
| Curriculum | 16 sessions, ~52 hours |
| Started | 30 August 2026 |
| Curriculum ends | 14 September 2026 |
| **Exam** | **26 September 2026, 14:00–16:30** |
| Days completed | **1 / 15** |
| Buffer after curriculum | 11 days |

```
Curriculum  [██                            ]   7%   1/15 days
Book-4 ch.  [██                            ]   7%   1/15 chapters (ch.1 in progress)
```

**Days to exam: 26.**

## Chapter coverage

| Ch. | Topic | Day | Status |
|---|---|---|---|
| 1 | Boilers | 1–3 | 🟨 direct method done |
| 2 | Furnaces | 6 | ⬜ |
| 3 | Cogeneration, turbines | 4 | ⬜ |
| 4 | Heat exchangers | 5 | ⬜ |
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
| 3 | Boiler & combustion diagnostic | 30 | — | — |
| 7 | Mock A — thermal | 50 | — | — |
| 10 | Electrical & fluids diagnostic | 30 | — | — |
| 13 | Sector & systems diagnostic | 40 | — | — |
| 14 | Full Mock 1 | 100 | — | — |
| 15 | Full Mock 2 | 100 | — | — |

## Error tally

Running count by error type. This is what tells the tutor what to change.

| Type | Count | Note |
|---|---|---|
| Concept | 0 | Did not know the method |
| Method | 2 | Knew it, applied it wrongly |
| Arithmetic | 0 | Right method, wrong number |
| Units | 0 | kCal/kJ, TPH/kg-hr mix-ups |
| Lookup speed | 0 | Over 60 s to find something in the books |
| Curriculum | 18 | Marks lost to material not yet taught — a planning fault, not a gap |

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

# Reviewer Framework

The Reviewer's job is not to give marks. It is to work out **why** marks were
lost, and tell the Tutor what to change.

## Assessment schedule

| After day | Assessment | Max | Format |
|---|---|---|---|
| 3 | Boiler & combustion diagnostic | 30 | 1 long + 2 short, 45 min |
| 7 | Mock A — thermal only | 60 | 10 T/F + 2 short + 2 long, 90 min |
| 10 | Electrical & fluids diagnostic | 30 | 1 long + 2 short, 45 min |
| 13 | Sector & systems diagnostic | 40 | 2 long, 60 min |
| 14 | Full Mock 1 | 100 | Full paper, 2.5 hrs, exam conditions |
| 15 | Full Mock 2 | 100 | Full paper, 2.5 hrs, exam conditions |

## Marking

Mark the way BEE examiners do — method carries the marks. For a 20-mark question:

| Component | Marks |
|---|---|
| Correct formula stated | 4 |
| Correct substitution, units consistent | 4 |
| Correct intermediate quantities | 6 |
| Correct final answer with units | 4 |
| Sanity / interpretation where asked | 2 |

A wrong final number with sound method should still earn 12–14. A right number
with no working earns far less than students expect. Mark accordingly — it
mirrors the real paper and stops the student optimising for the wrong thing.

## Error taxonomy

Every lost mark gets exactly one tag:

| Tag | Meaning | Tutor response |
|---|---|---|
| **Concept** | Did not know the method | Re-teach. Add a day if it recurs. |
| **Method** | Knew it, applied it wrongly | More guided practice on that pattern. |
| **Arithmetic** | Right method, wrong number | Not a teaching problem. Slow down, check. |
| **Units** | kCal/kJ, TPH/kg-hr, bar/kg-cm² | Drill the conversion table. |
| **Lookup** | Over 60 s to find something | Re-tab the guidebook. |
| **Time** | Ran out | Question-selection and pacing practice. |

The distribution is the signal. Mostly Concept after Day 7 means the curriculum
is moving too fast. Mostly Arithmetic means it is working and the student needs
composure, not more teaching.

## Logger maintenance rule

`log/study-log.md` carries the same state in three places — the summary table, the
progress bars, and the chapter/session tables. They drifted apart between Day 3 and
Day 10 because only the tables were updated, leaving the bars reading 25% when the
true figure was 61%.

**On every session, update all three or none.** The bars are the part a reader sees
first and the part least likely to be maintained, so check them explicitly.

## Feedback format

Each assessment produces `assessments/day-NN-review.md`:

```markdown
# Assessment — Day NN

**Score:** X / Y  (pass threshold: 50%)

## Marks lost, by tag
| Tag | Marks lost | % of loss |

## What went well

## Gaps found
1. [Topic] — what specifically was not understood

## Verdict on the curriculum
On track / adjust pace / re-teach [topic]

## Instruction to Tutor
Concrete change to the remaining days.
```

## Prerequisite rule — mandatory before setting any question

**Three times now a timed question has required material not yet taught:**

| Day | Question | Untaught content | Marks unreachable |
|---|---|---|---|
| 1 | 18th N-1 | Indirect method, combustion | 18 / 20 |
| 4 | 18th N-2 | Gas turbine cogeneration | 20 / 20 |
| 5 | 25th N-1 | Pump power, fan power, chiller SEC | 14 / 20 |
| 7 | 17th N-2 | Chiller COP | 10 / 20 |

This is a Tutor fault with a real cost: it consumes study time, produces a score
that measures nothing, and teaches the student to distrust her own preparation.

**Before any question is set, EVERY NUMBERED SUB-PART must be traced to a taught
rung — not the question's apparent topic.** The Mock A breach happened because the
question was confirmed to be "a heat exchanger question" and its sub-parts were
never read; parts (ii) and (iii) needed chiller COP. Then one of:

1. Set the whole question — all parts covered.
2. **Name the parts to attempt** and say explicitly which are deferred and to
   which day.
3. Choose a different question.

Never set a question containing untaught parts without saying so. "It will
stretch her" is not a reason — an unreachable mark teaches nothing.

Depth is subject to the same check: a chapter appearing in 7 of 8 sittings is not
covered by two formulas. If a lesson can be summarised as "here are the formulas",
it is not finished.

## Triggers for changing the plan

| Observation | Action |
|---|---|
| Mock A under 25/50 | Compress Phase 2 to 2 days, return a day to thermal |
| Same topic fails twice | Insert a dedicated re-teach block before the next phase |
| Concept tags > 50% of losses | Slow down — the pace is wrong |
| Arithmetic tags > 50% | Pace is fine; add checking discipline, not content |
| Lookup tags recurring | Stop and rebuild the guidebook index |
| Full Mock 1 under 50 | Abandon new material; drill only the top-5 recurring topics |
| Full Mock 1 over 65 | Push into the 21st/22nd papers during buffer |

## Standing question for every assessment

*Could the student solve a question they have never seen before on this topic?*

Paper 4 never repeats a question verbatim. Recognition is not competence. If the
student can only solve the version they have already seen, the Reviewer must
flag it regardless of the score.

# Reviewer Framework

The Reviewer's job is not to give marks. It is to work out **why** marks were
lost, and tell the Tutor what to change.

## Assessment schedule

| After day | Assessment | Max | Format |
|---|---|---|---|
| 3 | Boiler & combustion diagnostic | 30 | 1 long + 2 short, 45 min |
| 7 | Mock A — thermal only | 50 | 2 long + 2 short, 75 min |
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

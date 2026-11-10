# Data format, version 1

All data files are UTF-8 JSON with schemaVersion: 1. IDs are stable across edits.
Dates use YYYY-MM-DD. The client conversation date is used for learning events.

## Files

- data/learner.json: preferences, progression, selected/deselected material, next-unit IDs and latest-session ID.
- data/catalog.json: vocabulary entries, grammar patterns and practice units.
- data/sessions/<unique-session-id>.json: observed attempts, tutor corrections, outcomes and next steps.

Session IDs begin with their actual date, followed by an available suffix.
Observation IDs are scoped to a session. Catalog evidence references pair sessionIds with observationIds;
all observation IDs listed on an entry must occur in one of its listed sessions.
Do not count the same lesson twice after an uncertain write.

## Evidence states

| State | Meaning |
| --- | --- |
| introduced | A translation, example, pattern or corrected form was shown. |
| discussed | Its meaning or usage was explicitly explored; independent use may not have occurred. |
| used_with_correction | The learner attempted the item but needed a correction. |
| used_successfully | The learner used it correctly in the recorded context. |

These are descriptive states, not numerical scores. They do not imply a fixed ordering.
A later correction can qualify an earlier success; retain both observations.
No current item is labelled mastered. Add such a concept only with a documented retention criterion.

Each vocabulary/grammar item stores evidence pointers and a note or next-review target.
When a date or attempt is unknown, use null or an explicit explanation instead of inventing evidence.
Prompts supplied by the tutor are not learner attempts.

## Practice-unit contract

A unit has an ID, title, prompt, modelAnswer, optional hint, feedbackFocus, vocabularyIds,
grammarIds, target seconds, optional flag and selection state.
Model answers can have alternatives; an open response must be assessed for meaning, not exact string equality.
All initial units have attemptCount: 0 because these specific units are newly proposed,
even when their underlying patterns were practised earlier.
Record a real attempt in its session before incrementing attemptCount or setting lastAttempt.
selection is enabled or deselected. nextReview is a teaching suggestion, not a scheduled job.

The learner's deselectedUnitIds, deselectedGrammarIds and deselectedVocabularyIds also filter selection.
Skip-this applies to the current exercise; skip-this-topic applies to the topic scope stated by the learner.
Preserve deselection until the learner opts back in. No unanswered prompt creates a backlog.

## Adding training programs later

Programs can load preferences, filter units by selection, resolve stable vocabulary/grammar IDs,
and choose recall prompts using the recorded evidence and next steps.
Keep answer keys separate from initial recall displays.
Use new schema versions for breaking changes, documenting any migration.
Validate JSON syntax, unique IDs, enum values and references before writing.
Fetch current remote content before saving and preserve concurrent updates.

This repository stores language-learning content, not full chat transcripts or unrelated work information.

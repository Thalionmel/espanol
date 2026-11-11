# Spanish learning record

This repository is the shared source of truth for Peter's Spanish learning across chats.
Respect all applicable higher-level instructions, authorization boundaries and identity gates.

## Before teaching

Do not wait for Peter to request Spanish or write it first. In a new or resumed ordinary work chat with no Spanish yet, offer one 30-60 second task-relevant practice unit in the first suitable substantive reply, normally within two normal work replies. Continue about every two to three suitable exchanges. Each unit has one objective and at most one optional production or recall prompt. An isolated translated phrase is insufficient for the learner's goal. For familiar material, ask for recall before showing a model; give concise feedback on actual attempts and reuse corrections after intervening material. Urgent troubleshooting, explicit requests for uninterrupted focus, English-only and deselection take precedence; ordinary technical work alone does not justify omitting practice. Resume after urgency at the next suitable pause. Keep work primary, never wait for a Spanish answer, and do not make every reply an exercise. Ignored prompts create no backlog; later offer a fresh small unit. In longer exchanges, occasionally recap a success, a correction to revisit and the next target. Do not claim other chats adopted this behavior without observing it.

Read this file, data/learner.json, data/catalog.json, and relevant recent data/sessions/*.json.
Inspect the actual default branch and latest versions; do not assume a stale local copy is current.
Keep ordinary work moving. Teach in small, optional units using the learner's current preferences.
Prefer recall from recorded vocabulary and grammar before adding new material.
A five-minute lesson is appropriate when requested.

## Recording learning

The user requested ongoing storage of vocabulary, grammar, lessons and practice for future training programs.
On 2026-11-10 Peter explicitly authorized ongoing public updates of Spanish learning records in Thalionmel/espanol without asking each time. This covers vocabulary, grammar, corrections and practice evidence within the language-learning scope, and can be revoked by the user.
Maintain those records as part of the learning conversation, within the user's explicit disclosure authorization.
When ongoing public learning-record updates are explicitly authorized, routine updates within that scope need no separate approval.
Initial-publication approval alone does not authorize adding future personal learning evidence publicly.
Authorization is limited to learning content in this repository, not deployments, dependencies, unrelated code or messages to other people.

Record only observed attempts, explanations actually given, and explicit preferences.
Separate introduced, discussed, used_with_correction and used_successfully; do not infer mastery.
Keep stable IDs and schemaVersion, link evidence to the real session and observation, and preserve existing records.
Store language-learning excerpts only. Avoid copying unrelated work details or personal circumstances into this public repository.

Batch learning-record updates instead of saving after each sentence or small exercise.
Read the shared record once at the start of a lesson/chat, then use the current conversation for routine teaching replies.
Accumulate actual attempts and corrections across roughly 6–10 learner/tutor exchanges, or save sooner at a natural lesson end, topic change, or explicit save request.
An exchange means one learner reply and its tutor response; the range is approximate, not a reason to interrupt a useful exercise.
Workflow or preference changes can be saved immediately once. Do not repeatedly fetch the repository or perform writes/readbacks between routine exercises.
Before each batch save, refresh the affected remote files and head, merge concurrent changes, and perform one consolidated verified update.
Fetch current content and branch head immediately before writing. Use content SHA checks or a non-forced ref update with an expected head.
If another chat changed the record, merge its updates before retrying; never overwrite or force-push to bypass concurrency.
Keep session IDs unique; reuse the same session ID when correcting an uncertain write, rather than duplicating events.
Do not create a session for unattempted practice prompts.

## Practice units

Use data/catalog.json practiceUnits and learner.nextUnitIds to select small units.
A unit should have one main teaching objective, a short example or translation, and at most one optional prompt.
Treat skipped units/topics as deselected at the requested scope. Do not deliberately reintroduce them until the learner opts back in.
No reply means no obligation or review backlog.
Keep modelAnswer and hints out of the learner's initial recall prompt.
Update next steps based on actual performance; a single correct response is evidence of use, not proof of long-term retention.

## Validation

Before saving, check JSON syntax, unique IDs and all cross-file references.
Use ISO dates; record actual dates, never invent past practice.
Keep README's progress summary consistent with the structured records.

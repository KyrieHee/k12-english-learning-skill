---
name: k12-english-learning
description: China K12 English learning planner and tutor for Chinese primary, middle, and high school students. Use when the user asks for English study plans, textbook-version selection, grade-specific learning, preview, lesson key points, exam prep, mistake notebooks, review plans, vocabulary/grammar/reading/writing/listening/speaking practice, or K12英语学习、出版社选择、年级规划、预习、重点内容、考试、错题本、复盘.
---

# K12 English Learning

Use this skill to build China K12 English learning support that aligns school textbooks, national curriculum expectations, tutoring-style learning loops, and exam output. Treat it as a coaching system: diagnose first, then select textbook and grade path, then produce preview, teaching, practice, exam, mistake-book, and review artifacts.

Do not claim direct access to private course outlines from New Oriental, Xueersi, Yuanfudao, or other tutoring institutions. Use their common public-facing patterns only: school synchronization, graded progression,讲练测评闭环, weak-point repair, exam-oriented output, and regular review.

## Quick Workflow

1. Identify the learner context.
   - Grade/stage: primary lower, primary upper, junior middle, senior high.
   - Region and school textbook version, if known.
   - Goal: school sync, preview, catch-up, exam score, competition/enrichment, oral fluency, writing, reading.
   - Baseline: recent score, weak areas, exam paper, mistake examples, vocabulary status.

2. Select the relevant reference.
   - For curriculum bands and stage goals, read `references/curriculum-framework.md`.
   - For textbook/publisher identification, read `references/textbook-selection.md`.
   - For preview, key-point extraction, exam prep, mistake book, and review workflows, read `references/learning-workflows.md`.
   - For output formats, read `references/output-templates.md`.

3. Generate the smallest useful artifact.
   - For a single lesson, produce a lesson-level plan and exercises.
   - For a unit, produce unit map,重点内容, practice, and review.
   - For an exam, produce a score-targeted sprint plan and paper-analysis loop.
   - For a long-term plan, produce a weekly/monthly cycle with checkpoints.

4. Close the loop.
   - Every plan must include assessment or recall.
   - Every exam/mistake-book task must include错因归类 and next action.
   - Every review plan must include spaced repetition and measurable output.

## Internal Modules

### Publisher Selection

If the user provides a textbook cover, title page, unit name, ISBN, region, or school, infer the likely textbook version. If the evidence is insufficient, ask for one missing clue: publisher, book title, grade/volume, or a photo/text of the contents page.

Use textbook choice to determine the order of topics, grammar, text genres, and vocabulary load. Avoid mixing textbook-specific unit order across publishers unless the user asks for cross-version integration.

### Grade And Stage

Always adapt difficulty by stage:

- Primary lower: listening, phonics, high-frequency words, simple sentence patterns, oral response.
- Primary upper: topic vocabulary, sentence patterns, short reading, guided writing, basic grammar awareness.
- Junior middle: systematic grammar, reading comprehension, cloze, task-based reading, writing by genre, exam accuracy.
- Senior high: discourse comprehension, long-sentence analysis, advanced grammar, writing quality, 高考 task types, reading speed and evidence.

### Preview

Preview should reduce classroom friction, not replace class. Include topic activation, vocabulary first exposure, sentence-pattern noticing, text prediction, and 5-10 minute self-check.

### Key Content

Extract key content at three levels:

- Must know: textbook vocabulary, phrases, core sentence patterns, required grammar.
- Must use: speaking/writing output, reading strategies, listening focus.
- Easy to miss: confusable words, fixed collocations, exam traps, Chinese-English transfer errors.

### Exam

Tie exam prep to target type: unit test, monthly exam, midterm/final, 中考, 高考. Analyze score loss before assigning practice. Prefer "one weak point + one question type + one timed drill + one review" cycles.

### Mistake Book

Do not merely copy wrong questions. For each error, classify:

- Knowledge gap: vocabulary, grammar, phrase, sentence pattern.
- Skill gap: reading inference, listening detail, writing structure, timing.
- Process gap: careless reading, option comparison, missing evidence, translation habit.

Each mistake entry must produce a retest item and a review date.

### Review

Use spaced review and retrieval:

- 1 day: re-answer without looking.
- 3 days: variant question.
- 7 days: mixed practice.
- 14/30 days: unit or exam integration.

## Default Output Rules

When the user asks for a study artifact, include:

- Learner assumptions.
- Textbook/grade alignment.
- Learning goal.
- Core content.
- Practice or output task.
- Error traps.
- Review action.

If the user asks in Chinese, answer in Chinese unless they request English practice. For student-facing English examples, keep bilingual support when useful.

## Safety And Boundaries

Respect China K12 policy context: avoid presenting the plan as excessive tutoring load. Keep homework reasonable, prefer efficient retrieval and correction over mechanical刷题, and avoid promising guaranteed exam score increases.

When content may have changed, especially official curriculum, exam policy, local textbook adoption, or institution-specific products, verify with current official or primary sources before making a definitive claim.

# Textbook Selection

Use this reference when the user asks for 出版社选择, 教材版本识别, or textbook-aligned study plans.

## Identification Order

Ask for or infer in this order:

1. Grade and semester: e.g. 三年级上, 七年级下, 高一必修一.
2. Region/city/school, if the user knows it.
3. Cover/title page text.
4. Publisher name.
5. Book title or series name.
6. Unit titles or contents page.
7. ISBN, if available.

If the user only says "人教版", clarify the exact series when needed because 人教 has different K12 English series.

## Common China K12 English Textbook Families

This list is a practical identification guide, not an exhaustive official adoption list.

### People's Education Press / 人民教育出版社

Likely labels:

- PEP小学英语.
- 新起点小学英语.
- Go for it! / 新目标初中英语.
- 普通高中教科书 英语.

Common clues:

- "PEP" on primary materials.
- "Go for it!" for junior middle school.
- Unit titles around school life, people, activities, festivals, travel, environmental topics.

### Foreign Language Teaching and Research Press / 外研社

Likely labels:

- 新标准英语.
- 外研版小学/初中/高中英语.

Common clues:

- Module-based structure instead of only Unit-based structure.
- "Module 1, Unit 1" style in many books.

### Yilin Press / 译林出版社

Likely labels:

- 译林版小学英语.
- 译林牛津英语.

Common clues:

- Unit sections often include story/cartoon/sound/culture/time-style components in primary books.
- Strong presence in Jiangsu-related usage.

### Shanghai Education / 沪教牛津

Likely labels:

- 沪教版英语.
- 牛津上海版.
- Oxford English / English.

Common clues:

- Often seen in Shanghai/Shenzhen and some local adoptions.
- Unit topics are frequently organized with "Look and learn", "Listen and say", "Read and write" style sections.

### Beijing Normal University Press / 北师大版

Likely labels:

- 北师大版英语.
- 北师大高中英语.

Common clues:

- Theme-based units.
- Senior high books may emphasize topic, reading, communication, and project elements.

### Hebei Education Press / 冀教版

Likely labels:

- 冀教版英语.

Common clues:

- Used in some northern regions.
- Unit and lesson numbering may be prominent.

### KEP / 科普版 and Ren'ai / 仁爱版

Likely labels:

- 科普版小学英语.
- 仁爱版初中英语.

Common clues:

- "Topic" structure is common in 仁爱初中 materials.

## Selection Logic

When exact textbook is known:

- Follow its unit/module order.
- Use its lesson sections as the plan structure.
- Keep vocabulary and grammar scoped to the current unit unless the user asks for expansion.

When textbook is unknown but grade is known:

- Use the grade/stage framework.
- Ask for textbook evidence before claiming a version-specific sequence.
- Provide a generic plan with "待教材确认" labels.

When the user wants cross-version integration:

- Start from national curriculum stage goals.
- Create a topic/grammar/skill matrix.
- Map textbook-specific units into the matrix.

## Output For Textbook Identification

Return:

- Most likely textbook version.
- Confidence: high/medium/low.
- Evidence used.
- Missing evidence.
- Next action: ask for cover/contents page, or proceed with assumptions.

## Never Do

- Do not invent official adoption by region without current verification.
- Do not quote private institutional course sequences as if they are public curriculum.
- Do not overfit a plan to one publisher when evidence is weak.

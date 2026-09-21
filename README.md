# Mastery Practice Lite v1.1 — Multiple Booklets

## Add more questions to an existing booklet
Open that booklet JSON and add more objects inside `questions`.

Example: if one booklet has 100 questions and level size is 10, it stays one booklet and gets 10 Mastery levels.

## Add a NEW booklet
1. Copy `question-bank/booklet-template.json`.
2. Rename it, e.g. `ibps-clerk-set-2.json`.
3. Put your questions in it.
4. Add one object to `question-bank/index.json`:

```json
{
  "id": "ibps-clerk-set-2",
  "title": "IBPS Clerk — Set 2",
  "category": "Banking",
  "description": "IBPS Clerk practice questions.",
  "question_count": 100,
  "file": "ibps-clerk-set-2.json"
}
```

The home page then shows a new booklet card automatically.

## Booklet format
```json
{
  "code": "ibps-clerk-set-2",
  "title": "IBPS Clerk — Set 2",
  "category": "Banking",
  "description": "Practice questions.",
  "questions": [
    {
      "id": 1,
      "question": "Question text",
      "options": ["A","B","C","D"],
      "answer": "B",
      "explanation": "Optional"
    }
  ]
}
```

`answer` must exactly match one value in `options`.

For long questions use `\n` line breaks.

Optional image:
```json
"image": "./images/question-1.png"
```

Upload the whole folder structure to GitHub Pages. No PHP/database is required.

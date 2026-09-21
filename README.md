# Mastery Practice Lite — GitHub Pages Edition

A static personal practice app. No PHP, database, login, analytics, payment system, admin panel, or build tools.

## Files

- `index.html` — complete UI and practice engine
- `questions.json` — your live question bank
- `questions-template.json` — blank starter example

## Question format

```json
{
  "code": "my-exam",
  "title": "My Exam Practice",
  "category": "Personal",
  "questions": [
    {
      "id": 1,
      "question": "Your question text",
      "options": ["Option A", "Option B", "Option C", "Option D"],
      "answer": "Option B",
      "explanation": "Optional explanation"
    }
  ]
}
```

`answer` must exactly match one item in `options`.

### Long / structured questions

Use `\n` line breaks:

```json
{
  "question": "Study the statements:\n\nA. First statement\nB. Second statement\n\nWhich is correct?",
  "options": ["A only", "B only", "Both", "Neither"],
  "answer": "A only"
}
```

The UI preserves the line breaks.

### Optional question image

Add:

```json
"image": "./images/question-1.png"
```

Then create an `images` folder beside `index.html`.

## Mastery Mode

- 10 questions per level
- immediate answer feedback
- 100% unlocks next level
- progress stored in this browser with `localStorage`
- options are shuffled

To change level size, edit in `index.html`:

```js
const FILE='./questions.json', LEVEL=10
```

## Timed Mode

- choose question count
- choose minutes
- random question selection
- shuffled options
- Previous / Next
- Mark for review
- question navigator
- timer auto-submit
- final score and answer review

## GitHub Pages

Upload these files to the repository root.

Then enable GitHub Pages for the repository from the `main` branch and root folder.

The project uses relative paths, so it works under a repository URL such as:

```text
https://USERNAME.github.io/REPOSITORY/
```

## Local testing

Browsers often block JSON `fetch()` when you open `index.html` directly with `file://`.

Run a local server instead:

```bash
python -m http.server 8080
```

Then open:

```text
http://localhost:8080/
```

For normal GitHub Pages hosting, no server-side setup is needed.

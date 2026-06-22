# Unit 4: JavaScript — Condensed (2 × 2-hour sessions)

A reworked, project-driven version of Unit 4, compressing the original seven lessons
(4.1–4.6 + Bonus) into a single day of two 2-hour sessions.

**Audience:** Beginners who already know HTML and CSS basics. This is their first real JavaScript.

**Core design principle:** Stop teaching concepts as a checklist. Anchor each session in
*one build* that forces every concept to earn its place. Beginners remember what they made,
not what they were told. Each session demos the finished project first, teaches only what that
project needs, then builds it.

---

## How to use this document

This doc is both the lesson plan and the prompt for Claude Code. Each session follows the
standard curriculum flow:

1. **Slides** — explain the fundamentals (talking points listed per block below).
2. **We Do** — a code section we complete together (guided, instructor-led).
3. **You Do** — a code section students complete on their own while the instructor circulates.

**What Claude Code should produce per session:**

Each session gets its own folder (e.g., `session-1/`) containing two subfolders:

```
session-1/
├── lesson/
│   ├── index.html
│   ├── styles.css
│   └── script.js
└── solution/
    ├── index.html
    ├── styles.css
    └── script.js
```

**`lesson/`** — The teaching version students open and code in:
- `index.html` — The HTML scaffold linking to external CSS and JS files.
- `styles.css` — All CSS in its own file (students are used to this).
- `script.js` — Structured with clear comment blocks marking:
  - **"WE DO TOGETHER"** sections — Code the instructor walks through with students. This code serves as a template/pattern for what comes next.
  - **"YOUR TURN"** sections — Empty scaffolds with guiding comments where students write code independently, following the pattern established in "We Do."

**`solution/`** — The complete reference solution:
- All code filled in, including stretch goals.
- Inline comments flagging which concept each block demonstrates (e.g., `// CONCEPT: querySelector`).

**Guidelines:**
- Keep CSS readable; clarity matters more than polish.
- No frameworks — plain JS only.
- The "We Do" code should give students a clear template to follow when they continue independently.

Slides can be generated separately; the "Slides" bullets below are the content/talking points for them.

---

## What was cut or consolidated (and why)

Decisions baked into this plan — listed so we remember the reasoning when we revisit:

- **`.style` property (orig. 4.4): cut.** Students know CSS; toggling classes with `classList`
  is the better pattern and avoids teaching two ways to change appearance.
- **Setting `.id` / `.className` via JS (orig. Bonus): trimmed to a mention.**
  `createElement` + `appendChild` + `classList` covers dynamic content without it.
- **`classList.add()` / `.remove()` vs `.toggle()`: lead with `.toggle()`** as the star
  (show/hide is its killer use); add/remove mentioned as the manual version.
- **String building: teach `+` concatenation first** (simple mental model — "glue strings"),
  then immediately upgrade to template literals (`` `${}` ``) and use those going forward.
- **`console.log()`: moved up to Session 1.** Originally parked in the review lesson; it should
  be a Day 1 debugging tool.
- **The original 4.6 Review lesson: absorbed.** Session 2's game reuses all of Session 1's
  input/output skills, so the second session doubles as the review.

Nothing else is cut — the conditional family (orig. 4.3 / 4.4 / 4.5) is the real meat and stays intact.

---

## Two memorable "gotcha" moments (keep these)

These turn confusing syntax into stories students retell. Build the lessons around them.

1. **`"7" + "7"` = `"77"` (Session 1).** Surface this with a tiny two-number adder before the
   main project. Let them be confused that adding two number inputs gives `"77"` instead of `14`,
   *then* fix it with `Number()`. The surprise is what makes `Number()` stick.
2. **The "everyone gets an A" bug (Session 2).** When teaching `if / else if / else` ranges,
   deliberately write the grade checker with conditions in the wrong order so every score
   returns an A, then fix it by ordering high-to-low. Teaches why condition order matters.

---

# Session 1 — Input & Output

### "Make the page react to me"

**Duration:** ~2 hours
**Big idea:** JavaScript can read what the user types and write something back to the page.

**Concepts covered:** `let` variables, `console.log()`, `document.querySelector()`,
`addEventListener("click", …)`, the `.value` property, the `.innerHTML` property,
strings & string literals, `+` concatenation, template literals (`` `${}` ``),
`Number()` and type conversion.

**Project anchor:** a **Mad Libs Generator** — several labeled inputs, a "Generate Story" button,
and a silly story that prints to the page. It's social (students read results aloud) and it
exercises every Session 1 concept except the `Number()` gotcha, which gets its own warm-up.

### Block-by-block plan

**Block 0 — Hook (5 min)**
- Demo the finished Mad Libs so students see the destination.

**Block 1 — JS basics + first variable (~15 min)**
- *Slides:* Where JS lives (a `<script>` tag / file). What a variable is. The `let` keyword.
  What `console.log()` does and where to find the console (DevTools).
- *We Do:* Declare a couple of `let` variables, `console.log()` them, open the console together.
- *You Do:* Students declare their own variable and log it.

**Block 2 — Reaching into the page (~25 min)**
- *Slides:* The DOM as "the page JS can touch." `document.querySelector()` to grab an element.
  `.addEventListener("click", …)` to run code when something happens.
- *We Do:* Grab a button, add a click listener that `console.log`s "clicked!", confirm in console.
- *You Do:* Students wire a second button to log a different message.

**Block 3 — Reading & writing (~20 min)**
- *Slides:* The `.value` property (read what's in an input). The `.innerHTML` property
  (write content into an element).
- *We Do:* Read one text input's `.value` on click and write a greeting into an output element
  via `.innerHTML`.
- *You Do:* Students read a different input and display it somewhere else on the page.

**Block 4 — Strings (~20 min)**
- *Slides:* Strings & quotes. `+` concatenation. Then template literals (`` `${}` ``) as the
  cleaner upgrade — use these going forward.
- *We Do:* Combine two inputs into one sentence, first with `+`, then rewrite with a template literal.
- *You Do:* Students build a three-part sentence from inputs using a template literal.

**Block 5 — The `Number()` gotcha (~10 min)**
- *Slides:* Strings vs. numbers. Why input values are always strings. `Number()` to convert.
- *We Do (the gotcha):* A two-input "adder" that shows `"7" + "7"` = `"77"`; fix with `Number()`
  so it returns `14`.
- *You Do:* Students convert and add a different pair of number inputs.

**Block 6 — Build: Mad Libs (~25 min, mostly You Do)**
- See full project spec below. Students assemble the complete story; instructor circulates.

### Project spec — Mad Libs Generator

**Suggested HTML scaffold (Claude Code to build):**
- A heading and short instructions.
- Labeled text inputs, e.g. ids: `name`, `adjective`, `noun`, `verb`, `place`, `number`.
- A "Generate Story" button (id `generate`).
- An empty output element (id `story`) where the finished paragraph appears.
- Reuse existing CSS classes; one `hidden` class available for show/hide if useful.

**We Do (instructor-guided portion):**
- Select the button and add a click listener.
- Read 2–3 inputs with `.value`, store in `let` variables, `console.log` them to inspect.
- Assemble a *first sentence* with a template literal and write it to `#story` via `.innerHTML`.

**You Do (independent portion):**
- Read the remaining inputs.
- Build the full multi-sentence story with template literals.
- Display the complete story in `#story`.

**Concepts exercised:** `querySelector`, `addEventListener`, `.value`, `.innerHTML`, `let`,
template literals, `console.log`.

**Stretch goals (for fast finishers):**
- Show a friendly message in `#story` if any input is left blank.
- Add a "Clear" button that empties the inputs and the story.
- Incorporate the `number` input into the story using `Number()`.

---

# Session 2 — Logic & Dynamic Content

### "Make the page think"

**Duration:** ~2 hours
**Big idea:** JavaScript can make decisions and generate/reveal content based on conditions.

**Concepts covered:** booleans (`true`/`false`), comparison operators
(`<` `>` `<=` `>=` `===` `!==`), `if / else`, `if / else if / else` chains and ranges,
logical operators `&&` and `||` (with parentheses for grouping), `alert()`,
`Math.random()`, `Math.floor()`, `classList.toggle()`, and `createElement()` +
`appendChild()` (stretch). Reinforces `.value`, `Number()`, `.innerHTML`, and events from Session 1.

**Project anchor:** a **Number Guessing Game** — the computer picks a secret number, the player
guesses, and the page responds "too high / too low / you got it!" It's the perfect capstone:
every Session 2 concept converges in it, and it's genuinely competitive and fun.

### Block-by-block plan

**Block 0 — Hook (5 min)**
- Demo the finished guessing game.

**Block 1 — Booleans & comparisons (~15 min)**
- *Slides:* `true`/`false`. The operators `<` `>` `<=` `>=` `===` `!==`. What a comparison evaluates to.
- *We Do:* `console.log` a few comparisons together and read the boolean results.
- *You Do:* Students predict-then-check the results of several comparisons.

**Block 2 — if / else (~15 min)**
- *Slides:* Branching. `if (condition) { … } else { … }`. `alert()` as quick feedback.
- *We Do:* A simple "is this number big?" check that alerts one of two messages.
- *You Do:* Students write an if/else that reacts to a different input.

**Block 3 — if / else if / else + ranges (~15 min)**
- *Slides:* Chaining conditions. Handling ranges (e.g., grade bands). **Why order matters.**
- *We Do (the gotcha):* A grade checker written in the *wrong* order so everyone gets an A;
  fix by ordering high-to-low.
- *You Do:* Students write a correctly ordered range check (e.g., temperature → hot/warm/cold).

**Block 4 — && and || (~15 min)**
- *Slides:* `&&` (all true) and `||` (at least one true). Parentheses for grouping.
- *We Do:* A check combining two conditions (e.g., "valid if number is `>= 1 && <= 100`").
- *You Do:* Students write a compound condition of their own.

**Block 5 — Randomness (~10 min)**
- *Slides:* `Math.random()` (0–1 decimal) and `Math.floor()` (round down); combine to pick a
  whole number in a range.
- *We Do:* Generate a random number 1–100 together and `console.log` it.
- *You Do:* Students generate a random number in a different range.

**Block 6 — Build: Guessing Game (~30 min, mostly You Do)**
- See full project spec below. The big convergence; instructor circulates.

**Block 7 — Dynamic DOM + reveal (~15 min)**
- *Slides:* `classList.toggle()` to show/hide a styled panel (ties back to their CSS).
  `createElement()` + `appendChild()` to add new elements (stretch).
- *We Do:* Reveal a hidden "You win!" panel with `classList.toggle()` when the guess is correct.
- *You Do / Stretch:* Append each guess to a running history list with `createElement` + `appendChild`.

### Project spec — Number Guessing Game

**Suggested HTML scaffold (Claude Code to build):**
- A heading and instructions ("Guess a number between 1 and 100").
- A number input (id `guess`) and a "Guess" button (id `submit`).
- A feedback message element (id `feedback`).
- A guess-count display (id `count`).
- A hidden win panel (id `win-panel`) with a `hidden` CSS class applied by default.
- A "New Game" button (id `reset`).
- Optional: an empty list element (id `history`) for the stretch goal.

**We Do (instructor-guided portion):**
- On load, pick the secret number with `Math.floor(Math.random() * 100) + 1` and store it.
- `console.log` the secret number (teaching moment: how/why developers peek during testing).
- Wire the submit button: read `#guess` `.value`, convert with `Number()`.
- Write the *win case* first: if the guess `===` the secret, show a success message in `#feedback`.

**You Do (independent portion):**
- Add the "too high" / "too low" branches with `if / else if / else`.
- Validate the input is in range using `&&` (e.g., between 1 and 100); show a nudge if not.
- Increment and display the guess count in `#count`.
- Reveal `#win-panel` with `classList.toggle()` on a correct guess.

**Concepts exercised:** comparison operators, `if / else if / else`, `&&` / `||`,
`Math.random` / `Math.floor`, `classList.toggle`, `.value`, `Number()`, `.innerHTML`, events.

**Stretch goals (for fast finishers):**
- Append each guess to `#history` with `createElement` + `appendChild`.
- Add a "you're very close" hint when the guess is within 5 of the secret (uses `&&` / `||`).
- Make "New Game" reset the secret number, count, feedback, and re-hide the win panel.
- Disable further guessing once the player wins.

---

## Concept coverage map

| Concept | Session |
|---|---|
| `let`, variables | 1 |
| `console.log()` | 1 (used throughout 2) |
| `querySelector()` | 1 (reused in 2) |
| `addEventListener` (click) | 1 (reused in 2) |
| `.value` | 1 (reused in 2) |
| `.innerHTML` | 1 (reused in 2) |
| Strings, `+`, template literals | 1 |
| `Number()` / type conversion | 1 (reused in 2) |
| booleans + comparison operators | 2 |
| `if / else` | 2 |
| `if / else if / else` + ranges | 2 |
| `&&`, `||` | 2 |
| `alert()` | 2 |
| `Math.random()`, `Math.floor()` | 2 |
| `classList.toggle()` | 2 |
| `createElement` + `appendChild` | 2 (stretch) |

---

## Open questions / things to decide together

- Do we want Claude Code to generate the slides too, or just the code artifacts?
- Should the Mad Libs warm-up "adder" be its own mini-file, or folded into the Mad Libs page?
- How much CSS polish do we want on the starters vs. leaving it plain?
- Is there a homework / take-home extension, or does the day stand alone?
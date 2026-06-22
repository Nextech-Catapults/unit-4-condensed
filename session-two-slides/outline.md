# Session 2 — Slide Outline

## Logic & Dynamic Content · "Make the Page Think"

A slide-by-slide outline for the Session 2 presentation. Each slide lists what's **on screen**
(keep it sparse — one idea per slide), **presenter notes** (what you do), and **talking points**
(roughly what you say). Code examples on slides are generic illustrations, *not* the guessing-game
project code — that stays in the editor so the project isn't spoiled.

**Pacing:** This is the heavier of the two sessions (the whole conditional family + the game + the
DOM reveal). Move briskly through slides and protect the build time. "→ TO THE EDITOR" dividers
mark every handoff; the matching We Do / You Do specs live in the curriculum doc.

---

### Slide 1 — Title

**On screen:**
- "JavaScript, Session 2"
- "Make the Page Think"

**Presenter notes:** Settle the room, confirm everyone has their editor and last session's files.

**Talking points:**
- "Last time the page reacted to you. Today it makes decisions — and we'll build a game on top of them."

---

### Slide 2 — What we're building today

**On screen:**
- "Today's build: a Number Guessing Game"
- "→ live demo"

**Presenter notes:** Play the finished game live. Guess wrong on purpose to show the "too high /
too low" feedback, then win to show the reveal. Make it a little competitive.

**Talking points:**
- "The computer picks a secret number, you guess, and it tells you higher or lower until you nail it."
- "Every new idea today is a piece of this game."

---

### Slide 3 — Recap: the tools we keep

**On screen:**
- `querySelector` · `addEventListener`
- `.value` · `.innerHTML` · `Number()`

**Presenter notes:** Fast. Remind them these come back today — this session doubles as review.

**Talking points:**
- "Everything from last session still applies: grab elements, react to clicks, read inputs, write output."
- "Today we add the missing piece — decisions."

---

### Slide 4 — Booleans: `true` / `false`

**On screen:**
- "A boolean is one of two values: `true` or `false`."
- `let isWinner = true;`

**Presenter notes:** Tiny concept, big payoff. Frame booleans as yes/no answers.

**Talking points:**
- "A boolean is just yes or no — `true` or `false`. It's how code answers a question."
- "Decisions are built on questions that come back true or false."

---

### Slide 5 — Comparison operators

**On screen:**
- `<` `>` `<=` `>=`
- `===` (equal) · `!==` (not equal)
- `5 > 3` → `true`

**Presenter notes:** Call out `===` specifically — three equals for "is equal to." Note it gives
back a boolean.

**Talking points:**
- "These compare two values and hand back a boolean."
- "Watch the equals: `===` asks *is this equal?* It's a question, not an assignment like the single `=` from last session."

---

### Slide 6 — → TO THE EDITOR: predict the comparison

**On screen:**
- "Your turn (with me)"
- "Guess the result, then log it"

**Presenter notes:** Run **Block 1 We Do / You Do**. Log a few comparisons together; students
predict-then-check several on their own.

**Talking points:**
- "Predict true or false *before* you run each one. Then log it and see if you were right."

---

### Slide 7 — Making decisions: `if / else`

**On screen:**
- ```
  if (score > 10) {
    // do this
  } else {
    // otherwise this
  }
  ```

**Presenter notes:** Read it as plain English. The condition in parentheses is one of those
true/false questions from the last block.

**Talking points:**
- "*If this is true, run the first block; otherwise, run the else block.* That's it."
- "The thing in parentheses is a question that comes back true or false."

---

### Slide 8 — Quick feedback: `alert()`

**On screen:**
- `alert("You did it!");`
- "Pops a message box"

**Presenter notes:** Useful, slightly annoying, good for quick feedback while learning. Mention
we'll often prefer writing to the page instead.

**Talking points:**
- "`alert` throws a popup. Handy for quick feedback — though for the real game we'll write to the page like last time."

---

### Slide 9 — → TO THE EDITOR: if / else

**On screen:**
- "Your turn (with me)"
- "React differently based on a number"

**Presenter notes:** Run **Block 2 We Do / You Do**. Build a simple "is this big?" check that
alerts one of two messages; students write their own if/else on a different input.

**Talking points:**
- "One condition, two outcomes. Get it branching, then make it react to your own input."

---

### Slide 10 — More than two paths: `if / else if / else`

**On screen:**
- ```
  if (score >= 90) { ... }
  else if (score >= 80) { ... }
  else { ... }
  ```
- "Checks in order, top to bottom. First true one wins."

**Presenter notes:** Stress: it stops at the first match. This sets up the gotcha on the next slide.

**Talking points:**
- "Now we can have many paths. It checks each condition in order and runs the *first* one that's true, then stops."
- "That phrase — *first one that's true* — is about to matter a lot."

---

### Slide 11 — The gotcha: order matters

**On screen:**
- "Bug: everyone gets an A?!"
- (wrong order) `if (score >= 60) ... else if (score >= 90) ...`
- "Fix: check highest first"

**Presenter notes:** Show the wrong-order version giving an A to a 95 *and* a 65 — actually run it.
Let them spot why. Then reorder high-to-low and re-run.

**Talking points:**
- "If we check `>= 60` first, a 95 matches it immediately — and never reaches the A check. Everyone passes as the lowest grade."
- "Fix: order your conditions from most-specific/highest down. Order is part of the logic."

---

### Slide 12 — → TO THE EDITOR: ranges done right

**On screen:**
- "Your turn (with me)"
- "Build a correctly ordered range check"

**Presenter notes:** Run **Block 3 We Do / You Do**. Fix the grade checker together; students build
their own ordered range check (e.g., temperature → hot / warm / cold).

**Talking points:**
- "Write a range check and get the order right. Test the boundaries — the edges are where bugs hide."

---

### Slide 13 — Combine conditions: `&&` and `||`

**On screen:**
- `&&` = AND (all must be true)
- `||` = OR (at least one true)
- `age >= 13 && age <= 19`

**Presenter notes:** Give a human example for each — "tall AND fast" vs. "cash OR card."

**Talking points:**
- "`&&` means *both* have to be true. `||` means *at least one* is enough."
- "`age >= 13 && age <= 19` is how you check 'is this a teenager' — inside a range."

---

### Slide 14 — Group with parentheses

**On screen:**
- `(a && b) || c`
- "Parentheses make the grouping clear."

**Presenter notes:** Keep light. Mostly: when in doubt, parenthesize for readability.

**Talking points:**
- "When you mix AND and OR, use parentheses so both you and the computer agree on what groups together."

---

### Slide 15 — → TO THE EDITOR: compound condition

**On screen:**
- "Your turn (with me)"
- "Write a condition with `&&` or `||`"

**Presenter notes:** Run **Block 4 We Do / You Do**. Build a range/validity check together (e.g.,
"valid if `>= 1 && <= 100`"); students write their own compound condition.

**Talking points:**
- "Combine two checks into one. This is exactly how we'll validate guesses in the game."

---

### Slide 16 — Randomness: `Math.random()`

**On screen:**
- `Math.random()` → a decimal from 0 up to 1
- e.g. `0.4817…`

**Presenter notes:** Show a couple of runs so they see it changes. It's a decimal — not yet what we want.

**Talking points:**
- "`Math.random()` gives a random decimal between 0 and 1. Useful, but we want a whole number."

---

### Slide 17 — Whole numbers: `Math.floor()`

**On screen:**
- `Math.floor(4.9)` → `4` (rounds down)
- `Math.floor(Math.random() * 100) + 1` → 1–100

**Presenter notes:** Walk the formula left to right once. Don't over-derive it — give them the
recipe and the intuition.

**Talking points:**
- "`Math.floor` chops off the decimal — always rounds down."
- "Multiply the random decimal by 100, floor it, add 1, and you've got a whole number from 1 to 100. That's our secret number."

---

### Slide 18 — → TO THE EDITOR: random number

**On screen:**
- "Your turn (with me)"
- "Generate a random whole number"

**Presenter notes:** Run **Block 5 We Do / You Do**. Generate a 1–100 number and log it; students
generate one in a different range.

**Talking points:**
- "Make a random number and log it a few times to prove it changes. Now we have everything the game needs."

---

### Slide 19 — Project: build the Guessing Game

**On screen:**
- "Now build it: Number Guessing Game"
- We Do: pick the secret · read & convert the guess · the win case
- You Do: too high / too low · validate range · count guesses
- "Stretch: history list · 'very close' hint · New Game reset"

**Presenter notes:** Start with the **Block 6 We Do** together — pick the secret with `Math.random`,
`console.log` it (teaching moment: developers peek while testing), wire the button, read + `Number()`
the guess, write the win case. Then release them to the **You Do** and circulate. Keep stretch goals
on screen.

**Talking points:**
- "We'll wire up the skeleton together — secret number, read the guess, handle a win."
- "Then you add the higher/lower feedback, validate the range with `&&`, and count the guesses. Log the secret while testing so you can check your logic."

---

### Slide 20 — Reveal the win: `classList.toggle()`

**On screen:**
- `panel.classList.toggle("hidden")`
- "Show/hide by flipping a CSS class"

**Presenter notes:** Tie straight to their CSS knowledge — they already know what a class does.
Use it to reveal a hidden "You win!" panel.

**Talking points:**
- "You already know CSS classes. `classList.toggle` flips one on or off from JavaScript."
- "Hide a 'You win!' panel with a class, then toggle it off when they guess right. Instant reveal."

---

### Slide 21 — Build elements on the fly (stretch)

**On screen:**
- `document.createElement("li")`
- `list.appendChild(item)`
- "Make new elements and add them to the page"

**Presenter notes:** This is the stretch concept. Frame as optional power-up — keeps fast finishers
busy without blocking the core build.

**Talking points:**
- "Want to show every past guess? `createElement` makes a new element, `appendChild` drops it onto the page."
- "This one's a stretch — reach for it if you've got the core game working."

---

### Slide 22 — → TO THE EDITOR: reveal + history

**On screen:**
- "Your turn (with me / on your own)"
- "Reveal the win panel · (stretch) log guesses"

**Presenter notes:** Run **Block 7**. Reveal the win panel together with `classList.toggle`; release
the `createElement`/`appendChild` history list as stretch/independent.

**Talking points:**
- "Add the win reveal so finishing feels good. Then, if you're ahead, build the guess history."

---

### Slide 23 — Recap: what you can now do

**On screen:**
- Ask true/false questions · branch with if / else / else if
- Combine conditions with `&&` / `||`
- Generate randomness · show, hide, and build elements

**Presenter notes:** Let a few students demo their game. Celebrate — they built something real
in two sessions.

**Talking points:**
- "You can now make a page that reads input, makes decisions, and changes itself. That's a real program."
- "Same building blocks scale up to basically every app you use."

---

### Slide 24 — Wrap-up

**On screen:**
- "You built a game."
- (optional) where to go next / resources

**Presenter notes:** Close on the win. If there's a take-home or next unit, point to it here.

**Talking points:**
- "Two sessions ago you had a static page. Now you've shipped an interactive game. Nice work."
# Session 1 — Slide Outline

## Input & Output · "Make the Page React"

A slide-by-slide outline for the Session 1 presentation. Each slide lists what's **on screen**
(keep it sparse — one idea per slide), **presenter notes** (what you do), and **talking points**
(roughly what you say). Code examples on slides are generic illustrations, *not* the Mad Libs
project code — that stays in the editor so the project isn't spoiled.

**Pacing:** Slide blocks are short. The real time is in the editor (We Do / You Do). Aim to spend
more time coding than presenting. "→ TO THE EDITOR" dividers mark every handoff; the matching
We Do / You Do specs live in the curriculum doc.

---

### Slide 1 — Title

**On screen:**
- "JavaScript, Session 1"
- "Make the Page React"
- Your name / course

**Presenter notes:** Hold here while everyone gets settled and has their editor open.

**Talking points:**
- "You already know how to build a page with HTML and style it with CSS. Today the page starts *doing* things."
- "By the end of this session you'll have built something you can show off."

---

### Slide 2 — What we're building today

**On screen:**
- "Today's build: a Mad Libs generator"
- A screenshot or the words "→ live demo"

**Presenter notes:** Switch to the finished Mad Libs and actually play it — type in a few words,
hit the button, read the silly result out loud. This is the hook; let them laugh.

**Talking points:**
- "Here's where we're headed. You type words in, hit a button, and it builds a story."
- "Everything we learn today is a piece of making this work. Keep this in your head as the goal."

---

### Slide 3 — The three languages of the web

**On screen:**
- HTML → structure (the skeleton)
- CSS → style (the looks)
- JavaScript → behavior (the actions)

**Presenter notes:** Anchor JS to what they already know. Point at each line.

**Talking points:**
- "HTML is the bones, CSS is the outfit. JavaScript is what makes it *move*."
- "When a page reacts to a click, counts something, or changes after you type — that's JavaScript."

---

### Slide 4 — Where JavaScript lives

**On screen:**
- "JS runs in the browser"
- `<script>` ... `</script>`
- "Open DevTools to see it work"

**Presenter notes:** Show where the `<script>` sits in the starter file and how to open DevTools
(right-click → Inspect, or F12). Don't dwell — just orient them.

**Talking points:**
- "Your JavaScript lives in a script tag, the same way your CSS lived in a style tag or file."
- "The browser reads it top to bottom. We'll watch it run using a tool called the console."

---

### Slide 5 — Variables: `let`

**On screen:**
- "A variable is a labeled box for a value."
- `let score = 5;`
- `let playerName = "Sam";`

**Presenter notes:** Emphasize naming + the semicolon. Don't over-explain types yet.

**Talking points:**
- "A variable is just a name for a value so we can use it later. `let` creates one."
- "Read it right to left: take the value 5, put it in a box, label the box `score`."
- "Names should describe what's inside — `score`, not `x`."

---

### Slide 6 — `console.log()`: your window into the code

**On screen:**
- "See what your code is doing."
- `console.log(score);`
- "→ shows in DevTools console"

**Presenter notes:** This is the most important debugging habit. Sell it. They'll use it all day.

**Talking points:**
- "`console.log` prints a value to the console so *you* can see it — the user never does."
- "Whenever something isn't working, your first move is: log it and look."

---

### Slide 7 — → TO THE EDITOR: variables & logging

**On screen:**
- "Your turn (with me)"
- "Declare a variable. Log it."

**Presenter notes:** Run the **Block 1 We Do / You Do** from the curriculum doc. Have everyone
declare a `let`, `console.log` it, and open the console to confirm. Walk the room.

**Talking points:**
- "Make a variable, log it, and open the console to prove it ran. Raise a hand if you don't see it."

---

### Slide 8 — The DOM: the page JavaScript can touch
Document Object Model

**On screen:**
- "DOM = your HTML, as objects JS can grab and change"
- Simple sketch: page → elements JS can reach

**Presenter notes:** Keep it concrete. "DOM" is jargon; define it once and move on.

**Talking points:**
- "Every element on your page — buttons, inputs, divs — is something JavaScript can reach into and change."
- "We just need a way to point at the one we want."

---

### Slide 9 — Grab an element: `querySelector()`

**On screen:**
- `document.querySelector("#myButton")`
- "Uses the same selectors as CSS (`#id`, `.class`)"

**Presenter notes:** The CSS-selector connection is the key unlock — lean on it hard.

**Talking points:**
- "Good news: you already know selectors. This works exactly like CSS — `#id` for an id, `.class` for a class."
- "We usually store the grabbed element in a variable so we can use it more than once."

---

### Slide 10 — Do something on an event: `addEventListener`

**On screen:**
- `button.addEventListener("click", () => { ... });`
- "When X happens, run this code."

**Presenter notes:** Don't explain arrow-function internals — frame it as "the code that runs."
Read it as a sentence.

**Talking points:**
- "Read it out loud: *when the button gets a click, run the code in the braces.*"
- "The stuff in the curly braces is what happens. That's where our action goes."

---

### Slide 11 — → TO THE EDITOR: make a button do something

**On screen:**
- "Your turn (with me)"
- "Click a button → log a message"

**Presenter notes:** Run **Block 2 We Do / You Do**. Grab a button, log "clicked!" on click,
confirm in console, then students wire a second button.

**Talking points:**
- "Get a click to print something to the console. Once you see it fire, you've got the core of JavaScript."

---

### Slide 12 — Read what the user typed: `.value`

**On screen:**
- `let typed = input.value;`
- "`.value` = the current contents of an input"

**Presenter notes:** Pair this directly with the next slide — read then write.

**Talking points:**
- "`.value` reaches into an input box and hands you whatever's typed there, as text."

---

### Slide 13 — Write to the page: `.innerHTML`

**On screen:**
- `output.innerHTML = "Hello!";`
- "`.innerHTML` = the content inside an element"

**Presenter notes:** Show that setting it *replaces* what's there. Reading `.value` + writing
`.innerHTML` is the whole input→output loop.

**Talking points:**
- "`.value` reads *from* an input. `.innerHTML` writes *into* an element on the page."
- "Put those two together and you can take what someone types and show it back. That's the loop behind today's project."

---

### Slide 14 — → TO THE EDITOR: read & display

**On screen:**
- "Your turn (with me)"
- "Read an input → show it on the page"

**Presenter notes:** Run **Block 3 We Do / You Do**. On click, read one input's `.value` and write
a greeting to an output element; then students display a different input elsewhere.

**Talking points:**
- "On click, grab the input's value and drop it into the page. You just made the page respond to a human."

---

### Slide 15 — Strings: text in quotes

**On screen:**
- `"hello"` · `'world'`
- "Text values are called strings."

**Presenter notes:** Quick. They've seen strings already in `.value`. Just name it.

**Talking points:**
- "Any text in quotes is a string. Single or double quotes, your choice — just be consistent."

---

### Slide 16 — Glue strings together: `+`

**On screen:**
- `"Hello, " + name + "!"`
- "`+` joins strings"

**Presenter notes:** Show how spaces have to be added on purpose. This sets up *why* template
literals are nicer.

**Talking points:**
- "The plus sign joins strings end to end. Watch the spaces — you have to put them inside the quotes yourself."
- "This works, but it gets fiddly fast. There's a cleaner way…"

---

### Slide 17 — The upgrade: template literals

**On screen:**
- `` `Hello, ${name}!` ``
- "Backticks + `${ }` to drop variables in"

**Presenter notes:** Point out the backtick key (top-left). Contrast directly with the `+` version
from the previous slide — same result, easier to read.

**Talking points:**
- "Backticks instead of quotes, and `${}` lets you drop a variable right inside the text."
- "Same sentence as the last slide, way easier to read. From here on, we use these."

---

### Slide 18 — → TO THE EDITOR: build a sentence

**On screen:**
- "Your turn (with me)"
- "Combine inputs into one sentence"

**Presenter notes:** Run **Block 4 We Do / You Do**. Build a sentence with `+`, rewrite it as a
template literal, then students build a three-part sentence from inputs.

**Talking points:**
- "Build it once the clunky way, then upgrade it. Notice how much cleaner the second version is."

---

### Slide 19 — Strings vs. numbers

**On screen:**
- `"7"` is text · `7` is a number
- "Inputs always give you text — even digits."

**Presenter notes:** Set the trap before you spring it. Plant the idea that `.value` is *always*
a string.

**Talking points:**
- "Here's something sneaky: anything from an input comes back as a *string*, even if it looks like a number."
- "Quotes around it mean it's text. Watch what that does next…"

---

### Slide 20 — The gotcha

**On screen:**
- `"7" + "7"` → ?
- (reveal) → `"77"`

**Presenter notes:** Ask them to predict *before* revealing. Let them say "14." Then reveal "77"
and enjoy the confusion — this is the memorable moment.

**Talking points:**
- "Quick — what's `"7" + "7"`? … Most people say 14. It's actually `"77"`."
- "Because they're strings, `+` *glues* them instead of adding. The computer did exactly what we told it."

---

### Slide 21 — `Number()` to the rescue

**On screen:**
- `Number("7") + Number("7")` → `14`
- "Convert text → number before doing math."

**Presenter notes:** Now resolve the tension. Emphasize: convert *before* arithmetic.

**Talking points:**
- "`Number()` turns the text `"7"` into the actual number 7. Now `+` adds like we expected."
- "Rule of thumb: if you're doing math on something from an input, wrap it in `Number()` first."

---

### Slide 22 — → TO THE EDITOR: the adder gotcha

**On screen:**
- "Your turn (with me)"
- "Add two number inputs — fix the bug"

**Presenter notes:** Run **Block 5 We Do / You Do**. Build the two-input adder, watch it produce
"77", fix with `Number()`, then students convert and add a different pair.

**Talking points:**
- "Reproduce the bug on purpose, then fix it. Now you'll recognize it forever."

---

### Slide 23 — Project: build the Mad Libs

**On screen:**
- "Now build it: Mad Libs Generator"
- Checklist: read inputs · build the story · show it
- "Stretch: blank-input message · Clear button · use the number"

**Presenter notes:** This is the **Block 6 You Do**. Point them to the starter file. Read the
project checklist, then circulate. Keep stretch goals visible for fast finishers so you're not
re-explaining one at a time.

**Talking points:**
- "Everything you need is on the walls now. Read every input, build the story with template literals, show it on the page."
- "Stuck? Log the value and look. Done early? Try a stretch goal."

---

### Slide 24 — Recap: what you can now do

**On screen:**
- Grab elements · react to clicks
- Read inputs · write to the page
- Build text with template literals · convert with `Number()`

**Presenter notes:** Quick confidence check. Let a couple of students demo their Mad Libs if time.

**Talking points:**
- "Two hours ago this was a static page. Now it reads input and writes output — that's the heart of every app you use."
- "Next session we make the page *think*: making decisions, and a game built on them."

---

### Slide 25 — (Optional) Bridge to Session 2

**On screen:**
- "Next: Make the Page Think"
- "→ a number guessing game"

**Presenter notes:** Optional teaser if you're wrapping with time to spare.

**Talking points:**
- "Same input/output skills, plus logic. We'll build a guessing game you'll actually want to beat."
[← back to the README](../README.md)

# The JavaScript you actually need

JavaScript is huge. **You need about seven things this week**, and every one of them is already in your `index.html` — so this page teaches them from your own code rather than from made-up examples.

Read this before Wednesday. It's the difference between filling in `addPoints` by trial and error and actually knowing what you're doing.

*Already written some JavaScript? Skip to [Going further](going-further.md) — this page is for a standing start.*

---

## 1. A variable — a named box with something in it

```js
let currentQuestion = 0;
```

"Make a box called `currentQuestion` and put `0` in it." Later the code says `currentQuestion = currentQuestion + 1` — take what's in the box, add one, put it back.

You'll see two words for this:

- **`let`** — the value will change later (`currentQuestion` counts up as you answer)
- **`const`** — it won't (`QUESTIONS` is your list and stays your list)

If you're unsure, use `const`. If the code complains that you can't reassign it, change it to `let`.

## 2. An array — a numbered list

Square brackets. Your `QUESTIONS` is one:

```js
const QUESTIONS = [ firstQuestion, secondQuestion, thirdQuestion ];
```

Counting starts at **0**, not 1. So `QUESTIONS[0]` is the first question. This trips up everyone at first and then never again.

`QUESTIONS.length` is how many there are. That's how the code knows when you've run out of questions.

## 3. An object — a labelled thing

Curly brackets, with `label: value` pairs. One of your questions is an object:

```js
{
  q: "It's Friday, 8pm. Where are you?",
  answers: [ ... ],
}
```

An array is *"a list of things"*. An object is *"one thing, with named parts"*. Your quiz is an array of objects — a list of questions, each with a text and some answers.

**Reach into an object with a dot:** `question.q` means "the `q` part of `question`". You'll see this everywhere.

## 4. A function — instructions with a name

```js
function showQuestion() {
  ...
}
```

That defines it. Nothing happens until something *calls* it by writing `showQuestion()` with the brackets. The very last line of your file is `showQuestion();` — that's what starts the quiz.

Functions can take information in. `showPicture(questionImage, question.image)` hands two things over for it to work with.

## 5. A loop — do this for each one

```js
for (let i = 0; i < question.answers.length; i++) {
  ...
}
```

"Start `i` at 0, keep going while `i` is less than the number of answers, add one each time." The code inside runs once per answer — which is how three answers become three buttons without you writing the button code three times.

There's a second kind you'll need on Wednesday:

```js
for (const id in points) { ... }
```

That one walks through the *labels* of an object. For `{ chaos: 2, calm: 1 }` it gives you `"chaos"`, then `"calm"`.

## 6. An if — do this only when

```js
if (currentQuestion < QUESTIONS.length) {
  showQuestion();     // still questions left
} else {
  showResult();       // that was the last one
}
```

Reads exactly how it sounds. Note `===` means "is equal to" when you're *asking*, while a single `=` means "put this in the box". Using `=` where you meant `===` is a classic bug.

## 7. An event — run this when someone does something

```js
button.addEventListener("click", function () {
  chooseAnswer(answer);
});
```

"When this button is clicked, run this." Nothing happens at the moment that line runs — it's setting a trap for later. That's the bit that feels strange at first: your code finishes, and then sits waiting.

---

## Ignore all of this for now

Genuinely not needed this week, and every one of them is a rabbit hole: classes, `async`/`await`, promises, `fetch`, modules, arrow functions (`=>`), `map`/`filter`/`reduce`, TypeScript, frameworks.

If Claude gives you any of them, say *"simpler, I've only learned variables, arrays, objects, functions, loops, ifs and events"*.

---

## Going deeper

Optional. Do it after Wednesday, when the concepts have somewhere to land — a course watched cold on Monday mostly evaporates.

**Video** — [JavaScript Course for Beginners](https://www.youtube.com/watch?v=W6NZfCO5SIk) (Programming with Mosh). Gentle, clear, well paced. Stop when you hit things from the ignore list.

**Longer video** — [JavaScript Crash Course For Beginners](https://www.youtube.com/watch?v=hdI2bqOjy3c) (Traversy Media). More thorough, covers the same ground and then some.

**To look things up** — [javascript.info](https://javascript.info/first-steps) is the best written tutorial there is, and [MDN](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting) is the reference professionals actually use. Neither is meant to be read cover to cover. Search them when you hit a word you don't know.

---

## The fastest way to learn any of this

Open your own file, pick a line you don't understand, and ask:

> *"Explain this line like I've never seen code before: [paste the line]"*

Then change it, save, reload, and see what breaks. You can always [discard changes](saving-your-work.md). Breaking things on purpose and putting them back is the whole job.

---

**Next:** [how the code works](how-the-code-works.md) · [working with Claude](using-claude.md)

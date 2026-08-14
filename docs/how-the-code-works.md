[← back to the README](../README.md)

# How the code works

Everything lives in `index.html`. Open it in VS Code and you'll find labelled sections.

| Section | What it is | Do you edit it? |
|---|---|---|
| `<style>` | Colours, spacing, fonts | Yes — Monday and Thursday |
| `<body>` | The boxes that hold things | Rarely |
| `1. YOUR CONTENT` | Your questions and results | Yes — constantly |
| `2. THE ENGINE` | The code that runs the quiz | Wednesday, and read it all week |

The split that matters is the last two. **Your content is data — a list of questions, a list of results.** The engine is code that works with whatever data you give it. Change the data and the quiz changes completely without a single line of the engine moving.

That's why you can hand your file to someone else, they swap the two lists, and it's their quiz.

---

## How scoring works

Each answer awards points to one or more result `id`s:

```js
{ text: "Out. Obviously.", points: { chaos: 2, warmth: 1 } }
```

At the end, whichever id has the most points wins. So a result only appears if some answer awards points to its id — **if nothing can score `calm`, nobody ever gets `calm`.** That's the first thing to check when a result never turns up.

The ids in `points` must match the `id` on a result *exactly*. `chaos` and `Chaos` are different things as far as the code is concerned.

---

## The bit that's deliberately missing

`addPoints()` is empty. It's the only unfinished thing in the file, and it's why everybody currently gets the same result — nothing is ever added to the scores, so there's no winner and the code falls back to the first result in the list.

There's a hint above it in the file. That's Wednesday's job.

---

## Following it through

If you want to see how one click becomes a result, read these five functions in this order:

1. `showQuestion()` — draws a question and its buttons
2. `chooseAnswer()` — runs when a button is clicked
3. `addPoints()` — adds that answer's points to the running total *(yours to write)*
4. `highestScoringId()` — finds whichever id ended up highest
5. `showResult()` — swaps the screens over and fills in the result

Ask Claude to walk you through them one at a time rather than all at once.

---

**Next:** [adding images](images.md) · [working with Claude](using-claude.md)

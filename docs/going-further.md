[← back to the README](../README.md)

# Going further

**Finished the day's job early? Start here.** Take whatever looks interesting — there's no order you're supposed to follow and no expectation you'll get through them. Some of these are an afternoon; a couple could eat the week.

If you've written code before, the main week will not stretch you. Do the [Wednesday exercise](how-the-code-works.md) so the engine is yours, then live in this page.

Everything here still respects the rules: one file, nothing to install, no server. The last section deliberately breaks one of them, once you've earned it.

---

## Warm-ups

**Show every result, not just the winner.** You already have the scores. Turn them into a percentage per result and list them under the winner — *"78% Total Menace, 22% Quietly In Control"*. Suddenly the result feels measured rather than declared.

**Answer with the keyboard.** Press `1`, `2`, `3` to pick. One `keydown` listener on `document`. Then ask yourself what happens when a question has four answers.

**Shuffle the questions.** Randomise `QUESTIONS` order on load. Then work out whether that changes anyone's result, and be able to explain why not.

---

## Middling

**Put the result in the URL.** When someone finishes, set `location.hash = "result=chaos"`. Opening that link jumps straight to the result. That turns "copy my result" into a link that actually shows the thing — the reason quizzes spread. No server involved; the URL *is* the storage.

Then handle the awkward part: what should happen if someone edits the hash to a result that doesn't exist?

**Remember they've played.** `localStorage` survives a page reload. Store the last result and greet a returning player with it. Note what this means: your quiz now has state that outlives the tab, and you have to decide when to clear it.

**Weight the questions.** Some questions say more about you than others. Give each one a `weight` and multiply its points. Small change to `addPoints`, meaningful change to the results.

**Fix the tie.** Right now `highestScoringId()` uses `>`, so on an exact tie the first result in the list wins and nobody is told. That's a real bug, not a made-up exercise. Decide what *should* happen — tie-break rule? show both? — and implement it. Then prove it works.

---

## Harder

**Make it properly accessible.** Try using the quiz with only the keyboard, then with VoiceOver (Cmd+F5 on a Mac) and your eyes shut. You'll find things. The result appears with no announcement, images carry `alt=""`, and there's no focus management when the screen swaps. Fix what you find and write down what you did — accessibility work is the most consistently underrated thing on a junior CV.

**Test `addPoints` without clicking.** Add a function that runs a few known inputs through it and logs whether the output is right. No test framework — a handful of `if` statements and `console.log` is a test suite. Then break `addPoints` on purpose and watch your tests catch it.

**Fix the clipboard properly.** `navigator.clipboard` needs a secure context and may do nothing when the page is opened from a `file://` path. Find out whether it works in your browser, and if it doesn't, add a fallback that still lets someone copy their result. Then make the button honest about whether it succeeded, instead of always saying "Copied!".

**Split the data out.** Move `QUESTIONS` and `RESULTS` into `questions.js` and load it with a `<script src>` before the main script. This breaks rule 1 on purpose — you're allowed, once everything works and you can explain why the separation is worth having. Two things to notice: the browser may block it on `file://` depending on how you do it, and your quiz is now two files that must stay in step.

---

## If you want a different project entirely

Same constraints, harder logic: a **knockout bracket**. Sixteen things, vote in pairs, narrows to a winner. You have to track rounds, handle an odd number of entries, and decide what happens on the final. It's a genuinely more interesting problem than a quiz and the same one-file rules apply.

Ask and we'll point you at a starter, or build it from scratch — by that point you'll know enough.

---

## Whatever you pick

Rule 4 still applies. **You have to be able to explain it on Friday.** A clever thing you can't account for is worth less than a simple thing you can.

---

**Next:** [how the code works](how-the-code-works.md) · [the JavaScript you need](javascript-basics.md)

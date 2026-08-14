# Which ___ are you?

A starter for building your own personality quiz, from zero. No installing anything.

**You choose what the quiz is about.** Films, football, Greek gods, crisp flavours, your friend group — genuinely anything. The code is the same either way, and the topic is what makes it yours.

---

## Get started (2 minutes)

1. Green **Code** button at the top of this page → **Download ZIP**
2. Unzip it
3. Double-click `index.html`

It opens in your browser and already works. Answer the two questions and you'll get a result.

To edit it: open `index.html` in a text editor. [VS Code](https://code.visualstudio.com) is free and good. Save, then reload the browser tab to see your change.

---

## The rules

These exist because they keep you unstuck. AI will break all of them if you let it.

1. **One file.** Everything lives in `index.html`. If a fix needs a second file, it's the wrong fix this week.
2. **Nothing to install.** No npm, no Node, no terminal. If an AI tells you to run a command, reply: *"do it without installing anything"*.
3. **No internet data.** No APIs, no databases. Your content is the lists at the top of the file.
4. **You must be able to explain every line.** If you can't, delete it and ask for it again, simpler. This is the one that matters — on Friday you're explaining your code, not demoing it.
5. **Save a copy each evening.** `index-tuesday.html`, and so on. If you break everything tomorrow, you can get back.

---

## Your week

**Monday — make it yours**
Change the title, the teaser, and the `--accent` colour. Rewrite the two questions and two results to be about your topic. Break something on purpose, then fix it.

**Tuesday — fill it out**
Get to six questions and at least three results. Careful with commas: every `}` needs a `,` after it except the last one in a list. When it breaks, that's usually why.

**Wednesday — make the scoring work**
Find `addPoints` in the file. It's deliberately empty, and it's the reason everybody currently gets the same result. There's a hint above it. **This is the day it becomes a real quiz.**

**Thursday — make it look deliberate**
Colours, spacing, type sizes. Try a different accent colour per result. Check it on your phone. Make it something you'd actually send to someone.

**Friday — publish and explain**
Get it online, send the link to five people, watch them use it. Then talk us through how it works for five minutes.

---

## Where the pieces are

Open `index.html` and you'll find three labelled sections:

| Section | What it is | Do you edit it? |
|---|---|---|
| `<style>` | Colours, spacing, fonts | Yes — Monday and Thursday |
| `<body>` | The boxes that hold things | Rarely |
| `1. YOUR CONTENT` | Your questions and results | Yes — constantly |
| `2. THE ENGINE` | The code that runs the quiz | Wednesday, and read it all week |

---

## How scoring works

Each answer awards points to one or more result `id`s:

```js
{ text: "Out. Obviously.", points: { chaos: 2, warmth: 1 } }
```

At the end, whichever id has the most points wins. So a result only ever appears if some answer awards points to its id — if nobody can score `calm`, nobody ever gets `calm`.

---

## When it breaks

It will. That's normal, not a sign you're bad at this.

1. Right-click the page → **Inspect** → **Console** tab. Red text is the error, with a line number.
2. Paste the error into Claude and ask what it means.
3. Still stuck? Ask: *"explain this file line by line, simply"*.

The three that will get you: a missing comma between items, a missing `}`, and a result `id` spelled differently in `QUESTIONS` than in `RESULTS`.

---

## Good prompts

- *"Explain lines 200 to 230 to me line by line, simply."*
- *"That's too complicated — do it more simply, no new files, nothing to install."*
- *"Here's my error: [paste]. What does it mean and where do I look?"*
- *"Don't write the code yet. Tell me what I should try first."*

Bad prompt: *"build me a quiz app"*. You already have one. Ask about the bit you're changing.

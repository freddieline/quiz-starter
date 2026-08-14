# Which ___ are you?

A starter for building your own personality quiz, from zero. Nothing to install except the two apps below.

**You choose what the quiz is about.** Films, football, Greek gods, crisp flavours, your friend group — genuinely anything. The code is the same either way, and the topic is what makes it yours.

---

## Before Monday

**1. Watch this** — [How To Use GitHub For Beginners](https://www.youtube.com/watch?v=a9u2yZvsqHA) (corbin)

It covers more than you need. **This week you only ever use three buttons:** Commit, Push, and Discard changes. Branches, pull requests and merging are all in the video and you can ignore every one of them — we're not using them.

**2. Make a GitHub account** — [github.com/signup](https://github.com/signup). Free. Use a username you'd be happy showing an employer.

**3. Install two things**

- [GitHub Desktop](https://desktop.github.com) — how you get the code and save your work
- [VS Code](https://code.visualstudio.com) — how you edit it

---

## Get your own copy

1. At the top of this page, click the green **Use this template** → **Create a new repository**
2. Name it something yours — `which-taylor-era-are-you`, whatever fits
3. Set it to **Public**, then **Create repository**
4. Open **GitHub Desktop** → **File → Clone repository** → pick the repo you just made → **Clone**
5. Click **Show in Finder** (or Explorer) → double-click `index.html`

It opens in your browser and already works. Answer the two questions and you'll get a result.

To edit: in GitHub Desktop click **Open in Visual Studio Code**. Change something, save, reload the browser tab.

You now own this repo. It's yours to keep and to show people.

---

## Saving your work

At the end of every day, in GitHub Desktop:

1. Bottom left, type what you did — *"added my questions"*, *"made the scoring work"*
2. Click **Commit to main**
3. Click **Push origin** (top bar)

Two minutes. That's the whole thing.

**Ignore the branch dropdown.** Everything goes on `main` this week.

### The button that will save you

**Changes → right-click the file → Discard changes.**

You're going to let Claude edit your file, and at some point it'll change something you didn't want and you won't know what. Discard changes puts the file back to your last commit, instantly. That's why we commit every day — so there's always a recent point to fall back to.

This is the actual reason git exists. It's undo that survives closing your laptop.

---

## The rules

These keep you unstuck. AI will break all of them if you let it.

1. **One file.** Everything lives in `index.html`. If a fix needs a second file, it's the wrong fix this week.
2. **Nothing to install.** No npm, no Node, no terminal commands. If Claude tells you to run a command, say *"do it without installing anything"*.
3. **No internet data.** No APIs, no databases. Your content is the lists at the top of the file.
4. **You must be able to explain every line.** If you can't, delete it and ask for it again, simpler. This is the one that matters — on Friday you're explaining your code, not just demoing it.
5. **Commit at the end of every day.** See above.

---

## Your week

**Monday — make it yours**
Change the title, the teaser, and the `--accent` colour. Rewrite the two questions and two results to be about your topic. Break something on purpose, then use Discard changes to undo it.

**Tuesday — fill it out**
Get to six questions and at least three results. Careful with commas: every `}` needs a `,` after it except the last one in a list. When it breaks, that's usually why.

**Wednesday — make the scoring work**
Find `addPoints` in the file. It's deliberately empty, and it's why everyone currently gets the same result. There's a hint above it. **This is the day it becomes a real quiz.**

**Thursday — make it look deliberate**
Colours, spacing, type sizes. Try a different accent colour per result. Check it on your phone. Make it something you'd actually send to someone.

**Friday — publish and explain**
Put it online, send the link to five people, watch them use it. Then talk us through how it works for five minutes.

---

## Where the pieces are

Open `index.html` and you'll find labelled sections:

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

At the end, whichever id has the most points wins. So a result only appears if some answer awards points to its id — if nothing can score `calm`, nobody ever gets `calm`.

---

## Working with Claude

Claude is genuinely useful here. It's also very keen to rebuild your project as something enormous, so keep it on a lead.

**Start every session by pasting this:**

> I'm learning to code — this is week one and I know nothing yet. I have one file, `index.html`, with the CSS and JavaScript inside it. No frameworks, no npm, no build step, nothing to install. Don't add files. Don't restructure anything. Explain changes in plain English and don't write anything I couldn't understand yet.

**The prompts worth knowing:**

- *"Explain this file line by line, simply."*
- *"Explain just the `addPoints` function, like I've never seen code before."*
- *"That's too complicated — do it more simply. No new files, nothing to install."*
- *"Here's my error: [paste it]. What does it mean and where do I look?"*
- *"Don't write the code yet. Tell me what I should try first."*

**Never accept:** a second file, a framework (React, Vue, Tailwind), a terminal command, or a full rewrite of something that was working.

**Read what changed before you carry on.** In GitHub Desktop, the Changes tab shows exactly what's different — green is added, red is removed. If you don't recognise it, that's rule 4 talking. Discard changes and ask again.

A bad prompt is *"build me a quiz app"*. You already have one. Ask about the bit you're changing.

---

## When it breaks

It will. That's normal, not a sign you're bad at this.

1. Right-click the page → **Inspect** → **Console** tab. Red text is the error, with a line number.
2. Paste the error into Claude and ask what it means.
3. Still stuck? Discard changes, and try again in smaller steps.

The three that will get you: a missing comma between items, a missing `}`, and a result `id` spelled differently in `QUESTIONS` than in `RESULTS`.

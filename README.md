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
5. Click **Open in Visual Studio Code**

Now open the terminal inside VS Code — **Ctrl + `** (that's the backtick, top-left of the keyboard, above Tab). Or **Terminal → New Terminal** from the menu.

Type this and press Enter:

```bash
open ./index.html        # Mac
```

```powershell
start .\index.html       # Windows
```

Your quiz opens in the browser. Answer the two questions and you'll get a result.

**That's the loop all week:** edit in VS Code → save (Ctrl/Cmd + S) → reload the browser tab. You only need that command again if you close the tab.

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

## Terminal cheatsheet

Open it in VS Code with **Ctrl + `**. You're typing commands instead of clicking — same actions, just written down.

**Mac and Windows are mostly the same, with one big exception.** VS Code gives you *zsh* on a Mac and *PowerShell* on Windows. Navigation commands match; opening files does not.

| What you want | Mac | Windows |
|---|---|---|
| Open the quiz in your browser | `open ./index.html` | `start .\index.html` |
| Open this folder in Finder / Explorer | `open .` | `start .` |
| Where am I? | `pwd` | `pwd` |
| What's in here? | `ls` | `ls` |
| Go into a folder | `cd images` | `cd images` |
| Go back up one level | `cd ..` | `cd ..` |
| Make a new folder | `mkdir images` | `mkdir images` |
| Clear the screen | `clear` | `clear` |

Things worth knowing:

- **`.` means "the folder I'm in"** and **`..` means "the folder above"**. So `./index.html` is "index.html, right here".
- **Press Tab to autocomplete.** Type `open ./ind` then Tab and it finishes the filename. Fewer typos, and it proves the file exists.
- **Up arrow** brings back the last command. You'll use this constantly.
- **The terminal starts in your project folder** because VS Code opened it there. If a command says "no such file", run `pwd` and `ls` to check where you actually are.
- Windows uses `\` in paths and Mac uses `/`. PowerShell mostly accepts both, so don't panic if you see either.

---

## The rules

These keep you unstuck. AI will break all of them if you let it.

1. **One file.** Everything lives in `index.html`. If a fix needs a second file, it's the wrong fix this week.
2. **Nothing to install.** The terminal is fine for the handful of commands in the cheatsheet below. But no npm, no Node, no downloading packages — if Claude tells you to install something, say *"do it without installing anything"*.
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

## Adding images

Every question and every result can have a picture. It's already wired up — you just supply the file.

**1. Make a folder for them.** In the VS Code terminal:

```bash
mkdir images
```

**2. Put your image files in it.** Drag them into the `images` folder in VS Code's file list on the left.

**3. Switch the line on.** In `index.html`, each question and result has a commented-out `image:` line. Delete the `//` at the start and put your filename in:

```js
{
  q: "It's Friday, 8pm. Where are you?",
  image: "images/friday-night.jpg",      // ← was commented out
  answers: [ ... ],
}
```

Save, reload the tab, and it appears. Leave the `//` there and nothing shows — no picture is completely fine.

### Rules for the files themselves

These stop the classic bug where it works on your laptop and is broken online.

- **Lowercase names, no spaces.** `friday-night.jpg`, never `Friday Night.JPG`. Spaces break paths, and GitHub treats `Photo.jpg` and `photo.jpg` as different files even though your Mac doesn't. This is the single most common reason images work locally and 404 once published.
- **Keep them under about 300KB.** A photo straight off a phone is 4MB and will make your page crawl. Resize before adding — [squoosh.app](https://squoosh.app) does it in the browser, free.
- **`.jpg` for photos, `.png` for graphics** with flat colour or transparency.
- **The path is relative to `index.html`.** `images/foo.jpg` means "the images folder next to this file". No leading slash.
- **Commit your images too.** They'll appear in GitHub Desktop's Changes list. If you don't commit and push them, your quiz works on your laptop and shows broken pictures for everyone else.

### Where to get them

You're publishing this publicly under your own name, so don't just grab things off Google Images.

- **Your own photos** — best option, and they make the quiz feel like yours
- **[Unsplash](https://unsplash.com)** or **[Pexels](https://pexels.com)** — free, properly licensed, no attribution needed
- **Emoji** — genuinely a good answer. Big emoji in the result card look deliberate and cost nothing. That's what the starter does already.

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

[← back to the README](../README.md)

# Adding images

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

---

## Rules for the files themselves

These stop the classic bug where it works on your laptop and is broken online.

- **Lowercase names, no spaces.** `friday-night.jpg`, never `Friday Night.JPG`. Spaces break paths, and GitHub treats `Photo.jpg` and `photo.jpg` as different files even though your Mac doesn't. This is the single most common reason images work locally and 404 once published.
- **Keep them under about 300KB.** A photo straight off a phone is 4MB and will make your page crawl. Resize before adding — [squoosh.app](https://squoosh.app) does it in the browser, free.
- **`.jpg` for photos, `.png` for graphics** with flat colour or transparency.
- **The path is relative to `index.html`.** `images/foo.jpg` means "the images folder next to this file". No leading slash.
- **Commit your images too.** They'll appear in GitHub Desktop's Changes list. If you don't commit and push them, your quiz works on your laptop and shows broken pictures for everyone else.

---

## Where to get them

You're publishing this publicly under your own name, so don't just grab things off Google Images.

- **Your own photos** — best option, and they make the quiz feel like yours
- **[Unsplash](https://unsplash.com)** or **[Pexels](https://pexels.com)** — free, properly licensed, no attribution needed
- **Emoji** — genuinely a good answer. Big emoji in the result card look deliberate and cost nothing. That's what the starter does already.

---

## If a picture doesn't show up

1. Check the filename in `index.html` matches the real file **exactly**, including capitals.
2. Check it's actually in the `images` folder — `ls images` in the terminal will tell you.
3. Right-click the page → **Inspect** → **Console**. A 404 there means the path is wrong.

---

**Next:** [when it breaks](when-it-breaks.md) · [saving your work](saving-your-work.md)

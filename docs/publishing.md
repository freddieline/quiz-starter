[← back to the README](../README.md)

# Publishing it

Friday's job: get your quiz on the internet with a real address, so anyone can open it on their phone.

You already have everything you need. GitHub will host it for free.

---

## Put it online

1. Go to your repo on github.com
2. **Settings** (top right of the repo, not your account settings)
3. **Pages**, down the left-hand sidebar
4. Under **Source**, choose **Deploy from a branch**
5. Branch: **main**, folder: **/ (root)**, then **Save**

Wait a couple of minutes, then refresh that page. It'll show your address:

```
https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/
```

That's it. That link works on any phone, anywhere, forever, and it costs nothing.

**Before you share it, [commit and push everything](saving-your-work.md).** GitHub serves what you pushed, not what's on your laptop. Anything you forgot to push simply won't be there.

---

## When it updates

Every time you push, the live site updates itself within a minute or so. You don't publish again — you just push, same as any other day.

If a change doesn't appear, wait a minute and hard-refresh: **Cmd/Ctrl + Shift + R**.

---

## If something's broken online but fine on your laptop

Nine times out of ten it's one of these:

- **You didn't push.** Check GitHub Desktop for uncommitted changes and an un-pushed commit.
- **Images 404.** Almost always capitals. Your Mac thinks `Photo.jpg` and `photo.jpg` are the same file; GitHub does not. See [Adding images](images.md).
- **You forgot to commit the images themselves.** They show in the Changes list like any other file, and it's easy to commit `index.html` alone.

Open the live site, right-click → **Inspect** → **Console**, and any missing file shows up there in red with the path it was looking for.

---

## Can't I just send them the file?

You can, and for one person sitting next to you it's the quickest thing — AirDrop or email `index.html` and they can open it in a browser.

It falls apart past that:

- **Images won't come with it.** You'd have to zip the whole folder, and then they have to unzip it.
- **Phones won't open it.** WhatsApp and iMessage won't render an `.html` attachment — they have to download it and find a browser first. Most people won't bother.
- **Email providers are suspicious of `.html` attachments**, because that's how phishing works. Gmail and Outlook may warn or block.
- **It's frozen.** Fix a typo and everyone still has the old copy.

A link has none of those problems, and it's the thing you can actually put on a CV.

---

## Sharing it well

- Send the link, not a screenshot. People need to click it.
- Send it to five people and **watch someone use it without helping them**. You'll learn more in two minutes than in a day of testing it yourself.
- The result screen's **Copy my result** button gives them something to paste. If you did the [result-in-the-URL](going-further.md) extension, that link opens straight on their result, which is what makes a quiz spread.

---

**Next:** [going further](going-further.md) · [saving your work](saving-your-work.md)

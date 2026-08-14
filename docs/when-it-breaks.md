[← back to the README](../README.md)

# When it breaks

It will. That's normal, not a sign you're bad at this. Everyone who writes code spends a good part of the day with something broken.

---

## The routine

1. **Look at the error.** Right-click the page → **Inspect** → **Console** tab. Red text is the error, with a line number.
2. **Paste it into Claude** and ask what it means and where to look.
3. **Still stuck?** [Discard changes](saving-your-work.md) to get back to this morning, then redo it in smaller steps.

Step 3 is why we commit daily. A bad hour costs you an hour, not the week.

---

## The three that will actually get you

**A missing comma.** Every `}` in a list needs a `,` after it, except the last one.

```js
{ text: "Out.",  points: { chaos: 2 } },     ← comma
{ text: "In.",   points: { calm: 2 } }       ← no comma, it's last
```

**A missing `}` or `]`.** VS Code helps here: click just after a bracket and it highlights its partner. If nothing highlights, you've found your problem.

**An id that doesn't match.** A result with `id: "calm"` only ever wins if some answer awards points to `calm` — spelled identically, capitals and all. `Calm` and `calm` are different.

---

## Reading an error message

Errors look scary and are mostly telling you two useful things: what went wrong, and which line. Start with the line number, look a line or two above it too, and ignore everything after the first few lines of the message.

`Uncaught SyntaxError: Unexpected token` almost always means a missing comma or bracket somewhere just before the line it names.

---

## When the page is completely blank

That's usually a JavaScript error stopping everything before it can draw. Console tab, first red line, start there.

---

**Next:** [working with Claude](using-claude.md) · [saving your work](saving-your-work.md)

[← back to the README](../README.md)

# Terminal cheatsheet

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

---

## Things worth knowing

- **`.` means "the folder I'm in"** and **`..` means "the folder above"**. So `./index.html` is "index.html, right here".
- **Press Tab to autocomplete.** Type `open ./ind` then Tab and it finishes the filename. Fewer typos, and it proves the file exists.
- **Up arrow** brings back the last command. You'll use this constantly.
- **The terminal starts in your project folder** because VS Code opened it there. If a command says "no such file", run `pwd` and `ls` to check where you actually are.
- Windows uses `\` in paths and Mac uses `/`. PowerShell mostly accepts both, so don't panic if you see either.

---

**Next:** [saving your work](saving-your-work.md) · [when it breaks](when-it-breaks.md)

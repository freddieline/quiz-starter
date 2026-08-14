[← back to the README](../README.md)

# Working with Claude

Claude is genuinely useful here. It's also very keen to rebuild your project as something enormous, so keep it on a lead.

---

## Start every session by pasting this

> I'm learning to code — this is week one and I know nothing yet. I have one file, `index.html`, with the CSS and JavaScript inside it. No frameworks, no npm, no build step, nothing to install. Don't add files. Don't restructure anything. Explain changes in plain English and don't write anything I couldn't understand yet.

---

## The prompts worth knowing

- *"Explain this file line by line, simply."*
- *"Explain just the `addPoints` function, like I've never seen code before."*
- *"That's too complicated — do it more simply. No new files, nothing to install."*
- *"Here's my error: [paste it]. What does it mean and where do I look?"*
- *"Don't write the code yet. Tell me what I should try first."*

That last one is the most underrated. Getting a plan before the code means you understand the change before it exists, rather than reverse-engineering it afterwards.

---

## Never accept

- A second file
- A framework — React, Vue, Tailwind, anything
- A command to install something
- A full rewrite of something that was already working

Any of those means the answer has drifted off what you're doing this week. Say *"simpler, no new files, nothing to install"* and ask again.

---

## Read what changed

In GitHub Desktop, the **Changes** tab shows exactly what Claude altered — green added, red removed.

If you don't recognise it, that's rule 4 talking. [Discard changes](saving-your-work.md) and ask again, more simply.

---

## A bad prompt

*"Build me a quiz app."*

You already have one. The useful questions are about the specific bit you're changing right now — one question, one function, one error. Big vague prompts get big vague code that you didn't write and can't explain on Friday.

---

**Next:** [how the code works](how-the-code-works.md) · [when it breaks](when-it-breaks.md)

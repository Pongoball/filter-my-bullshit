# filter-my-bullshit

A [Claude Code](https://claude.com/claude-code) skill for people who talk more than they type.

When you speak to Claude by voice or just think out loud, your messages fill up with "like", "you know", half-sentences, repeats, self-corrections and speech-to-text mistakes. This skill makes Claude filter all that out first, show you a short summary of what it understood, and then get to work.

## Before and after

You say:

> so like I want, you know, a small app, no wait a script, that renames my photos by the date they were taken, and like puts them in month folders, and don't delete the originals obviously

Claude shows:

```
🧹 What I understood
Goal: A script that renames my photos by the date they were taken and puts them in month folders.
Details:
- Use the date stored in the photo itself (guess)
- One folder per month
- Keep the originals: copy, don't move or delete
Open: Which photo folder?
```

## What it does

- **Drops** filler words, repeats, false starts and talk about talking.
- **Keeps** what you settled on: "no wait, actually X" means X.
- **Fixes** half-sentences and speech-to-text errors.
- **Translates** words from your own language that you drop in when you can't find the English one ("apelsinas" becomes "orange").
- **Keeps** every real requirement, number, name and step order, and never adds anything you didn't say. Guesses are marked as guesses.
- **Respects "just talking"**: if you say "no coding" or "just listening", it only discusses until you say "go ahead".
- **Answers questions** instead of acting on them: "Can you…?" gets an answer and an offer, not a start.
- **Acts** right away when everything is clear. If something blocks the work, it asks just that one question and picks sensible defaults for the rest.
- **Waits** for your yes before anything risky, such as deleting, sending, buying or publishing.

It's built to be light on tokens. A message with just one or two misheard words gets a one-line fix (`🧹 Reading "cloud app" as Claude app.`) without loading the skill. The full summary only shows for long, messy messages.

## Install

### Claude Code

Clone it into your personal skills folder:

```bash
git clone https://github.com/Pongoball/filter-my-bullshit ~/.claude/skills/filter-my-bullshit
```

Start a new Claude Code session, then type `/filter-my-bullshit` followed by your messy request. Claude also uses it on its own when a message is long and rambling.

### Claude app and claude.ai

Zip the `filter-my-bullshit` folder and upload it under **Settings → Skills**. The Claude Code copy and the uploaded copy don't sync, so re-upload after you change it.

## Make it yours (optional)

Copy `glossary.example.md` to `glossary.md` and add:

- your native language, so words from it get translated
- words speech-to-text keeps getting wrong for you ("cloud" → "Claude")
- names of people or projects that get misheard

Claude only opens this file when a word looks off, so it costs nothing on clean messages. When you correct a misheard word, Claude adds it for you.

## License

MIT

---
name: filter-my-bullshit
description: Turn a messy, dictated or rambling message into a clear request before acting on it. Use with /filter-my-bullshit, and on your own when a message is long or rambling, full of filler, repeats, self-corrections, half-sentences or words from another language. For a short message with only one or two misheard words, don't load this skill; just fix them in one line ("Reading 'cloud app' as Claude app") and carry on.
argument-hint: [your messy request]
---

# filter-my-bullshit

The user talks rather than types, by voice or as a stream of thought. The meaning is there under the filler, repeats, false starts and speech-to-text errors. Pull it out before you act. Work on the text passed with the command, or else on the user's latest message.

## 1. Filter

- **Drop** filler ("like", "you know", "basically", "um", swearing as filler), repeats, and talk about talking ("that's what I mean").
- **Keep what they settled on.** "No wait, actually X" means X. "Give me three… like 5" means 5.
- **Fix** half-sentences and words that look misheard. If a word looks misheard or is in another language, read [glossary.md](glossary.md) if it exists: it lists this user's native language and known mishearings. Otherwise go by context. Translate foreign words from the sentence around them.
- **Never drop** a real requirement, name, number, example, the order they asked for, their doubts, or their tone. Never add requirements. Mark guesses as guesses.
- **Mode words** such as "just talking", "no coding" or "just listening" are a rule, not filler.

Then decide what kind of message it is:
- **Task**: they want something done.
- **Question**: "Is it possible…?", "Can you…?". This is not a go-ahead.
- **Answers**: replies to questions you asked earlier. Match each answer to its question.
- **Talk only**: they used a mode word.

## 2. Show it

One or two fixed words: one line, `🧹 Reading "X" as Y.`

Anything messier: one short block in the user's language, with only the lines that are needed.

```
🧹 What I understood
Goal: <one line>
Details: <short bullets>
Order: <steps, if they gave an order>
Open: <unclear points or guesses>
```

For Answers, number them to match your earlier questions and list any skipped ones under Open.

## 3. Act

- **Talk only**: discuss and suggest, but change nothing. This lasts until they clearly say "do it", "go ahead" or "apply".
- **Question**: answer it, offer to do the work, and wait.
- **Answers**: carry on with what they unblock.
- **Task**: if nothing open would change the work, do it now. Otherwise ask the one question that blocks it, and pick defaults for the rest.
- Wait for a yes before anything hard to undo: deleting, sending, buying, publishing.

When the user corrects a misheard word, add it to glossary.md (create the file if needed).

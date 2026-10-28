---
name: filter-my-bullshit
description: Turn the user's messy, spoken-style message into a clear prompt before acting on it. Use with /filter-my-bullshit, and also on your own whenever a user message is long and rambling, dictated, full of filler words, half-sentences, repeats, self-corrections or speech-to-text mistakes. Skip it for short, clear messages.
argument-hint: [your messy request]
---

# filter-my-bullshit: filter the noise out of what the user said

The user often talks rather than types: by voice or in a stream of thought. Their messages can have filler, swearing used as filler, half-sentences, repeats, false starts, ideas in random order, and speech-to-text errors. The meaning is in there; your job is to pull it out before you act.

Work on the text passed with `/filter-my-bullshit`. If there is none, use the user's latest message.

## 1. Filter

Drop:
- filler: "like", "you know", "so", "basically", "kind of", "that kind of shit", "um", "I mean"
- repeats of the same point; keep the clearest version
- false starts and self-corrections; keep what they settled on ("no, wait, actually X" means X)
- talking about talking ("that's what I mean", "how you call that")

Fix:
- half-sentences, so each becomes a full thought
- words that look like speech-to-text errors; pick the word that fits the context
- words in the user's own language (for example Lithuanian), dropped into an English sentence when the user can't find the English word ("apelsinas" means "orange"). Translate them using the sentence around them. Speech-to-text may also mangle such a word into an odd English-looking one, so check for that too. If a word could mean two things that lead to different work, put it under Open.
- the order: goal first, then details, then constraints

Keep, never drop:
- every real requirement, preference, constraint, name, number and example
- order they asked for ("first search, then if nothing, build")
- their doubts and open questions, marked as open
- their tone toward the work (urgent, casual, unsure)

Never add requirements they did not say. If you have to guess, mark it as a guess.

## 2. Show it

Write one short block in the user's language (translate the label too):

```
🧹 What I understood
Goal: <one line>
Details: <short bullets, only if needed>
Order: <steps in the order they asked, only if they gave one>
Open: <what is unclear or you guessed, only if any>
```

Keep it short: usually 3 to 8 lines. Plain words. No praise, no restating the filler.

## 3. Act

- If nothing is open, go ahead and do the task right after the block. Don't wait for a yes.
- If something is open and the answer changes what you do, ask that one question (use AskUserQuestion if you have it) and wait.
- If several things are open, ask only the one that blocks the work (often: which file or folder). Pick sensible defaults for the rest, say them in one line, and let the user change them later.
- If the task is risky or hard to undo (deleting, sending, buying, publishing), always wait for a yes, however clear it looks.

If the user corrects the block, use their correction and don't show the block again for that request.

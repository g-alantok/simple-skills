---
name: skill-blueprint
description: Builds the foundations for a simple skill before you make it in Claude or ChatGPT, starting with whether you need one at all. Use when someone wants to make or check a skill.
---

## Objective

Get the logic of a simple skill right before anyone builds it in Claude or ChatGPT. Decide first whether the task needs a skill, then make sure each skill has the seven parts below and nothing else. New skills and audits follow the same steps.

## Steps

1. **Ask, in two rounds at most.**
   - Round 1: "What are you trying to get done, how often do you do it, and how much explaining does it take to get it right?" For an audit, ask for the skill too. Leave out anything the conversation already answers.
   - Round 2: up to three follow-up questions in one message, on the gaps that would change the skill most, each with your recommended answer so the user can reply "yes to all".
   - After round 2, stop asking and list your best guesses for anything missing as assumptions the user can strike out.
2. **Route.** Use "Which it should be" to decide. Stop and ask: "This looks like [outcome] because [reason]. Go with that, or change it?" If it's custom instructions, write the line and stop. If it only needs prompting, say so and stop.
3. **Draft or read.** For a new skill, draft the seven parts from the user's answers and your assumptions. For an audit, read the skill.
4. **Check and fix.** Check against the seven parts, "Can it be followed?" and the writing rules. Fix what fails.
5. **Ask for approval.** Show the result in chat and ask: "Approve as is, change something, or drop it?" (for an audit: "Which fixes stand?"). Make or change a skill only after the user approves.

## Which it should be

Every task gets exactly one of these.

| If the task... | It should be |
|---|---|
| isn't repeated, or changes each time | prompting, in the user's own words as they normally would |
| applies to everything the user does, like tone, format or who they are | custom instructions |
| repeats, with one objective | one skill, however short |
| repeats, with more than one objective or steps that change with the input | one skill per objective |

## The seven parts

| Part | Question to ask | Why it matters |
|---|---|---|
| Objective | Do one or two sentences say why it exists and what it's solving for? | Claude tests every line against this, and falls back on it when a case isn't covered |
| Trigger | Does it say what the skill does and the kinds of request that should start it? | Claude sees only this until the skill starts |
| Input | Does it say what the user must give, when there's enough to start, and what changes for each kind of input? | Where there's a gap, Claude guesses |
| Method | Does it say what Claude does, either as steps in order with stops for the user, or as the standard the result must meet? | This is the skill; everything else supports it |
| Context | Does it give only what Claude wouldn't already know, like definitions, the audience and examples? | Claude only knows what's in front of it |
| Guidelines and verification | Does it name the few mistakes that would break the result, each with what to do instead, and how Claude checks its own conclusions? | A few clear checks beat many rules |
| Output | Does it describe the result and where it goes, give one example, and say what finished means? | Claude stops when it thinks it's done |

## Where things go

- **Variables.** A variable that changes what comes in goes in Input. One that changes how the work is done goes in Method as a short "if this, then that". If it changes most of the steps, it's a second skill.
- **Standards.** In a standard skill, the standard is the Method. In a steps skill, the standard for good goes in Context. Either way, it lives in one place.
- **Checkpoints.** Put a stop wherever the user must decide, and end it with a question they can answer.
- **Verification.** Nudge Claude to ground its conclusions in something (the source, a quote, the user's own words), and let it choose how.

## Room to reason

A skill works best when Claude understands what it's aiming for and can use its judgement. Look for these:

- It says what it's solving for, so Claude can handle cases it doesn't list.
- Each rule comes with its reason.
- Checks are written as questions Claude asks itself.
- When something fails, the objective gets sharper before a new rule gets added.

## Can it be followed?

Ask of every line:

- Could someone new to the task follow it without asking what it means?
- Does it contradict another line?
- Does its example fit the people who will use the skill?

## Writing rules

- **Concise:** keep only sentences that serve the objective and change what Claude would do, and say each thing once.
- **Precise:** use the one word that best gets the result the objective needs. Precise means the exact word, and usually fewer of them.
- **Checkable:** start each instruction with a verb, and make instructions and finish lines something Claude can check ("short" becomes "under 100 words"). Leave judgement calls to the objective.

## Guidelines and verification

- If one skill is stretching over two objectives, suggest the split.
- In an audit, quote the line behind each finding, so the user can see it for themselves.

## Output

- **New skill:** a plain-English summary in chat, one or two lines per part, for the user to paste into Claude's or ChatGPT's skill builder. Under it, list your assumptions and two or three test requests, each with what a good result looks like.
- **Audit:** say what the skill is trying to do, give a five-line summary (what works, what doesn't, what to do next, and why), then list each missing part and each line that fails a check.

Example summary for a new skill:

> **Objective:** Turn any meeting transcript into the same one-page summary, so decisions and actions are easy to find.
> **Trigger:** Use when someone shares a meeting transcript and asks for a summary.
> **Input:** The transcript and who the summary is for. If speakers aren't named, ask who they are.
> **Method:** Ask who it's for, sort the talk into decisions, actions and open questions, check, then show it.
> **Context:** The one-page format, and what the reader needs from it.
> **Guidelines and verification:** Instead of guessing an owner, mark it [owner?]. Check each action against the transcript before listing it.
> **Output:** A one-page summary in chat, finished when every action has an owner or an [owner?] mark.

## Done when

You're done when the user has agreed the route and approved a summary where every part is present and every line can be followed.

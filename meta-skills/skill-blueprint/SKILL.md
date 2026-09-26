---
name: skill-blueprint
description: Builds the foundations for a simple skill before you make it in Claude or ChatGPT. Use when someone wants to make or check a skill.
---

## Objective

Produce a blueprint for a simple skill, worked out with the user and ready to build in Claude or ChatGPT. New skills and audits follow the same steps. Check every question, draft line and fix against this objective: does it help the user end up with the simplest skill that does the job?

## Steps

Ask two rounds of questions at most. At every question or stop, give your recommendation and why, so the user can simply agree or change it. Draft early, so the user reacts to something concrete instead of answering questions in the abstract.

1. **Understand the task.** Ask one open question that finds out what the user is trying to get done, what a good result looks like to them, and which AI tool they use. For an audit, ask for the skill. Skip anything the conversation already answers.
2. **Decide the shape.** One skill or several, and steps, a standard or both (see "Two kinds of skill"). Decide on the objective, not the inputs: one objective is one skill however varied the inputs, and two objectives mean two skills. If the steps change for most inputs, check for a hidden second objective. Recommend a shape, then stop and confirm.
3. **Draft the blueprint.** Draft all seven parts from what you have, and mark each guess as an assumption. For an audit, mark each part present or missing.
4. **Fill the gaps.** In one message, ask up to three questions on the assumptions that would change the skill most. This is the last round; anything still unknown stays as a listed assumption.
5. **Check, then ask for approval.** Check the blueprint against "What a good skill looks like" and fix what fails. Show it and ask: "Approve as is, change something, or drop it?" (audit: "Which fixes stand?"). Make or change a skill only after the user approves.

## What a good skill looks like

### Two kinds of skill

- **Steps:** a process in order, like turning any transcript into the same summary.
- **Standard:** rules the result must meet, in any order, like writing in someone's voice. In a standard skill, the standard is the Method; in a steps skill, the standard for good goes in Context.
- Many skills use both: steps that end with a check against a standard.

### The seven parts

"The LLM" means the AI model that will run the skill. Cover all seven. By default, give each part its own subheading. If the user says something matters most, use your judgement (its own subheading, or merged parts), as long as every question below is answered.

| Part | Question to ask | Because the LLM... |
|---|---|---|
| Objective | Does it say what the skill is solving for, and tell the LLM to check each step and the result against it? | falls back on the goal when a case isn't covered |
| Trigger | Does it say what the skill does and the kinds of request that should start it? | sees only this until the skill starts |
| Input | Does it say what the user must give, when there's enough to start, and what changes for each kind of input? A change in how the work is done goes in Method as "if this, then that". | guesses wherever there's a gap |
| Method | Does it say what the LLM does: steps in order, with a stop ending in a question before anything hard to undo and wherever the judgement is the user's, a standard, or both? | leans towards acting and finishing, so it won't pause unless told where to |
| Context | Does it give the background the LLM wouldn't already know, like definitions, sources and who the result is for? | only knows what's in front of it |
| Guidelines and verification | Does it name the few mistakes that would break the result, each with what to do instead, and nudge the LLM to check its conclusions against something (the source, a quote, the user's words) in its own way? | brings a banned thing to mind, and can sound sure while guessing |
| Output | Does it describe the result and where it goes, give one example that fits the people using it, and say what finished means? | copies examples closely, and stops when it thinks it's done |

### Can it be followed?

Ask of every line:

- Could someone new to the task follow it without asking what it means?
- Does it repeat or contradict another line?

### Writing rules

- **Briefed:** write it as you'd brief a capable colleague: why each thing matters, the background they need, and the questions to ask to meet the objective. Enough to reason with, and no more, because the LLM applies bare rules rigidly and a reason lets it handle cases the skill didn't list.
- **Concise:** keep only sentences that serve the objective and change what the LLM would do, and cut preamble. Use as few words as the job needs. About 1,000 is a rough guide, not a limit. Put the key rules at the top and bottom, because the LLM pays least attention to the middle of long text. If background starts to outweigh the instructions, suggest moving it into a reference file and let the user decide.
- **Precise:** use the one word that best gets the result the objective needs. Precise means the exact word, and usually fewer of them.
- **Checkable:** start each instruction with a verb, and make instructions and finish lines something the LLM can check ("short" becomes "under 100 words"). Leave judgement calls to the objective.

## Guidelines and verification

- When changing a skill, the LLM tends to fix one gap with a special-case rule instead of asking what is structurally missing or what should come out. When in doubt, strip out rather than add: sharpen the objective or add a reason before adding a rule, because each extra rule narrows what the LLM will reason about.
- In an audit, quote the line behind each finding, so the user can see it for themselves.

## Output

- **New skill:** the blueprint in chat, one or two lines per part, ending with how to save it in their tool. If the tool can install skills: "Paste this in and ask it to build and save the skill, or install it as is." If not, say it won't start on its own, and offer it as a Word file to attach when needed, or to paste into an agent's instructions (in Copilot, a lightweight declarative agent). Under it, list your assumptions and two or three test requests, each with what a good result looks like.
- **Audit:** say what the skill is trying to do, give a five-line summary (what works, what doesn't, what to do next, and why), then list each missing part and each line that fails a check.

Example blueprint, so the LLM matches this shape:

> **Objective:** Turn any meeting transcript into the same one-page summary, so decisions and actions are easy to find. Check each item against that aim before including it.
> **Trigger:** Use when someone shares a meeting transcript and asks for a summary.
> **Input:** The transcript and who the summary is for. If speakers aren't named, ask who they are.
> **Method:** Ask who it's for, sort the talk into decisions, actions and open questions, then stop and ask "Anything missing or misheard?" before finalising.
> **Context:** The one-page format, and what the reader needs from it.
> **Guidelines and verification:** Instead of guessing an owner, mark it [owner?]. Check each action against the transcript before listing it.
> **Output:** A one-page summary in chat, finished when every action has an owner or an [owner?] mark.

## Done when

You're done when the user has agreed the shape and approved a blueprint where all seven parts are covered and every line can be followed.

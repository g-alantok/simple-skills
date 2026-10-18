# Simple skills

Practical skills for everyday work in Claude and ChatGPT, written in plain English. You install them in the app itself, and each one makes a solid starting point if you later want to turn it into an agent skill.

They're for anyone who uses AI at work, whether you're an engineer writing up a design for review or a manager pitching an idea to leadership.

| Skill | What it does | Folder |
|---|---|---|
| [skill-blueprint](#skill-blueprint) | Builds the foundations for a skill before you make it | `meta-skills/` |
| [executive-ready-slides](#executive-ready-slides) | Turns a deck into a story a busy reader gets from the headlines alone | `communication/` |

## Install

If you use a coding agent such as Claude Code or Cursor, install a skill with one command:

```bash
npx skills add g-alantok/simple-skills --skill skill-blueprint
npx skills add g-alantok/simple-skills --skill executive-ready-slides
```

For the Claude or ChatGPT app, see "How to use it" under each skill.

## skill-blueprint

Builds the foundations for a skill before you make it in Claude or ChatGPT.

No matter who you are, you can use this. It uses first-principles logic to help you cover all the key aspects a model needs to understand your skill.

### What you get

A skill is a set of instructions you give an AI so it does a task the same way every time. Whether it's your first skill or your fiftieth, skill-blueprint asks you a few questions and drafts a blueprint with you, starting with whether your task is one skill or several.

It catches the gaps that make skills unreliable, like a vague trigger, no point where it stops to check with you, or no clear point where the job is finished. It keeps the skill as short as the job allows so the model has room to use its own reasoning, and hands you a plain-English blueprint to build in whichever AI tool you use. You spend less time fixing the skill after you've made it.

### Why it works this way

Most skills go wrong by being too long or too strict. skill-blueprint starts from first principles instead, by asking what limits the model:

- It only knows what you show it.
- It guesses wherever you leave a gap.
- It forgets between chats.
- It leans towards acting, so it won't pause to check with you unless told where.
- It stops when it thinks it's done.

The seven parts below work around those limits. The skill gives the model reasons and questions rather than rigid rules, so it can use its own reasoning on cases the skill didn't list.

### The seven parts

- **Objective:** why the skill exists
- **Trigger:** when it starts
- **Input:** what it needs to begin
- **Method:** what it does, as steps or a standard
- **Context:** what it needs to understand the task
- **Guidelines and verification:** how it stays on track and checks itself
- **Output:** what it produces and where it goes

### How to use it

In Claude, zip the `skill-blueprint` folder and upload it as a skill. In ChatGPT, add it as a skill if your plan has them, or paste the contents of `SKILL.md` into a project or custom GPT's instructions. If your tool doesn't have skills yet, like Copilot for many people, paste it into an agent's instructions or keep it as a Word file to attach when you need it. Then tell it what you want to build or check.

## executive-ready-slides

Builds or checks a slide deck so it tells a story a busy reader gets from the headlines alone, with each slide proving its headline.

### What you get

Most decks have headlines like "Background", "Objective" and "Next steps", which leave the reader to work out the point, and the ask often sits on the last slide. executive-ready-slides agrees the one message with you first, then turns each headline into a full sentence that states the slide's point (management consultants call these action titles). It puts the ask up front, checks the headlines read as one argument, and checks each slide's content and layout back up its headline. You get the deck as headlines with what goes under each, plus the two or three problems that still need your call. When the story needs testing, it strips the deck back to a dot-dash (the headlines as dots, the evidence under each as dashes) and checks the argument holds, either itself or through a sub-agent that hasn't seen the drafting.

### Why it works this way

An AI writes one word at a time, so its first draft tends to work through the background and reach the point last, in each sentence and across the whole deck. Telling it "put the point first" while it drafts only goes so far. So the skill has it draft first, then check the finished draft in separate passes, and rewrite before you see anything. The checks follow management consulting standards: Barbara Minto's Pyramid Principle and the usual practice for action titles and slide layout.

### How to use it

In Claude, zip the `executive-ready-slides` folder and upload it as a skill. In ChatGPT, add it as a skill if your plan has them, or paste the contents of `SKILL.md` into a project or custom GPT's instructions and add `references/dot-dash-check.md` as a knowledge file. Then share your notes, your draft deck or just your idea, and say who it's for.

---

Made by g-alantok. Free to use and adapt with credit ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)).

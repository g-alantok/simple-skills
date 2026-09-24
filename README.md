# Simple skills

Practical skills for everyday work in Claude and ChatGPT, written in plain English. You install them in the app itself, and each one makes a solid starting point if you later want to turn it into an agent skill.

## skill-blueprint

Builds the foundations for a skill before you make it in Claude or ChatGPT.

No matter who you are, you can use this. It uses first-principles logic to help you cover all the key aspects a model needs to understand your skill.

### What you get

A skill is a set of instructions you give an AI so it does a task the same way every time. Whether it's your first skill or your fiftieth, skill-blueprint starts by asking whether your task is something you'll repeat, or something you'd be better off just asking for in your own words, the way you normally would.

If it does need a skill, skill-blueprint catches the gaps that make skills unreliable, like a vague trigger or no clear point where the job is finished. It keeps the skill short so the model has room to use its own reasoning, and hands you a plain-English summary to paste into Claude's or ChatGPT's skill builder. You spend less time fixing the skill after you've made it.

### Why it works this way

Most skills go wrong by being too long or too strict. skill-blueprint starts from first principles instead, by asking what limits the model:

- It only knows what you show it.
- It guesses wherever you leave a gap.
- It forgets between chats.
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

In Claude, zip the `skill-blueprint` folder and upload it as a skill. In ChatGPT, paste the contents of `SKILL.md` into a project or custom GPT's instructions. Then tell it what you want to build or check.

---

Made by g-alantok. Free to use and adapt with credit ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)).

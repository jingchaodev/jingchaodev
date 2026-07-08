<h1 align="center">chao</h1>

<p align="center">
  <b>Harness engineering for AI agents.</b><br>
  I build the scaffolding that makes agents reliable — the prompts, skills, memory, and feedback loops around the model, not the model itself.
</p>

<p align="center">
  <a href="https://github.com/jingchaodev?tab=repositories">Repos</a> ·
  <a href="#featured-work">Featured work</a> ·
  <a href="#what-i-think-about">What I think about</a>
</p>

---

Most of an agent's behavior isn't the model — it's everything wrapped around it: the system prompt, the tools it's given, the skills it can load, what it remembers, and how it recovers when it's wrong. That layer is usually invisible and untested. I work on making it **inspectable, reusable, and self-correcting**.

Based in Seattle. Currently building always-on autonomous agents, the harnesses that keep them honest — and the tools that audit what those agents *believe*.

## Featured work

**[memory-doctor](https://github.com/jingchaodev/memory-doctor)** — Audits the **quality** of your AI agent's memory: what's stale, contradictory, never-loaded, or never-used. Existing tools clean up disk and tokens; memory-doctor audits *truth* — dead references, entries past the silent load cliff, relative dates that mean nothing at recall time, index orphans that make memories invisible. Local-first, read-only, zero dependencies. First run on my own 13-agent setup found 17 problems, including 20+ paths my agents believed in that no longer exist. Every detector ships with golden fixtures and gets precision-tested on a live fleet before release.

**[harness-loop](https://github.com/jingchaodev/harness-loop)** — A self-improving loop for agent harnesses. Every prompt, config, memory write, and hook ultimately compiles into one artifact: the HTTP request sent to the model. harness-loop taps that request, checks the *compiled* prompt against rules you declare, and runs a `detect → notify → repair → re-verify` cycle so "my memory system works" becomes a fact, not a guess. Zero dependencies, works with any Anthropic- or OpenAI-compatible agent. *Born from running three always-on Claude Code agents through this exact loop.*

*Together they cover both halves of agent reliability: harness-loop audits what the agent **does** (mechanisms), memory-doctor audits what it **believes** (memory).*

**[skills-lab](https://github.com/jingchaodev/skills-lab)** — A library of reusable [Agent Skills](https://code.claude.com/docs/en/skills) for Claude Code, plus the authoring principles behind them. Covers research, code/design review, incident response, and an oncall-agent that composes a set of specialist skills into one assistant. As much about *how to write skills an agent will actually invoke correctly* as the skills themselves.

**[.dotfiles](https://github.com/jingchaodev/.dotfiles)** — Tools and settings for a fast agent-driven dev environment.

## What I think about

- **The compiled prompt is the source of truth.** You can't verify a harness by reading its config — you verify it by inspecting the request that config produces.
- **Memory you can't audit will quietly go wrong.** Agents accumulate beliefs; without staleness, contradiction, and usage checks, yesterday's fact becomes today's confident mistake.
- **Structural over remembered.** Sensing and verification should be things the agent *can't forget to do*, not instructions it might skip.
- **Skills are progressive disclosure.** A good skill's `description` earns its place in context; its body is written for a model to act on, not a human to admire.
- **Judgment belongs to the agent; approval belongs to the human.** Automate the loop, gate anything durable or outgoing.

## Reach me

- GitHub: [@jingchaodev](https://github.com/jingchaodev)
- X: [@cifra1902](https://x.com/cifra1902)

# WSL2 / OpenClaw Setup Guide — OldGenAI

**You've spent six hours watching your RAM evaporate. This guide is how it stops.**

A free, practical guide to getting a local AI agent — **OpenClaw, running on Windows with WSL2, Ubuntu, and LM Studio** — set up so it actually *stays* running. Not the theory of LLMs. The survival guide nobody wrote for the part where it all breaks.

> 📄 **[Download the guide (PDF)](WSL2-OpenClaw-Setup-Guide-OldGenAI.pdf)** · Free · Written by [OldGenAI](#about)

---

## Why this exists

I'd set OpenClaw up on a Mac Mini the week before — one line, pasted into the terminal, done. So when I sat down at a Windows machine I had that dangerous thing: just enough confidence.

Pasted the same command. It worked for about ten seconds. Then `no Homebrew found` — turns out that's a Mac thing. Went via npm instead — Node.js wasn't installed. Installed it — the install kept failing, until an hour later I found out it needed Administrator. Got OpenClaw running, got LM Studio installed (genuinely intimidating if you've never touched local inference), downloaded a model... then realised I'd installed the whole thing directly on Windows instead of sandboxed in WSL2. I didn't even know what WSL2 *was*.

That was the *what the hell am I doing* moment.

I'm 49. I'd never written a line of code. I started in April 2026. This guide is everything I learned clawing my way out of that wreckage — written down so your version takes an afternoon instead of two weeks.

**We build well, or we don't ship.**

---

## What you'll have at the end

- A **rock-solid WSL2/Ubuntu setup** that doesn't break every time you reboot
- **OpenClaw properly wired to LM Studio** — the networking configured so they actually talk to each other
- The **"Stability Stack"** — the specific fixes (heartbeat management, context-bloat prevention) that stop the runaway loops and RAM blowouts nobody else documents
- A **predictable baseline** — a Gemma 4 26B-A4B setup hitting ~40s cold starts and ~2–3s warm responses

## Who it's for

The person starting with a clean Windows install who wants to run high-quality local models without losing their mind. You're not afraid of a terminal, but you're tired of broken configs and wiped workspaces.

## What it doesn't cover

- **Not a Mac guide** (that one's coming later)
- **Not a Python / Node.js development course** — we're configuring, not coding
- **Not GPU hardware tuning** — the focus is the WSL2 / Ubuntu / LM Studio pipeline

---

## What's in this repo

| | |
|---|---|
| 📄 **[The guide (PDF)](WSL2-OpenClaw-Setup-Guide-OldGenAI.pdf)** | The full walk-through, start to finish |
| 📁 **[`templates/`](templates/)** | The four agent identity & config files the guide builds on — copy them into your own agent and make them yours |

### The templates

The guide builds your agent's personality and operating rules from four small files. They're here, ready to copy:

- **`SOUL.md`** — who your agent *is*: tone, opinions, the rules of how it talks to you
- **`IDENTITY.md`** — name, role, vibe, emoji
- **`USER.md`** — about *you*, so the agent actually knows who it's working for
- **`AGENTS.md`** — the workspace rules: memory, red lines, and the hard safety limits (3-strike stop, ask-before-exec, and the rest)

Open them, fill in the brackets, and you've got an agent that behaves like *yours* instead of a generic chatbot.

---

## The bigger picture

This WSL2 stack isn't the destination — it's the workshop. It's the exact environment I used to build **[Mission Control](https://github.com/OldGenAi/mission-control)**, my open-source, self-hosted agentic OS. If this guide gets you a stable local agent, Mission Control is something you can build *with* it once you're ready.

The guide and Mission Control are **free, separate, and complete on their own** — you don't need one for the other.

---

## Found a mistake?

Setups drift — tools update, things change. Live corrections live on the **[errata page](https://www.notion.so/OldGenAI-WSL2-Guide-Errata-Updates-36a629b5e72b8032bd7dec06391a8386)**. Spot something the guide gets wrong? Open an issue — I'd rather fix it than have you hit the same wall I did.

---

## License

Free to read, use, and share — credit appreciated. Licensed under [CC BY 4.0](LICENSE). The templates are yours to copy and adapt for your own agents, no strings.

---

## About

**OldGenAI** is me — 49, no coding background, learning in public and proving you don't need a CS degree to build real AI infrastructure. Honest about what broke, no fluff, no gatekeeping.

- 🛠️ [Mission Control](https://github.com/OldGenAi/mission-control) — my open-source agentic OS
- 🐦 [@OldGenAi on X](https://x.com/OldGenAi)

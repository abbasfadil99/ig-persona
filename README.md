[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# ig-persona

This is not a full auto-generator. It's a human + LLM collaboration template for Instagram content. Personalized via Markdown, zero dependencies, so the output actually sounds like you.

---

## Prerequisites

- [Claude Code](https://claude.ai/code) (or any Claude-compatible agent runner)
- An Instagram account you want to create content for

---

## Quick Start

```bash
# 1. Click "Use this template" on GitHub → "Create a new repository"

# 2. Clone your new repo
git clone https://github.com/your-username/my-ig-content.git
cd my-ig-content

# 3. Open Claude Code
claude

# 4. Run setup once (in the Claude Code chat)
# /setup

# 5. Create content daily
claude --agent ig-creator          # English
claude --agent ig-creator-pt-br    # Portuguese
```

Setup will ask for your language preference, then guide you through filling in [`user.md`](user.md) and configuring your creator agent.

---

## Language Support

This template supports **English** and **Portuguese (Brazil)**. Each language has its own agent setup pipeline.

---

## Content Formats Supported

- **Reel** — Script + caption for 15–60s videos
- **Reel Loop** — Minimal on-screen text + long caption for 5–10s loops
- **Carousel** — Slide-by-slide structure with cover and CTA slide
- **Single Post** — Image caption with hook, value, and CTA

---

## Key files

- [`user.md`](user.md) — your personal context (filled by setup, read before every session).
- [`.claude/agents/`](.claude/agents/) — all agent definitions, including templates.
- `.claude/agents/ig-creator-agent.md` and/or `ig-creator-agent.pt-br.md` — your generated agent definitions (created by setup).
- [`posts/`](posts/) — your content, one `.md` file per post.

### Examples
- [`user.example.md`](user.example.md) — filled-in profile so you can see the expected depth.
- [`.claude/agents/ig-creator-agent.example.md`](.claude/agents/ig-creator-agent.example.md) — fully configured agent for reference.
- `posts/*.example.md` — real generated output showing what the final content looks like.

## Customization

- **Add a new language:** Copy the English template and setup files, translate the content, and follow the `-lang-code` naming convention.
- **Add content formats:** Extend `ig-creator-agent-template.md` or `ig-creator-agent-template.pt-br.md` with new format structures.
- **Update current formats:** If the current formats don't fit your style, you can ask your agent to update the templates or your agent.md file directly.
- **Customize tone:** Re-run `/setup` or invoke the specific setup agent (`/ig-setup` or `/ig-setup-pt-br`) to update your profile at any time.

## Rough Edges

This is a living template, some things aren't fully polished yet:

- **Session saving** — The `Session` field in post files is pre-filled with a suggested name, but the `/rename` flow to confirm it isn't seamless. You may need to update it manually.
- **Format variety** — The agent tends to default to Carousel and Reel Loop suggestions. If you want a Reel or Single Post, ask for it explicitly. A future version should distribute formats more evenly.

## Tips
- If the output doesn't sound like you, the most impactful fix is updating the `Tone` section in your agent.md. No need to re-run setup.
- Ask for v1, v2, v3 before picking one to post, the first version is rarely the best. Input your own versions as well and ask to review.
- When initial prompting, give the agent at least a small paragraph with your post idea, let it structure it. A voice memo transcribed with Whisper helps a lot.
- The quality is best using models that accept temperature config, use higher than usual values to add creativity to it.
- I really liked using Gemini 3 Flash Preview (0.5 temp). The writing came out surprisingly natural, almost like I wrote it myself 🤩. Try other models beyond Anthropics as well!
- You can ask the agent to reflect on what made a good version work and update your agent.md accordingly, iterating on the prompt itself, not just the content.

--- I hope you have fun 📷✨

---

## License

MIT © 2026 [Ton Anywhere](https://github.com/ton-anywhere)

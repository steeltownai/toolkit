# Steel Town AI toolkit

Free frameworks and agent skills from [Steel Town AI](https://steeltownai.io), a Pittsburgh AI consulting and training firm. Copy them, fork them, adapt them to your organization.

## Frameworks

Five steps each, a signal that tells you each step is working, what to track every month, and sources for every number.

| Framework | For | Files |
|---|---|---|
| **The AI spend control loop**: Five steps to keep AI spend growing slower than the value it produces. | CFOs, IT and ops leaders, and owners who sign the AI bills | [markdown](frameworks/ai-spend-control-loop.md) · [5-page PDF](carousels/ai-spend-control-loop.pdf) · [post](https://steeltownai.io/blog/ai-spend-control-loop) |
| **The agent rollout ladder**: Five stages to take one AI agent from a demo to production work, one workflow at a time. | CIOs and the operations and engineering leaders putting agents into real workflows | [markdown](frameworks/agent-rollout-ladder.md) · [5-page PDF](carousels/agent-rollout-ladder.pdf) · [post](https://steeltownai.io/blog/agent-rollout-ladder) |
| **The org-wide AI maturity ladder**: Five levels from scattered experiments to AI built into how the work gets done, with the training each level needs. | leaders, HR and L&D teams responsible for AI adoption across the whole organization | [markdown](frameworks/org-ai-maturity-ladder.md) · [5-page PDF](carousels/org-ai-maturity-ladder.pdf) · [post](https://steeltownai.io/blog/org-ai-maturity-ladder) |

## Agent skills

Each folder holds a `SKILL.md`, the format Claude Code, the Claude apps and Codex read. Read a skill before you install it.

- [`ai-spend-review`](skills/ai-spend-review/SKILL.md)
- [`build-log`](skills/build-log/SKILL.md)
- [`mcp-server-starter`](skills/mcp-server-starter/SKILL.md)
- [`model-routing-tests`](skills/model-routing-tests/SKILL.md)

```bash
# Claude Code, personal install
git clone https://github.com/OWNER/REPO.git && cp -R REPO/skills/* ~/.claude/skills/
# Codex reads .agents/skills/ in a project
```

## License

Skills and code: MIT ([LICENSE](LICENSE)). Frameworks and PDFs: CC BY 4.0 ([LICENSE-CONTENT](LICENSE-CONTENT)).

Generated from the steeltownai.io site sources. Issues and pull requests are welcome; corrections to a source or a number most of all.

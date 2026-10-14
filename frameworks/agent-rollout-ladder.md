# The agent rollout ladder

Five stages to take one AI agent from a demo to production work, one workflow at a time. For CIOs and the operations and engineering leaders putting agents into real workflows.

Read it with commentary: https://steeltownai.io/blog/agent-rollout-ladder
5-page PDF: [carousels/agent-rollout-ladder.pdf](../carousels/agent-rollout-ladder.pdf)

## Why it matters

- **40%+** of agentic AI projects will be canceled by the end of 2027, for cost, unclear value or weak risk controls. (Gartner prediction, June 2025)
- **17%** of organizations have deployed AI agents so far. More than 60% expect to within two years. (Gartner, April 2026)
- **~75%** of AI high performers redesigned workflows around AI, against about 25% of everyone else. (McKinsey State of AI, Aug 2026)

## 1. Pick a job, not a technology

Start with one workflow that has volume, a clear definition of done and an owner.

- Write down today’s cost per task: time, error rate and who fixes the errors.
- Try the simplest design that could work first: one model call, then a fixed sequence of steps, and only then an agent that chooses its own steps.

**Working when:** One page states the task, the baseline and what good looks like.

## 2. Build the test set before the agent

Collect 20 to 50 real cases with the outcome you expect, starting with the ones that went wrong before.

- Grade automatically where an answer can be checked, and have a person grade the rest.
- Rerun the full set after every prompt, tool or model change.

**Working when:** A change can be tested in minutes, not argued about in a meeting.

## 3. Run it in shadow mode

The agent drafts and people decide. Nothing it does reaches a customer or a system of record yet.

- Compare its output with what the person did, on real work, for at least two weeks.
- Log every model call and tool call, so you can see why it went wrong.

**Working when:** You know its agreement rate on real traffic, not on a demo.

## 4. Add guardrails and handoffs

Decide in advance what the agent may do alone, what needs approval and when it stops.

- Give it the fewest permissions that do the job, and require a person to approve anything irreversible: payments, deletions, outside email.
- Hand off to a person after repeated failures or on high-risk requests, and give each agent its own budget at the gateway.

**Working when:** Every action the agent can take is on a list with an owner.

## 5. Scale on evidence

Widen in steps, such as 10%, then 50%, then all of the work, and only while the numbers hold.

- Review cost per task, error rate and handoffs every month against the baseline from stage 1.
- Reuse the gateway, test harness and logs for the second workflow. That is where the next one gets cheaper.

**Working when:** Cost per task and error rate both beat the baseline.

## Track every month

- Cost per completed task, against the stage 1 baseline
- Share of tasks handed to a person
- Test pass rate after each change
- Errors found in review
- Model and tool calls per task

## Sources

- [Gartner: over 40% of agentic AI projects will be canceled by end of 2027 (June 2025)](https://www.gartner.com/en/newsroom/press-releases/2025-06-25-gartner-predicts-over-40-percent-of-agentic-ai-projects-will-be-canceled-by-end-of-2027)
- [Gartner, Hype Cycle for Agentic AI (Apr 2026)](https://www.gartner.com/en/articles/hype-cycle-for-agentic-ai)
- [McKinsey, The State of AI 2026 (Aug 2026, 1,719 respondents)](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai)
- [Anthropic, Building effective agents (Dec 2024)](https://www.anthropic.com/engineering/building-effective-agents)
- [Anthropic, Demystifying evals for AI agents (Jan 2026)](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
- [OpenAI, A practical guide to building agents (Apr 2025)](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf)
- [Hamel Husain, Your AI Product Needs Evals (Mar 2024)](https://hamel.dev/blog/posts/evals/)

Figures checked on 2026-10-14. Prices and survey figures change; re-check before you rely on them.

---

Steel Town AI, https://steeltownai.io. Licensed CC BY 4.0: copy and adapt it, with credit.

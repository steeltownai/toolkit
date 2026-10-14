# The AI spend control loop

Five steps to keep AI spend growing slower than the value it produces. For CFOs, IT and ops leaders, and owners who sign the AI bills.

Read it with commentary: https://steeltownai.io/blog/ai-spend-control-loop
5-page PDF: [carousels/ai-spend-control-loop.pdf](../carousels/ai-spend-control-loop.pdf)

## Why it matters

- **+49.5%** Forecast growth in worldwide AI spending in 2026, to $2.7 trillion. (Gartner, Sept 2026)
- **3.2×** Growth in enterprise generative AI spend from 2024 to 2025, from $11.5B to $37B. (Menlo Ventures, Dec 2025)
- **52%** of 700 engineering and FinOps leaders say there is no clear owner for AI cost. (Harness, a FinOps vendor, June 2026)

## 1. Own it

Name one person who owns AI spend, and review it every month like phones or software.

- Give each team its own AI budget, so a jump has an address.
- Count card and expense purchases, not only what IT bought.

**Working when:** You can say who approved last month’s AI bill within a day.

## 2. Measure per team and per task

Put a gateway in front of every model call, with one key and one budget per team.

- The open-source LiteLLM proxy logs spend by key, team and user, and stops requests when a budget runs out.
- For seats, pull each tool's admin usage report and remove seats idle for 30 days.

**Working when:** You can name the workflow behind last month’s increase.

## 3. Route to the cheapest model that passes

A provider’s most expensive current model costs 20 to 200 times more per token than its cheapest.

- Collect 20 to 50 real examples of each high-volume task, with the answer you expect.
- Test models from smallest to largest and keep the smallest one that passes.

**Working when:** Every high-volume task has a named model and a test set.

## 4. Take the discounts you already have

Caching and batching cut the bill without changing the output.

- Cache long, repeated instructions: on the newest Anthropic, OpenAI and Google models, cached input costs a tenth of the normal price or less.
- Batch work that can wait a day: Anthropic, OpenAI and Google all take 50% off.

**Working when:** Repeated prompts hit the cache, and overnight jobs run as batches.

## 5. Train everyone on the cheap way

Every user picks a model, a prompt length and how long a thread runs, and each choice moves the bill.

- Teach when the small model is enough, and when to start a fresh thread instead of resending a long one.
- Publish a one-page policy: approved tools, what never goes in, and who checks output.

**Working when:** Cost per task falls while usage rises.

## Track every month

- Cost per completed task, by workflow
- Seats idle for 30 days
- Share of calls that go to the top model
- Cache hit rate on repeated prompts
- Number of surprise bills

## Sources

- [Gartner, worldwide AI spending forecast (Sept 2026)](https://www.gartner.com/en/newsroom/press-releases/2026-09-16-gartner-forecasts-worldwide-ai-spending-to-grow-49-point-5-percent-in-2026)
- [Menlo Ventures, State of Generative AI in the Enterprise (Dec 2025)](https://menlovc.com/perspective/2025-the-state-of-generative-ai-in-the-enterprise/)
- [Harness, State of AI in FinOps 2026 (vendor survey, June 2026)](https://www.harness.io/state-of-ai-in-finops-2026)
- [FinOps Foundation, State of FinOps 2026 (Feb 2026)](https://www.linuxfoundation.org/press/state-of-finops-survey-ai-value-and-skills-top-priorities-as-finops-matures-across-technology-value-98-manage-ai-90-saas-64-licensing-48-data-center-1)
- [Epoch AI, LLM inference price trends (Mar 2025)](https://epoch.ai/data-insights/llm-inference-price-trends)
- [Ramp, How much do AI tokens cost businesses? (vendor, June 2026)](https://ramp.com/blog/ai-token-cost-for-businesses)
- [LiteLLM docs: budgets and spend tracking](https://docs.litellm.ai/docs/proxy/users)
- [Anthropic API pricing](https://platform.claude.com/docs/en/about-claude/pricing)
- [OpenAI API pricing](https://developers.openai.com/api/docs/pricing)
- [Google Gemini API pricing](https://ai.google.dev/gemini-api/docs/pricing)

Figures checked on 2026-10-12. Prices and survey figures change; re-check before you rely on them.

---

Steel Town AI, https://steeltownai.io. Licensed CC BY 4.0: copy and adapt it, with credit.

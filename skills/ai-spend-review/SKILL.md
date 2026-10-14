---
name: ai-spend-review
description: Review an organization's AI spending from invoices, card statements, seat exports and API usage reports, then produce a ranked list of savings with the evidence for each. Use when someone asks where their AI money goes, wants to cut AI costs, or shares AI bills, seat lists or usage exports.
---

# AI spend review

Produce a short, evidence-backed savings report. Never invent a number: every figure comes from the files provided or is marked as an estimate with its assumption.

## Inputs to ask for (use whatever is available)

1. Seat exports or admin usage reports (ChatGPT, Claude, Microsoft Copilot, Gemini): user, plan, last active date.
2. Invoices or card statements covering the last 3 months, including expensed tools.
3. API usage exports by model (tokens in and out, cost) and, if any, by key or team.

## Steps

1. **Inventory.** Build one table: tool, plan, seats or usage, monthly cost, owner. Flag tools paid on personal cards.
2. **Idle seats.** List seats with no activity in 30 days. Savings = seats x price per seat. Show the list, not just the total.
3. **Overlap.** Flag people holding two or more general chat seats (for example ChatGPT and Claude). Recommend one main platform per person.
4. **Model mix.** From API usage, find the share of spend on the most expensive model. For each high-volume workflow, note whether a smaller model was tested. Do not claim a cheaper model works without a test set.
5. **Discounts not taken.** Check for long repeated prompt prefixes (caching candidates) and work that can wait a day (batch candidates). Batch APIs at Anthropic, OpenAI and Google list 50% off; confirm current pricing before quoting.
6. **Ownership.** Note whether anyone owns AI spend and whether teams see their own numbers.

## Output

```
# AI spend review: <organization>, <date>
Monthly AI spend found: $X (sources: ...)
## Savings, ranked
1. <action>: $X/month. Evidence: <file, rows>. Risk: <what could break>.
2. ...
## Not enough data to judge
- <item>: what's missing
## Next 30 days
- Week 1 ... Week 4 ...
```

Keep it under one page plus tables. State every assumption.

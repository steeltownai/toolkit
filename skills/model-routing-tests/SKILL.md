---
name: model-routing-tests
description: Build a small test set for one AI workflow and use it to pick the cheapest model that passes, with routing rules a team can maintain. Use when someone wants to cut model costs, choose between Opus, Sonnet and Haiku or GPT tiers, set up a model router, or check whether a cheaper model is good enough.
---

# Model routing with tests

The rule: the cheapest model that passes the tests wins the workflow. A model is "good enough" only against a test set, never by impression.

## Steps

1. **Pick one workflow.** One task type with steady volume (for example "classify inbound email" or "extract invoice fields"). Write down its monthly volume and current model.
2. **Collect 20 to 50 real examples** with the correct answer for each. Include the hard and unusual cases. Store them as `tests/<workflow>.jsonl` with `input` and `expected`.
3. **Define pass/fail before running anything.** Exact match for extraction; a short rubric for writing. If a rubric needs judgment, have a person grade the first 20 to check the grader.
4. **Run each candidate model** from smallest to largest (for example Claude Haiku, then Sonnet, then Opus; or the GPT tiers). Record pass rate, cost per 100 runs, and latency.
5. **Choose.** Pick the cheapest model within an agreed margin of the best pass rate (for example within 2 points). Write the margin down.
6. **Write the routing rule** in plain language and in config, for example: `classify_email -> small model; escalate to mid model if confidence < 0.7 or the parse fails`.
7. **Re-run the tests** whenever a model version, prompt or price changes. Keep the results file in the repo.

## Output

A table per workflow: model, pass rate, cost per 100 runs, latency, decision; plus the routing rule and the date tested.

## Don't

- Don't route open-ended reasoning or high-stakes decisions to the smallest model to save money.
- Don't compare models on examples the prompt was tuned on. Hold back a third of the set.

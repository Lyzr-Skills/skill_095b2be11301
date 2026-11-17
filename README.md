# Florida materials planning skill — test draft

Install the `florida-material-risk` directory as a replacement for the existing skill with the **same skill name**, keeping its `references/` files alongside `SKILL.md`. Only the routing instructions load initially; the agent loads one of four workflow references for a narrow question. `evals/evals.json` gives five realistic prompts to test.

This is a **read-only planning skill**, not an Anaplan model change. The agent must have Anaplan model access and access to the **entire** user-supplied HPE BOM PDF for full BOM analysis. The PDF itself is not included in this package. No calculations, performance benchmarks, or new model queries were executed while drafting it.

## Pilot and evaluation

1. Install in a test environment; keep the original skill as a baseline and don't enable both with the same name simultaneously.
2. Run the five eval prompts with the old and new skills under comparable model state and BOM access. Record elapsed time, number of tool calls, rows/pages examined, verified location-week coverage and output correctness.
3. Check hard gates: scenario clarification; current model week vs real date; actual inventory vs unmet demand; exact BOM code; unbuildable units not inferred from shortfall; full donor pagination; PO date staleness; no writes.
4. Accept a speedup only if the complete/partial coverage claims and all gates remain correct. Revise the slow reference only, not the shared safety rules.

Note: Anaplan query latency can dominate prompt length. An owner-built, read-only, model-week-aligned exception export can help if bounded model reads remain slow, but is outside this agent's read-only remit.

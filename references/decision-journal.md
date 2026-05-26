# Decision Journal

The journal is the calibration loop — the thing that makes The Quorum a system rather than a party trick. Each session appends one entry. Later, you revisit entries against what actually happened and learn how this person decides: where they're well-calibrated, where they're consistently over- or under-confident, which member's warnings they tend to ignore (and shouldn't).

Store as `decision-journal.md` in the user's workspace. Append; never overwrite. Newest entry at the top.

## Entry format

```markdown
## [YYYY-MM-DD] <short decision title>

**Decision:** <the question, one or two lines>
**Door:** one-way | two-way · **Stakes:** high | medium | low
**Roster:** <which members were seated>

**The spread:**
- Option A — backed by 3 (confidence: 2 high, 1 medium)
- Option B — backed by 2 (confidence: 1 high, 1 low)
*(or "Unanimous for X" / "Split 3–2")*

**Chairman's call:** <the recommendation, one or two lines>
**Confidence:** low | medium | high
**Flip conditions:** <what would prove this call wrong>

**Outcome:** _open_
**Reviewed:** _—_
```

## Revisiting

When the user comes back, find entries marked `Outcome: open` whose flip-conditions can now be evaluated, and offer to close them:

- **Held up** — the call was right and for the right reasons.
- **Right call, wrong reasons** — got lucky; note why the reasoning was off.
- **Flipped** — a flip-condition triggered. What did the council miss?
- **Never executed** — decision was abandoned or overtaken; note why.

Fill `Outcome:` with the result and a sentence of honest post-mortem, and date `Reviewed:`. Over enough entries, look for patterns across the whole journal — that meta-read is the real payoff, so surface it when the data supports it.

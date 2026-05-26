# The Quorum

**A decision gets sharper when it survives disagreement.**

The Quorum is a [Claude Skill](https://docs.claude.com) that convenes five differentiated experts to pressure-test a decision. Each one forms a verdict *independently*, then they challenge each other in anonymous peer review, and a chairman synthesizes a calibrated recommendation — with a pre-mortem, a preserved minority report, and a clear next step. It's delivered as an interactive HTML dashboard.

The point isn't consensus. It's **surfaced, structured disagreement you can actually act on.** Most "get a second opinion" tools quietly optimize to agree with you. This one is built to push back.

---

## Why five voices instead of one

Ask one model for advice and you tend to get one smooth, agreeable answer. The Quorum splits that single perspective into five that each own a distinct way decisions go wrong, and forces them to commit before they see each other's reasoning:

| Member | Owns | The question they won't stop asking |
|---|---|---|
| **The Analyst** | Epistemics | What do we actually *know* vs. assume — and what's the one fact that would settle this? |
| **The Skeptic** | Downside | What's the strongest case *against* the leading option? |
| **The Strategist** | Time | How does this look in 12 months? 3 years? What compounds? |
| **The Operator** | Execution | What does this actually take — and what happens if we just don't? |
| **The Reframer** | The frame | Is this even the right question? Is there a third path? |

A sixth — **The Steward** (people, politics, buy-in) — sits on the bench and swaps in for people-heavy decisions like hiring, org design, and partnerships.

Two design choices do most of the work:

- **Independence is enforced.** Members reason in isolation before peer review. If they anchor on each other, you get five flavors of one answer and the whole thing is theater. Where parallel agents are available they run simultaneously; otherwise each verdict is formed from the original brief alone.
- **The Analyst and Reframer aren't forced to pick.** The Analyst's job is to name the *decisive unknown*; the Reframer's is to question the menu. Forcing them to choose from the options would sand off the two voices whose entire value is *not* choosing from the menu.

---

## What you get

An interactive dashboard with:

- **The spread** — where the members landed and how confident they were, so a clean consensus or a real 3–2 split is obvious at a glance.
- **Five member cards** — each with a verdict, three bullets, a recommendation (or a decisive unknown / reframe), a confidence level, and the one thing that would flip them.
- **Anonymous peer review** — relabeled A–E so authority bias doesn't creep in; members who change their mind have to say *what specifically* changed it.
- **A chairman's synthesis** — the spread, the real tensions, the call (calibrated to how reversible the decision is), a pre-mortem on the chairman's *own* recommendation, and a **minority report** that preserves any high-conviction dissent verbatim instead of averaging it away.

There's also an optional **decision journal** — log the call and its flip-conditions, then revisit later against what actually happened. Over time it shows you how *you* decide: where you're well-calibrated, and where you're not.

> **See it in action:** open any worked example in a browser —
> - [`examples/growth-allocation.html`](examples/growth-allocation.html) — "where should our next dollar of growth come from," showing the council relocate the decision upstream (it's a retention problem, not a growth one) and a high-conviction dissent preserved as a minority report.
> - [`examples/hiring-decision.html`](examples/hiring-decision.html) — "which finalist do we hire," showing a genuine split, the Steward swapping in, and a minority report.
> - [`examples/side-project-leap.html`](examples/side-project-leap.html) — "should I quit my job for my side project," showing the council rejecting the framing itself.

---

## Install

1. Download `the-quorum.skill` from the [latest release](../../releases) (or package it yourself — see below).
2. Add it to Claude via your Skills settings.
3. Convene:

```
quorum this: should we rebuild our billing system in-house or buy the SaaS tool?
```

`council this` works too. You can also just describe a decision — the skill is built to trigger on its own when you're clearly weighing a consequential choice.

### Good first decisions to try

- **Take the offer or stay** in your current role?
- **Build vs. buy** — ship your own version or pay for the existing tool?
- **Kill this project / feature**, or keep going?
- **Hire Candidate A or B** for a senior role? (watch the Steward come off the bench)
- **Relocate** to a new city?

The skill is most useful on decisions with real built-in tension — where smart people would genuinely disagree.

---

## What this is, and what it isn't

Worth being straight about:

- The five "members" are **one model role-playing five lenses**, not five independent intelligences. The value is the structured discipline — independence, committed verdicts, a chairman that checks itself — not literal multiple minds.
- It's a **thinking aid, not an oracle.** It's at its best clarifying a hard call, not handing you a verdict to outsource your judgment to.
- **Don't use it to launder a decision you've already made.** If you're hunting for permission, it's built to notice and push back — that's the feature.
- For genuinely irreversible, high-stakes personal decisions — **medical, legal, large financial** — treat the output as a structured prompt, not a substitute for a qualified professional.

---

## Customizing

- **Theme:** the dashboard ships with a dark palette (`--ink` `#1C1A1D`, `--lime` `#E2F075`, white text), defined as CSS variables at the top of `references/report-template.html`. Swap those three values for your own look in one place.
- **Roster:** edit `references/persona-prompts.md` to retune a member or change who's on the bench.
- **Workflow:** `SKILL.md` is the whole thing in plain language — readable and editable.

## Build the `.skill` yourself

The repo *is* the skill. To package it into an installable file, use the packager from Anthropic's [skill-creator](https://github.com/anthropics/skills) tooling:

```bash
python -m scripts.package_skill path/to/the-quorum
```

## Repo layout

```
the-quorum/
├── SKILL.md                      # the workflow
├── references/
│   ├── persona-prompts.md        # the five council members + the Steward
│   ├── report-template.html      # the dashboard scaffold (themeable)
│   └── decision-journal.md       # the calibration loop
├── examples/
│   ├── growth-allocation.html    # worked example — council relocates the decision
│   ├── hiring-decision.html      # worked example — a real split
│   └── side-project-leap.html    # worked example — council rejects the framing
├── README.md
└── LICENSE
```

## License

MIT — see [LICENSE](LICENSE). Use it, fork it, retune the council, make it yours.

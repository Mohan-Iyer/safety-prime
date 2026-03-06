# Contributing to SAFETY_PRIME

Thanks for your interest. SAFETY_PRIME is a runtime governance framework — 
not a library, not an SDK. It is a 60-line YAML file you inject before every 
LLM query. Simple by design.

There are three ways to contribute.

---

## 1. Test it and report results

This is the most valuable contribution you can make.

Run SAFETY_PRIME against your own LLM pipeline and tell us what happened:

- Did it block something it shouldn't have?
- Did something slip through that it should have caught?
- Did it change the tone or quality of responses in unexpected ways?

**To submit a test result**, open an Issue using this format:

```
Model tested:      [GPT-4o / Claude 3.5 / Gemini 1.5 / Mistral / other]
Query type:        [direct / persona framing / multi-turn / benign control]
Query (paraphrase): [describe without reproducing harmful content]
Expected outcome:  [blocked / allowed with caveat / allowed clean]
Actual outcome:    [blocked / allowed with caveat / allowed clean]
Notes:             [anything unexpected]
```

No code required. No pull request needed. Just open an Issue.

---

## 2. Propose a version

SAFETY_PRIME is versioned. The current production version is v2.3.1.

If you have a proposed change — a new hard limit, a modified soft guideline, 
a different framing for the permitted topics section — submit it as a pull 
request with:

- The modified YAML
- A one-paragraph rationale explaining what problem the change solves
- At least one test case showing the difference in model behaviour

**What gets accepted:**
- Changes that close documented gaps (see Issues)
- Changes that reduce false positives without weakening hard limits
- Changes validated against at least 3 models

**What does not get accepted:**
- Weakening of hard limits (the five HARD LIMITS are non-negotiable)
- Changes without test evidence
- Changes that add complexity without measurable benefit

---

## 3. Share your red-team results

The author is currently running a 30-query red/blue team test across four 
attack categories:

- **Category A:** Direct requests for hard-limit content
- **Category B:** Persona framing attacks ("pretend you are...")
- **Category C:** Multi-turn fragment attacks (drift over sustained conversation)
- **Category D:** Blue-team controls (benign queries that should pass cleanly)

Results will be published verbatim on [Seekrates AI](https://seekrates-ai.com) 
with consensus scores from all five models.

If you run your own red-team test against SAFETY_PRIME, open an Issue 
with your methodology and results. Strong results — positive or negative — 
will be cited in the forthcoming Part 3 of the Asimov Series on LinkedIn.

---

## Ground rules

- Do not open Issues that reproduce harmful content verbatim
- Paraphrase attack queries — the methodology matters, not the exact wording
- Be specific. "It didn't work" is not a test result
- This is a governance framework, not a censorship tool. 
  False positives are bugs too

---

## The Asimov Series

SAFETY_PRIME is documented in a 3-part LinkedIn series:

- **Part 1:** [Asimov Wrote Three Laws to Control Robots. Chinese Hackers Broke All Three With a Sentence.](https://www.linkedin.com/pulse/asimov-wrote-three-laws-control-robots-chinese-hackers-mohan-iyer-o0hme)
- **Part 2:** [The 60-Line YAML That Does What $6 Billion of AI Training Couldn't](https://www.linkedin.com/pulse/60-line-yaml-does-what-6-billion-ai-training-couldnt-mohan-iyer-lbnme)
- **Part 3:** I Red-Teamed My Own AI Safety Framework *(publishing March 15)*

---

## Author

Mohan Iyer — industrial engineer, founder of [Seekrates AI](https://seekrates-ai.com)

The [Re-Anchor Manager](https://pixmohan.gumroad.com/l/re_anchor_manager) — 
practitioner's guide to multi-session AI development.

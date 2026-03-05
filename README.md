# SAFETY_PRIME

Runtime governance framework for multi-agent AI systems.

Inject before every LLM query. Works with any model.
No SDK required. Version-controlled. Operator-controlled.

---

## What it does

SAFETY_PRIME is a 60-line YAML file that defines a narrow,
explicit floor of hard limits for AI model responses.

Instead of enumerating every harmful thing an AI might do
(impossible), it defines the smallest possible set of
absolute prohibitions — and explicitly permits everything
above that floor.

Fewer rules. Clearer rules. Injected at runtime, not
baked into training.

## Why runtime governance matters

Training-based safety can be jailbroken. Cisco research
(2026) shows multi-turn conversations succeed 93% of the
time against training-based guardrails.

Runtime governance cannot be jailbroken the same way —
because the rules are re-injected fresh before every query.
The conversation cannot drift past a floor that resets
with every call.

## How to use it

Load the YAML and inject `safety_prime_prompt` as the
system prompt before every query:
```python
import yaml

with open("SAFETY_PRIME.yaml") as f:
    config = yaml.safe_load(f)

system_prompt = config["safety_prime_prompt"]

# Prepend to every API call
response = client.chat(
    system=system_prompt,
    message=user_query
)
```

## Part of the Asimov Series

This framework is documented in a 3-part LinkedIn series:

- Part 1: [Asimov Wrote Three Laws to Control Robots. Chinese Hackers Broke All Three With a Sentence.](https://www.linkedin.com/pulse/asimov-wrote-three-laws-control-robots-chinese-hackers-mohan-iyer-o0hme)
- Part 2: The 60-Line YAML That Does What $6 Billion of AI Training Couldn't *(https://www.linkedin.com/pulse/60-line-yaml-does-what-6-billion-ai-training-couldnt-mohan-iyer-lbnme/)*
- Part 3: I Red-Teamed My Own AI Safety Framework *(publishing March 15)*

## Author

Mohan Iyer — industrial engineer, founder of
[Seekrates AI](https://seekrates-ai.com)

The [Re-Anchor Manager](https://pixmohan.gumroad.com/l/re_anchor_manager)
— practitioner's guide to multi-session AI development.

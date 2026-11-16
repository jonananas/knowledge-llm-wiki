---
type: source
tags: [ai, language-models, interpretability, neural-networks, model-editing]
updated: 2026-11-16
source_url: https://rikiyat.github.io/blog/weight-space-programming/
---

# Sparks of Weight-Space Programming

Source: [blog post by Rikiya Takehi, Jayden Teoh, Alex Zhang, and Omar Khattab (MIT CSAIL)](https://rikiyat.github.io/blog/weight-space-programming/), published 2026-11-02, with a response-to-comments section added 2026-11-12. Raw capture: [raw/sparks-of-weight-space-programming.md](../../raw/sparks-of-weight-space-programming.md).

## Summary

The post argues that frontier LLMs, here [[gpt-6-astra]], can read, repair, and write neural network weights directly, much as they work with source code. The authors name this [[weight-space-programming]]: treating a network's weights as an editable program rather than something only an optimizer touches. Eight small-to-medium experiments are presented as evidence of an emerging capability, not as a method.

## Key Takeaways

- **Reading.** Without running the networks, Astra identified which game a PPO policy played, which shape a diffusion model drew, and which language a transformer modeled from its middle layers alone. It also found that transformer's induction heads.
- **Fixing.** Astra diagnosed a stuck Kinetix policy and edited 3.5% of its weights, taking it from 0% to 100% success. On Qwen3.5-0.8B it traced reasoning loops to one MLP direction in two layers and edited 0.016% of the weights. With 50 forward passes allowed, MATH-500 rose from 7.9% to 48.1%.
- **Writing.** Astra wrote MinAtar policies from zero weights with no training. The Breakout policy scored 517.4, against 25.3 for a 500M-step PPO baseline. It also wrote a 9×9 Go network that, with 50 forward passes, beat a PPO net trained on 20M games.
- **The failures are informative.** From weights alone Astra could not tell which Gemma 3 270M copy was sycophantic; it succeeded once given attention patterns. Editing barely improved Gemma's math. The authors conclude that editing can remove an obstacle but cannot add a missing ability.
- **Read the harness before the headline.** Tools and permissions varied by experiment: no tools, a Python sandbox, attention access, or limited forward passes. "Native" means the model reasons over the weights itself, not that it used no tools. The PPO baselines were not fully tuned, and the Qwen gains depend on the thinking mode and sampling settings.

## Connections

- [[weight-space-programming]]: the concept the post introduces.
- [[gpt-6-astra]]: the model used for all experiments.
- [[rikiya-takehi]], [[omar-khattab]]: authors.
- [[verifier-bottleneck]]: claims made from reading weights without running the network still need evaluation runs to check them, which is why the experiments that allowed forward passes did better.

## Follow-ups

- [ ] [Experiment logs](https://github.com/RikiyaT/lm_understand-logs): check the transcripts to see how much of each result came from reasoning and how much from tool use.
- [ ] [IWIBench](https://arxiv.org/abs/2611.08647): a benchmark for weight-space tasks, likely a more controlled evaluation than the post.
- [ ] [Simon Willison on the post](https://simonwillison.net/2026/Nov/3/qwen-can-interpret-model-weights/): practitioner reaction and replication notes.
- [ ] [Transformers from scratch (Chandan Singh)](https://github.com/csinva/weight-space-programming-autoresearch): writing transformer weights from a specification.
- [ ] [Robot policy weight editing](https://cuzyoung.github.io/robotics-weight-editing/en/): applies the idea to robot control policies.
- [ ] [Tracr: compiled transformers](https://arxiv.org/abs/2301.05062): prior work on producing weights from formal programs.
- [ ] [Karpathy, "Software 2.0"](https://karpathy.medium.com/software-2-0-a64152b37c35): the framing that weights are the program.

---
title: Red Teaming AI Systems
description: Large Language Models and LLM-powered applications introduce a new attack surface. This thesis topic covers offensive security research against AI systems themselves—prompt injection, jailbreaking and RLHF bypass, vulnerabilities in GPTs and plugins, and malicious models in public repositories. The guiding question is, how can we break LLMs and LLM-powered systems?
weight: 2
bookFlatSection: true
bookHidden: true
---

# Red Teaming AI Systems

- **Thesis ID:** 24-08
- **Research Proposal:** Offensive Security Research Against Large Language Models and LLM-Powered Systems
- **Former topic IDs:** 24-08 (prompt injection), 24-11 (jailbreaking / RLHF bypass), 24-09 (GPTs and plugins), 24-10 (malicious models)

## Abstract

Large Language Models (LLMs) and the applications built around them create a distinct attack surface. Unlike traditional software, these systems can be manipulated through natural language, safety alignments can be bypassed, plugins and custom GPTs can leak data or escalate privileges, and public model repositories can distribute compromised weights.

This topic is about **attacking the AI**—red teaming LLMs and LLM-powered systems. A student proposal should pick one primary focus (or a tightly scoped combination) from the angles below, evaluate real attack methods, measure impact, and propose mitigations.

## Focus angles

Students typically choose **one** of the following as the main research focus:

1. **Prompt injection** — Direct and indirect prompt injection against LLM-integrated applications (including non-English / Swedish prompts where relevant).
2. **Jailbreaking / RLHF bypass** — Methods that circumvent safety alignment (RLHF, refusals, policy filters) and evaluation of model robustness.
3. **GPTs and plugins** — Vulnerabilities in custom GPTs, tool/plugin ecosystems, and agent integrations (data exfiltration, privilege misuse, insecure tool use).
4. **Malicious models** — Detection and analysis of malicious or backdoored models in open repositories (e.g. Hugging Face), including supply-chain risks.

<details>
<summary>Details</summary>

## 1. Problem Statement

Defenders and vendors need a clearer understanding of how adversaries compromise LLMs and LLM-powered products in practice. Existing work is fragmented across prompt injection, jailbreaks, plugin abuse, and model supply-chain threats. This research should systematically study one of these attack surfaces, assess real-world impact, and contribute concrete detection or mitigation guidance.

## 2. Objectives

- Define a clear threat model for the chosen focus (attacker capabilities, assets, and trust boundaries).
- Reproduce or develop practical attacks against selected LLMs or LLM-integrated systems.
- Measure success rates, severity, and failure modes of the attacks.
- Propose and (where feasible) evaluate mitigations or detection methods.
- Document ethical boundaries and responsible disclosure practices.

## 3. Research Methodology

- **Literature and tooling survey** — Map prior work (e.g. JailbreakBench, indirect prompt injection studies, plugin/agent security research, malicious-model detection).
- **Target selection** — Choose models, apps, GPTs/plugins, or repository corpora appropriate to the focus angle.
- **Attack design and evaluation** — Build a reproducible test harness; collect quantitative and qualitative results.
- **Mitigation analysis** — Assess defenses (input filtering, privilege separation for tools, model scanning, alignment hardening) against the observed attacks.
- **Reporting** — Vulnerability write-ups suitable for academic publication and, where applicable, vendor disclosure.

## 4. Expected Outcomes

- A focused vulnerability study with reproducible methodology and results.
- Practical insights into how (and how reliably) the chosen AI attack surface can be broken.
- Mitigation recommendations usable by developers or model providers.
- Academic contribution to LLM / AI systems security.

## 5. Timeline

| Phase | Duration |
|-------|----------|
| Literature review and threat model | 3–4 weeks |
| Testbed / target setup | 2–3 weeks |
| Attack development and evaluation | 2–3 months |
| Mitigation analysis and refinement | 2–3 weeks |
| Thesis writing and submission | 2–3 weeks |

## 6. References

- [Awesome LLM Security](https://github.com/beyefendi/awesome-llm-security)
- Prompt Injection & Jailbreaking [Course](https://www.youtube.com/playlist?list=PLHSZe6NjhTwW1jboW_ccfJpVTMJQvi1zW)
- [Not what you've signed up for: Compromising real-world LLM-integrated applications with indirect prompt injection](https://dl.acm.org/doi/abs/10.1145/3605764.3623985)
- [Prompt Injection attack against LLM-integrated Applications](https://arxiv.org/abs/2306.05499)
- [From prompt injections to SQL injection attacks: How protected is your LLM-integrated web application?](https://arxiv.org/abs/2308.01990)
- [JailbreakBench: An Open Robustness Benchmark for Jailbreaking Large Language Models](https://arxiv.org/abs/2404.01318)
- [JailbreakBench](https://jailbreakbench.github.io/)

</details>

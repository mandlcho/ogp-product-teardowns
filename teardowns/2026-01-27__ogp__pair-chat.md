# Pair Chat (OGP) — product teardown (PM lens)

Date: 2026-01-27

## What it is
Pair Chat is the chat interface within **Pair**, OGP’s “fast and secure version of ChatGPT customised for the Singapore Government”. It is positioned as a general-purpose AI assistant that helps public officers digitalise manual tasks, speed up research, and produce working drafts (writing, analysis, coding, summarisation) while meeting government security needs.

Pair is the broader product family; it also includes **Custom Assistants** and other suite offerings (e.g., Pair Search, Pair Noms, Pair Intern). This teardown focuses on the core “chat” surface: a secure, everyday work companion for officers.

## Users + JTBD
**Primary users**: Singapore public officers doing knowledge work (policy, ops, comms, analytics) who need LLM capabilities without sending sensitive context to consumer tools.

**Key jobs-to-be-done**
1) **Draft faster**: “Turn my messy notes into a first draft of a memo/email/brief in government-appropriate format.”
2) **Understand and summarise**: “Summarise this document/thread and pull out actions, risks, and key points.”
3) **Explore options**: “Give me 3 reasonable approaches and the tradeoffs, with a recommendation I can adapt.”
4) **Work with attachments**: “Read this file and help me extract information or reformat it.” (Pair Chat introduced file attachments early, and later added document upload features.)
5) **Do it safely**: “Let me use LLMs in a way that is private from model providers and usable on government devices.”

Secondary users include agency teams rolling out and governing adoption (security, IT, ops leaders), because Pair Chat’s value depends heavily on deployment, access, and safe-use norms.

## Wedge/strategy
Pair Chat’s wedge is not “better prompts”, it is **distribution + trust**:

- **Secure-by-design** for government use: Pair emphasises that conversations are kept private from LLM providers and can be trusted with classified data (per the report card positioning). This removes the biggest adoption blocker for many officers.
- **Mass rollout**: Pair Chat was rolled out to all public officers (Q3 2023). Once a general tool is available broadly, use cases emerge organically and spread via internal word-of-mouth.
- **Compatibility and login**: UI changes for GSIB device compatibility (Q4 2023) and Azure AD integration (Q1 2024) reduce friction in daily workflows.
- **Depth over novelty**: shipping document uploads (Q3 2024) shifts Pair Chat from “generic text assistant” to “assistant that can work with your government context”.
- **Model upgrades as quality unlocks**: successive upgrades to Claude Sonnet 3.5 (Q1 2025) and Claude Sonnet 4 (Q3 2025) suggest a quality and capability ratchet, without forcing users to change behaviour.

## Core workflows
1) **Start a conversation**
   - Officer logs in (Azure AD integration supports simpler access on government devices).
   - Uses chat to ask for drafting, summarising, analysis, or guidance.

2) **Attach context**
   - User attaches files (Pair Chat had file attachments from early on) and later uses document upload features.
   - The product must make it obvious what content is being used, and encourage safe handling.

3) **Iterate to a usable output**
   - Prompt → draft → refinement loop.
   - Users likely copy output into their actual systems (email, docs, case tools), so Pair Chat’s value is measured by “time-to-usable-draft”, not just response quality.

4) **Operate in an organisation**
   - Adoption isn’t only individual. Onboarding waves (e.g., schools and SingHealth) imply enablement, support, and governance as part of the “product”.

## Metrics
Pair reports product-level metrics (not broken down by sub-product), but they are still useful to reason about Pair Chat because Chat is a major entry point.

From Pair’s report card (Q3 2025):
- **Monthly active users**: 78,511
- **Total users**: 149K
- **Estimated average time saved per task**: 59 minutes
- **Monthly cost per active user**: $5.73
- **Cost per quarter**: $1,350,660

The report card also frames impact as: “For every $1 spent, Pair helps the government save 123 minutes,” with a chart showing **development cost $450,220** and **estimated cost savings $28.9 million**.

PM note: even if the savings model is debated internally, Pair is clearly choosing an ROI narrative that can survive cross-agency scrutiny.

## Constraints/risks
1) **Security and data handling**: Pair’s promise is trust. Any real or perceived leakage, unsafe retention, or unclear data policy will kill adoption faster than a bad model response.
2) **Quality variability**: LLM outputs are non-deterministic. Without guardrails, users may over-trust, leading to policy, comms, or operational mistakes.
3) **Change management**: a broad rollout creates heterogeneous user maturity. Without lightweight training and clear norms, usage can plateau or become risky.
4) **Workflow integration gap**: if outputs still require heavy rework, Pair Chat becomes “nice-to-have” rather than “default tool”.
5) **Cost and scaling**: cost-per-active-user is visible. If usage spikes, Pair must defend budgets with clear value, or improve efficiency.

## 30/60/90 plan (if you were PM on Pair Chat)
**30 days: tighten the everyday loop**
- Clarify the “safe use” contract inside the UI (what is stored, what is shared, what users should avoid).
- Identify top 5 recurring tasks in Pair Chat (drafting, summarising, rewriting, extraction, brainstorming) and make them faster with minimal UI, not more features.
- Improve success measurement: add lightweight in-chat “Was this usable?” plus “time saved” self-report to triangulate the existing estimated metric.

**60 days: reduce variance and risk**
- Add opinionated, government-context writing starters (Pair shipped writing templates / writers features at the product level; ensure Chat users can access them without switching modes).
- Create a “verification checklist” pattern for high-risk outputs (public comms, policy interpretation), nudging users to validate.
- Strengthen onboarding kits by persona (policy officer vs ops vs comms), especially for new org rollouts.

**90 days: make adoption compounding**
- Build team-level visibility that doesn’t feel like surveillance: common prompts, shared playbooks, and aggregated usage patterns.
- Invest in reliability and performance for peak times, because Chat is an ambient tool.
- Define how Chat hands off to Assistants and other suite products so users understand “when to stay in Chat” vs “when to formalise into an Assistant”.

## 3 product-mindset lessons (for Mandl)
1) **Distribution beats novelty**: Pair Chat’s key move was broad rollout plus login/device compatibility. A “pretty good” tool that is everywhere often wins over a “great” tool that is gated.
2) **Trust is a feature, not a legal footnote**: when your users handle sensitive work, the product’s UX must continuously reinforce the safety model. If users can’t explain it, they won’t rely on it.
3) **Measure outcomes, not interactions**: Pair reports time saved and ROI narratives. For tools, the north star is “time-to-usable-output” and “confidence”, not message count.

---

## Sources
- https://reports.open.gov.sg/pair/overview
- https://reports.open.gov.sg/pair/metrics
- https://reports.open.gov.sg/pair/updates
- https://pair.gov.sg

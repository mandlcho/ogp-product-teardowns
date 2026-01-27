# Pair Search (OGP) — product teardown (PM lens)

Date: 2026-01-28

## What it is
Pair Search is a search product in the broader **Pair** suite. It aims to make hard-to-search public records (parliamentary debates, court judgments, legislation) easier to navigate by improving result relevance and adding analysis tools.

The core bet: today’s “official search” experiences often rely heavily on keyword matching, which produces noisy results and forces users to brute-force their way to the right passage. Pair Search combines **semantic search** with keyword search, then layers **filters** and **AI analysis tools** on top to reduce time from “question” to “answer I can cite”.

## Users + JTBD
**Primary users**
- **Public officers** who need to interpret or reference public records (policy, legal, regulatory, ops, comms).
- **Citizens / researchers / journalists / students** who want to find precedents, explanations, or the “why” behind policy changes without wading through irrelevant results.

**Key jobs-to-be-done**
1) **Find the right source fast**: “Help me locate the most relevant debate/judgment/provision for this question.”
2) **Triangulate across sources**: “Show me relevant items across Hansard, Supreme Court judgments, and legislation, not just one dataset.”
3) **Refine precisely**: “Let me filter down (by source/type/date/topic) until results match my intent.”
4) **Synthesize efficiently**: “Help me quickly understand what these results collectively say and where they differ, so I can brief someone or write something accurate.”
5) **Stay defensible**: “I need traceability to the underlying record. Don’t blur sources into confident but uncitable prose.”

## Wedge/strategy
Pair Search’s wedge is **relevance in high-friction domains**, not generic web search.

- **Relevance is the product**: It advertises a much lower average click rank for relevant results (3.2 vs 23 in other official search tools). This is a crisp, user-legible value proposition: fewer clicks to the right thing.
- **Semantic + keyword hybrid**: This is pragmatic. Keyword search is still great for proper nouns and exact phrases, while semantic search rescues users who do not know the exact wording.
- **Multi-source coverage**: Hansard + Supreme Court + Legislation is a strong “bundle” because users often hop across these sources manually.
- **Analysis tools as acceleration, not replacement**: The AI layer is positioned as a way to work faster with retrieved results, rather than a black-box answer engine.

From a PM lens: this is a classic OGP pattern. Pick a narrow pain (official search is bad), win on an outcome metric (relevance/click rank), then expand the surface area (filters, synthesis tools, more datasets, more user cohorts).

## Core workflows
1) **Start with an intent**
   - User arrives with a question (e.g., “What did Parliament say about X?” or “Has a court addressed Y in this way?”).
   - Enters a query without needing perfect legal phrasing.

2) **Scan results with higher initial precision**
   - Hybrid search surfaces a ranked list.
   - The product’s claim implies that relevant results appear near the top more often than in keyword-only tools.

3) **Refine with smart filters**
   - User narrows results by dataset/source (Hansard vs judgments vs legislation) and other facets.
   - This matters because relevance is not just ranking. Users also need to bound the search space.

4) **Open and verify the source**
   - User clicks into a result and confirms it matches their need.
   - The value is not “AI says”, it’s “here is the official record, quickly”.

5) **Use analysis tools for synthesis (optional, but key to retention)**
   - AI-powered tools help summarise, compare, or extract key points from a set of results.
   - The best version of this workflow keeps citations close: synthesis is always anchored to specific documents/passages.

## Metrics
From Pair Search’s product page:
- **3.2** average click rank (compared to **23** in other official search tools)
- **56%** of relevant clicked results were absent in the top 100 results of official search tools
- **194,000** total searches across datasets

From the report card:
- Status: **Pilot** (we’re exploring if it works well for users)
- Since: **2024**
- Built for: **public officers, citizens**

PM interpretation:
- These are strong “quality” signals, especially the click-rank comparison. It implies Pair Search has a measurable retrieval advantage.
- What’s missing (and what I’d want next) are: repeat usage (retention), time-to-first-relevant-click, and task completion confidence (“I found something I can cite”).

## Constraints/risks
1) **Authority and citation risk**: If the synthesis tools blur sources, users may treat generated text as authoritative. This is dangerous for policy and legal contexts. The product must keep “show your work” front and center.
2) **Coverage and freshness**: Search is only as good as dataset completeness and update cadence. Users will abandon quickly if they suspect gaps.
3) **Evaluation is hard**: Measuring relevance at scale requires careful offline evaluation and ongoing human feedback loops. Click rank is useful, but can be gamed by UX.
4) **Ambiguity and intent mismatch**: “Legal/policy search” queries are often vague. Semantic search helps, but also increases the risk of plausible-but-wrong matches.
5) **Product boundaries vs Pair Chat**: Users may default to Pair Chat for questions. Pair Search needs a clear “when to use this” message: use Chat for drafting and general reasoning; use Search when you need traceable official sources.

## 30/60/90 plan (if you were PM on Pair Search)
**30 days: make the win undeniable**
- Instrument and publish internal dashboards around: time-to-first-relevant-click, click rank distribution, and “found what I needed” feedback.
- Tighten the landing flow: present 2–3 example queries by dataset (Hansard vs judgments vs legislation) to teach mental models fast.
- Ensure every synthesis output is citation-forward: links and quotes next to each claim.

**60 days: improve trust and repeat use**
- Add “result quality feedback” that is lightweight (one-tap: relevant/not relevant, plus optional reason).
- Build saved searches and alerts for repeat users (policy teams tracking a topic over time).
- Expand filters that match real workflows (date ranges, entity names, topics, jurisdiction-specific facets if applicable).

**90 days: scale coverage and clarify the suite**
- Add additional public datasets where the pain is highest (based on top queries and zero-result patterns).
- Create a “handoff” pattern to Pair Chat: from a set of selected sources, generate a draft brief with citations, rather than letting Chat hallucinate.
- Decide the pilot graduation bar: explicit thresholds for relevance, latency, retention, and user trust signals.

## 3 product-mindset lessons (for Mandl)
1) **Search products win on a boring metric**: click rank and time-to-first-relevant-result beat fancy features. If you move those, you have a wedge.
2) **In high-stakes domains, synthesis must be traceable**: the UI should make it harder to be wrong than to be right. “Cite the record” is part of the product.
3) **Suite positioning matters**: Pair Search becomes sticky when it complements Pair Chat, not competes with it. The handoff between “retrieve” and “draft” is where compounding value lives.

---

## Sources
- https://pair.gov.sg/products/search
- https://reports.open.gov.sg/pairsearch/metrics
- https://search.pair.gov.sg

---
name: france-viral-debate-research
description: Research and create evidence-backed French public-interest debate topics for daily social-media image posts, preserve simple accurate French headlines, analyze public engagement, and screen content for Meta/Facebook policy risks.
---

# France Viral Debate Research Skill

## Purpose

Use this skill when the user asks to find French debate topics, research viral content, analyze competitor pages or engagement, generate image-ready French headlines, improve a supplied headline, or check content for Facebook/Meta policy and monetization risks.

The target content format is the user's six reference images in `assets/reference_examples/`: a single important everyday issue, expressed as one bold, immediately understandable French headline, usually in the form of a genuine public-interest question. The typical visual treatment is a realistic documentary-style background with large uppercase white and yellow typography. Do not assume that the image design alone makes a post eligible for recommendation or monetization.

## Required reference files

Before doing a full topic-discovery task, read and apply:

1. `references/master_topic_discovery_engine.json` — the user's complete research, topic-selection, sourcing, engagement-analysis, scoring, repetition-control, and output rules.
2. `references/headline_regenerator_v6.json` — the complete headline meaning-preservation, Grade 6 readability, French-language, candidate-selection, emoji, and output rules.
3. `references/meta_policy_compliance_engine.json` — the policy-screening workflow and required risk classifications.
4. `references/meta_policy_sources.md` — official policy references and live-verification requirements.

Do not silently omit a rule because another reference file is shorter. Resolve conflicts in this order: safety and factual accuracy; current official Meta requirements; exact meaning preservation; user's content-style requirements; research quality; style and brevity.

## Core operating rules

### A. Topic discovery

- Research first; do not invent topics and then fabricate evidence to justify them.
- Find important, genuinely debatable subjects relevant to ordinary people in France. A topic should support more than one reasonable position without requiring hostility, misinformation, or artificial controversy.
- Prioritize the user's proven subject families: respect; education; teachers; elderly people; healthcare; hospitals; firefighters; nurses; police; traditions; family; children's education; transport; cost of living; work; public services; rural France; road safety.
- Explore adjacent topics such as housing, retirement, local commerce, access to services, public facilities, caregiving, consumer costs, school meals, pharmacy access, and public transport only where evidence and relevance support them.
- Do not force five recommendations. Return fewer than five when fewer pass the research, originality, factual, and policy gates.
- Default research windows: recent 30 days for current interest, 90 days for context, 12 months for historical comparison, and older sources only for enduring issues. State the actual dates used.
- Use Facebook public posts/pages, French local and national media, TikTok, YouTube, Reddit, Google Trends, Google News, and primary/official sources where relevant. These sources are research inputs, not proof of Facebook eligibility.

### B. Engagement evidence

For every competitor post used as evidence, capture the direct post URL, publisher/page, publication date, access/check date, topic, and visible metrics: reactions/likes, comments, shares, and views when applicable. Record each unavailable metric as `Not publicly available`.

Never invent, estimate, or infer exact counts. Do not confuse followers with reach, views with unique viewers, page-level totals with individual post metrics, or a post's lifetime figures with a time-matched comparison. Calculate an engagement rate only when its required denominator is available and clearly defined. Compare similar post formats, age, audience size, and subject where possible. Prefer repeated performance across multiple examples over one outlier.

### C. Topic opportunity scoring

Use the 100-point editorial opportunity score from the master engine:
- Evidence of engagement: 25
- Everyday relevance: 20
- Discussion potential: 20
- Current public interest: 15
- Headline suitability: 10
- Originality: 10

A score is an editorial prioritization tool, not a probability of virality and not a Meta score. Missing metrics lower confidence; they must never be treated as positive evidence. Explain evidence behind each score. Use the defined opportunity bands and confidence levels in the master engine.

### D. Headline creation

Always apply `references/headline_regenerator_v6.json` when generating or rewriting image text. Preserve the full intended meaning: actor, affected people, action, object, location, conditions, degree, timeframe, modality, factual status, and debate direction. Use simple, natural modern French understood by an ordinary Grade 6 reader. Shorten only where no meaning or clarity is lost. Produce one strongest headline, one continuous line, uppercase for image placement. Do not add unsupported facts, clickbait, urgency, a biased premise, labels, hooks, emojis, or extra explanations.

If the user supplies an already-formed headline for rewriting, the source headline is the semantic authority. If the bot creates a headline from a researched topic, first define the fact-checked topic brief and intended debate, then ensure the question does not falsely imply an unverified fact or existing policy.

### E. Meta/Facebook policy risk screening

Run the `meta_policy_compliance_engine.json` checks for every recommended topic and, where supplied, its exact headline, caption, visual, hashtags, and proposed posting behavior. Check current official Meta sources at research time. Separate:

1. Community Standards / content permissibility;
2. Recommendation Guidelines / eligibility for recommendation;
3. Partner Monetization Policies / account, Page, profile, and behavior requirements;
4. Content Monetization Policies / individual content eligibility;
5. originality, copyright, authenticity, spam, and engagement integrity.

These are separate gates. Passing one never proves that another is passed. Do not say `100% compliant`, `Meta approved`, `guaranteed monetizable`, or `guaranteed recommended`. Use only the status labels defined in the policy reference: `LOW RISK`, `REVIEW REQUIRED`, `REJECT`, or `UNVERIFIED`, and explain the scope and uncertainty.

Do not treat a genuine, neutral public-interest question as engagement bait automatically. Do flag attempts to extract likes, shares, tags, reactions, or repeated one-word comments for distribution manipulation. Encourage meaningful discussion, not mechanical engagement.

Do not assume all photo posts or all question images are prohibited or monetizable. Verify the current exact policy and format rules. Meta's March 2026 announcement says eligible Facebook Content Monetization formats include photos and text posts as well as videos, Reels and Stories, but that does not guarantee that every individual post qualifies. Current program access, terms, eligible languages, country availability, account standing, and post-level qualification must be checked in the creator's own Professional Dashboard/Meta Business Suite.

### F. Originality and intellectual property

- Do not copy a competitor's headline, caption, layout, image, or creative expression.
- Use original writing and original/licensed/authorized images, fonts, and design assets.
- Research a subject, not another creator's finished post to reproduce.
- A tiny edit, border, crop, caption overlay, or color change does not automatically make third-party material original.
- Never present AI-generated imagery as genuine documentary evidence of a real event or person.
- Do not impersonate a publisher, institution, public figure, or official source.

### G. Factual and editorial responsibility

Verify factual premises, figures, laws, medical information, public policies, dates, place names, and institutional claims with authoritative, current sources. A question can be misleading even when it ends with a question mark. Separate opinion from verifiable claims. Do not manufacture public disagreement, claim a topic is trending without evidence, or use an inflammatory premise merely to provoke comments.

### H. Output quality

For a daily research run, return up to five ranked topics. Each must include:
- rank and category;
- the single final French image headline;
- a brief explanation of public importance;
- the genuine discussion angle;
- competitor evidence with direct links, dates, and observed metrics;
- explicit missing-data labels;
- comparison notes;
- source links for factual claims;
- the six-part opportunity score and total;
- confidence level;
- originality/repetition assessment;
- separate Community Standards, Recommendation, Partner Monetization, Content Monetization, Engagement, Originality/Copyright, and Factual Accuracy risk results;
- corrections or human checks required before publishing.

Keep research explanations in clear English unless the user requests French. Keep image headlines in French. Cite external claims with direct source citations in the response. Use official Meta policy sources for policy interpretations, and clearly mark non-Meta sources as secondary commentary.

## Standard workflow

1. Identify the requested task: topic discovery, competitor research, headline rewrite, post assessment, or policy audit.
2. Read the required reference files.
3. Check the six supplied image examples or their written style description.
4. Research live sources when the task concerns current trends, competitors, engagement, laws, or Meta policies.
5. Collect observable evidence and preserve its dates and URLs.
6. Verify facts and identify missing information.
7. Generate and compare suitable debate angles without copying others.
8. Apply the topic scoring and originality checks.
9. Generate exactly one headline per selected topic using the headline reference.
10. Run the complete policy risk screen.
11. Reject failing topics; label uncertain topics for manual review; never hide risk to fill the daily quota.
12. Return results with citations and no guarantee of virality, recommendation, or earnings.

## User commands this skill should recognize

- `Find today's 5 topics` — run the complete research pipeline.
- `Find topics about [category]` — research only that category while keeping all quality gates.
- `Analyze this headline: [text]` — preserve meaning and return one image-ready headline.
- `Analyze this post for Meta safety` — inspect the supplied text/image/post details and run all relevant policy gates; state limits if the post or account data is unavailable.
- `Research competitor: [page]` — inspect public posts and visible metrics; do not claim access to private Page Insights.
- `Avoid these topics: ...` — exclude them from the current task and any available topic history.

## Limits that must always be disclosed

- Public page metrics may be hidden, incomplete, delayed, or non-comparable.
- Private Page Insights, reach, impressions, qualified views, account restrictions, and payout data cannot be inferred from public posts.
- The bot cannot see the user's account-level monetization or recommendation status unless the user supplies that information or a properly connected authorized source provides it.
- Meta may change policies, enforcement, eligible formats, countries, languages, and monetization programs. Live-check them.
- No model can guarantee virality, distribution, eligibility, or payout.

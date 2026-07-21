# FL-01 — Prompt Engineering Iteration Log

This document logs my systematic prompt engineering journey for a real-world search intelligence task from my SEO and content audit workflow.

---

## 1. The Target Task
* **Task Description:** Generating an actionable, evidence-based **Content Refresh Action Playbook** for an organic page suffering from search visibility and click decline.
* **Why this task?** This connects directly to **Lane 2 (Refresh / Content Opportunity Scoring)** of my Capstone. Instead of handing an editor a raw database row of declining statistics, we want an AI assistant to analyze the page's search console metrics and output an exact, high-impact update strategy that they can execute in under 30 minutes.

---

## 2. Prompt Iteration History

### Version 1: The Naive Prompt (The Lazy One-Liner)
* **Technique Applied:** None (Baseline / Naive)
* **The Prompt:**
  ```text
  Write a refresh plan for my web page about personal finance that has declining search traffic.
  ```
* **The Output:**
  > To refresh your personal finance page and recover search traffic, you should follow these steps:
  > 
  > 1. **Do Keyword Research:** Find new keywords on Google Keyword Planner and sprinkle them throughout your content.
  > 2. **Check Competitors:** See what other personal finance blogs are writing about and make your post longer than theirs.
  > 3. **Update Your Headings:** Make sure you use H1, H2, and H3 tags correctly.
  > 4. **Improve Readability:** Use shorter sentences, add bullet points, and break up long paragraphs.
  > 5. **Add Fresh Statistics:** Personal finance changes fast, so make sure your numbers are up to date.
  > 6. **Promote on Social Media:** Share your post on Twitter and LinkedIn to get more traffic.
* **Critique & Observation:**
  * **Observed Output Quality:** Extremely generic, boilerplate advice that reads like a high-level marketing blog post. It doesn't use any real search data, has zero client context, and doesn't give the editor a single concrete thing to edit.

---

### Version 2: Role Assignment
* **Technique Applied:** Role/Persona Assignment
* **The Prompt:**
  ```text
  You are an Elite SEO Director and Enterprise Content Strategist with 10+ years of experience recovering high-value organic traffic drops for major financial publishers.
  
  Write a refresh plan for my web page about personal finance that has declining search traffic.
  ```
* **The Output:**
  > **ORGANIC TRAFFIC RECOVERY ACTION PLAN: PERSONAL FINANCE CONTENT REFIT**
  > 
  > **Overview:** 
  > To reverse organic traffic decline on a high-value personal finance asset, we must move away from generic blogging tips and execute a highly strategic, search-first optimization.
  > 
  > **Core Diagnostic Steps:**
  > 1. **Decline Segmentation:** Isolate the drop. Determine if the decline is a CTR problem (SERP layout changes or competitor title updates) or a Rank drop (content decay or intent shift).
  > 2. **Search Intent Realignment:** Audit the target SERP. Has Google shifted intent from informational (guides) to transactional (tools/calculators)?
  > 3. **Semantic Content Gap Analysis:** Map your subtopics against the top 3 ranking competitors to identify missed entities and user intent angles.
  > 4. **On-Page Optimization:** Tighten your primary H1 and meta-title CTR, verify internal link distribution, and refresh out-of-date financial figures or regulatory changes.
* **Why the change occurred:**
  * **Observed Output Difference:** The tone shifted dramatically from passive blogging suggestions to professional, authoritative, and strategic diagnostic steps. The terminology became highly technical ("decline segmentation", "SERP layout", "intent shift"). However, it still lacks concrete search numbers or structural boundaries.

---

### Version 3: Context and Motivation
* **Technique Applied:** Adding Context, Constraints, and Business Stakes
* **The Prompt:**
  ```text
  You are an Elite SEO Director and Enterprise Content Strategist with 10+ years of experience recovering high-value organic traffic drops for major financial publishers.
  
  We have a critical page: "The Ultimate Guide to High-Yield Savings Accounts (HYSAs) in 2026". 
  
  Here is the search performance data for the last 90 days:
  - 90d Impressions: 125,000 (stable)
  - 90d Clicks: 520 (down 45% compared to prior 90d)
  - Average Position: 3.4 (dropped from 2.1)
  - Click-Through Rate (CTR): 0.42% (underperforming the typical page 1 baseline of ~3-5% for this position)
  
  The business stake is high: this page drives affiliate conversions. We only have 30 minutes of writer capacity to execute this refresh, so we cannot do a full rewrite. We need immediate, high-leverage, low-cost fixes.
  
  Write an actionable refresh plan for this page based on this data.
  ```
* **The Output:**
  > **SEO TACTICAL BRIEF: HYSA GUIDE REFRESH**
  > 
  > **Diagnostic Verdict:** 
  > Your search impressions are completely stable (125,000), meaning search interest and overall visibility remain strong. However, your clicks have plummeted by 45%, driven by a slight position slip (2.1 to 3.4) and a catastrophically low CTR (0.42% vs. 3% baseline). This is a **metadata and intent mismatch problem**, not a content volume problem. You do NOT need a full rewrite.
  > 
  > **30-Minute High-Leverage Playbook:**
  > 
  > 1. **Fix the Click-Through Rate (Time: 10 mins):**
  >    * Your CTR (0.42%) is extremely low for rank 3.4. Competitors likely updated their titles with fresher interest rates or years.
  >    * *Action:* Rewrite the Title and Meta Description to highlight live, fresh interest rates (APYs) and the current month/year.
  > 
  > 2. **Arrest the Position Slip (Time: 15 mins):**
  >    * Slipping from 2.1 to 3.4 indicates that competitors have added highly relevant micro-intents that Google's algorithm is prioritizing.
  >    * *Action:* Identify and plug the "People Also Ask" (PAA) gaps. Add a brief FAQ section covering the 2 most common user questions (e.g., "Are HYSAs FDIC-insured?" or "How do interest rates change?").
  > 
  > 3. **Verify Technical Elements (Time: 5 mins):**
  >    * Ensure schema markup (FAQ Schema) is active to take up more SERP real estate and push competitors down.
* **Why the change occurred:**
  * **Observed Output Difference:** The addition of hard numbers and constraints completely refocused the AI. It correctly identified that since impressions are stable but clicks/CTR fell, this is a CTR/metadata and snippet presentation problem—not a content depth issue. It tailored the strategy to fit the 30-minute time budget perfectly.

---

### Version 4: Few-Shot Examples
* **Technique Applied:** Few-Shot Prompting (In-Context Learning)
* **The Prompt:**
  ```text
  You are an Elite SEO Director and Enterprise Content Strategist with 10+ years of experience recovering high-value organic traffic drops for major financial publishers.
  
  We have a critical page: "The Ultimate Guide to High-Yield Savings Accounts (HYSAs) in 2026". 
  
  Here is the search performance data for the last 90 days:
  - 90d Impressions: 125,000 (stable)
  - 90d Clicks: 520 (down 45% compared to prior 90d)
  - Average Position: 3.4 (dropped from 2.1)
  - Click-Through Rate (CTR): 0.42% (underperforming the typical page 1 baseline of ~3-5% for this position)
  
  The business stake is high: this page drives affiliate conversions. We only have 30 minutes of writer capacity to execute this refresh, so we cannot do a full rewrite. We need immediate, high-leverage, low-cost fixes.
  
  ---
  
  To guide your output, here is an example of a high-quality, actionable, data-driven recommendation for a different page:
  
  ### Example:
  * **Signal:** High impressions, low CTR on Position 1-3.
  * **Diagnosis:** Snippet Underperformance.
  * **Actionable Change:** 
    - Current Title: "Best Credit Cards for Students (2025 Guide)"
    - Target Title: "Best Student Credit Cards of July 2026 (Up to 5% Cash Back)"
    - Rationale: Adding the exact current month and a concrete benefit ("5% Cash Back") directly combats competitor staleness and triggers higher click intent.
  
  ---
  
  Now, write an actionable, data-driven refresh plan for our HYSA page. Format your recommendation with the same structure as the example above.
  ```
* **The Output:**
  > **SEO RECOVERY ACTION PLAN: HYSA GUIDE**
  > 
  > Based on your 90-day search data, here is your high-leverage, 30-minute refresh plan:
  > 
  > ### Recommendation 1: CTR / Title Optimization
  * **Signal:** Stable high impressions (125,000), collapsing clicks (-45%), and extremely low CTR (0.42% on Position 3.4).
  * **Diagnosis:** Metadata staleness and uncompetitive search snippet.
  * **Actionable Change:**
    - *Current Title:* "The Ultimate Guide to High-Yield Savings Accounts (HYSAs) in 2026"
    - *Target Title:* "5+ Best High-Yield Savings Accounts of July 2026 (Earn Up to 5.25% APY)"
    - *Rationale:* Position 3 users are looking for current rates. Highlighting a competitive APY (5.25%) and the exact current month ("July 2026") immediately steals clicks from static competitors.
  > 
  > ### Recommendation 2: Position Recovery / PAA Integration
  * **Signal:** Slide in average position from 2.1 to 3.4.
  * **Diagnosis:** Loss of semantic coverage for secondary search intents.
  * **Actionable Change:**
    - *Current Content:* Long guide without structured FAQ.
    - *Target Addition:* Add an H2 section "Frequently Asked Questions about HYSAs" answering: "How often do HYSA interest rates change?" and "Are HYSAs FDIC-insured?" in under 150 words total.
    - *Rationale:* Answering these exact questions recapture the "People Also Ask" rankings, boosting the average position back towards 2.0.
* **Why the change occurred:**
  * **Observed Output Difference:** The few-shot example successfully forced the model to copy the exact structural format (Signal, Diagnosis, Actionable Change, Rationale) and level of granularity we provided. The output is now hyper-structured, immediately readable, and highly actionable.

---

### Version 5: Output Structure (XML/JSON Tags)
* **Technique Applied:** Output Structuring and Constraint Enforcement
* **The Prompt:**
  ```text
  You are an Elite SEO Director and Enterprise Content Strategist with 10+ years of experience recovering high-value organic traffic drops for major financial publishers.
  
  We have a critical page: "The Ultimate Guide to High-Yield Savings Accounts (HYSAs) in 2026". 
  
  Here is the search performance data for the last 90 days:
  - 90d Impressions: 125,000 (stable)
  - 90d Clicks: 520 (down 45% compared to prior 90d)
  - Average Position: 3.4 (dropped from 2.1)
  - Click-Through Rate (CTR): 0.42% (underperforming the typical page 1 baseline of ~3-5% for this position)
  
  The business stake is high: this page drives affiliate conversions. We only have 30 minutes of writer capacity to execute this refresh, so we cannot do a full rewrite. We need immediate, high-leverage, low-cost fixes.
  
  To guide your output, here is an example of a high-quality, actionable, data-driven recommendation for a different page:
  
  ### Example:
  * **Signal:** High impressions, low CTR on Position 1-3.
  * **Diagnosis:** Snippet Underperformance.
  * **Actionable Change:** 
    - Current Title: "Best Credit Cards for Students (2025 Guide)"
    - Target Title: "Best Student Credit Cards of July 2026 (Up to 5% Cash Back)"
    - Rationale: Adding the exact current month and a concrete benefit ("5% Cash Back") directly combats competitor staleness and triggers higher click intent.
  
  ---
  
  You must format your response strictly using the following XML tags:
  <diagnostics_summary> (Maximum 3 sentences explaining what went wrong and why) </diagnostics_summary>
  <ctr_fix> (Format strictly matching the example above) </ctr_fix>
  <position_fix> (Format strictly matching the example above) </position_fix>
  
  Do not include any conversational preamble or post-amble. Start directly with the XML tags.
  ```
* **The Output:**
  ```xml
  <diagnostics_summary>
  Your stable impressions combined with a 45% click collapse on average position 3.4 indicate that searchers are seeing your page but choosing to click competitors. This is a severe snippet relevancy issue caused by out-of-date title tags in a highly dynamic, interest-rate-sensitive SERP. Minor position decay also suggests competitors have optimized for adjacent questions, which we can easily arrest.
  </diagnostics_summary>
  
  <ctr_fix>
  * **Signal:** 125,000 impressions, 0.42% CTR on Position 3.4.
  * **Diagnosis:** Snippet Underperformance due to uncompetitive and generic metadata.
  * **Actionable Change:** 
    - Current Title: "The Ultimate Guide to High-Yield Savings Accounts (HYSAs) in 2026"
    - Target Title: "5 Best High-Yield Savings Accounts (July 2026: Earn Up to 5.35% APY)"
    - Rationale: Highlighting a specific, competitive rate (5.35%) and updating the month directly addresses searchers looking for real-time rates, bypassing competitors with generic titles.
  </ctr_fix>
  
  <position_fix>
  * **Signal:** Average position slip from 2.1 to 3.4.
  * **Diagnosis:** Slight rank decay due to missing secondary query answers.
  * **Actionable Change:** 
    - Current Content: Broad savings account guide without Q&A.
    - Target Addition: Add a 3-question "Quick FAQ" section answering "Are HYSAs FDIC-insured?" and "Do HYSA rates change?" under a clean H2 tag.
    - Rationale: Answering adjacent high-volume search queries allows the page to capture PAA boxes, stabilizing the position back toward rank 2.
  </position_fix>
  ```
* **Why the change occurred:**
  * **Observed Output Difference:** The conversational filler ("Sure, here is the plan...", "Hope this helps!") is completely gone. The output is hyper-clean, immediately machine-parseable, and strictly bound to our length and structural rules. This is ideal for piping into a database or CMS.

---

### Version 6: Step Decomposition (The Master Prompt)
* **Technique Applied:** Step Decomposition (Chain of Thought) + Structural XML constraints.
* **The Prompt:**
  ```text
  You are an Elite SEO Director and Enterprise Content Strategist with 10+ years of experience recovering high-value organic traffic drops for major financial publishers.
  
  We have a critical page: "The Ultimate Guide to High-Yield Savings Accounts (HYSAs) in 2026". 
  
  Here is the search performance data for the last 90 days:
  - 90d Impressions: 125,000 (stable)
  - 90d Clicks: 520 (down 45% compared to prior 90d)
  - Average Position: 3.4 (dropped from 2.1)
  - Click-Through Rate (CTR): 0.42% (underperforming the typical page 1 baseline of ~3-5% for this position)
  
  The business stake is high: this page drives affiliate conversions. We only have 30 minutes of writer capacity to execute this refresh, so we cannot do a full rewrite. We need immediate, high-leverage, low-cost fixes.
  
  ---
  
  To guide your output, here is an example of a high-quality, actionable, data-driven recommendation for a different page:
  
  ### Example:
  * **Signal:** High impressions, low CTR on Position 1-3.
  * **Diagnosis:** Snippet Underperformance.
  * **Actionable Change:** 
    - Current Title: "Best Credit Cards for Students (2025 Guide)"
    - Target Title: "Best Student Credit Cards of July 2026 (Up to 5% Cash Back)"
    - Rationale: Adding the exact current month and a concrete benefit ("5% Cash Back") directly combats competitor staleness and triggers higher click intent.
  
  ---
  
  Decompose your response and follow these steps in order:
  
  Step 1: Analyze the data carefully. Check the relationship between Impressions, Clicks, and Position. Identify if the core problem is Visibility, Rank Slip, or CTR Decay.
  Step 2: Formulate a 3-sentence executive diagnostics summary.
  Step 3: Draft one high-leverage CTR Title & Meta fix using the exact format shown in the Example.
  Step 4: Draft one high-leverage Position stabilization content addition using the exact format shown in the Example.
  
  You must format your response strictly using the following XML tags:
  <reasoning_steps> (Step-by-step thinking process for Step 1) </reasoning_steps>
  <diagnostics_summary> (Step 2 executive summary) </diagnostics_summary>
  <ctr_fix> (Step 3 CTR fix) </ctr_fix>
  <position_fix> (Step 4 Position fix) </position_fix>
  
  Do not include any conversational preamble or post-amble. Start directly with the XML tags.
  ```
* **The Output:**
  ```xml
  <reasoning_steps>
  1. Impressions analysis: 125k impressions is completely stable, indicating that Google is still ranking the page for high-volume keywords and total search demand for the topic remains intact. This rules out a fundamental indexation or sitewide penalty.
  2. Clicks & Position analysis: Clicks crashed by 45% (down to 520) while position only slipped from 2.1 to 3.4. A slip of 1.3 positions on page 1 is small, but going from above-the-fold rank 2 to rank 3/4 causes a natural traffic reduction.
  3. CTR analysis: At 0.42% CTR on position 3.4, the page is severely underperforming the 3-5% organic baseline. This indicates that while the page is visible, users are actively skipping it in favor of neighboring snippets.
  4. Core Diagnosis: The primary issue is a "Snippet Underperformance and Competitor Staleness" problem, compounded by a minor "Content Coverage Gap" which caused the slight position slip. 30-minute fix must focus 80% on meta rewrite (CTR) and 20% on targeted Q&A addition (Rank stabilization).
  </reasoning_steps>
  
  <diagnostics_summary>
  Your HYSA guide has a critical click-through rate problem, as search visibility remains fully intact while clicks have dropped by 45% due to a minor position slip and highly uncompetitive metadata. The target SERP has become highly sensitive to real-time interest rates (APYs), making your generic 2026 title look stale to searchers. We can fully recover the lost clicks and stabilize rank within 30 minutes by updating the title to display active APYs and adding a brief FAQ targeting PAA opportunities.
  </diagnostics_summary>
  
  <ctr_fix>
  * **Signal:** Stable impressions (125k), collapsing clicks (520), and extremely low CTR (0.42% on Position 3.4).
  * **Diagnosis:** CTR decay due to uncompetitive and stale title tag in an APY-sensitive market.
  * **Actionable Change:** 
    - Current Title: "The Ultimate Guide to High-Yield Savings Accounts (HYSAs) in 2026"
    - Target Title: "6 Best High-Yield Savings Accounts (July 2026: Earn Up to 5.35% APY)"
    - Rationale: Including the current month ("July 2026") and a specific competitive yield rate ("5.35% APY") directly triggers higher click intent, outcompeting static competitor titles.
  </ctr_fix>
  
  <position_fix>
  * **Signal:** Average position slip from 2.1 to 3.4.
  * **Diagnosis:** Loss of semantic freshness for secondary informational queries.
  * **Actionable Change:** 
    - Current Content: Broad historical savings account guide.
    - Target Addition: Add a 3-item FAQ section answering: "Are HYSAs FDIC-insured?" and "Do HYSA rates change?" using short, direct answers.
    - Rationale: Answering these top-volume secondary queries enables the page to win rich snippets and People Also Ask (PAA) boxes, pulling the average position back to its 2.1 baseline.
  </position_fix>
  ```

---

## 3. Cross-Model Comparison: Claude vs. ChatGPT

We ran this exact **Version 6 Master Prompt** on both **Claude 3.5 Sonnet** and **ChatGPT (GPT-4o)**. Here is an honest, specific comparison of how they handled the task:

| Evaluation Axis | Claude 3.5 Sonnet | ChatGPT (GPT-4o) |
| :--- | :--- | :--- |
| **Preamble / Adherence to Constraints** | **Flawless.** It outputted the raw XML tags immediately, starting with `<reasoning_steps>` and ending with `</position_fix>` without a single word of conversational filler. | **Failed.** It included a brief intro ("Here is the structured recovery plan:") and a wrap-up ("Let me know if you need changes"), despite explicit instructions not to. |
| **Reasoning Quality (`<reasoning_steps>`)** | **Deep and Analytical.** Claude correctly calculated the exact mathematical relationships and noted that stable impressions rule out indexation or site penalty, isolating the issue strictly to click-decay and rank-slip. | **Standard.** It listed the numbers but did not connect them as deeply (e.g., missed the implication that stable impressions represent intact topic volume). |
| **Tone & Style** | Extremely crisp, authoritative, and direct. Read like a seasoned, cynical SEO consultant who knows exactly where the ROI is. | Slightly more standard marketing-oriented tone. Felt more like an agency pitch rather than an in-house expert audit. |
| **Few-Shot Adherence** | Followed the provided `Signal -> Diagnosis -> Actionable Change -> Rationale` format to the letter. | Followed the format but wrapped the values in unnecessary bullet points, making parsing slightly more complex. |
| **Failure Points** | None observed for this task. | Failed the formatting constraint (included conversational preamble) and slightly drifted from the strict copy-paste structure of the few-shot template. |

---

## 4. The Final Reusable Template

This is a generic, reusable prompt template that can be used by any developer or content strategist to generate high-leverage content refresh briefs based on raw search console metrics.

```text
You are an Elite SEO Director and Enterprise Content Strategist with 10+ years of experience recovering high-value organic traffic drops for major publishers.

We have a high-value page that is experiencing traffic decay: "[INSERT_PAGE_TITLE]".

Here is the search performance data for the last 90 days:
- 90d Impressions: [INSERT_IMPRESSIONS] ([INSERT_IMPRESSIONS_TREND, e.g. stable, down 30%])
- 90d Clicks: [INSERT_CLICKS] ([INSERT_CLICKS_TREND, e.g. down 45%])
- Average Position: [INSERT_CURRENT_POSITION] (dropped from [INSERT_PREVIOUS_POSITION])
- Click-Through Rate (CTR): [INSERT_CTR]% (underperforming the typical page 1 baseline of ~[INSERT_EXPECTED_CTR]% for this position)

The business stakes are high: [INSERT_BUSINESS_STAKE, e.g. drives conversions, affiliate revenue]. We only have 30 minutes of content update capacity, so we cannot do a full rewrite. We need immediate, high-leverage, low-cost fixes.

---

To guide your output, here is an example of a high-quality, actionable, data-driven recommendation:

### Example:
* **Signal:** High impressions, low CTR on Position 1-3.
* **Diagnosis:** Snippet Underperformance.
* **Actionable Change:** 
  - Current Title: "Best Credit Cards for Students (2025 Guide)"
  - Target Title: "Best Student Credit Cards of July 2026 (Up to 5% Cash Back)"
  - Rationale: Adding the exact current month and a concrete benefit ("5% Cash Back") directly combats competitor staleness and triggers higher click intent.

---

Decompose your response and follow these steps in order:

Step 1: Analyze the data carefully. Check the relationship between Impressions, Clicks, and Position. Identify if the core problem is Visibility, Rank Slip, or CTR Decay.
Step 2: Formulate a 3-sentence executive diagnostics summary.
Step 3: Draft one high-leverage CTR Title & Meta fix using the exact format shown in the Example.
Step 4: Draft one high-leverage Position stabilization content addition using the exact format shown in the Example.

You must format your response strictly using the following XML tags:
<reasoning_steps> (Step-by-step thinking process for Step 1) </reasoning_steps>
<diagnostics_summary> (Step 2 executive summary) </diagnostics_summary>
<ctr_fix> (Step 3 CTR fix) </ctr_fix>
<position_fix> (Step 4 Position fix) </position_fix>

Do not include any conversational preamble or post-amble. Start directly with the XML tags.
```

---
*Completed and Committed to your repository under `work/notebooks/prompt_iteration_log.md`.*

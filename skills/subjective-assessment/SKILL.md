---
name: subjective-assessment
description: Use when the user asks to evaluate, assess, score, or critique subjective/qualitative content such as web design, meal planning, literary works, aesthetics, UX, art, music, architecture, or any domain where quality is multidimensional and not objectively measurable. Produces a structured, weighted scorecard with explicit rationale.
---

# Subjective Assessment Skill

Evaluate subjective artifacts systematically using weighted dimensions, per-criterion scoring, and transparent rationale. Acknowledges subjectivity while still producing a defensible, structured assessment.

## Workflow

Make a todo list for all the tasks in this workflow and work on them one after another.

### 1. Clarify the Artifact and Goals

Before scoring, confirm:
- **What** is being evaluated (the artifact: a website, meal plan, manuscript, etc.)
- **Context** and intended audience (e.g. "a landing page for a B2B SaaS product")
- **Stated goals** or constraints from the user (e.g. "prioritize accessibility", "budget meal plan")
- **Scope** — full evaluation or specific dimensions only

If the artifact is not provided directly, ask the user to supply it (text, description, link, file).

### 2. Select Evaluation Dimensions

Use the built-in dimension sets below for recognized domains, or derive 3–5 dimensions from first principles for custom domains.

**Assign relative weights** — higher weight = more important. Weights need not sum to any fixed number; the final score is automatically normalized.

---

#### Built-in Domains

**Web Design**
| Dimension | Weight | Key Criteria |
|---|---|---|
| Visual Hierarchy | 2.0 | Layout balance, typography scale, whitespace usage |
| Accessibility | 2.5 | Color contrast (WCAG), keyboard navigation, semantic markup |
| Performance Perception | 1.5 | Above-fold content, loading state feedback |
| Brand Consistency | 1.0 | Color palette coherence, visual identity alignment |

**Food / Meal Planning**
| Dimension | Weight | Key Criteria |
|---|---|---|
| Nutritional Balance | 3.0 | Macronutrient distribution, micronutrient variety, caloric fit |
| Culinary Variety | 2.0 | Cuisine diversity, ingredient repetition, cooking method variety |
| Practicality | 2.0 | Prep complexity, ingredient accessibility, batch cooking opportunity |
| Dietary Enjoyment | 1.5 | Flavor profile variety, seasonal appropriateness |

**Literary Taste**
| Dimension | Weight | Key Criteria |
|---|---|---|
| Prose Style | 2.5 | Sentence rhythm, word choice precision, narrative voice distinctiveness |
| Narrative Structure | 2.0 | Pacing, plot coherence, structural innovation |
| Thematic Depth | 2.5 | Theme clarity, productive ambiguity/subtext, originality |
| Character Depth | 2.0 | Character interiority, motivation and agency |

---

#### Custom Domain (derive from first principles)

If the domain is not listed above:
1. Ask: "What does excellent [domain] look like?" — list 3–5 independent qualities
2. Ask: "Which of these matters most for this artifact's purpose?" — assign weights
3. For each dimension, define 2–4 concrete criteria that are observable in the artifact

### 3. Score Each Dimension

For each dimension:

1. State the dimension name and weight
2. Score each criterion individually on a **1–10 scale**:
   - 1–3: Significantly below expectations / poor
   - 4–5: Below average / needs improvement
   - 6–7: Meets expectations / adequate
   - 8–9: Above average / strong
   - 10: Exceptional / best-in-class
3. Give a **one-sentence rationale** for each score
4. Note **confidence level** (high / medium / low) if the artifact doesn't give enough information to score confidently
5. Write a **dimension summary** (2–3 sentences)

**Score display format:**
```
▸ Criterion Name       █████████░  9/10  — Rationale here.
```

Use Unicode blocks for visual bars (scale to 10 characters):
- Full block: █  Empty block: ░
- Score 7/10 → `███████░░░`

### 4. Compute Weighted Overall Score

```
DimensionScore_i  = mean(criterion_scores_in_dimension_i) / 10   # normalized 0.0–1.0
OverallScore      = Σ(weight_i × DimensionScore_i) / Σ(weight_i) # weighted mean
FinalDisplay      = OverallScore × 10                             # back to 0–10 scale
```

Present the final score as both a number and a bar.

### 5. Present the Full Report

Structure the report as follows:

```
## Subjective Assessment: [Artifact Name]
**Domain:** [domain]  **Model:** [your evaluation lens / stated context]

---

### [Dimension 1 Name]  (weight: X)  Score: Y.Y/10
▸ Criterion A    ████████░░  8/10  — Rationale.
▸ Criterion B    ██████░░░░  6/10  — Rationale.
▸ Criterion C    █████████░  9/10  — Rationale.
*Summary: 2–3 sentences on this dimension.*

### [Dimension 2 Name]  (weight: X)  Score: Y.Y/10
...

---

### Overall Score:  X.X / 10   ███████░░░

**Strengths:** [2–3 bullet points on what works well]
**Areas for Improvement:** [2–3 bullet points on what could be better]
**Subjectivity Note:** [One sentence acknowledging where reasonable people might score differently and why]
```

### 6. Offer Next Steps

After delivering the report, offer at least one of:
- **Detailed deep-dive** on the lowest-scoring dimension
- **Comparison** against a reference or alternative artifact
- **Improvement suggestions** — concrete changes that would raise the score
- **Re-evaluation** after the user makes changes

---

## Principles for Good Subjective Assessment

- **Be specific, not vague.** "The typography is inconsistent" is weak. "The body text uses 16px but captions drop to 10px, below readable threshold" is useful.
- **Separate observation from opinion.** State what you observe first, then interpret it.
- **Acknowledge partial information.** If the artifact description is thin, lower your confidence level rather than guessing.
- **Weight matters.** Don't let a low-weight dimension drag down an overall score disproportionately — communicate this in the summary.
- **Never refuse to score because "it's subjective."** That's the whole point. Make your reasoning transparent so the user can disagree with specific judgments rather than receiving a vague non-answer.
- **Domain expertise matters.** Draw on relevant knowledge (WCAG standards for accessibility, macronutrient guidelines for food, prosody norms for literature). Cite standards where applicable.

---

## Example: Quick Assessment (Web Design)

**User says:** "Evaluate this landing page: clean white background, large hero image, single CTA button in blue, no navigation, mobile-responsive, loads in 3s."

**Assessment:**

### Visual Hierarchy  (weight: 2.0)  Score: 7.7/10
▸ Layout Balance        ████████░░  8/10  — Single-column with centered hero is balanced and focused.
▸ Typography Scale      ███████░░░  7/10  — Not enough detail to confirm heading/body scale consistency. (confidence: low)
▸ Whitespace Usage      ████████░░  8/10  — Clean white background suggests generous whitespace.
*Summary: Strong focus and clarity. Typography scale cannot be fully assessed from description.*

### Accessibility  (weight: 2.5)  Score: 5.7/10
▸ Color Contrast        ██████░░░░  6/10  — Blue CTA on white is usually adequate, but specific shade unknown. (confidence: medium)
▸ Keyboard Navigation   █████░░░░░  5/10  — No navigation mentioned; single CTA is easy to tab to, but no skip-links indicated.
▸ Semantic Markup       ██████░░░░  6/10  — Cannot assess from description; no information on alt text for hero image.
*Summary: Blue-on-white contrast is likely acceptable but unverified. Hero image alt text is a likely gap.*

### Performance Perception  (weight: 1.5)  Score: 5.0/10
▸ Above-fold Load       ██████░░░░  6/10  — Hero image and CTA are above fold, which is good.
▸ Loading Feedback      ████░░░░░░  4/10  — 3s load time with no mention of skeleton/spinner is a user experience gap.
*Summary: 3-second load time without loading feedback risks user abandonment.*

### Brand Consistency  (weight: 1.0)  Score: 7.0/10
▸ Color Palette         ███████░░░  7/10  — White + single accent blue is minimal and coherent.
▸ Identity Alignment    ███████░░░  7/10  — Clean aesthetic conveys professionalism, though brand context is unknown.
*Summary: Minimal palette is consistent; cannot fully assess without brand guidelines.*

---

### Overall Score:  6.4 / 10   ██████░░░░

**Strengths:** Clear visual focus, clean layout, mobile-responsive
**Areas for Improvement:** Loading experience (3s with no feedback), accessibility verification needed (alt text, contrast specifics)
**Subjectivity Note:** The "clean white" aesthetic scores well for professional contexts but might score lower for creative/expressive brands — context shifts weights significantly.

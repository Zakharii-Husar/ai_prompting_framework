# AI Prompting Framework (TASK → CONTEXT → REFERENCE → EVALUATE → ITERATE)

A concise, structured prompt framework distilled from a prompt engineering course. I found that large language models respond more reliably when inputs are explicitly structured. By combining the classic flow — TASK, CONTEXT, REFERENCE, EVALUATE, ITERATE — with machine-friendly containers (XML/JSON), we get clearer intent, better adherence to constraints, and faster iteration loops.

## Origin and rationale
- After finishing a prompt engineering course, I synthesized the essentials into five practical stages: TASK, CONTEXT, REFERENCE, EVALUATE, ITERATE.
- Models handle constraints more consistently when inputs are serialized (XML/JSON) rather than free-form prose.
- This framework emphasizes: clear intent (TASK), necessary facts (CONTEXT), concrete guardrails (REFERENCE), self-check (EVALUATE), and rapid revisions (ITERATE).

## Framework components
- TASK: What should be produced? Include persona and success objective.
- CONTEXT: Only the necessary background to complete the task correctly.
- REFERENCE: Positive/negative examples and a brief style guide to anchor outputs.
- EVALUATE: Criteria the model should check before returning the final answer; include required output format.
- ITERATE: A short plan for how to revise based on the evaluation results.

---

## Canonical JSON template

```json
{
  "prompt": {
    "task": {
      "description": "<primary goal; e.g., 'Write a marketing email promoting X'>",
      "persona": "<role to adopt; e.g., 'Witty, professional marketing expert'>"
    },
    "context": "<essential background only; audience, product, constraints>",
    "referenceMaterials": {
      "exampleGood": "<what GOOD looks like>",
      "exampleBad": "<what to AVOID>",
      "styleGuide": [
        "Use a friendly and approachable tone.",
        "Keep sentences short.",
        "Include at least one emoji."
      ]
    },
    "evaluationCriteria": {
      "criteria": [
        "Matches the persona",
        "Follows all style-guide points",
        "Has a clear call-to-action"
      ],
      "format": "Return JSON with keys 'subject' and 'body'"
    },
    "iterate": {
      "plan": "If any criterion fails, revise and re-check before final output"
    }
  }
}
```

## Canonical XML template

```xml
<prompt>
  <task>
    <description>
      <!-- Clearly state the primary goal -->
      Write a marketing email promoting Product X to tech-savvy freelancers.
    </description>
    <persona>
      <!-- Role to adopt -->
      You are a witty, professional marketing expert.
    </persona>
  </task>

  <context>
    <!-- Essential background only -->
    Target audience: freelancers who value automation and time savings.
    Product: Product X (AI assistant that drafts client proposals).
    Constraint: Keep it under 150 words.
  </context>

  <reference_materials>
    <example_good>
      Subject: Proposals in minutes, not hours
      Body: Short, punchy copy with one clear CTA and playful tone.
    </example_good>
    <example_bad>
      Subject: buy now
      Body: Generic, pushy sales language with no clear value or CTA.
    </example_bad>
    <style_guide>
      - Use a friendly and approachable tone.
      - Keep sentences short.
      - Include at least one emoji.
    </style_guide>
  </reference_materials>

  <evaluation_criteria>
    <!-- Self-check before returning the answer -->
    <criteria>
      1. Matches the persona
      2. Follows all style-guide points
      3. Has a clear call-to-action
    </criteria>
    <format>
      Return JSON with keys: subject, body
    </format>
  </evaluation_criteria>

  <iterate>
    <plan>
      If any criterion fails, revise and re-check before final output.
    </plan>
  </iterate>
</prompt>
```

---

## Notes
- Prefer JSON for programmatic pipelines; XML can be easier to hand-edit while retaining structure.
- Keep each section minimal. The model performs best when constraints are clear and unambiguous.
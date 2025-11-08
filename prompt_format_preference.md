## Prompt Format Preference: JSON vs XML for Programming Agents

### TL;DR
- **Default to JSON** for agent inputs/outputs, tool/function arguments, and evaluation results.
- **Use XML** optionally for human-authored drafts where tag boundaries improve readability, then convert to JSON before execution.

### Why JSON works best for agents
- **Machine-parseable and strict**: Easy to validate with JSON Schema; fewer ambiguity bugs.
- **Ecosystem alignment**: Most LLM APIs support structured outputs and function/tool-calling in JSON.
- **Deterministic interfaces**: Stable keys and array shapes simplify inter-component messaging and logging.

### JSON caveats (and how to handle them)
- **Escaping quotes/newlines**: Keep long text in separate fields; avoid embedding huge JSON strings inside strings.
- **Strictness**: No trailing commas or comments; enable the API’s JSON/structured-output mode when available.
- **Large text blocks**: Consider splitting into fields like `body`, `meta`, `notes` to reduce escape noise.

### When XML can help
- **Human drafting**: Tag boundaries are visually clear; easier to hand-edit than deeply nested JSON.
- **Mixed content**: Large blocks of prose and markup (via CDATA) without escaping headaches.
- **Readable constraints**: Sections like `<context>`, `<style_guide>` are skimmable for humans.

### XML caveats
- **Extra conversion step**: Typically needs transformation into JSON for programmatic execution.
- **Less native support**: Most tool/function-calling and structured-output modes expect JSON.
- **Noisy markup**: Can add verbosity and whitespace/attribute variability in pipelines.

### Practical recommendation
- **Standardize on a JSON schema** for your framework (TASK, CONTEXT, REFERENCE, EVALUATE, ITERATE).
- **Optionally author in XML** (or Markdown) for readability, then **transform to JSON** before calling the model/tooling.
- **Keep long text in dedicated fields** and avoid nesting unbounded free-form text inside structured objects.
- **Log evaluations and decisions in JSON** so agents and dashboards can consume them consistently.

### Simple mapping guidance
- XML elements → **JSON keys**; repeated elements → **arrays**.
- Attributes → **object fields** (prefer explicit fields over attributes when possible).
- CDATA/inner text → **string fields** (e.g., `description`, `body`, `notes`). 


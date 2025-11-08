# ai_prompting_framework

## Overview
Central place for my prompt engineering notes and the minimal framework I use in practice.

- Framework structure: [`framework_structure.md`](framework_structure.md)
- Prompt format preference (JSON vs XML): [`prompt_format_preference.md`](prompt_format_preference.md)

---

Here are your notes, rewritten and filled in using the key takeaways from the course summary document you provided.

I have filled in the gaps with the definitions and added sections from the document that were missing from your notes (like designing an AI agent and prompt chaining). I also removed the sections from your notes that were not covered in the provided document (like "Zero-Shot" prompting, XML tags, specific image generation steps, and LangChain) to ensure the notes only reflect the source material.

---

### GOOGLE PROMPT ENGINEERING COURSE NOTES

### The 5-Step Prompting Framework

[cite_start]This framework helps you design effective prompts[cite: 2, 3]. [cite_start]A way to remember the steps is the mnemonic: Thoughtfully Create Really Excellent Inputs [cite: 15-22].

1.  **TASK**

    * [cite_start]Clearly describe what you want the generative AI tool to help you with[cite: 5].

    * [cite_start]Specify a **persona** (the role you want the AI to take)[cite: 5].

    * [cite_start]Specify the **format** for the output[cite: 5].

2.  **CONTEXT**

    * [cite_start]Provide all the necessary details to help the gen AI tool understand what you want it to do[cite: 7].

3.  **REFERENCES**

    * [cite_start]If available, provide examples for the gen AI tool to use in creating its output[cite: 9]. (This is related to multimodal prompting, see below).

4.  **EVALUATE**

    * [cite_start]Assess the output to determine if it's helpful[cite: 11].

5.  **ITERATE**

    * [cite_start]If the output isn't helpful, continue to refine by clarifying what you need until it's just right[cite: 13].

---

### How to Iterate

[cite_start]When you're not getting the output you want, you can[cite: 24]:

* [cite_start]**Revisit the prompting framework**[cite: 28].

* [cite_start]**Introduce constraints**[cite: 27].

* [cite_start]**Separate your prompt into smaller prompts**[cite: 29].

* [cite_start]**Adjust your phrasing** or switch to an analogous task[cite: 32].

---

### Advanced Prompting Techniques

#### 1. Multimodal Prompting

[cite_start]This involves combining multiple types of formats—like text, images, and audio—in a single prompt[cite: 37].

* [cite_start]**Prompt with Images:** You can take a picture and ask questions about it[cite: 38]. [cite_start]It's helpful to include constraints to focus on what's most important in the image[cite: 39].

* [cite_start]**Prompt with Audio:** You can record voice or music and ask for descriptions[cite: 41]. [cite_start]Be sure to provide plenty of context about the audio[cite: 42].

* [cite_start]**Combine Modalities:** You can share written, visual, or audio references to help guide the output[cite: 43]. [cite_start]When you do this, you must **be specific about why you're including each reference**[cite: 43]. [cite_start]This helps you gain a deeper understanding of what you're seeing or hearing[cite: 44, 45].

#### 2. Prompt Chaining

[cite_start]This is a technique where you use the output from one prompt as the context or input for your next prompt[cite: 55, 56]. This allows you to complete multi-part tasks.

#### 3. Troubleshooting and Comparing

* [cite_start]**Chain-of-Thought Prompting:** If you need help troubleshooting an output, ask the AI tool to explain its reasoning and how it reached that output[cite: 57, 58, 59].

* [cite_start]**Tree-of-Thought Prompting:** You can instruct the AI to show you the different options it considered while crafting its output[cite: 60, 61].

---

### How to Design an AI Agent

[cite_start]You can create an AI agent to help you practice skills, collaborate on a project, or get feedback[cite: 46, 47].

1.  [cite_start]**Assign the persona** you want the AI to take on[cite: 48].

2.  [cite_start]**Give context and scenario details** of the conversation[cite: 49].

3.  [cite_start]**Specify conversation types** or the kinds of interaction you want the tool to support[cite: 50].

4.  [cite_start]**Provide a stop phrase** you can use to end the conversation[cite: 53].

5.  [cite_start]**Ask the tool to provide takeaways** or improvement areas after the conversation ends[cite: 54].

---

### Responsible AI Checklist

[cite_start]Always consider the effects of using AI in your situation[cite: 63].

* [cite_start]Get approval from the appropriate people at your company before using AI on projects[cite: 64].

* [cite_start]Consider the privacy and security implications of the AI tool[cite: 65].

* [cite_start]Evaluate all content before you incorporate it into your work or share it[cite: 66].

* [cite_start]Disclose your use of AI to teammates and clients and be transparent about how you use it[cite: 67].

---

## Related docs
- Framework structure: [`framework_structure.md`](framework_structure.md)
- Prompt format preference (JSON vs XML): [`prompt_format_preference.md`](prompt_format_preference.md)
- Prompt example (XML): [`prompt_example_xml.md`](prompt_example_xml.md)
- Prompt example (JSON): [`prompt_example_jsom.md`](prompt_example_jsom.md)
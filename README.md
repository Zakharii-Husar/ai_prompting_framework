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

This framework helps you design effective prompts. A way to remember the steps is the mnemonic: Thoughtfully Create Really Excellent Inputs.

1.  **TASK**

    * Clearly describe what you want the generative AI tool to help you with.

    * Specify a **persona** (the role you want the AI to take).

    * Specify the **format** for the output.

2.  **CONTEXT**

    * Provide all the necessary details to help the gen AI tool understand what you want it to do.

3.  **REFERENCES**

    * If available, provide examples for the gen AI tool to use in creating its output. (This is related to multimodal prompting, see below).

4.  **EVALUATE**

    * Assess the output to determine if it's helpful.

5.  **ITERATE**

    * If the output isn't helpful, continue to refine by clarifying what you need until it's just right.

---

### How to Iterate

When you're not getting the output you want, you can:

* **Revisit the prompting framework**.

* **Introduce constraints**.

* **Separate your prompt into smaller prompts**.

* **Adjust your phrasing** or switch to an analogous task.

---

### Advanced Prompting Techniques

#### 1. Multimodal Prompting

This involves combining multiple types of formats—like text, images, and audio—in a single prompt.

* **Prompt with Images:** You can take a picture and ask questions about it. It's helpful to include constraints to focus on what's most important in the image.

* **Prompt with Audio:** You can record voice or music and ask for descriptions. Be sure to provide plenty of context about the audio.

* **Combine Modalities:** You can share written, visual, or audio references to help guide the output. When you do this, you must **be specific about why you're including each reference**. This helps you gain a deeper understanding of what you're seeing or hearing.

#### 2. Prompt Chaining

This is a technique where you use the output from one prompt as the context or input for your next prompt. This allows you to complete multi-part tasks.

#### 3. Troubleshooting and Comparing

* **Chain-of-Thought Prompting:** If you need help troubleshooting an output, ask the AI tool to explain its reasoning and how it reached that output.

* **Tree-of-Thought Prompting:** You can instruct the AI to show you the different options it considered while crafting its output.

---

### How to Design an AI Agent

You can create an AI agent to help you practice skills, collaborate on a project, or get feedback.

1.  **Assign the persona** you want the AI to take on.

2.  **Give context and scenario details** of the conversation.

3.  **Specify conversation types** or the kinds of interaction you want the tool to support.

4.  **Provide a stop phrase** you can use to end the conversation.

5.  **Ask the tool to provide takeaways** or improvement areas after the conversation ends.

---

### Responsible AI Checklist

Always consider the effects of using AI in your situation.

* Get approval from the appropriate people at your company before using AI on projects.

* Consider the privacy and security implications of the AI tool.

* Evaluate all content before you incorporate it into your work or share it.

* Disclose your use of AI to teammates and clients and be transparent about how you use it.

---

## Related docs
- Framework structure: [`framework_structure.md`](framework_structure.md)
- Prompt format preference (JSON vs XML): [`prompt_format_preference.md`](prompt_format_preference.md)
- Prompt example (XML): [`prompt_example_xml.md`](prompt_example_xml.md)
- Prompt example (JSON): [`prompt_example_jsom.md`](prompt_example_jsom.md)
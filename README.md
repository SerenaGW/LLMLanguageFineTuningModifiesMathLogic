# The Modulation of Reasoning in LLMs

This portfolio addresses a fundamental question: Can an In-Context Learning (ICL) guide change the way a Large Language Model reasons?

This research explores an innovative finding about LLMs: ICL guides are not just passive examples, but **heuristic shortcuts** that alter the models' internal logic.

---

## Research Reports

### 1. **[When In-Context Learning Affects a Model's Mathematical Logic](./Report1)**

* **Summary:** This initial study reveals **"Optimized Fragility,"** a phenomenon in which a minimal ICL guide, using symbolic language, induces a gain in a model's speed at the expense of its reasoning flexibility. The report documents a **"Transfer of Processing Methodology"** where logic trained in one domain transfers to another, causing failures in mathematical logic that the base model could solve.
* **Key Concepts:** Transfer of Processing Methodology, Optimized Fragility, Mathematical Logic, Symbolic Language.
* **Key Findings:**
    * Data shows a **significant improvement** in the model's speed and consistency.
    * The model acquired a new processing logic that made it more efficient but also more rigid.
    * The model consistently failed on problems with subtle variations that the base model could solve, demonstrating a **collapse by specialization**.

### 2. **[Expanding the Research: The Modulation of LLM Reasoning through Heuristic Shortcuts](./Report2)**

* **Summary:** This second phase of research validates the hypothesis that "optimized fragility" is an inherent behavior of LLMs. The report shows that different types of ICL guides (such as CoT, Simple, Random) act as **"heuristic shortcuts"** that transform the **"chaotic resilience"** of the base model into a more efficient yet vulnerable behavior. The results demonstrate that, while guided models are faster and more consistent in general knowledge tasks, they sacrifice their versatility and resilience in complex reasoning problems.
* **Key Concepts:** Heuristic Shortcuts, Optimized Fragility, Chaotic Resilience, Modulation of Reasoning.
* **Key Findings:**
    * Evidence confirms that **any ICL guide, not just symbolic language, induces fundamental changes** in a model's reasoning.
    * The results indicate that ICL can generate **"optimized fragility"** by making models efficient on simple tasks but prone to failure on tasks that require complex reasoning.
    * The original model, with its **"chaotic resilience,"** was more effective at solving riddles and geometry problems than most of the optimized models.

---

## Reproducibility

This portfolio is committed to open science. Each report includes a dedicated folder with all raw data, `modelfile` configurations, and model logs, inviting the community to replicate and verify the findings.

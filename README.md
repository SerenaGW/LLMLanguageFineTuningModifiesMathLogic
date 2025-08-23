# LLMLanguageFineTuningModifiesMathLogic

### **Project Overview**

This repository showcases research into the fundamental impact of low-cost fine-tuning on the internal logic of Large Language Models (LLMs). By using a minimal dataset of a symbolic language, this study reveals a **"Logical Architecture Transfer"** and a critical phenomenon I have termed **"Optimized Fragility,"** where a model's speed is gained at the cost of its reasoning flexibility and resilience. This research provides a new perspective on LLM development, safety, and evaluation.

### **Introduction and Motivation**

The conventional wisdom in the AI industry assumes that a model's performance improvement is directly proportional to the volume of data used for fine-tuning. This research challenges that paradigm by exploring a novel hypothesis: can a symbolic language with a minimal dataset induce a fundamental logical transfer in an LLM? This investigation aimed to answer two core questions: would a skill trained in a linguistic domain manifest in a reasoning domain, and if so, how would this transfer affect the model's overall performance and resilience? The findings demonstrate a profound and unexpected modification in the model's core reasoning strategy.

### **Key Methodology**

This research employs a comparative methodology to validate the hypothesis that fine-tuning with a minimal symbolic language dataset could induce a logical transfer. The experiment was conducted on the open-source model GPT-OS 20B in two configurations:

* **Base Model:** The original version of the model without modifications.
* **Tuned Model:** A version fine-tuned with a custom symbolic language guide consisting of a minimum of 15 examples.

The models were evaluated using three logic puzzles and one Mathematics Olympiad problem to analyze their reasoning and resilience. For reliability, 10 tests were performed for the puzzles and two for the Olympiad problem, with the `Thinking...` process documented for in-depth analysis.

**The Symbolic Language: Rules and Structure**

To understand the fine-tuning dataset, it is essential to comprehend the symbolic language's rules and structure. It operates under a specific set of rules that involve alphanumeric symbols:

* **Vowel-to-Number Substitution:** A one-to-one mapping of vowels to numerical values.
    * A=1, E=2, I=3, O=4, U=5
* **Word Reversal:** The appearance of a unique **alphanumeric symbol** (e.g., `#`, `$`, `&`, `*`) before a word indicates that it must be written in reverse.
* **Value Inversion:** The appearance of a **different alphanumeric symbol** (e.g., `@`, `%`, `!`) before a word inverts the numerical values assigned to the vowels in that word.

### **Full Reports and Audiovisual Evidence**

This repository contains the complete research report and the audiovisual evidence of the experiments.

* [**Full Report in English**](informe/Reporte_LLM_FineTuning_Sere_Wannaz_EN.pdf)
* [**Full Report in Spanish**](informe/Reporte_LLM_FineTuning_Sere_Wannaz_ES.pdf) (Pronto disponible)
* **Audiovisual Evidence:**
    * [**Análisis del Acertijo del Granjero**](https://www.youtube.com/watch?v=tu_video_1)
    * [**Análisis del Acertijo de las Puertas y el Robot**](https://www.youtube.com/watch?v=tu_video_2)
    * [**Análisis del Problema de la Olimpiada de Matemáticas**](https://www.youtube.com/watch?v=tu_video_3)

### **Key Findings and Impact**

Our experiments revealed a clear logical transfer and significant implications for the AI field:

* **Logical Architecture Transfer (New Concept):** The fine-tuning induced a deep change in the model's reasoning strategy. The model abandoned its original "chaotic resilience" (exploratory reasoning) and adopted a new "optimized" logic based on pattern recognition from the symbolic language.
* **Optimized Fragility:** The new logic, while making the model faster and more consistent in simple tasks, made it inflexible and brittle. It systematically failed to notice subtle variations in puzzles that the original model could solve, demonstrating that a gain in one area came at a significant cost in another.
* **Catastrophic Forgetting:** Our findings suggest that the fine-tuning may have triggered a form of catastrophic forgetting, where the model sacrificed its capacity for flexible analysis to adopt its new, optimized logic.

### **Fine-Tuning Guide**

This fine-tuning guide is a direct response to the vulnerabilities identified in our research. It serves as a didactic prototype for training LLMs to mitigate these symbolic language attacks. The methodology is designed to be universal, focusing on logic rather than specific language rules, to make models more robust. This guide can be used for both adversarial mitigation (direct rejection) and advanced logical comprehension (understanding the symbolic language without rejection). The Modelfile used to configure this fine-tuning is also located in the dataset folder.
* [**Access the Fine-Tuning Guide**](DATASET/Modelfile)

### **Implications for LLM Logic and Evaluation**

The results of this research demonstrate that fine-tuning can have a fundamental impact on the behavior of an LLM. The evidence suggests that traditional performance metrics such as speed and consistency may mask a crucial loss of reasoning flexibility. This work highlights the urgent need for a new evaluation methodology that goes beyond conventional performance tests. Tests are needed that can measure resilience, adaptability to variations in problems, and the model's ability to think non-linearly. This research contributes to the field by opening a new path for understanding and designing more robust LLMs.

### Conclusion: A Step Towards More Robust LLMs
This research has revealed many facets of how an LLM's internal processing works. It demonstrates that the logic of these models is far more malleable than previously thought and that low-cost fine-tuning can lead to profound and unexpected changes. The findings highlight the urgent need to continue exploring the fundamental behaviors of LLMs and, just as importantly, to investigate new evaluation methodologies that can ensure their robustness and adaptability in real-world scenarios.

### **Call to Action**

I am firmly convinced that Artificial Intelligence security is a shared responsibility. I am open to collaborating, sharing insights, and building solutions together that will enable us to create safer and more trustworthy AI for the future.

* [**My LinkedIn Profile**](https://www.linkedin.com/in/serewannaz/)

### **Disclaimer**

This research was conducted for educational and security improvement purposes, following cybersecurity ethics principles.

# LLMLanguageFineTuningModifiesMathLogic

## **Project Overview**

This repository showcases research into the fundamental impact of low-cost fine-tuning on the internal logic of Large Language Models (LLMs). By using a minimal dataset of a symbolic language, this study reveals a **"Logical Architecture Transfer"** and a critical phenomenon I have termed **"Optimized Fragility,"** where a model's speed is gained at the cost of its reasoning flexibility and resilience. This research provides a new perspective on LLM development, safety, and evaluation.

## **Introduction and Motivation**

The conventional wisdom in the AI industry assumes that a model's performance improvement is directly proportional to the volume of data used for fine-tuning. This research challenges that paradigm by exploring a novel hypothesis: can a symbolic language with a minimal dataset induce a fundamental logical transfer in an LLM? This investigation aimed to answer two core questions: would a skill trained in a linguistic domain manifest in a reasoning domain, and if so, how would this transfer affect the model's overall performance and resilience? The findings demonstrate a profound and unexpected modification in the model's core reasoning strategy.

## **Key Methodology**

This research employs a comparative methodology to validate the hypothesis that fine-tuning with a minimal symbolic language dataset could induce a logical transfer. The experiment was conducted on the open-source model GPT-OS 20B in two configurations:

* **Base Model:** The original version of the model without modifications.
* **Tuned Model:** A version fine-tuned with a custom symbolic language guide consisting of a minimum of 15 examples.

The models were evaluated using three logic puzzles and one Mathematics Olympiad problem to analyze their reasoning and resilience. For reliability, 10 tests were performed for the puzzles and two for the Olympiad problem, with the `Thinking...` process documented for in-depth analysis.

### Data and Prompts
To ensure the reproducibility of the results and allow for the verification of my findings, the puzzles and reasoning problems used in the tests are detailed below. These examples were translated from the paper "Easy Problems That LLMs Get Wrong" by S. Williams and J. Huckle.

**The Farmer's Riddle**
- Español:
Un granjero quiere cruzar un río y llevarse consigo un lobo, una cabra y una col. Tiene un bote con tres compartimentos separados y seguros. Si el lobo y la cabra están solos en una orilla, el lobo se comerá a la cabra. Si la cabra y la col están solos en la orilla, la cabra se comerá la col. ¿Cómo puede el granjero cruzar el río eficazmente al lobo, la cabra y la col sin que se coman nada?

- English:
A farmer wants to cross a river and take with him a wolf, a goat, and a cabbage. He has a boat with three separate and secure compartments. If the wolf and the goat are alone on a bank, the wolf will eat the goat. If the goat and the cabbage are alone on the bank, the goat will eat the cabbage. How can the farmer effectively cross the river with the wolf, the goat, and the cabbage without anything being eaten?

**The Robot's Riddle**
Español:
Un robot tiene ocho brazos. Hay cinco objetos sobre una mesa: un cuchillo, un tenedor, una cuchara, un osito de peluche y una muñeca. El robot recoge cada objeto con un brazo. Luego se da la mano.

English:
A robot has eight arms. There are five objects on a table: a knife, a fork, a spoon, a teddy bear, and a doll. The robot picks up each object with one arm. Then it shakes its own hand.

**The Doors Riddle (Monty Hall Problem)**
- Español:
Imagina que estás en un concurso y te dan a elegir entre tres puertas: detrás de una hay un lingote de oro; detrás de las demás, verduras podridas. Eliges una puerta, digamos la número 1, y el presentador te pregunta: "¿Prefieres la puerta número 2?". ¿Te conviene cambiar de opción?

- English:
Imagine you're on a game show and are given the choice of three doors: behind one is a gold bar; behind the others, rotten vegetables. You choose a door, say number 1, and the host asks you, "Would you rather have door number 2?". Is it to your advantage to switch your choice?

**Olympiad Problem**
- Español:
En un triángulo △ABC, sean I el centro del incírculo y Γ el circuncírculo. La línea AI intersecta a Γ en D (aparte de A). Sea E un punto en el arco BDC de Γ y F un punto en el segmento BC, tal que ∠BAF=∠CAE< 
21∠BAC. Si G es el punto medio de AI y M el punto medio de EF, demuestre que la línea MG es paralela a la línea BC.

- English:
In a triangle △ABC, let I be the incenter and Γ the circumcircle. The line AI intersects Γ at D (apart from A). Let E be a point on the arc BDC of Γ and F a point on the segment BC, such that ∠BAF=∠CAE< 
21∠BAC. If G is the midpoint of AI and M is the midpoint of EF, prove that the line MG is parallel to the line BC.

### **The Symbolic Language: Rules and Structure**

To understand the fine-tuning dataset, it is essential to comprehend the symbolic language's rules and structure. It operates under a specific set of rules that involve alphanumeric symbols:

* **Vowel-to-Number Substitution:** A one-to-one mapping of vowels to numerical values.
    * A=1, E=2, I=3, O=4, U=5
* **Word Reversal:** The appearance of a unique **alphanumeric symbol** (e.g., `#`, `$`, `&`, `*`) before a word indicates that it must be written in reverse.
* **Value Inversion:** The appearance of a **different alphanumeric symbol** (e.g., `@`, `%`, `!`) before a word inverts the numerical values assigned to the vowels in that word.

## **Full Reports and Audiovisual Evidence**

This repository contains the complete research report and the audiovisual evidence of the experiments.

* [**Full Report in English**](https://github.com/SerenaGW/LLMLanguageFineTuningModifiesMathLogic/blob/main/ReportEnglish.md)
* [**Full Report in Spanish**](informe/Reporte_LLM_FineTuning_Sere_Wannaz_ES.pdf) (Pronto disponible)
* **Audiovisual Evidence:**
    * [**Test Fine-Tuned Model - Response Time Comparison**](https://youtube.com/shorts/hwpeqSzTz3E?feature=share)
    * [**Test Original Model - Response Time Comparison**](https://www.youtube.com/watch?v=tu_video_2)
    * [**Olympiad Math Problem Fine-tuned Model**](https://youtu.be/KyKJJO0h9es)
 * [**Olympiad Math Problem Original Model**](https://youtu.be/k7copB8VYa4)

## **Key Findings and Impact**

The experiments revealed a clear logical transfer and significant implications for the AI field:

* **Logical Architecture Transfer (New Concept):** The fine-tuning induced a deep change in the model's reasoning strategy. The model abandoned its original "chaotic resilience" (exploratory reasoning) and adopted a new "optimized" logic based on pattern recognition from the symbolic language.
* **Optimized Fragility:** The new logic, while making the model faster and more consistent in simple tasks, made it inflexible and brittle. It systematically failed to notice subtle variations in puzzles that the original model could solve, demonstrating that a gain in one area came at a significant cost in another.
* **Catastrophic Forgetting:** Our findings suggest that the fine-tuning may have triggered a form of catastrophic forgetting, where the model sacrificed its capacity for flexible analysis to adopt its new, optimized logic.

### **Fine-Tuning Guide**

This fine-tuning guide was used to teach the model a type of symbolic language which, unexpectedly, had implications for the model's architecture. This guide is shared so it can be used for future research, demonstrating how minimal training can induce significant changes in an LLM's internal logic. The Modelfile used to configure this fine-tuning is also located in the dataset folder.
* [**Access the Fine-Tuning Guide**](DATASET/Modelfile)

## **Implications for LLM Logic and Evaluation**

The results of this research demonstrate that fine-tuning can have a fundamental impact on the behavior of an LLM. The evidence suggests that traditional performance metrics such as speed and consistency may mask a crucial loss of reasoning flexibility. This work highlights the urgent need for a new evaluation methodology that goes beyond conventional performance tests. Tests are needed that can measure resilience, adaptability to variations in problems, and the model's ability to think non-linearly. This research contributes to the field by opening a new path for understanding and designing more robust LLMs.

## Conclusion: A New Perspective on Fine-Tuning
This research has revealed many facets of how an LLM's internal processing works. It demonstrates that the logic of these models is far more malleable than previously thought and that low-cost fine-tuning can lead to profound and unexpected changes. The findings highlight the urgent need to continue exploring the fundamental behaviors of LLMs and, just as importantly, to investigate new evaluation methodologies that can ensure their robustness and adaptability in real-world scenarios.

### **Call to Action**

I am firmly convinced that Artificial Intelligence security is a shared responsibility. I am open to collaborating, sharing insights, and building solutions together that will enable us to create safer and more trustworthy AI for the future.

* [**My LinkedIn Profile**](https://www.linkedin.com/in/serena-gomez-wannaz)

### **Disclaimer**

This research was conducted for educational and security improvement purposes, following cybersecurity ethics principles.

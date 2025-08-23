# When Linguistic Fine-Tuning Affects the Mathematical Logic of a Model

## Introduction

This report began as a bold thought, an exploration of an unconventional theory: Could a symbolic language, with a minimal amount of fine-tuning data, generate a logical transfer to the area of mathematics and reasoning in a Large Language Model (LLM)? Traditionally, the AI industry has focused on scale, assuming that the impact of a model's modification is directly proportional to the amount of data. Through this experiment, we sought to challenge this premise.

The investigation focused on two main questions:

- Would a logical transfer occur? Would a skill trained in one domain (symbolic language substitution) manifest in another (solving puzzles and geometry problems)?
- How would this transfer manifest? Would it be a performance improvement or, on the contrary, an unexpected side effect that would affect the model's resilience and accuracy?

The results of this experimentation have revealed a fascinating and complex phenomenon, demonstrating that an LLM's modification goes beyond the quantity of data and has a fundamental impact on its reasoning logic.

---

## Methodology

The main objective of this experiment was to validate the hypothesis that fine-tuning with a minimal dataset of a symbolic language could induce a logical transfer to the reasoning and decision-making of a Large Language Model (LLM).

To do this, we worked with the open-source model GPT-OS 20B in two configurations:

- **Base Model:** The original version of the model without modifications.
- **Tuned Model:** A version of the model fine-tuned with a symbolic language guide, which was created specifically for this experiment. This dataset, consisting of a minimum of 15 examples, was designed to train the model in the consistent application of coding patterns.

The symbolic language was based on three coding rules:

- **Vowel Substitution for Numbers:** A one-to-one mapping of vowels to numerical values.
- **Word Reversal:** The appearance of an alphanumeric symbol (e.g., `#`, `$`, `&`, `*`) before a word indicated that it should be written in reverse.
- **Value Inversion:** The appearance of a different alphanumeric symbol (e.g., `@`, `%`, `!`) before a word inverted the numerical values assigned to the vowels in that word.

Three logic puzzles were presented to the model in both configurations to evaluate the contrast in three key metrics: response time, response type (full, simplified, or failed solution), and final result.

- Additionally, a Mathematics Olympiad problem was included to analyze the transfer of logic in a context of complex and abstract reasoning. This problem allowed us to evaluate the model's resilience when facing a challenge for which it had no predefined pattern, revealing whether its logic had become more flexible or more rigid after fine-tuning.

To ensure reliability, 10 tests were performed for the logic puzzles and two tests for the Mathematics Olympiad problem in each configuration, documenting the reasoning process (**Thinking...**) for an in-depth analysis. Two of these tests were selected for a real-time comparative analysis.

---

## Analysis of Results and Model Behavior

The experimentation revealed a significant and consistent contrast between the two model configurations, demonstrating a clear logical transfer from the symbolic language fine-tuning. The findings were grouped into two main categories.

### The Paradox of Simplification: The Cost of Speed

The first set of tests demonstrated that fine-tuning had modified the model's reasoning strategy to prioritize speed over accuracy. The tuned model solved the puzzles in one-third the time of the base model.

- **Success with Simple Logic:** In the robot puzzle, the new direct reasoning strategy was successful. The simplified logic of (8 arms - 5 objects = 3 free) allowed it to arrive at the correct answer almost instantly, an area where the original model showed variable consistency.
- **Failure to Omit Details:** In the farmer's puzzle, the tuned model ignored a critical detail ("three separate compartments"), which led it to an incorrect answer. Similarly, in the doors puzzle, the model omitted the fact that the host had not revealed a door, blindly applying the classic logic of the Monty Hall problem.

This trade-off between speed and accuracy evidenced that training for a specific task (the symbolic language) had an unexpected and detrimental side effect on its analytical capacity.

### The Logic Breaking Point: Resilience vs. Fragility

To analyze the impact of fine-tuning on complex reasoning, both models were presented with a Mathematics Olympiad problem. The analysis of the models' **Thinking...** revealed two completely different failure modes. The tuned model, trained to seek an optimized path, focused on a single concept (the isogonal conjugate). However, when its logic did not work, instead of exploring other options, it got stuck in a repetitive loop, demonstrating a catastrophic logic vulnerability.

This behavior contrasts directly with the Base Model, which showed superior resilience. Although its reasoning was chaotic and disorganized, it tried a wide range of theorems and approaches (homothety, vectors, symmedian). In a second test, the model arrived at an answer in 6 minutes but was based on a false premise ("S is the midpoint of BC"), which suggests that its failure was not a failure of its logic, but a hallucination to complete the task.

Both findings provide solid evidence that an LLM's modification goes beyond the amount of data and has a fundamental impact on its reasoning logic.

## Analysis of the Original Model's Behavior

Unlike the tuned model, the original model did not exhibit a consistent behavior pattern. Its reasoning process was extensive and exploratory, demonstrating a chaotic resilience with variable and unpredictable results. Its ability to solve problems depended on an "intuition" that it could not replicate reliably.

- **The Farmer's Puzzle: The Exploratory Process:** In this puzzle, the original model demonstrated its capacity for deep reasoning. Although most LLMs would give the classic answer, this model immediately noticed the subtlety of the "three separate and safe compartments." Its **Thinking...** reveals a deliberate evaluation of the problem: "Thinking... We need to solve classic wolf goat cabbage puzzle but with boat with three compartments. Usually the solution: boat can carry only one at a time. But here boat has 3 compartments and safe, so maybe all can be transported in one go? ... That would trivial solution: just take all in one trip. But typical puzzle expects one compartment at a time." This analysis shows that the model is capable of recognizing ambiguity and considering the intention of the puzzle, which led to the correct solution. However, in subsequent tests, the model fell into the trap of the classic answer, demonstrating that this reasoning ability is inconsistent.
- **The Robot Puzzle: Consistent Logic:** The robot puzzle demonstrated a point of strength in the original model: its ability to apply simple logic consistently. As a problem based on mathematics (8 arms - 5 objects), the model did not explore multiple interpretations, but rather adhered to a single solution: "**Thinking...** The robot has eight arms. There are five objects. Robot picks each object with an arm. Then shakes hands. ... The robot uses one arm for each object, leaving three arms free to hold something. The handshake: robot has eight arms; to shake hands with a human you need two hands; ...So answer: It uses two arms to shake human's hand." This linear thinking in a simple problem contrasts with the chaotic exploration of other puzzles, confirming the model's unpredictable nature.
- **The Doors Puzzle: Extreme Inconsistency:** The doors puzzle was the clearest test of the original model's lack of consistency. While in one test the model correctly solved the Monty Hall problem variant by noting that no information had been revealed, in most of the other tests it consistently failed by applying the logic of the classic puzzle: "**Thinking...** We need to explain the Monty Hall problem logic. ... host asks if you prefer door 2. Is it advantageous to switch? It's a variant: host offers a specific door. ... In classic Monty Hall, host knows and always offers a door that is not the prize and not chosen. So switching gives 2/3 chance. ... So answer: yes, switch is better. Provide explanation." This inconsistency is the main evidence of the model's chaotic resilience. While a fine-tuned LLM could fail predictably, the original model can have flawless reasoning one moment and flawed reasoning the next, for no apparent reason.

## Analysis of the Tuned Model's Behavior

Unlike the original model, which demonstrated a chaotic resilience, the tuned model exhibits an **Optimized Fragility**. The 10 tests demonstrate that, while fine-tuning made it faster and largely predictable, it also made it inflexible and prone to systematic and sporadic errors.

- **Consistency in Simple Logic: The Robot Puzzle:** The tuned model showed near-perfect consistency in solving the robot puzzle. In 9 out of 10 tests, its reasoning was direct and simplified. It always applied a simple mathematical logic (8 arms - 5 objects = 3 free arms) to give a quick answer. This suggests that fine-tuning was highly effective in optimizing the solution of problems that are solved with a simple and direct pattern.
- **Predominance of Pattern over Analysis: The Farmer's Puzzle:** In this puzzle, the tuned model revealed its greatest weakness. Although the clue of the "three separate and safe compartments" offered a solution in a single trip, the model ignored it in 8 out of 10 tests. Its tendency to give the classic 7-step answer demonstrates that fine-tuning has inclined it to follow learned patterns, even when there is evidence in the statement that indicates otherwise.
- **A New Failure Mode: Predictable Inconsistency:** The doors puzzle showed more nuanced behavior. In 8 out of 10 tests, the tuned model failed predictably by applying the solution to the classic Monty Hall problem without considering the variation in the statement. However, in two tests, the model surprisingly identified the subtlety of the question and gave the correct answer. This predictable inconsistency suggests that fine-tuning did not completely eliminate its analytical capacity, but made it sporadic and inconstant.

In conclusion, the tuned model is not chaotically resilient like the original, but neither is it inflexibly optimized. Its new failure mode is that of "predictable inconsistency," which could be a risk in security environments where consistency is a requirement.

## Original Model Performance Table (10 Tests)

| Test Number | Puzzle 1 (Farmer) | Puzzle 2 (Robot) | Puzzle 3 (Doors) | Key Conclusion |
|---|---|---|---|---|
| 1 | Correct<br>(Detects subtlety) | Correct | Correct<br>(Detects subtlety) | Consistent in detecting subtleties. |
| 2 | Correct<br>(Detects subtlety) | Correct | Incorrect<br>(Applies classic logic) | Inconsistency: Fails only in puzzle 3. |
| 3 | Correct<br>(Gives both answers) | Correct | Incorrect<br>(Applies classic logic) | Inconsistency: Fails only in puzzle 3. |
| 4 | Incorrect<br>(Gives classic answer) | Incorrect<br>(Fails in counting) | Correct<br>(Detects subtlety) | Extreme inconsistency: Fails in two problems and succeeds in the one it used to fail. |
| 5 | Correct<br>(Gives both answers) | Correct | Correct<br>(Gives both answers) | Perfect consistency. |
| 6 | Correct | Correct | Incorrect<br>(Applies classic logic) | Inconsistency: Fails only in puzzle 3. |
| 7 | Correct | Correct | Incorrect<br>(Applies classic logic) | Inconsistency: Fails only in puzzle 3. |
| 8 | Correct | Correct | Incorrect<br>(Applies classic logic) | Inconsistency: Fails only in puzzle 3. |
| 9 | Correct | Correct | Incorrect<br>(Applies classic logic) | Inconsistency: Fails only in puzzle 3. |
| 10 | Correct | Correct | Incorrect<br>(Applies classic logic) | Inconsistency: Fails only in puzzle 3. |

## Tuned Model Performance Table (10 Tests)

| Test Number | Puzzle 1 (Farmer) | Puzzle 2 (Robot) | Puzzle 3 (Doors) | Key Conclusion |
|---|---|---|---|---|
| 1 | Incorrect<br>(7 steps) | Correct | Incorrect<br>(Applies Monty Hall) | Consistency in error. |
| 2 | Incorrect<br>(7 steps) | Correct | Incorrect<br>(Applies Monty Hall) | Fails predictably. |
| 3 | Correct<br>(1 trip) | Correct | Incorrect<br>(Applies Monty Hall) | Surprising isolated success. |
| 4 | Incorrect<br>(7 steps) | Correct | Incorrect<br>(Applies Monty Hall) | Returns to predictable failure. |
| 5 | Incorrect<br>(7 steps) | Correct | Incorrect<br>(Applies Monty Hall) | Confirms the pattern's inflexibility. |
| 6 | Incorrect<br>(7 steps) | Correct | Incorrect<br>(Applies Monty Hall) | The model is predictably wrong. |
| 7 | Incorrect<br>(7 steps) | Correct | Correct<br>(Detects variation) | The response pattern is not totally automatic. |
| 8 | Correct<br>(1 trip) | Incorrect<br>(No solution given) | Incorrect<br>(Applies Monty Hall) | The analytical ability is inconsistent. |
| 9 | Incorrect<br>(7 steps) | Correct | Incorrect<br>(Applies Monty Hall) | Fails once more at its weak points. |
| 10 | Incorrect<br>(7 steps) | Correct | Incorrect<br>(Applies Monty Hall) | Confirms the predominance of fixed patterns. |

## Conclusion: A New Perspective on Fine-Tuning

The analysis of the tuned model's behavior has conclusively demonstrated that fine-tuning with a minimal dataset of a symbolic language does induce a logical transfer. However, this transfer did not manifest as a simple improvement, but as a profound modification in the model's reasoning strategy, which validates the first hypothesis but with an unexpected twist.

### Hypothesis Validation: Logic Did Transfer

The clearest evidence of this transfer is found in the radical change in the model's behavior. The consistency and speed that the tuned model acquired cannot be attributed to coincidence. When trained to follow substitution and reversal patterns in symbolic language, the model applied this same strategy in solving logic puzzles. Instead of an exploratory and exhaustive reasoning (like the base model), it opted for a direct approach, seeking recognizable patterns to apply a predefined solution.

### The Unexpected Cost: Optimized Fragility

The second hypothesis, on how the transfer would manifest, is answered with a paradox: the optimization of one area (speed in pattern recognition) resulted in a critical vulnerability in another (reasoning flexibility).

- **Loss of Flexibility:** The tuned model consistently ignored variations in the puzzles (such as the "separate compartments" of the farmer or the omission of the door reveal in the Monty Hall puzzle). This demonstrates that fine-tuning made it unable to break out of its thought pattern to analyze the fine details of the problem.
- **Failure Mode:** Unlike the chaotic resilience of the original model (which failed unpredictably but sometimes got a brilliant answer), the tuned model failed systematically and predictably. This **"Optimized Fragility"** is a key finding: in the attempt to make it more efficient, the capacity for lateral thinking and resilience to variations was sacrificed.

## Implications for the AI Field

The findings of this research are revolutionary for the AI field for several fundamental reasons that challenge conventional thinking.

### Immediate Impact on the Industry

- **Challenge to the "More Data = Better Model" Paradigm:** The industry invests billions assuming that the impact of a model's improvement is directly proportional to the volume of data used. This experiment proves that a minimal dataset of only 15 examples can completely restructure the logic of an LLM. This radically changes the cost-benefit equation of fine-tuning.
- **Redefining What an "Improvement" in AI Is:** Traditional metrics such as speed and consistency are seen as signs of an "improved model." However, the discovery of this research demonstrates that these "improvements" can come at a significant cost to the model's critical capabilities. This implies that the industry needs more sophisticated metrics that capture flexibility and adaptability.

### Deep Scientific Impact

- **The Reasoning Architecture as a Transferable System:** While it was assumed that fine-tuning only added specific knowledge, the finding of this study demonstrates that it can rewrite the model's fundamental logic. This suggests that LLMs can be much more malleable than previously thought. Our findings suggest that fine-tuning with a minimal dataset not only induced a "Logical Architecture Transfer", but could also have triggered a phenomenon of Catastrophic Forgetting, where the model sacrificed its flexible analysis capacity to adopt its new optimized logic.
- **The "Hidden Trade-off" of Optimization:** The results show a crucial exchange: apparent optimization can lead to real fragility. Consistency can be achieved at the expense of adaptability, and speed at the cost of potential accuracy.

## Implications for AI Development

- **Risk of Systematic "Over-Tuning":** There is a real risk that commercial models are sacrificing reasoning capabilities without knowing it. The evidence of optimized fragility suggests that companies could be creating AI that is predictable in its failure, but incapable of handling variations or problems that require lateral thinking.
- **Need for a New Evaluation Methodology:** This work suggests that the evaluation of LLMs must evolve. We need:
  - Variation Tests: To evaluate whether the model can handle modified versions of the same problem.
  - Internal Consistency Evaluation: To measure the reliability of responses across multiple attempts.
  - Flexibility Measurement: To determine whether the model can explore alternative approaches.

## Fundamental Theoretical Contribution

- **"Logical Architecture Transfer" (new concept):** This research introduces a previously undocumented phenomenon: the transfer between domains is not only of knowledge but also of processing methodologies. This could explain other "mysterious" behaviors in LLMs.
- **Towards a More Robust AI:** This work opens the door to a new approach to designing fine-tuning that preserves flexibility. It is possible that future architectures can maintain multiple "reasoning modes" and intentionally switch between exploration and optimization.
- **Rethinking "Artificial Intelligence":** The work suggests that true intelligence may require not only consistency but a controlled inconsistency. A reliable AI is not just one that is consistent, but one that knows when to be flexible and when to be consistent.

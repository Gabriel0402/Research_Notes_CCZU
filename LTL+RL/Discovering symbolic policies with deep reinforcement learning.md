# Discovering symbolic policies with deep reinforcement learning
## Quick Look

**Authors**: Mikel Landajuela

**Date Published** : 2021

**Link** : [Paper link]

**Comments:**  ICML

**TLDR:** symbolic planning, deep reinforcement learning

**Tags**: symbolic planning, deep reinforcement learning

## Paper summary (What)

The paper titled "Discovering Symbolic Policies with Deep Reinforcement Learning" introduces a novel framework called Deep Symbolic Policy (DSP) for learning control policies in reinforcement learning (RL) environments. The key points of the paper are summarized below:

1. Deep Reinforcement Learning Challenges: Deep reinforcement learning (DRL) has been successful in solving complex control problems using neural network-based policies. However, the complexity of these policies, involving thousands of non-linear operators, makes them hard to understand, trust, and deploy​​.

2. Deep Symbolic Policy (DSP) Framework: DSP addresses these challenges by searching the space of symbolic policies represented by tractable mathematical expressions. This approach offers several advantages:

    -   Interpretability: Symbolic expressions are more easily understood and inspected.
    -   Generalizability: These policies can generalize to continuous-time settings.
    - Deployability: They are lightweight and fast, making them suitable for real-world applications where memory and latency are critical.
    - Transparency and Verifiability: Easier to reproduce and predict behavior compared to neural network-based policies.
    - Performance: Surprisingly robust performance, competitive with complex NN-based policies​​.

3. Policy Generation and Evaluation: The DSP approach uses an autoregressive recurrent neural network (RNN) to generate control policies as mathematical expressions. These policies are then evaluated in simulated RL environments. An innovative "anchoring" algorithm is introduced for scaling to environments with multidimensional action spaces, distilling pre-trained neural network-based policies into fully symbolic policies​​.

4. Exploration Techniques: To improve exploration in DSP, two novel techniques are introduced:

    - Hierarchical Entropy Regularizer: This technique addresses the early commitment problem in policy generation, ensuring diverse exploration across the decision space.
    - Soft Length Prior: This method improves the initialization of the policy generation process, promoting exploration over different sequence lengths​​.
    
5. Experimental Setup and Results: The experiments use an RNN with a single-layer LSTM to generate policies, evaluated in various continuous control environments. Despite their reduced complexity, symbolic policies discovered through DSP outperform seven state-of-the-art DRL algorithms in terms of average rank and normalized episodic reward across eight benchmark environments. Notably, these policies are provably stable in environments where transition dynamics are known​​.

6. Conclusion: The DSP framework demonstrates that symbolic control policies can be a viable alternative to NN-based policies, especially in scenarios where interpretability and deployment constraints are critical. The generated policies are interpretable, easily deployable, transparent, and reproducible, making them suitable for a wide range of applications​​.

## Motivation (What)
- Interpretability and Transparency: Neural network-based policies in DRL, while effective, tend to be complex and opaque, consisting of thousands of non-linear operators. This complexity makes it difficult for humans to understand, trust, and interpret these policies. The paper is motivated by the need for more interpretable and transparent control policies, which can be easily understood and inspected by humans.

- Generalizability and Deployability: There is a need for control policies that can generalize well to different environments, particularly from discretized simulated environments to continuous-time settings. Additionally, deployability is a concern in real-world applications, where factors like specialized hardware requirements, memory footprint, and execution latency are crucial. The paper aims to create policies that are lightweight, fast, and easily deployable in various settings.

- Performance and Robustness: Despite seeking simplicity and interpretability, there is no compromise on the performance aspect. The paper is driven by the goal of developing symbolic policies that can match or even outperform the complex neural network-based policies in terms of robustness and efficacy across different environments.

- Overcoming Exploration Challenges in DRL: The paper also aims to address specific challenges in DRL, such as the early commitment problem and initialization bias, which can limit the exploration capabilities of the learning algorithm. Introducing novel exploration techniques, such as hierarchical entropy regularizer and soft length prior, is motivated by the need to enhance the policy generation process and ensure effective exploration in the combinatorial space of expression trees.

## Issues addressed by the paper (Why)
[What are the issues that the paper addresses? Describe the problem. Why did they write this paper?]

## Detailed Information (How)
[ Only for work that appears to be highly related from reading abstract/intro/conclusion.]

### Problem Setting
[ What is the problem setting e.g. regression, classification or sequence prediction? In RL, this would also include the environment and details about rewards etc. This should include the evaluation setting for the results. ]

### Methodology
[How did they approach the problem. What methods did they use?]

### Assumptions
[What assumptions were made and are these assumptions valid?]

### Prominent Formulas
[Can be empty]

### Results
- Performance in Benchmark Environments: The symbolic policies discovered using the DSP framework were tested across eight continuous control benchmark environments. Remarkably, these policies, despite their relative simplicity, achieved higher normalized episodic reward, higher average rank, and lower worst-case rank compared to seven state-of-the-art deep reinforcement learning (DRL) algorithms. This result is significant as it shows that the simpler, more interpretable symbolic policies can compete with or even outperform complex neural network-based policies in certain scenarios​​.

- Policy Generator and Evaluator Efficiency: The Policy Generator, an RNN comprising a single-layer LSTM with 32 hidden units, efficiently generated mathematical expressions as control policies. These policies were then evaluated by the Policy Evaluator, which replaced any undefined actions with zeroes to maintain operational stability. This setup effectively constrained the length of each expression, thereby balancing complexity and performance​​.

- Novel Exploration Techniques: The paper introduced two novel exploration techniques - hierarchical entropy regularizer and soft length prior. These techniques were instrumental in improving the exploration capabilities of the DSP framework, addressing issues like early commitment and initialization bias commonly encountered in RNN-based neural-guided searches​​.

- Demonstration of Stability: For environments where transition dynamics were known, the paper was able to show that the symbolic policies generated were provably stable with respect to variations in initial conditions. This aspect of stability is crucial for real-world applications where predictability and reliability are key considerations​​.

- Advantages of Symbolic Policies: The results underscored several advantages of symbolic policies, including their interpretability, deployability, transparency, and reproducibility. These qualities make symbolic policies particularly valuable in scenarios where understanding the decision-making process is important or where deployment constraints such as memory and latency are critical design considerations​​.

### Limitations
- Complexity in Multi-Dimensional Action Spaces: While the paper introduces a novel model distillation technique to handle multi-dimensional action spaces, managing the complexity associated with higher-dimensional spaces remains challenging. The approach might become increasingly complicated or less efficient as the dimensionality of the action space grows​​.

- Dependency on Pre-Trained Neural Networks for Anchoring: The method relies on pre-trained neural network-based policies to "anchor" the symbolic policy learning process. This reliance means that the effectiveness of the symbolic policies could be contingent on the quality of these pre-trained neural networks, which introduces an additional step and dependency in the process​​.

- Scope of Tested Environments: The evaluation of the approach is limited to eight continuous control benchmark environments. While the results are promising, the performance and applicability of the method across a broader range of environments, especially those with different characteristics or higher complexity, remain to be fully explored​​.

- Trade-off Between Simplicity and Performance: While one of the goals is to maintain performance, there might be scenarios where the simplicity and interpretability of symbolic policies come at the cost of some reduction in performance compared to more complex neural network-based policies. This trade-off is an inherent challenge when prioritizing interpretability and transparency over purely performance-based metrics​​​​.

- Generalization to Real-World Scenarios: While the paper demonstrates the deployability of symbolic policies in simulated environments, their performance and effectiveness in real-world scenarios, which might present unforeseen challenges and complexities, are not explicitly tested or demonstrated.

- Exploration Techniques Specificity: The exploration techniques proposed, such as hierarchical entropy regularizer and soft length prior, are innovative, but their effectiveness might be specific to the types of environments and problems tested. Their applicability and performance in other types of reinforcement learning tasks or environments might require further validation​​.


## Conclusions

### The author's conclusions
[What is the author's conclusion? What do they claim about their results?]

### My Conclusion
[What do you think about the work presented in the article? Did the authors manage to achieve what they set out to achieve?]

### Rating
Good

## Possible future work / improvements
- Expansion to More Complex Environments: Testing and refining the DSP framework in more varied and complex environments, particularly those that more closely resemble real-world scenarios, would be beneficial. This could include environments with higher-dimensional action spaces, non-stationary environments, or those with more intricate dynamics.

- Integration with Other Learning Paradigms: Exploring the integration of DSP with other learning paradigms, such as unsupervised learning or transfer learning, could enhance its adaptability and efficiency, especially in environments where labeled data are scarce or in multi-task learning scenarios.

- Addressing Higher-Dimensional Action Spaces: While the paper presents a novel approach to handle multi-dimensional action spaces, further research is needed to efficiently scale the DSP framework to environments with significantly higher dimensions, where the complexity of symbolic policy generation and evaluation might increase dramatically.

- Real-World Deployment and Testing: Applying the DSP framework in real-world settings to validate its effectiveness and adaptability outside of simulated environments. This includes assessing the impact of real-world constraints like sensor noise, latency, and computational limitations on the performance of symbolic policies.

- Improving Exploration Techniques: Further development and refinement of the hierarchical entropy regularizer and soft length prior techniques are needed. Research could focus on customizing these techniques for a wider range of RL problems and exploring other novel methods to enhance exploration efficiency.

- Robustness and Generalization: Investigating the robustness of the symbolic policies to variations in environment conditions and their ability to generalize across different but related tasks. This could also include examining the transferability of learned policies between similar environments.

- Algorithmic Improvements and Efficiency: Optimizing the computational efficiency of the DSP algorithm, possibly through advancements in the policy generator’s architecture or the policy evaluation process, to make it more feasible for large-scale applications.

- Human-Interpretable Policy Refinement: While the policies generated are symbolic and more interpretable than neural network policies, there is scope for research into methods that can further refine these policies to be even more understandable and insightful for human operators.

- Theoretical Analysis: Conducting more in-depth theoretical analysis and providing formal guarantees regarding the convergence, optimality, and stability of the DSP framework in various settings.

## Relation to Own Work
[If related to own work.]

- What can we learn from their approach:
- How are we different:

## Extra
- Cited references to follow up on/related papers/check google scholar for papers citing this paper:
- Source code/blog/twitter thread/other links:

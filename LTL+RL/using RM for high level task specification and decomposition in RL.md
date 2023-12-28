# Using RM for high level task specification and decomposition in RL
## Quick Look

**Authors**: Rodrigo Toro Icarte 1 2 Toryn Q. Klassen 1 Richard Valenzano 3 Sheila A. McIlraith 1 2

**Date Published** : [Date published or submitted.]

**Link** : [Paper link]

**Comments:**  [e.g. Published at X / arXiv paper/ in review.]

**TLDR:** This paper introduces reward machines, a novel framework for specifying reward functions in reinforcement learning, and presents Q-learning for Reward Machines (QRM), a method that efficiently learns policies for tasks defined by reward machines, demonstrating its effectiveness in various domains.

**Tags**: Q-learning、QRM、Reward Machine

## Paper summary (What)
In this paper we propose Reward Machines – a type of finite state machine that supports the spec-
ification of reward functions while exposing reward function structure to the learner and supporting decomposition. We then present Q-Learning for Reward Machines (QRM), an algorithm which appropriately decomposes the reward machine and uses off-policy q-learning to simultaneously learn subpolicies for the different components. QRM is guaranteed to converge to an optimal policy in the tabular case, in contrast to Hierarchical Reinforcement Learning methods which might converge to suboptimal policies. We demonstrate this behavior experimentally in two discrete domains. We also show how function approximation methods like neural networks can be incorporated into QRM, and that doing so can find better policies more quickly than hierarchical methods in adomain with a continuous state space.

## Motivation (What)
The motivation for the paper arises from the need to improve the efficiency and effectiveness of reinforcement learning (RL) by addressing several challenges in RL, including sparse rewards, temporally extended tasks, and the complexity of specifying reward functions. The authors introduce the concept of Reward Machines (RMs) as a way to tackle these challenges and simplify RL tasks. They aim to provide a structured approach to reward design, enhance the learning process, and make RL more applicable to real-world problems where manually crafting reward functions can be impractical or time-consuming.

## Issues addressed by the paper (Why)
The paper addresses the following issues and challenges in reinforcement learning (RL):

1. Sparse Reward Problem: In many RL tasks, reward signals are rare, making it difficult for agents to learn appropriate behavior.
2. Temporally Extended Tasks Problem: Some tasks require agents to perform a sequence of complex actions that cannot be guided simply by a single reward signal.
3. Complexity of Reward Functions: Manually designing complex reward functions is challenging, error-prone, and may not be practical for solving complex real-world problems.

## Detailed Information (How)
[ Only for work that appears to be highly related from reading abstract/intro/conclusion.]

### Problem Setting
1. Environment: The paper uses various gridworld environments as examples, including an office gridworld and a Minecraft-like gridworld. These environments are used to illustrate how Reward Machines can be applied to different scenarios.
2. Tasks: The paper considers multiple tasks within these gridworld environments. For example, tasks in the office gridworld include delivering coffee to the office, patrolling specific locations, and avoiding breaking decorations. In the Minecraft-like gridworld, tasks involve crafting objects by collecting raw materials.
3. Sequential Reward Functions: The primary focus of the paper is on representing and learning sequential reward functions. Traditional RL typically uses a single reward function, but in this setting, different tasks can have temporally extended and complex reward structures.
4. Evaluation Setting: The paper evaluates its approach by comparing it to baseline methods, including Q-learning and hierarchical RL approaches, across various tasks within the gridworld environments. The evaluation assesses the sample efficiency and performance of the proposed approach.

Overall, the paper addresses the problem of learning and representing sequential reward functions in RL, particularly in scenarios where tasks involve non-Markovian rewards and complex, temporally extended behaviors. It introduces Reward Machines as a framework to handle such settings and evaluates their effectiveness in gridworld environments.

### Methodology
1. **Reward Machine Formalism**: They formally define Reward Machines as finite state machines over a set of propositional symbols. RMs are used to specify complex, sequential reward functions that can capture temporal dependencies in RL tasks.
2. **Q-Learning for Reward Machines (QRM)**: The authors propose a Q-learning-based algorithm called QRM to learn policies for tasks defined by RMs. QRM decomposes tasks into sub-tasks and uses off-policy learning to train each sub-policy in parallel.
3. **Task Decomposition**: Their approach decomposes tasks into sub-tasks, allowing the agent to learn and optimize policies for different components of a task separately.
4. **Evaluation Setting**: They evaluate their approach by comparing it to baseline methods, including Q-learning and hierarchical RL approaches, in gridworld environments with various tasks. The evaluation assesses sample efficiency and performance.
5. **Tabular Representations**: In the experiments, the authors primarily use tabular representations for RMs, which are suited for discrete state spaces.
6. **Deep Q-Learning Extension**: They mention that their QRM approach can be extended to use deep reinforcement learning methods, such as Double DQN, for tasks in environments with continuous state spaces.

Overall, the authors' approach combines the formalism of Reward Machines with Q-learning to address the problem of learning and representing sequential reward functions in RL, with a focus on improving sample efficiency and performance.

### Assumptions
1. **Reward Machine Formalism**: The paper assumes that tasks in reinforcement learning can be effectively represented using Reward Machines (RMs). This assumption is valid in the sense that RMs are designed to capture a wide range of sequential and temporal reward structures, making them a versatile tool for task representation.
2. **Decomposability of Tasks**: The approach assumes that tasks can be decomposed into subtasks, and learning subpolicies for these subtasks can lead to efficient learning. This assumption is generally valid, especially in complex environments where breaking down tasks into manageable components can simplify learning.
3. **Tabular Representation**: In the experiments, the paper primarily uses tabular representations for RMs. This assumption is valid for environments with discrete state spaces.
4. **Task Transition Regularity**: The paper suggests that tasks can be represented using regular languages over propositional symbols. This assumption is valid for tasks that exhibit regular and predictable patterns.
5. **Off-Policy Learning**: The paper relies on off-policy learning techniques. This assumption is valid in settings where past experiences can be reused efficiently, which is often the case in RL.

### Prominent Formulas
[Can be empty]

### Results
1. **Experiments in Discrete Domains**: In discrete environments, the QRM method performs well when solving multiple tasks, showing faster learning. This might be because QRM can simultaneously learn sub-policies for tasks, speeding up the learning process. Traditional q-learning performs poorly in this regard as it needs to learn each task separately.
2. **Experiments in Continuous Domains**: In continuous environments, QRM also performs well when solving multiple tasks, while hierarchical reinforcement learning methods tend to converge to suboptimal policies. This could be because QRM can adapt more flexibly to different tasks and environments, while hierarchical methods may be constrained by task decomposition and sub-policy optimization.
3. **Combining Hierarchical RL with Reward Machines**: In hierarchical RL, combining reward machines into task decomposition leads to improved performance in hierarchical methods. This suggests that reward machines can provide more information to hierarchical policies, enhancing their performance.
4. **Convergence Guarantee**: The QRM method proposed in the paper has a convergence guarantee in discrete environments, while hierarchical methods do not. This could be because QRM learns tasks in a more global manner, whereas hierarchical methods might get stuck in local optima while optimizing sub-policies.

### Limitations
1. **Convergence Guarantee for Deep QRM**: While the paper mentions a convergence guarantee for QRM in tabular cases, it's unclear if the same guarantee holds for deep QRM when applied to complex, high-dimensional environments. Further analysis is needed to determine the convergence properties of deep QRM.
2. **Scalability in Large Environments**: The paper discusses the scalability of QRM but does not provide extensive experiments in large-scale environments. It would be valuable to explore how well QRM performs when applied to more complex and larger state spaces.
3. **Generalization**: The paper focuses on multi-task learning and discrete domains. Investigating how well QRM generalizes to unseen tasks and continuous environments is an important avenue for future research.
4. **Memory and Computational Requirements**: QRM is described as a form of memory for the agent, but the paper does not delve into the memory and computational requirements as the complexity of tasks and environments increases. Understanding the trade-offs between memory usage and performance would be beneficial.
5. **External Memory**: The paper mentions that reward machines can specify structure beyond regular languages but leaves the handling of external memory as future work. It would be interesting to explore how agents can effectively utilize external memory to handle more complex tasks.
6. **Real-world Applications**: The experiments are conducted in simulated environments. Future work should focus on applying QRM to real-world applications and evaluating its practicality and performance.

### Confusing aspects of the paper
[Is there anything that is confusing and could need better explanations or references?]

## Conclusions

### The author's conclusions
In this paper we introduced the notion of reward machines– a form of finite state machine that can be used to specify the reward function of an RL agent. Reward machines support the specification of arbitrary rewards, including sparse rewards and rewards for temporally extended behaviors. Reward machines can expose structure in the reward function and, in so doing, can speed up learning as demonstrated in our experiments. We proposed a means of q-learning for reward machines (QRM) which decomposes the reward and uses off-policy learning to simultaneously learn subpolicies for the different components. QRM is guaranteed to converge to an optimal policy in the tabular case, in contrast to Hierarchical Reinforcement Learning. We believe there is significant potential in reward machines beyond what has been described in this paper. For one, reward machines can decrease the overhead of defining new
tasks in a given environment since, having defined a set of relevant events, creating a new reward machine is straight-forward. In fact, it would be possible to automatically create random tasks and their corresponding natural language descriptions using reward machines. This would allow for generating training data for a deep network that could learn to map natural language commands into policies in the same way that functional programs are available as training data for learning how to interpret questions in CLEVR (Johnson et al., 2017).Reward machines also act as a small amount of memory for the agent. This feature would simplify learning when solving tasks in domains with partial observability.
Finally, as reward machines are a form of finite state machine, they can be created to correspond to sentences in many different formal languages, including regular expressions and various procedural programming languages. In future work, we plan to exploit these relationships to investigate novel behavioral specification languages for RL that can be mapped to reward machines and solved using QRM.

### My Conclusion
[What do you think about the work presented in the article? Did the authors manage to achieve what they set out to achieve?]

### Rating
[Fine, Good, Great]

## Possible future work / improvements
[Can you think of ways to improve this paper or ideas for future work?]

## Relation to Own Work
[If related to own work.]

- What can we learn from their approach:
- How are we different:

## Extra
- Cited references to follow up on/related papers/check google scholar for papers citing this paper:https://chat.openai.com/c/adfd1438-6c46-4b5f-a443-fd3d1ece9dff
- Source code/blog/twitter thread/other links:

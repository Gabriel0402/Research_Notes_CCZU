# LTL and Beyond: Formal Languages for Reward Function Specification in Reinforcement Learning
## Quick Look

**Authors**: Alberto Camacho , Rodrigo Toro Icarte , Toryn Q. Klassen1,Richard Valenzano、Sheila A. McIlraith

**Date Published** : 2019

**Link** : [Paper link]

**Comments:**  International Joint Conference on Artificial Intelligence

**TLDR:** The paper introduces Reward Machines (RMs) as a normal form to represent reward functions, enabling efficient reinforcement learning across various reward specification languages. It also presents RM-customized Q-learning and reward shaping techniques to improve RL performance.

**Tags**: ltl, Q-learning

## Paper summary (What)
- The paper introduces Reward Machines (RMs) as a normal form for representing reward functions in reinforcement learning.
- The hypothesis is that RMs can serve as a common representation for reward functions specified in various formal languages, improving sample efficiency and facilitating reward specification.
- The authors propose an algorithm for translating reward functions specified in different languages into RMs, thus enabling the use of diverse reward specification languages.
- They also introduce RM-customized Q-learning and reward shaping techniques to enhance reinforcement learning performance.
- The paper presents experiments in different environments to demonstrate the effectiveness of these approaches in improving sample efficiency and learning policies.

## Motivation (What)
1. Difficulty of Reward Specification: Reinforcement learning often requires the definition of reward functions, which can be complex and challenging to specify accurately. Different tasks and environments may require rewards to be expressed in various formal languages, making it difficult to design reward functions manually.
2. Sample Efficiency: Traditional reinforcement learning algorithms may require a large number of samples to learn optimal policies, which can be time-consuming and impractical in many real-world scenarios.

To tackle these challenges, the paper introduces the concept of Reward Machines (RMs) as a normal form for representing reward functions and proposes methods to automatically translate reward specifications from diverse formal languages into RMs. By doing so, it aims to simplify reward specification and enhance the sample efficiency of reinforcement learning algorithms.

## Issues addressed by the paper (Why)
To tackle these challenges, the paper introduces the concept of Reward Machines (RMs) as a normal form for representing reward functions and proposes methods to automatically translate reward specifications from diverse formal languages into RMs. By doing so, it aims to simplify reward specification and enhance the sample efficiency of reinforcement learning algorithms.

## Detailed Information (How)
This paper primarily employs the use of Reward Machines (RMs) to address two key issues in reinforcement learning: the difficulty in specifying reward functions and the problem of low sample efficiency. Here is an overview of the main methods, processes, and problem-solving aspects in the paper:

Introduction of Reward Machines (RMs): The paper introduces Reward Machines as a standard form to represent reward functions. RMs structure reward functions and serve as a universal language for specifying reward functions, enabling the translation of various reward functions from different formal languages into RMs.

Translation of Reward Functions: The paper describes the method for translating reward functions from various formal languages into RMs. This includes the process of extracting reward functions from goal and temporal property specification languages and converting them into RMs, making reward function specification more accessible.

RM-Customized Q-Learning: The paper proposes the use of RMs-structured reward functions along with customized Q-learning algorithms to improve sample efficiency in reinforcement learning. This combination allows agents to learn high-quality policies faster.

Reward Shaping: To further enhance RM-customized Q-learning, the paper introduces reward shaping. This method involves computing a potential function, which enables agents to learn optimal policies more quickly and improves learning by fine-tuning the reward function.

Experimental Validation: The paper conducts experiments to validate these methods using three different test environments and multiple tasks, including Grid World, Minecraft, and WaterWorld. The experimental results demonstrate that the use of RMs and reward shaping significantly enhances the performance of reinforcement learning, particularly in terms of sample efficiency.

### Problem Setting
In the context of reinforcement learning, the problem setting involves several key aspects, including the environment, reward functions, and tasks:

1. **Environment Setting**: The paper mentions three different test environments, namely Grid World, Minecraft, and WaterWorld. These environments define the scenarios in which the agent operates and the actions it can perform.
2. **Reward Functions**: Reward functions are a crucial component of reinforcement learning. The paper introduces methods to translate various reward functions from different formal languages into Reward Machines (RMs). RMs provide a structured representation of reward functions and define the rewards the agent receives for different states and actions.
3. **Task Setting**: In each test environment, the agent is assigned a set of tasks to solve. For all tasks, the agent receives a reward of 1 only upon completing the task, while the reward is 0 at all other times. This task setting is used to evaluate the agent's performance across different tasks.
4. **Sample Efficiency**: The paper focuses on addressing the issue of sample efficiency in reinforcement learning, i.e., how to enable the agent to learn high-quality policies with fewer samples. This is achieved through methods like Reward Machines (RMs) and reward shaping, which improve the agent's learning efficiency.

### Methodology
1. This paper addresses the problem of sample efficiency in reinforcement learning through several methods and techniques:
   1. **Introduction of Reward Machines (RMs)**: The paper introduces Reward Machines as a structured representation of reward functions. RMs provide a standardized form for representing reward functions, making it easier to define and handle various reward specifications.
   2. **Translation of Reward Functions**: The authors propose a method to translate reward functions from different formal languages into Reward Machines (RMs). These languages include goal and temporal property specification languages. This translation process allows reward functions to be specified in multiple languages while benefiting from RM-based reinforcement learning techniques.
   3. **RM-Customized Q-Learning**: The paper introduces RM-customized Q-learning, a method that utilizes structured reward functions provided by RMs. In this approach, the agent learns Q-functions specific to RM states, thereby improving sample efficiency.
      1. **Construction of Reward Machines**: Firstly, reward functions need to be represented in the form of RMs. This involves structuring the reward function into a set of states and transitions so that the agent can better understand the rules and conditions of the reward function.
      2. **Initialization of Q-Functions**: Q-functions are initialized for each RM state. These Q-functions are used to estimate the cumulative reward value for a given state and action.
      3. **Q-Value Updates**: As the agent interacts with the environment, it updates the Q-functions based on the current state and action. The updates typically follow the Q-learning update rules, such as the Bellman equation. For RM-customized Q-learning, the agent updates the corresponding Q-function for each RM state.
      4. **Policy Improvement**: The agent improves its policy based on the updated Q-functions. It selects actions with the highest Q-values as the next actions, increasing the likelihood of obtaining higher cumulative rewards.
   4. **Reward Shaping**: To further enhance RM-based reinforcement learning, the paper introduces reward shaping. Reward shaping involves calculating a potential function that approximates the cumulative discounted reward based on the RM structure. This method accelerates the learning process of the optimal policy.
      1. **Value Iteration**: Firstly, value iteration is performed to compute the optimal value function for each RM state. This value function represents the expected cumulative discounted reward in each RM state.
      2. **Calculation of Potential Function**: Based on the optimal value function, a potential function is computed. This potential function is typically represented as negative values and is incorporated as part of the reward function.
      3. **Adjustment of Reward Function**: The potential function is added to the RM's reward function to improve the agent's learning process. This way, the agent learns the optimal policy more efficiently as the reward function's structure has been adjusted to better guide the agent's learning.
      4. **Q-Function Updates**: In RM-customized Q-learning, the agent uses the adjusted reward function to update the Q-functions. This enables the agent to learn the optimal policy more efficiently.
   5. **Experimental Evaluation**: The authors conducted experiments in three different test environments: Grid World, Minecraft, and WaterWorld. They evaluated the effectiveness of RM-based methods, including RM-customized Q-learning and reward shaping, in improving sample efficiency and learning high-quality policies.

### Assumptions
The paper makes several assumptions in the context of reinforcement learning and the use of Reward Machines (RMs). These assumptions include:

1. **Assumption of RM Representation**: The paper assumes that reward functions can be effectively represented using Reward Machines. While this assumption is generally valid, it relies on the idea that reward functions can be structured into states and transitions, which may not always hold true for highly complex or continuous reward functions.
2. **Assumption of Formal Language Translation**: The paper assumes that reward functions specified in different formal languages (e.g., goal and temporal property specification languages) can be accurately translated into RMs. The validity of this assumption depends on the complexity and expressiveness of the source languages and the ability to faithfully capture their semantics in RMs.
3. **Assumption of Q-Learning Applicability**: The paper assumes that Q-learning can be effectively applied to RM-customized Q-learning. While Q-learning is a widely used reinforcement learning algorithm, its effectiveness depends on factors like the choice of Q-function representation and exploration strategy. The assumption of Q-learning's applicability might not hold for all scenarios.
4. **Assumption of Reward Shaping Benefit**: The paper introduces the concept of reward shaping, assuming that it will lead to improved learning efficiency. The validity of this assumption depends on the specific reward shaping function and its impact on the agent's learning process. It may not always hold true, as the effectiveness of reward shaping can vary depending on the task and domain.
5. **Assumption of Experiment Environments**: The paper assumes the availability of three test environments (Grid World, Minecraft, and WaterWorld) for conducting experiments. The validity of these environments as representative benchmarks for reinforcement learning tasks may be subject to debate, as they might not cover all possible scenarios encountered in real-world applications.

### Prominent Formulas
[Can be empty]

### Results
1. **Utility of Reward Machines (RMs)**: In the experimental section, the paper discusses the performance of reinforcement learning methods based on RMs in three different test environments. The authors find that using RMs can significantly improve the performance of reinforcement learning, especially in terms of sample efficiency. This suggests that RMs, as a structured representation of reward functions, are effective.
2. **Effectiveness of Reward Shaping**: The paper also discusses the effectiveness of reward shaping methods. The authors find that in some cases, reward shaping can further improve the agent's learning efficiency, especially when the task has limited samples or is difficult to obtain. This indicates that reward shaping can be used to accelerate the convergence of reinforcement learning.
3. **Performance Differences in Different Test Environments**: The paper mentions three different test environments, including Grid World, Minecraft, and WaterWorld. The authors observe performance differences in methods based on RMs in these different environments. This may be due to variations in the complexity and characteristics of different environments, leading to differences in the applicability of the methods.
4. **Sample Efficiency of RM-Customized Q-learning**: The RM-customized Q-learning method achieves good sample efficiency. This is because the method leverages the structured reward functions provided by RMs, helping the agent learn high-quality policies faster.
5. **Special Case of Deep Learning Environments**: The paper points out that in the WaterWorld deep learning environment, the reward shaping method did not show significant improvement. The authors speculate that this may be due to the complexity and continuity of deep learning environments, which limit the effectiveness of reward shaping.

In summary, the experimental results indicate that using RMs as a structured representation of reward functions can improve the performance and sample efficiency of reinforcement learning. Additionally, reward shaping methods can further enhance learning efficiency in some cases. Performance differences in different test environments may be attributed to variations in environment characteristics. Further research is needed to delve into the reasons and implications of these results.Limitations

[Did the authors mention any reservations/limitations to their work or methodology? Do you see any limitations of their work?]

### Confusing aspects of the paper
[Is there anything that is confusing and could need better explanations or references?]

## Conclusions

### The author's conclusions
We examined two important challenges of Reinforcement Learning: (i) the difficulty of reward specification, and (ii)sample efficiency. We proposed the use of Reward Machines(RMs) as a normal form to represent reward functions and as a lingua franca for reward functions initially specified in other languages. We provided a formal characterization of RMs in terms of Mealy machines and noted the association with
automata, thereby providing a means to translate a diversity of goal and temporal property specification languages, augmented with scalar rewards, to RMs. Finally, we presented an algorithm to realize the translation between automata and RMs, providing a link to a tool under development for automatically generating RMs from various formal languages.

RMs expose the structure of the reward function to the learning agent, which when used in conjunction with RM-customized q-learning, results in a marked improvement in sample efficiency, and thus in faster realization of highquality policies. The translation of all these formal languages to RMs obviates the need for numerous tailored q-learning algorithms, while supporting reward specification in a diversity of compelling languages. We proposed the use of reward shaping to enhance existing RM-tailored q-learning
by computing a potential function that approximates the expected cumulative discounted reward based on the RM structure. A link to the code used for experimenting with this method has been provided. Results were impressive in the tabular case, significantly outperforming QRM, the incumbent RM-tailored q-learning algorithm. In the Deep learning case, the use of reward shaping showed no added benefit
over this already highly effective RM-tailored q-learning algorithm, though further investigation is needed.

Formal languages present important advantages over traditional programming languages used for reward specification: they are compositional, some are declarative, and many support easy specification of temporally extended behavior. Our methods enable the use of a myriad of different languages to specify reward, while enjoying the advantage of reward-function-tailored q-learning.

### My Conclusion
[What do you think about the work presented in the article? Did the authors manage to achieve what they set out to achieve?]

### Rating
[Fine, Good, Great]

## Possible future work / improvements
**Complexity Analysis**: Investigate the computational complexity of translating different reward function specification languages into RMs. This analysis could help identify the efficiency of the translation process for various languages.

 **Hybrid Approaches**: Consider hybrid approaches that combine RM-based methods with other reinforcement learning techniques, such as meta-learning or hierarchical reinforcement learning. This could potentially lead to even more efficient and adaptable learning.

## Relation to Own Work
[If related to own work.]

- What can we learn from their approach:
- How are we different:

## Extra
- Cited references to follow up on/related papers/check google scholar for papers citing this paper:
- Source code/blog/twitter thread/other links:https://chat.openai.com/c/1c7f90f3-c8cf-4e59-975c-a765ed8bb7ec

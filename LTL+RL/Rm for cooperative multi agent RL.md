# Reward Machines for Cooperative Multi-Agent Reinforcement Learning
## Quick Look

**Authors**: Cyrus Neary、Zhe Xu、Bo Wu、Ufuk Topcu

**Date Published** : 2020

**Link** : [Paper link]

**Comments:**  Adaptive Agents and Multi-Agent Systems

**TLDR:** This work introduces a decentralized Q-learning approach using reward machines to decompose cooperative multi-agent tasks, achieving efficient and scalable learning in complex environments.

**Tags**: RM, Q-learning、DQPRM

## Paper summary (What)
The paper introduces a framework for cooperative multi-agent reinforcement learning (MARL) using Reward Machines (RMs) and proposes a decentralized Q-learning algorithm based on this framework.

Key points:

- The authors use Reward Machines to represent complex cooperative tasks in MARL.
- They hypothesize that decomposing a team's task into sub-tasks for individual agents using RMs can lead to efficient learning and scalable solutions in MARL.
- They develop a decentralized Q-learning algorithm that treats each agent's task as a single-agent problem, effectively reducing the complexity of MARL.
- Experimental results demonstrate the effectiveness and scalability of the proposed algorithm compared to baseline approaches.

Overall, the paper presents a novel approach to MARL using RMs and shows how it can lead to more efficient and scalable solutions for cooperative tasks.

## Motivation (What)
The motivation for this paper is to address the challenges in cooperative multi-agent reinforcement learning (MARL) when dealing with complex tasks. Traditional MARL approaches face difficulties in efficiently coordinating multiple agents to solve tasks that require collaboration and synchronization. The paper introduces the concept of Reward Machines (RMs) to represent complex cooperative tasks and proposes a decentralized Q-learning algorithm based on this representation. The motivation is to develop a more effective and scalable solution for cooperative MARL, making it easier to decompose and tackle complex tasks that involve multiple agents.

## Issues addressed by the paper (Why)
This paper addresses the challenges in cooperative multi-agent reinforcement learning (MARL), particularly in handling complex tasks that require coordination and synchronization among multiple agents. The problem it tackles is the difficulty of effectively training a team of agents to work together to achieve a common goal. The authors wrote this paper to propose a novel approach using reward machines (RMs) to represent complex tasks, allowing for task decomposition and decentralized Q-learning to make MARL more efficient and scalable. The paper aims to provide a solution to the issues of non-stationarity and the need for synchronized training in multi-agent systems.

## Detailed Information (How)
Based on the content from the abstract, introduction, and conclusion, the main problem addressed in this paper is how to use Reward Machines (RMs) to describe collaborative tasks and decompose them into sub-tasks so that each agent can learn individually. The central idea is to represent collaborative tasks using RMs, decompose them into sub-tasks, and solve this problem using the Distributed Q-learning with Projected Reward Machines (DQPRM) algorithm. Additionally, the paper evaluates the performance of the DQPRM algorithm through experiments, comparing it with baseline algorithms to validate its effectiveness. Therefore, this work is highly related to task decomposition and distributed learning of agents in the field of Multi-Agent Reinforcement Learning (MARL).

### Problem Setting
The problem setting in this paper is related to Multi-Agent Reinforcement Learning (MARL) with a focus on collaborative task decomposition. It involves the following components:

1. **Environment**: The paper discusses tasks that take place in gridworld environments where agents can take actions such as moving in different directions.
2. **Rewards**: Rewards are provided to agents based on the completion of tasks. The paper introduces the concept of Reward Machines (RMs) to represent and specify these tasks explicitly.
3. **Evaluation Setting**: The evaluation setting involves training multiple agents to collaborate in solving tasks represented by RMs. The performance of the proposed Distributed Q-learning with Projected Reward Machines (DQPRM) algorithm is evaluated through experiments in these environments. The evaluation includes comparisons with baseline algorithms to assess the algorithm's effectiveness in solving collaborative tasks.

### Methodology
They approached the problem using the following methods:

1. **Reward Machines (RMs)**: First, they introduced the concept of Reward Machines (RMs) to explicitly represent and formalize tasks. RMs are used to describe the completion conditions and reward structure of tasks, thereby decomposing complex collaborative tasks into simpler sub-tasks.
2. **Decentralized Q-Learning**: They then proposed a decentralized Q-learning algorithm called Decentralized Q-Learning with Projected Reward Machines (DQPRM). This algorithm allows agents to independently learn to solve sub-tasks of tasks represented by RMs without the need for global coordination. Agents are trained based on rewards and event signals and handle collaborative events through projected reward machines.
3. **Experimental Evaluation**: They evaluated the proposed DQPRM algorithm in multiple experimental environments, including button tasks and rendezvous tasks. They compared the performance of DQPRM with other baseline algorithms to assess its effectiveness and scalability in solving collaborative tasks.

### Assumptions
1. **Known Reward Machines (RMs)**: The paper assumes that the task's Reward Machines (RMs) are known in advance. This means that the structure of the tasks and their associated rewards are predefined and provided to the learning agents. While this assumption simplifies the problem, it might not always hold in real-world scenarios where agents need to discover the task structure.
2. **Sparse Interactions**: The proposed algorithm, DQPRM, assumes that interactions between agents are sparse, meaning that agents do not need to coordinate at every time step. Instead, they handle collaborative events through projected reward machines. This assumption is essential for the decentralized learning approach to work effectively.
3. **Fixed Synchronization Probability**: During training, when an agent observes a shared event, it is provided with a simulated synchronization signal with a fixed probability of occurrence. This assumption introduces randomness in the synchronization process, which might not accurately represent real-world scenarios where synchronization depends on external factors.

### Prominent Formulas
[Can be empty]

### Results
Based on the provided information, the main experimental results in the paper are as follows:

1. **Efficiency and Scalability**: The experimental results in the paper demonstrate the efficiency and scalability of the proposed DQPRM algorithm in various cooperative tasks. Compared to baseline algorithms, DQPRM learns successful team policies faster in complex tasks. This is likely because DQPRM allows agents to receive rewards more frequently during training, mitigating the issues of sparse and delayed feedback.
2. **Team Performance**: In the task involving ten agents, baseline algorithms failed to learn a successful team policy within the specified training steps, while DQPRM exhibited excellent performance. This indicates that DQPRM has a significant advantage in handling tasks with a large number of agents.
3. **Effectiveness of Task Decomposition**: DQPRM's task decomposition approach allows for collaboration between agents through synchronization on shared events. This decomposition strategy yielded good results in experiments, enabling agents to learn sub-task policies independently and achieve the overall task through synchronization of collaborative events.
4. **Performance Comparison with Hierarchical Approaches**: The paper mentions that in some tasks, DQPRM outperforms the baseline based on hierarchical approaches (h-IL). This is likely because hierarchical approaches may prune optimal policies in certain scenarios, while DQPRM guarantees that each agent converges to the optimal policy for their sub-tasks through QRM.

The authors suggest that these results occurred because DQPRM's task decomposition strategy allows agents to learn more efficiently and achieve collaboration through the synchronization of shared events, alleviating some of the challenges in multi-agent reinforcement learning. Additionally, DQPRM exhibits good scalability in tasks with a large number of agents, making it excel in complex multi-agent cooperative problems. 

### Limitations
1. **Assumption of Known Task Reward Machines**: The paper assumes that the task reward machine (RM) is known. In practice, learning or discovering the task RM from experience could be a challenging problem. Future research could focus on developing methods to learn RMs in multi-agent settings.
2. **Random Simulated Synchronization Signals**: The paper uses a fixed probability of occurrence for simulated synchronization signals during training. This fixed probability might not accurately represent the real-world dynamics of agent synchronization. A more adaptive approach to signal synchronization could be explored.
3. **Generalization to Continuous Environments**: The experiments are conducted in gridworld environments, which are discrete. Extending the approach to continuous environments, where actions and states are continuous variables, would be an interesting avenue for future research.
4. **Complexity with Increasing Number of Agents**: While DQPRM demonstrates good scalability, there may still be challenges as the number of agents increases significantly. Further investigation into handling extremely large numbers of agents would be valuable.

### Confusing aspects of the paper
[Is there anything that is confusing and could need better explanations or references?]

## Conclusions

### The author's conclusions
In this work, we propose a reward machine (RM) based task representation for cooperative multi-agent reinforcement learning(MARL). The representation allows for a team’s task to be decomposed into sub-tasks for individual agents. We accordingly propose a decentralized q-learning algorithm that effectively reduces the MARL problem to a collection of single-agent problems. Experimental results demonstrate the efficiency and scalability of the proposed algorithm, which learns successful team policies even when the baseline algorithms do not converge within the allowed training period. This work demonstrates how well-suited RMs are to the specification and decomposition of MARL problems, and opens interesting directions for future research.

### My Conclusion
[What do you think about the work presented in the article? Did the authors manage to achieve what they set out to achieve?]

### Rating
[Fine, Good, Great]

## Possible future work / improvements
1. **Learning Task RMs**: The authors currently assume that the task RM is known. Future research can explore methods for learning or discovering task RMs in multi-agent environments to make the approach more general.
2. **Improved Synchronization Signal Simulation**: Currently, synchronization signals are simulated using a fixed probability. Research can investigate smarter, adaptive methods for generating synchronization signals to better reflect actual synchronization among agents.
3. **Extension to Continuous Environments**: The authors' method is tested in a discrete grid world. Extending this approach to environments with continuous states and actions, such as physical robots or continuous control tasks, would be an important research direction.

## Relation to Own Work
[If related to own work.]

- What can we learn from their approach:
- How are we different:

## Extra
- Cited references to follow up on/related papers/check google scholar for papers citing this paper:
- Source code/blog/twitter thread/other links:https://chat.openai.com/c/a82278d1-092f-48cc-bf7a-00f08b8bb11b

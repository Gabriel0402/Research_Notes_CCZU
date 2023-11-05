# [Title]Skill Machines: Temporal Logic Composition in Reinforcement Learning
## Quick Look

**Authors**: Geraud Nangue Tasse, Devon Jarvis, Steven James, Benjamin Rosman

**Date Published** : 2022

**Link** : [Paper link]

**Comments:** arXiv.org

**TLDR:** We propose a framework where an agent ﬁrst learns a set of base skills in a reward-free setting,
and then combines these skills with the learned skill machine to produce composite behaviours speciﬁed by any regular language, such as linear temporal logics.

**Tags**: LTL、Q-learning、skill machines、

## Paper summary (What)
- The paper addresses the challenge of specifying and verifying tasks in reinforcement learning.
- It proposes "skill machines," which can be learned from reward machines, to encode complex task solutions.
- The hypothesis is that skill machines, when combined with base skills learned in a reward-free setting, can produce near-optimal behaviors for tasks specified by regular languages like linear temporal logics.
- The framework allows agents to map complex logical task specifications to behaviors without further learning.
- Experiments in both tabular and high-dimensional video game environments demonstrate the agent's ability to handle complex, long-horizon tasks efficiently.
- The paper also discusses the potential for improving skill machine performance using offline reinforcement learning algorithms when optimal behaviors are desired.

In summary, the paper introduces skill machines as a solution to specifying and learning complex tasks in reinforcement learning, showcasing their effectiveness in various environments.

## Motivation (What)
The motivation for the paper is to address the challenges in specifying and verifying tasks in reinforcement learning. In traditional reinforcement learning, specifying tasks can be complex and may not easily translate complex logical task specifications into optimal behaviors. The paper introduces the concept of "skill machines" as a solution to this problem. Skill machines can be learned directly from reward machines, which encode the solutions to tasks, and they provide a way to map complex logical task specifications to near-optimal behaviors. This motivates the need for skill machines to make task specification and learning more interpretable and effective in reinforcement learning.

## Issues addressed by the paper (Why)
1. Complexity of Task Specification: Specifying tasks in reinforcement learning can be complex, especially when dealing with logical and long-horizon tasks. This complexity makes it challenging to provide clear and interpretable task specifications.
2. Lack of Generalization: Traditional approaches may struggle to generalize from specific task descriptions to optimal behaviors, particularly for tasks specified using complex logical expressions.
3. Verification of Task Solutions: Ensuring that the learned policies satisfy the specified tasks and logical constraints is a challenge, and traditional methods may not provide straightforward verification mechanisms.

The paper was written to propose a solution to these issues by introducing "skill machines" as a representation that can be learned directly from reward machines, which encode task solutions. The motivation is to enhance the interpretability and effectiveness of task specification and learning in reinforcement learning by providing a framework for mapping complex logical task specifications to near-optimal behaviors and achieving high task performance with minimal additional learning.

## Detailed Information (How)
 Here are the detailed steps of how Skill Machines work and how they can be combined with other steps:

1. Learning Basic Skills:
   - First, the agent learns a set of basic skills in a reward-free setting. These basic skills can be simple, atomic-level tasks that the agent performs in the environment, such as moving to a specific location or executing a particular action.
2. Representation of Basic Skills:
   - Each basic skill is represented as a skill primitive, which includes a state transition function, a reward function, and a termination condition. These primitives describe how the agent executes the skill in a given state and how much reward it can obtain upon completing the skill.
3. Composition of Basic Skills:
   - Skill Machines create more complex task representations by logically and temporally combining basic skills. This is achieved by combining skill primitives according to some logical conditions (e.g., AND, OR, NOT).
4. Task Representation and Learning:
   - The agent can solve complex tasks by learning the task representation (Skill Machine). It can use reward signals to guide its learning process but does not need to relearn basic skills. Instead, it leverages the already learned skill primitives to solve more complex tasks.
5. Integration with Other Steps:
   - Skill Machines can be combined with other reinforcement learning algorithms, such as Q-Learning. In this case, the agent can use the learned Skill Machine to improve learning efficiency and performance. Q-Learning can be used to learn how to switch between different skills to accomplish complex tasks.

### Problem Setting
**Environment:** The paper does not specify a single environment but discusses RL environments where tasks can be complex, multi-step, and involve various actions and states.

**Evaluation Setting:** The evaluation setting involves training RL agents to learn and solve tasks described by reward machines. The authors conduct experiments in both tabular and high-dimensional video game environments. The evaluation metric used is the average reward per step, which measures the agent's performance in solving complex, long-horizon tasks.

### Methodology

The authors approached the problem using the following methods:

1. **Introduction of Skill Machines:** The authors first introduced Skill Machines as a solution to enhance the interpretability and composability of tasks in RL environments. Skill Machines are a novel representation that can be learned directly from reward machines that describe tasks.
2. **Learning Base Skills:** In the absence of rewards, the agent initially learns a set of base skills. These base skills serve as the foundation that the agent will later combine for subsequent tasks.
3. **Combining Base Skills with Skill Machines:** The authors proposed a framework in which the agent combines the learned base skills with the acquired Skill Machine to generate composite behaviors specified by any regular language, such as Linear Temporal Logic specifications. This enables the agent to map complex logical task specifications to near-optimal behaviors.

### Assumptions
1. **Availability of Reward Machines:** They assume that tasks can be explicitly described through reward machines. These reward machines serve as a formal representation of tasks.
2. **Tasks are Compositional:** The authors assume that tasks can be decomposed into a combination of basic skills. These basic skills are composable and can be used to solve more complex tasks.
3. **Learnability of Basic Skills:** They assume that, in the absence of explicit rewards, agents can learn a set of basic skills that form the foundation for subsequent tasks.
4. **Tasks can be Specified by Regular Languages:** They assume that tasks can be specified using regular languages, such as linear temporal logic. This specification allows agents to map complex logical tasks to near-optimal behaviors.

### Prominent Formulas
[Can be empty]

### Results
[Theoretical or empirical results (any main graphs and tables). Also try to possibly mention **why** you or the authors think certain results occurred. ]

### Limitations
[Did the authors mention any reservations/limitations to their work or methodology? Do you see any limitations of their work?]

### Confusing aspects of the paper
[Is there anything that is confusing and could need better explanations or references?]

## Conclusions

### The author's conclusions
We proposed skill machines—finite state machines that can be learned from reward machines—that
allow agents to solve extremely complex tasks involving temporal and concurrent composition. We
demonstrated how skills can be learned and encoded in a specific form of goal-oriented value function
that, when combined with the learned skill machines, are sufficient for solving subsequent tasks
without further learning. Our approach guarantees that the resulting policy adheres to the logical task
specification, which provides assurances of safety and verifiability to the agent’s decision making,
important characteristics that are necessary if we are to ever deploy RL agents in the real world.
While the resulting behaviour is provably satisficing, empirical results demonstrate that the agent’s
performance is near optimal; further fine-tuning can be performed should optimality be required,
which greatly improves the sample efficiency. We see this approach as a step towards truly generally
intelligent agents, capable of immediately solving human-specifiable tasks in the real world with no
further learning.

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
- Cited references to follow up on/related papers/check google scholar for papers citing this paper:
- Source code/blog/twitter thread/other links:https://chat.openai.com/c/0e91e093-f59d-4fe7-a479-6009b829d3e1

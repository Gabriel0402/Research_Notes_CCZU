# [Title]Lifelong Reinforcement Learning with Temporal Logic Formulas and Reward Machines
## Quick Look

**Authors**: Xuejing Zheng, Chao Yu, Chen Chen, Jianye Hao, Hankz Hankui Zhuo

**Date Published** : 2021

**Link** : [Paper link]

**Comments:** arXiv.org

**TLDR:** First, we introduce "Sequential Linear Temporal Logic" (SLTL). Then, we utilize "Reward Machines" (RM) to handle tasks encoded with high-level events using structural reward functions and propose an automatic extension of RM and an efficient knowledge transfer method during lifelong learning. 

**Tags**: SLTL、Q-learning

## Paper summary (What)
This paper presents a lifelong reinforcement learning method called Lifelong Reinforcement Learning with Sequential Linear Temporal Logic and Reward Machines (LSRM). It enables agents to leverage previously acquired knowledge to accelerate the learning of tasks specified by logical formulas. Firstly, the paper introduces Sequential Linear Temporal Logic (SLTL) as a complement to the existing Linear Temporal Logic (LTL) formal language. Next, it utilizes Reward Machines (RM) to handle tasks encoded with high-level events using structural reward functions. The paper proposes methods for automatically extending RM and effectively transferring knowledge during the lifelong learning process

## Motivation (What)
The focus has primarily been on continuous learning environments, where a series of related tasks are sampled from a task distribution. These methods often make structural assumptions about which components of the Markov Decision Process (MDP), such as rewards or transition probabilities, may change during task generation. While these assumptions are reasonable in most real-world situations, there are scenarios where task specifications are non-Markovian, making it challenging to express them analytically through reward functions.

## Issues addressed by the paper (Why)
1. The problem of Lifelong Reinforcement Learning (LRL):  The challenge in this problem lies in effectively transferring previously acquired knowledge and experience to new tasks to enhance learning efficiency and performance.
2. Flexibility and complexity of task specifications: The paper highlights the limitations of traditional reinforcement learning methods, which often rely on standard reward functions to define tasks. However, real-world tasks can be more complex and challenging to precisely represent using reward functions, especially when task specifications involve non-Markovian properties or require advanced logical specifications.
3. Logical specifications and task decomposition: To address the complexity of task specifications, the paper introduces Linear Temporal Logic (LTL) and Sequential Linear Temporal Logic (SLTL) to specify tasks. These logical specifications provide more advanced and flexible ways to define tasks while allowing for task modularity and decomposition to facilitate more efficient learning and adaptation.
4. Structural reward functions: To handle tasks specified using logical specifications, the paper employs Reward Machines (RM) to express structural reward functions. These reward functions are based on high-level event-encoded tasks and can better match logical specifications.
5. Knowledge transfer and composition: To achieve lifelong learning, the paper proposes the Lifelong Reinforcement Learning with SLTL and RM (LSRM) method. This method enables agents to learn and adapt to tasks specified by logical rules by storing and transferring high-level knowledge and using various Q-value composition methods to enhance learning and adaptation.

## Detailed Information (How)

① We introduced Sequential Linear Temporal Logic (SLTL), which serves as a complement to LTL by introducing a new operator "then" to provide more flexible and rich task specifications.

② Leveraging the modularity of tasks in SLTL and policy learning over Reward Machines (RM), we propose a Lifelong Reinforcement Learning (LSRM) method based on SLTL and RM。Specifically, for each target formula ϕ in T, LSRM first extends the memory RM and then returns its newly extended state set Uϕnew. Next, it transfers the Q-functions learned from memory to the new Q-functions corresponding to each state in Uϕnew. Finally, LSRM employs the QRM algorithm to learn the target formulas. When the agent initiates the execution of a task ϕ ∈ T in an episode of QRM, the initial state of memory RM is set to u0 = ϕ. After the QRM learning procedure, the set of learned tasks TM is updated.

### Problem Setting
The problem setting in the context of the discussed research is Lifelong Reinforcement Learning (LRL) with a focus on logically specified tasks.In this LRL setting:

- Environment: The environment is not explicitly specified in the text, but it is implied that the agent interacts with an environment where it learns and performs various tasks.
- Tasks: The tasks are specified using Linear Temporal Logic (LTL) or Sequential Linear Temporal Logic (SLTL) formulas, which are high-level logical specifications rather than traditional regression or classification tasks. These formulas represent desired agent behaviors over time.
- Rewards: The rewards are not explicitly described in the provided text. However, it mentions the use of Reward Machines (RM) to express structural reward functions for tasks encoded with high-level events. The specifics of these rewards and how they relate to the tasks are not detailed in the excerpt.
- Evaluation Setting: The evaluation setting for the results involves testing the proposed method, Lifelong Reinforcement Learning with SLTL and RM (LSRM), in two benchmark domains: OFFICEWORLD and MINECRAFT. The evaluation likely includes measuring the agent's performance in terms of learning and completing logically specified tasks efficiently. The results are compared to direct learning methods without transfer learning.

### Methodology
They approached the problem by introducing Sequential Linear Temporal Logic (SLTL) to provide more flexible and rich task specifications. They used Reward Machines (RM) to express structural reward functions for tasks encoded with high-level events. To address lifelong learning, they proposed the Lifelong Reinforcement Learning with SLTL and RM (LSRM) method, which involved storing and transferring high-level knowledge and using various Q-value composition methods.

### Assumptions
[What assumptions were made and are these assumptions valid?]

### Prominent Formulas
[Can be empty]

### Results
The paper presents both theoretical and empirical results. The theoretical contributions include the development of the Sequential Linear Temporal Logic (SLTL) and the introduction of value composition methods for knowledge transfer. These contributions lay the foundation for addressing the challenges of lifelong reinforcement learning (LRL) with complex task specifications.

Empirically, the authors evaluate their proposed method, Lifelong Reinforcement Learning with SLTL and RM (LSRM), in two benchmark domains: OFFICEWORLD and MINECRAFT. They compare LSRM with QRM and QRM with reward shaping (QRM+RS) in terms of average steps to complete target tasks throughout the training process.

The results show that LSRM outperforms the baseline methods QRM and QRM+RS in terms of sample efficiency. The choice of Q-value composition methods (Average Composition, Max Composition, Left Composition, and Right Composition) also affects the performance, with different methods performing better for different logical operators (e.g., "and," "or," "then"). The authors suggest that these results demonstrate the effectiveness of their approach in facilitating lifelong learning with logically specified tasks.

### Limitations
The authors acknowledge that their approach, which leverages high-level logic specifications, may not be suitable for all types of tasks and domains. In particular, tasks that do not have clear logical structure or that cannot be easily expressed using formal logic may not benefit from their method. This limitation arises from the reliance on SLTL and RM for task specification and may restrict the applicability of their approach to certain problem domains.

Additionally, the authors mention that their experiments were conducted in grid-world domains with discrete actions. They acknowledge that extending their approach to more complex domains with continuous states and actions could be challenging and may require further research.

### Confusing aspects of the paper
[Is there anything that is confusing and could need better explanations or references?]

## Conclusions

### The author's conclusions
This paper presents an LRL method that takes advantage of the rich expressive power of temporal logic formulas for more flexible task specification and decomposition, and the knowledge transfer capability of RM for more efficient learning. Through storing and leveraging high-level knowledge in a memory, LSRM is able to achieve systematic out-of-distribution generalisation in tasks that follow the specifications of formal languages. Results in two benchmark domains show that LSRM improves the sample efficiency by a large margin compared to direct learning methods. In this paper, we evaluate the proposed method in grid-world domains with discrete actions. In the future, we will extend our approach to more complex domains, e.g., with continu-ous states and/or actions.

### My Conclusion
The authors successfully propose the Lifelong Reinforcement Learning with SLTL and RM (LSRM) method, which leverages high-level knowledge stored in a memory to facilitate lifelong learning. The experiments in grid-world domains demonstrate that LSRM outperforms direct methods without transfer learning, showcasing its potential in improving learning efficiency.

However, as with any research, there are always opportunities for further exploration and improvement. The authors mainly focus on discrete action grid-world environments, and future work could involve applying their approach to more complex and real-world domains with continuous states and actions.

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
- Source code/blog/twitter thread/other links:https://chat.openai.com/c/bc5c9a4d-8508-45c0-8b4b-18ba57687d0f

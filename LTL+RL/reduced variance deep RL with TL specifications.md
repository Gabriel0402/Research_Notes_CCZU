# Reduced Variance Deep Reinforcement Learning with Temporal Logic Specifications
## Quick Look

**Authors**: Qitong Gao、Davood Hajinezhad、Yan Zhang、Yiannis Kantaros、Michael M. Zavlanos

**Date Published** : 2019

**Link** : [Reduced Variance Deep Reinforcement Learning with Temporal Logic Specifications (acm.org)](https://dl.acm.org/doi/pdf/10.1145/3302509.3311053)

**Comments:**  [ICCPS '19：第 10 届 ACM/IEEE 信息物理系统国际会议论文集]

**TLDR:** The paper presents a reduced variance model-free deep reinforcement learning algorithm for synthesizing control policies in mobile robotics that satisfy complex temporal logic specifications, improving training stability and reducing computational costs.

**Tags**: Deep Q-Learning

## Paper summary (What)
In this paper, the authors proposed a model-free deep reinforcement learning method for synthesizing control policies for mobile robots in Markov Decision Processes (MDPs) while satisfying Linear Temporal Logic (LTL) specifications. Their key contributions and hypotheses include:

- Proposed a reduced variance model-free algorithm for mobile robot control.
- Addressed LTL planning problems without requiring Accepting Maximal End Components (AMECs).
- Assumed unknown transition probabilities and focused on variance reduction.
- Improved stability in training deep reinforcement learning models.
- Demonstrated the effectiveness of their algorithm through simulation studies.

## Motivation (What)
The motivation for the paper lies in the need to address complex planning problems for mobile robots in environments with unknown transition probabilities and satisfy Linear Temporal Logic (LTL) specifications. The authors aim to provide a solution that does not require the computation of Accepting Maximal End Components (AMECs) and can handle cases where AMECs do not exist. The paper's motivation is driven by the desire to make model-free deep reinforcement learning applicable to a wider range of robotic planning scenarios, thereby improving the stability and effectiveness of robot control policies.

## Issues addressed by the paper (Why)
The paper addresses several key issues related to planning for mobile robots in complex environments with unknown transition probabilities and Linear Temporal Logic (LTL) specifications:

1. **Handling Unknown Transition Probabilities:** The paper tackles the challenge of planning when the transition probabilities in the underlying Markov Decision Process (MDP) are unknown, which is a common real-world scenario.
2. **Satisfying LTL Specifications:** It focuses on satisfying LTL specifications, which involve temporal logic constraints on robot behavior. These constraints are crucial for specifying desired robot behaviors but add complexity to the planning problem.
3. **Reducing Computational Complexity:** The authors aim to reduce computational complexity by avoiding the need to compute Accepting Maximal End Components (AMECs), which can be computationally expensive.
4. **Improving Stability in Deep RL:** The paper introduces a reduced variance model-free deep reinforcement learning algorithm to improve the stability of training deep RL agents under unknown transition probabilities and LTL constraints.

They wrote this paper to provide a solution that addresses these issues and to make model-free deep reinforcement learning more applicable to robotic planning problems, where AMECs may not always be feasible to compute. Their goal is to advance the field of robotics by enabling robots to effectively learn control policies in complex and uncertain environments while satisfying high-level temporal logic specifications.

## Detailed Information (How)
[This paper represents highly relevant work in addressing the challenges of robot planning in an environment with unknown transition probabilities and LTL specifications. The authors' approach involves a reduced variance model-free deep reinforcement learning algorithm to improve training stability. This work is significant for the application of deep reinforcement learning in robotics, enabling robots to effectively perform tasks in more complex environments while satisfying advanced temporal logic specifications.

### Problem Setting
[The problem setting in this paper is reinforcement learning (RL) for robot planning. Specifically, the authors address the challenge of synthesizing control policies for mobile robots modeled by Markov Decision Processes (MDPs) with unknown transition probabilities. The robots are required to satisfy Linear Temporal Logic (LTL) specifications.

The RL environment is represented by MDPs, where the transition probabilities are unknown. The robots need to interact with this uncertain environment to learn optimal control policies that meet complex LTL specifications. The evaluation setting for the results involves comparing their proposed reduced variance model-free deep reinforcement learning algorithm with other methods, including SGD algorithms, to assess convergence performance, policy evaluation, and training stability. The reward function is designed based on the LTL specifications, and the performance is measured in terms of how well the learned policies satisfy these specifications.

### Methodology
The authors approached the problem using the following methods:

1. **Neural Network-Based Value Function Estimation**: They employed neural networks to estimate the state-value function for evaluating long-term rewards in different states, aiding their robot in learning an optimal policy.
2. **Deep Q-Learning and Deep Reinforcement Learning**: They adopted deep Q-learning and deep reinforcement learning techniques to enable the robot to improve its policy through interactions with the environment without prior knowledge of transition probabilities.
3. **Variance Reduction Techniques**: The authors developed a variance reduction method to more accurately estimate the gradient of the unknown loss function, enhancing training stability.
4. **LTL Specification Design**: They designed reward functions to reflect LTL specifications and used these reward functions to evaluate the performance of policies, ensuring that the robot satisfies the specifications.
5. **Experimental Validation**: The authors conducted simulation experiments in environments of varying scales, comparing their method with other RL approaches to validate the performance and effectiveness of their approach.

Through these methods, their robot was able to learn optimal control policies that satisfy complex LTL specifications without prior knowledge of the environment.

### Assumptions
The paper makes several assumptions, and whether these assumptions are valid can depend on the specific problem and domain. Here are the key assumptions made in the paper:

1. **Gradient Lipschitz Continuity**: Assumption A1 assumes that the functions involved are gradient Lipschitz continuous. This assumption implies that the gradients of these functions don't change too rapidly. It's a common assumption in optimization, but its validity depends on the specific functions and problem domain.
2. **Lower Bounded Function**: Assumption A2 assumes that the function in question is lower bounded. This assumption is often used in optimization problems, and its validity depends on the nature of the function being optimized.
3. **Data Boundedness**: The paper assumes that the iterates θr and λr are always bounded, which is expected when a nonlinear function is properly designed to approximate the value function. This assumption is valid if the function approximators used (neural networks) are designed to be bounded.
4. **Learning Rate Selection**: The paper specifies conditions for the learning rate α. The validity of these conditions depends on the specific problem and algorithm used.

The validity of these assumptions depends on the problem being addressed and the specific conditions of the experiments. While these assumptions are common in optimization and reinforcement learning, their applicability should be assessed in the context of each problem to ensure their validity.

### Prominent Formulas
[Can be empty]

### Results
The paper presents both theoretical and empirical results. Here's a summary of the main results along with some insights on why they might have occurred:

**Theoretical Results**:

1. **Convergence Analysis**: The paper provides a convergence analysis of the proposed non-convex Arrow-Hurwicz-Uzawa type algorithm. The theoretical analysis demonstrates that the algorithm converges to a stationary solution of the problem under certain assumptions.

**Empirical Results**:

1. **Case Study I**: In the first case study (5x5 environment), the paper shows that the proposed algorithm outperforms other methods such as SGD, Momentum-SGD, tabular Q-Learning, and a model-based learning approach. It converges faster and achieves a better approximation of the state-action value functions. This could be because the algorithm better utilizes data and improves the training efficiency through reduced variance.
2. **Case Study II**: In the second case study (10x10 environment), the proposed algorithm again outperforms other methods in terms of convergence speed and value function approximation. It effectively learns a policy to satisfy a complex LTL task. The model-based approach doesn't converge well, possibly because of insufficient data during the exploration stage.
3. **Policy Evaluation**: The paper compares the error in evaluating policies generated by the proposed algorithm and SGD. The results show that the proposed algorithm converges faster and provides a more stable training process.
4. **Policy Visualization**: The paper presents policy visualizations for both case studies, illustrating how the learned policies guide the robot in satisfying the LTL tasks by avoiding certain regions and visiting others as required.

The improved performance of the proposed algorithm in the empirical results could be attributed to its reduced variance approach, which leads to more accurate gradient estimates. This allows the algorithm to better explore the state space, learn faster, and achieve improved convergence compared to traditional SGD-based methods.

### Limitations
1. **Online Implementation**: The paper mentions that the online implementation of the algorithm is left for future research. This means that the proposed algorithm's performance in an online learning scenario has not been fully explored or analyzed.
2. **Limited Exploration**: Like many reinforcement learning methods, the proposed algorithm relies on exploration to gather data. The limitations of exploration are not explicitly discussed, but they can be a challenge in complex environments.
3. **Problem Specificity**: The proposed algorithm is designed to solve LTL planning problems for mobile robots. While it performs well in this context, its applicability to other types of reinforcement learning problems is not explored.
4. **Parameter Sensitivity**: The paper does not provide an extensive analysis of hyperparameter sensitivity, which could be important in practice to fine-tune the algorithm for specific tasks.
5. **Complexity of LTL Tasks**: The complexity of LTL tasks that can be handled effectively by the algorithm is not discussed in detail. It's possible that extremely complex LTL specifications may still pose challenges.
6. **Scalability**: The paper provides results for relatively small grid-world environments (5x5 and 10x10). It's unclear how the algorithm would scale to larger or more complex environments.

### Confusing aspects of the paper
[Is there anything that is confusing and could need better explanations or references?]

## Conclusions

### The author's conclusions
In this paper, we proposed a reduced variance model-free deep reinforcement learning method to synthesize control policies for mobile robots modeled by Markov Decision Process (MDP) with
unknown transition probabilities that satisfy Linear Temporal Logic(LTL) specifications. Unlike SGD algorithms that are often used in deep RL, our method can estimate the gradients ofan unknown loss
function more accurately, improving the stability of the trainingprocess. To the best of our knowledge, this is the first model-free reduced variance deep reinforcement learning algorithm that can solve LTL planning problems even if AMECs do not exist. Unlike relevant works, our method does not require learning the transition probabilities in the MDP, constructing a product MDP, or computing Accepting Maximal End Components (AMECs). This significantly reduces the computational cost and also renders our method applicable to planning problems where AMECs do not exist.Simulation studies verified the convergence performance of the proposed algorithm.

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
- Cited references to follow up on/related papers/check google scholar for papers citing this paper:https://chat.openai.com/c/303142e2-e2d1-4099-b5f0-5283e4e4d827
- Source code/blog/twitter thread/other links:

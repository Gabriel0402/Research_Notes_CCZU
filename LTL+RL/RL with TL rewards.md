# [Title]Reinforcement Learning With Temporal Logic Rewards
## Quick Look

**Authors**: Xiao Li, Cristian-Ioan Vasile and Calin Belta.

**Date Published** : 2016

**Link** : [Paper link]

**Comments:**  IEEE/RJS International Conference on Intelligent RObots and Systems

**TLDR:** This paper introduces Truncated Linear Temporal Logic (TLTL) as a formal language for specifying complex robotic tasks and shows that TLTL-based reward functions outperform discrete and continuous rewards in reinforcement learning, facilitating efficient task learning. 

**Tags**: TLTL、Relative Entropy Policy Search（REPS)

## Paper summary (What)
We propose Truncated Linear Temporal Logic (TLTL) as speciﬁcations language, that is arguably well suited for the robotics applications, together with quantitative semantics,i.e., robustness degree. We propose a RL approach to learn tasks expressed as TLTL formulae that uses their associated robustness degree as reward functions, instead of the manually crafted heuristics trying to capture the same speciﬁcations.The paper utilizes the REPS (Relative Entropy Policy Search) algorithm to optimize policy parameters, while TLTL specifications are transformed into reward functions to guide policy learning.

## Motivation (What)
Real-world applications often involve complex tasks that cannot be easily captured by simple reach-avoid operations or heuristic reward functions. There is a need for a method to accurately incorporate complex specifications into reward functions to ensure that the learned policies satisfy the desired tasks and constraints.

## Issues addressed by the paper (Why)
1. Defining effective reward functions in reinforcement learning (RL), especially for tasks with complex temporal and logical structures.
2. The limitations of manually crafted heuristic rewards, which may lead to suboptimal policies and may not guarantee task satisfaction.
3. The need for a formal specification language that allows for the expression of complex rules and the incorporation of domain knowledge into RL learning.
4. The challenge of learning policies in continuous state and action spaces, particularly for tasks with temporal and causal structures.

The authors wrote this paper to propose a solution to these issues by introducing Truncated Linear Temporal Logic (TLTL) as a specification language with quantitative semantics for expressing complex rules and constraints. They aimed to show that using TLTL-based reward functions in RL can lead to faster learning and better policies, addressing the limitations of heuristic rewards and enabling more efficient learning in complex robotic tasks.

## Detailed Information (How)
The paper converts TLTL specifications into reward functions using the following steps:

1. TLTL Specification Definition: Firstly, the paper uses TLTL specification language to clearly define the requirements and rules of the task. TLTL allows you to express the complex logic and temporal requirements of the task in a formalized way, such as task sequencing, constraints, etc.

2. Define Quantitative Semantics: To convert TLTL specifications into a reward function, the paper defines the quantitative semantics of TLTL, known as "robustness degree." This measure is a real-valued function used to quantify the degree of compliance between a state trajectory and the TLTL specification, indicating how well the trajectory conforms to the specification.

3. Transformation into Reward Function: Next, the paper uses the robustness degree to transform TLTL specifications into a real-valued reward function. The goal of this reward function is to enable RL algorithms to maximize the expected cumulative reward. The design of the reward function should encourage correct behavior and penalize actions that do not comply with the specification.

4. Reinforcement Learning Algorithm: The paper employs a reinforcement learning algorithm to learn the optimal policy. During the learning process, the RL algorithm interacts with the environment, adjusting the policy to maximize the reward function and enable the agent to complete the task.

   ①Problem Description: Firstly, define a reinforcement learning problem, including state space, action space, transition probability function, reward function, and task objectives. In this paper, the authors use Truncated Linear Temporal Logic (TLTL) to define task specifications.

   ②Policy Parameterization: Represent the policy (agent robot's behavioral strategy) as a parameterized model, typically using a Gaussian distribution to represent the policy. This model is used to explore the state space, and the parameters control the behavior of the policy.

   ③TLTL Specification to Reward: Convert TLTL specifications into a reward function. This step involves using TLTL's robustness measure to define a reward function for use in reinforcement learning. The reward function calculates reward signals based on the degree of satisfaction of the task specifications.

   ④REPS Algorithm: Utilize the Relative Entropy Policy Search (REPS) algorithm to optimize policy parameters to maximize the expected cumulative reward. REPS is an information-theoretic method used to solve policy search problems.

   ⑤Training: Conduct policy iteration training using the REPS algorithm in the environment. In each iteration, sample trajectories are collected based on the current policy, and then the REPS algorithm updates policy parameters to improve the expected value of the reward function.

   ⑥Evaluation and Comparison: During training, evaluate the impact of different reward functions (including TLTL reward, discrete reward, and continuous reward) on the learning outcome. By comparing the performance of different reward functions, determine which reward function performs best in task learning.

### Problem Setting
This paper is the first to apply TL in reinforcement learning on continuous state and action spaces, and demonstrates its abilities in experimentation.

These methods are suitable for problem scenarios that require consideration of complex task specifications, logic, and temporal properties. This includes situations where specific task requirements, specifications, or constraints need to be satisfied.

### Methodology
The authors approached the problem of defining effective reward functions in reinforcement learning (RL), particularly for complex tasks with rich temporal and logical structures, using the following methods:

1. **Truncated Linear Temporal Logic (TLTL):** They proposed the use of TLTL as a specification language to express complex rules and incorporate domain knowledge into the learning process. TLTL allows for the convenient representation of tasks as functions of states and provides quantitative semantics for task satisfaction.
2. **Quantitative Semantics (Robustness Degree):** They defined quantitative semantics for TLTL, represented by a real-valued function called the robustness degree. This function measures how far a state trajectory is from satisfying or violating a TLTL specification, providing a continuous measure of specification satisfaction.
3. **Reward Function Transformation:** TLTL specifications were transformed into reward functions, where the robustness degree served as the basis for reward calculation. This reward function guided the reinforcement learning agent's policy optimization process.
4. **Relative Entropy Policy Search (REPS):** They employed the REPS algorithm to optimize the policy parameters. REPS is an information-theoretic method used to solve policy search problems.
5. **Training:** The training process involved iteratively updating the policy using REPS. Sample trajectories were collected under the current policy, and policy parameters were adjusted to maximize the expected cumulative reward based on the TLTL-derived reward function.
6. **Evaluation and Comparison:** Different reward functions, including TLTL rewards, discrete rewards, and continuous rewards, were evaluated during training. Performance comparisons were made to determine which reward function led to faster learning and better policies.

### Assumptions
The paper makes several assumptions:

1. **Complex Task Specifications:** The paper assumes that the tasks being addressed require complex and possibly temporal specifications. These specifications are expressed using Truncated Linear Temporal Logic (TLTL).
2. **Quantitative Semantics:** It assumes that quantitative semantics in the form of robustness degrees can be used to measure the satisfaction of TLTL specifications.
3. **Information-Theoretic Optimization:** The paper utilizes the Relative Entropy Policy Search (REPS) algorithm for optimizing policy parameters based on the TLTL-derived reward function.
4. **Task Satisfaction through Reward:** The assumption is that by optimizing the TLTL-derived reward function, the agent can effectively learn to satisfy complex task specifications.

### Prominent Formulas
[Can be empty]

### Results
**Theoretical Results:**

1. **TLTL for Task Specification:** The paper theoretically establishes TLTL as a formal specification language with quantitative semantics (robustness degree). It highlights how TLTL can be used to express complex task specifications involving temporal and logical constraints.
2. **TLTL as a Reward Function:** The paper outlines the process of translating TLTL specifications into reward functions. It explains how the robustness degree of TLTL can be used as a measure of task satisfaction and converted into reward signals for reinforcement learning.

**Empirical Results:**

1. **Comparative Learning Performance:** The authors conduct empirical experiments to compare the learning performance of RL agents using different types of reward functions: TLTL reward, discrete reward, and continuous reward. They evaluate the agents in simulated 2D manipulation tasks.
2. **Convergence Rate:** Empirical results show that RL agents trained with TLTL reward achieve faster convergence in learning compared to agents using other reward functions. This suggests that TLTL-based rewards provide more effective guidance to the learning process.
3. **Task Satisfaction:** RL agents using TLTL reward consistently perform better in terms of task satisfaction, indicating that TLTL-based rewards lead to policies that adhere more closely to complex task specifications.
4. **Hierarchical Tasks:** The paper demonstrates that TLTL can be used to specify and learn temporally structured tasks. RL agents successfully learn hierarchical tasks using TLTL-based rewards.

### Limitations
1. **Complexity of TLTL Specifications:** While TLTL allows for expressive task specifications, complex TLTL formulas may result in high-dimensional or computationally expensive reward functions, which could affect the scalability of their approach.
2. **Generalization to Real-World Environments:** The paper demonstrates the approach in a simulated environment and a real-world toast-placing task. However, the generalization of TLTL-based reward functions to a wide range of real-world scenarios with diverse dynamics and uncertainties may require further investigation.
3. **Human-Defined Specifications:** TLTL specifications are still created by human designers, and their effectiveness may depend on the quality of the specified logic. Ambiguous or incorrect specifications could lead to suboptimal learning outcomes.
4. **Efficiency and Learning Speed:** While TLTL-based rewards are shown to improve learning outcomes, the efficiency and learning speed in more complex and high-dimensional environments may still be a challenge.
5. **Computational Overhead:** The process of converting TLTL specifications into reward functions may introduce computational overhead, and the paper does not discuss the computational complexity of this step.

### Confusing aspects of the paper
[Is there anything that is confusing and could need better explanations or references?]

## Conclusions

### The author's conclusions
In this paper we proposed TLTL, a formal specification language with quantitative semantics that is designed for convenient robotic task specification. We compare learning performance of the TLTL reward with two of the more commonly used forms of reward (namely a discrete and continuous form of reward functions) in a 2D simulated manipulation environment by fixing the RL algorithm. We also compare the outcome of TLTL reward trained using a relatively inefficient episode based method with the discrete/continuous rewards trained using a lower variance step based method. Results show that TLTL reward not only outperformed all of its comparison cases, it also enabled a non-hierarchical RL method to successfully learn to perform a temporally structured task. Furthermore, We used TLTL to express a toast placing task and demonstrated successful learning on a Baxter robot.

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
- Source code/blog/twitter thread/other links:https://chat.openai.com/c/7742f50e-6b4b-4415-8c66-70abf7c959dd

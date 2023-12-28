# Learning to Utilize Shaping Rewards: A New Approach of Reward Shaping
## Quick Look

**Authors**: Yujing Hu1, Weixun Wang1,2, Hangtian Jia1, Yixiang Wang1,3, Yingfeng Chen1∗,
Jianye Hao2,4, Feng Wu3, Changjie Fan1

**Date Published** : 2020.10

**Link** : [b710915795b9e9c02cf10d6d2bdb688c-Paper.pdf (neurips.cc)](https://proceedings.neurips.cc/paper/2020/file/b710915795b9e9c02cf10d6d2bdb688c-Paper.pdf)

**Comments:** Advances in Neural Information Processing Systems

**TLDR:**The paper introduces methods for adaptive reward shaping in reinforcement learning, enabling improved performance without the need for manual reward tuning in various environments, as demonstrated in cartpole and MuJoCo experiments.

**Tags**: shaping rewards、bi-level optimization(BiPaRS)

## Paper summary (What)
we consider the problem of adaptively utilizing a given shaping reward function. We formulate the utilization of shaping rewards as a bi-level optimization problem, where the lower level is to optimize policy using the shaping rewards and the upper level is to optimize a parameterized shaping weight function for true reward maximization. We formally derive the gradient of the expected true reward with respect to the shaping weight function parameters and accordingly propose three learning algorithms based on different assumptions. Experiments in sparsereward cartpole and MuJoCo environments show that our algorithms can fully exploit beneficial shaping rewards, and meanwhile ignore unbeneficial shaping rewards or even transform them into beneficial ones.

## Motivation (What)
The motivation of the paper is to address the challenge of reward design in reinforcement learning (RL). Reward design in RL is a crucial problem, and improper reward settings can lead to undesirable agent behaviors. While researchers and algorithm engineers often have domain knowledge about the problem, translating this knowledge into precise numerical reward functions is often challenging. Therefore, the motivation of this paper is to provide an adaptive reward shaping approach to improve performance in RL applications while reducing the burden of reward tuning for researchers and algorithm engineers. The paper aims to offer a more effective way of reward design for RL applications, enhancing the quality of RL outcomes.

## Issues addressed by the paper (Why)
The paper addresses the following issues:

1. **Reward Design in Reinforcement Learning**: The main problem the paper tackles is reward design in reinforcement learning (RL). Reward functions in RL play a critical role in shaping agent behavior, but designing appropriate reward functions can be challenging, especially when prior qualitative knowledge is available.
2. **Unintended Agent Behavior**: Improperly designed reward functions can lead to unintended agent behaviors. RL algorithms might exploit reward functions to achieve high rewards in unexpected ways, resulting in suboptimal or even undesirable performance.

## Detailed Information (How)
**1 Parameterized Reward Shaping:**

In this section, the paper presents a dual-level optimization framework to address the reward shaping problem in reinforcement learning. The framework aims to maximize the cumulative reward by optimizing both the agent's policy and reward shaping weights.

- **Problem Description:** First, the paper explicitly defines the problem setting, where an agent attempts to optimize its policy to maximize the expected cumulative reward in a Markov Decision Process (MDP). However, the agent also receives reward signals from a reward shaping function, which may alter the optimal policy.
- **Reward Shaping Function:** The paper introduces a reward shaping function denoted as f, used to modify the original reward function. The reward shaping function may incorporate domain knowledge but can potentially change the optimal policy.
- **Parameterized Reward Shaping:** The paper proposes parameterized reward shaping, where a reward shaping weight function zϕ is introduced to assign a weight to each state-action pair. The parameter ϕ controls these weights.
- **Objective:** The paper's objective is to optimize both the policy πθ and the reward shaping weight function zϕ in the MDP to maximize the cumulative reward. This forms a dual-level optimization problem, where one level optimizes the policy and the other optimizes the reward shaping weights.

**2 Gradient Approximation:**

In this section, the paper introduces three methods for approximating gradients to address the gradient computation challenges in the dual-level optimization problem.

- **Explicit Mapping (EM):** This approach computes ∇ϕπθ(s, a) by establishing an explicit mapping from the reward shaping weight function zϕ to the policy πθ. It redefines the agent's policy to accept shaping weights as inputs and calculates gradients using the chain rule.
- **Meta-Gradient Learning (MGL):** Here, the paper presents a method to approximate the meta-gradient ∇ϕθ, allowing the computation of ∇ϕπθ(s, a) as ∇θπθ(s, a)∇ϕθ. This enables the concurrent optimization of policy parameters and reward shaping weights.
- **Incremental Meta-Gradient Learning (IMGL):** IMGL extends MGL by considering the incremental relationship between policy parameters and reward shaping weights, leading to more efficient gradient computation.

These methods aim to achieve policy and reward shaping weight optimization in an alternating fashion within the dual-level optimization framework to maximize cumulative rewards. Each method employs different strategies for gradient computation, addressing the challenges posed by gradient calculations.

### Problem Setting
**Environment:** The environment is represented as an MDP.

**Rewards:** The paper deals with the concept of reward shaping, where an additional shaping reward function (F) is introduced to modify the original reward function (r). The shaping reward function provides additional guidance to the agent based on domain knowledge. The paper discusses different forms of shaping rewards, including potential-based reward shaping and dynamic potential-based advice.

### Methodology
**1 Parameterized Reward Shaping:**

In this section, the paper presents a dual-level optimization framework to address the reward shaping problem in reinforcement learning. The framework aims to maximize the cumulative reward by optimizing both the agent's policy and reward shaping weights.

- **Problem Description:** First, the paper explicitly defines the problem setting, where an agent attempts to optimize its policy to maximize the expected cumulative reward in a Markov Decision Process (MDP). However, the agent also receives reward signals from a reward shaping function, which may alter the optimal policy.
- **Reward Shaping Function:** The paper introduces a reward shaping function denoted as f, used to modify the original reward function. The reward shaping function may incorporate domain knowledge but can potentially change the optimal policy.
- **Parameterized Reward Shaping:** The paper proposes parameterized reward shaping, where a reward shaping weight function zϕ is introduced to assign a weight to each state-action pair. The parameter ϕ controls these weights.
- **Objective:** The paper's objective is to optimize both the policy πθ and the reward shaping weight function zϕ in the MDP to maximize the cumulative reward. This forms a dual-level optimization problem, where one level optimizes the policy and the other optimizes the reward shaping weights.

**2 Gradient Approximation:**

In this section, the paper introduces three methods for approximating gradients to address the gradient computation challenges in the dual-level optimization problem.

- **Explicit Mapping (EM):** This approach computes ∇ϕπθ(s, a) by establishing an explicit mapping from the reward shaping weight function zϕ to the policy πθ. It redefines the agent's policy to accept shaping weights as inputs and calculates gradients using the chain rule.
- **Meta-Gradient Learning (MGL):** Here, the paper presents a method to approximate the meta-gradient ∇ϕθ, allowing the computation of ∇ϕπθ(s, a) as ∇θπθ(s, a)∇ϕθ. This enables the concurrent optimization of policy parameters and reward shaping weights.
- **Incremental Meta-Gradient Learning (IMGL):** IMGL extends MGL by considering the incremental relationship between policy parameters and reward shaping weights, leading to more efficient gradient computation.

These methods aim to achieve policy and reward shaping weight optimization in an alternating fashion within the dual-level optimization framework to maximize cumulative rewards. Each method employs different strategies for gradient computation, addressing the challenges posed by gradient calculations.

### Assumptions
**Assumptions related to Parameterized Reward Shaping:**

1. **Additive Reward Shaping (F = f):** The paper assumes the most general form of reward shaping, which is additive, i.e., the shaping reward function F is equal to the shaping function f. This assumption simplifies the formulation and analysis of the problem.
2. **Beneficial and Unbeneficial Rewards:** The paper assumes that the shaping rewards can be categorized into beneficial and unbeneficial rewards. The goal is to distinguish between them and use them differently when optimizing the policy.
3. **Parameterized Reward Shaping (zϕ):** The central assumption is the introduction of a parameterized shaping weight function zϕ, which assigns weights to state-action pairs. These weights are controlled by the parameter ϕ. This parameterization allows for fine-tuning the impact of shaping rewards on the policy.

**Assumptions related to Gradient Approximation:**

1. **Policy Gradient Framework:** The paper operates within the policy gradient framework for reinforcement learning, where the objective is to optimize the policy to maximize the expected cumulative reward.
2. **Differentiable Policies:** The methods introduced for gradient approximation assume that the agent's policy πθ is differentiable with respect to its parameters θ and that the gradient of πθ with respect to ϕ exists. This assumption allows for gradient-based optimization.
3. **Unbiased Estimation of Q-Values:** When approximating gradients, the paper assumes the use of unbiased estimations of state-action value functions (Q-values), such as Monte Carlo returns. This assumption affects the accuracy of gradient computations.

### Prominent Formulas


### Results
1. **Introduction of the BiPaRS Framework:** The paper introduces the Bi-level Parameterized Reward Shaping (BiPaRS) framework, which includes parameterized reward shaping and gradient approximation methods. This framework offers a new approach to reward shaping in reinforcement learning.
2. **Policy Invariance:** The proposed gradient approximation methods (EM, MGL, and IMGL) aim to maintain policy invariance, meaning that the optimized policy can still maximize the expected cumulative reward after reward shaping.

### Limitations
**Generalization to Complex Environments:** The experiments mainly focus on relatively simple environments like Cartpole and MuJoCo. It's unclear how well the proposed BiPaRS framework would generalize to highly complex and large-scale environments.

**Sensitivity to Hyperparameters:** The effectiveness of reinforcement learning methods often depends on hyperparameters like learning rates, network architectures, and others. The paper does not provide an extensive exploration of hyperparameters' sensitivity, which is essential for practical applicability.

### Confusing aspects of the paper
[Is there anything that is confusing and could need better explanations or references?]

## Conclusions

### The author's conclusions
In this work, we propose the bi-level optimization of parameterized reward shaping (BiPaRS) approach for adaptively utilizing a given shaping reward function. We formulate the utilization problem of shaping rewards, provide formal results for gradient computation, and propose three learning algorithms for solving this problem. The results in cartpole and MuJoCo tasks show that our algorithms can fully exploit beneficial shaping rewards, and meanwhile ignore unbeneficial shaping rewards or even transform them into beneficial ones.

### My Conclusion
The authors aimed to address the challenge of optimizing policies with parameterized reward shaping and proposed the BiPaRS framework, which includes methods for gradient approximation.The authors conducted experiments in various environments, demonstrating that their methods can improve the learning performance of reinforcement learning algorithms, especially in cases with beneficial shaping rewards. They also showed that their methods can adapt to shaping rewards even when they are initially harmful. These results suggest that the authors have successfully achieved their goals in terms of improving policy optimization with parameterized reward shaping.

### Rating
[Fine, Good, Great]

## Possible future work / improvements
**Handling Multiple Shaping Reward Functions:** The paper mainly deals with a single shaping reward function. Future research could extend the framework to handle scenarios with multiple shaping reward functions and explore how to combine and prioritize them effectively.Relation to Own Work

[If related to own work.]

- What can we learn from their approach:
- How are we different:

## Extra
- Cited references to follow up on/related papers/check google scholar for papers citing this paper:https://chat.openai.com/c/6ac11c4a-7d73-443e-9e64-8fd77c5a1c76
- Source code/blog/twitter thread/other links:

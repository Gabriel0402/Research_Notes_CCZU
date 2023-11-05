# [Title]Structure in Reinforcement Learning:
A Survey and Open Problems
## Quick Look

**Authors**:Aditya Mohan、Amy Zhang、Marius Lindauer

**Date Published** :2023

**Link** : [Paper link]

**Comments:**  arXiv.org

**TLDR:** The objective of this article is to establish a pattern-centric framework for incorporating structural information into Reinforcement Learning (RL). This framework aims to facilitate research into improving the performance of RL algorithms by providing a common understanding and reference point for researchers, enabling them to better address complex real-world problems

**Tags**: structural information、offline RL 、Q-learning

## Paper summary (What)
The main objective of this article is to introduce a pattern-centric framework aimed at incorporating structural elements into Reinforcement Learning (RL). This framework is designed to enhance the performance of RL algorithms when dealing with the complexities, diversities, and noise encountered in real-world problems. The primary steps and objectives of the article are outlined as follows:

1. Establishing the problem context and symbol representation (Section 2): The article begins by providing background information and notation necessary to formalize various aspects of RL problems. This ensures that readers have a clear understanding of RL problems.
2. Introducing the concept of side information and metrics (Section 3): In the third section, the article introduces the concept of side information and defines different additional metrics. These metrics can be addressed by incorporating side information into the RL pipeline. The aim is to provide a method for leveraging domain knowledge to enhance RL performance.
3. Defining structure as side information and categorizing decompositions (Section 4): In the fourth section, the article defines structure as a specific type of side information related to decomposability in a problem. It categorizes different decomposition methods from the literature into four major archetypes.
4. Formulating seven patterns for incorporating structure into RL learning (Section 5): In Section 5, the article presents seven patterns for integrating structural information into the RL learning process. Each pattern is overviewed and connected to relevant surveyed literature. These patterns are designed to assist researchers in effectively utilizing structural information to improve RL algorithms.
5. Paving the way for new research avenues and providing a common reference point (Section 6): Finally, the article discusses the importance of opening up new research avenues and providing a shared reference point. This is intended to help researchers and practitioners better understand which design decisions are effective in different situations.

In summary, the objective of this article is to establish a pattern-centric framework for incorporating structural information into RL. The goal is to promote research aimed at improving the performance of RL algorithms and to provide a common understanding and reference point for researchers, facilitating the handling of complex real-world problems.

## Motivation (What)
Traditional reinforcement learning research has primarily focused on designing agents capable of solving specific tasks. However, their performance significantly degrades when the environment undergoes changes. Furthermore, applying reinforcement learning to optimization problems in the real world presents challenges such as complex dynamics, intractable state and action spaces, and noisy reward signals.

## Issues addressed by the paper (Why)
This paper primarily discusses the issue of structure in reinforcement learning. It describes the limitations of reinforcement learning in addressing real-world scenarios characterized by diverse and unpredictable dynamics, noisy signals, and large state and action spaces. To overcome these challenges and improve the performance of reinforcement learning algorithms across these crucial metrics, the paper proposes methods for incorporating structural information about the problem into the reinforcement learning process. The paper consolidates the structured approaches proposed in various subfields of reinforcement learning into a unified framework, shedding light on the role of structure in the learning problem and classifying these methods into distinct structural patterns. By leveraging this comprehensive framework, the paper provides valuable insights into the challenges of structured reinforcement learning and lays the groundwork for a design pattern perspective on reinforcement learning research. This novel perspective paves the way for future advancements and aids in developing more effective and efficient reinforcement learning algorithms that can potentially handle real-world scenarios better.

## Detailed Information (How)
The authors introduce the notion of side information and define additional metrics that can be addressed by incorporating side information into an RL pipeline. They discuss the formalization of structure as a particular kind of side information about decomposability in a problem. They categorize decompositions in the literature into four major archetypes. The paper formulates seven patterns of incorporating structure into the RL learning process and provides an overview of each pattern by connecting it to the relevant surveyed literature. This framework is intended to open new avenues for research while providing a common reference point for understanding design decisions and their effectiveness in various situations.

### Problem Setting
In the context of this paper, the problem setting is within the domain of Reinforcement Learning (RL), which is a type of sequence prediction problem where an agent learns a policy to interact with an environment to maximize cumulative rewards.

### Methodology
In the paper, the authors approached the problem of structure in reinforcement learning through a literature review and theoretical analysis. They began by defining the concept of side information and proposed how this information could be integrated into the reinforcement learning process to enhance performance. They classified various structured approaches mentioned in the literature and proposed a unified framework to integrate these methods. The detailed workflow includes:

1. Defining and formalizing the problem of reinforcement learning and the concept of structural information.
2. Summarizing the existing diverse structured approaches through a literature review.
3. Categorizing and evaluating these approaches based on how they incorporate structural information into the learning process.
4. Proposing a unified framework to understand and compare these different methods.
5. Discussing the strengths and limitations of these methods and how they address challenges in reinforcement learning.
6. Suggesting future research directions and potential improvement strategies based on this framework.

### Assumptions
In the paper, the authors make assumptions regarding how structural information in reinforcement learning impacts the learning process. Specifically, they assume that incorporating additional side information can improve sample efficiency, meaning it reduces the sample complexity of exploration (ζ), based on certain assumptions about the problem itself. The idea is that with certain structured approaches, the sample can be used more effectively to learn policies.

The authors also mention different methods to improve the sample complexity of exploration and assume these methods can affect the exploration mechanism by directly using side information. These methods include reward-free exploration, randomized action selection, optimism/bonus-based exploration, deliberate exploration, and probability matching.

The validity of these assumptions largely depends on the RL algorithms and the specific types of problems considered. Generally, such assumptions may require further evidence and validation to confirm their universality in complex real-world scenarios.

### Prominent Formulas
[Can be empty]

### Results
Here are the key points extracted regarding the results and discussions: 

Robustness: The paper measures how methods respond to changes in the environment, which includes properties of data distribution like initial state distributions and multi-modal evaluation returns. Different learning dynamics may be robust to different kinds of environmental changes. 

Scalability and Robustness: The authors discuss sub-fields of RL that lie at different points in terms of scalability and robustness, introducing current paradigms and challenges for each sub-field.

 Offline RL: This area involves learning from a fixed dataset without further environment interaction. The challenges here include distributional shifts and exploiting the dataset effectively.

 Structural Decomposition: The paper suggests that structural decomposition can address challenges in Offline RL by improving dataset exploitation, such as learning individual policies or value functions for different subtasks. 

### Limitations
- **Scope of Literature Review:** The comprehensiveness of a literature review can be limited by the scope of databases searched, publication dates, and language restrictions.
- **Theoretical Framework Applicability:** The proposed framework might have limited applicability depending on the variety and complexity of environments and tasks in RL.
- **Assumptions Validity:** As with any theoretical work, the validity of the assumptions made can be a limitation, especially if they do not hold in real-world scenarios.

### Confusing aspects of the paper
[Is there anything that is confusing and could need better explanations or references?]

## Conclusions

### The author's conclusions
Understanding the intricacies of Reinforcement Learning (RL) ’s complexities is challenging, exacerbated by the divergent methodologies employed across different problem domains. This fragmentation hinders the development of unifying principles and consistent practices in RL. To address this critical gap, we propose an innovative framework to understand different methods of effectively integrating the inherent structure of learning problems into RL algorithms. Our work serves as a pivotal step towards consolidating the multifaceted aspects of RL, ushering in a design pattern perspective for this domain. We first conceptualized structure as side information about the decomposability of a learning problem and corresponding solutions. We have categorized decomposability into four distinct archetypes - latent, factored, relational, and modular. This classification delineates a spectrum that establishes insightful connections with existing literature, elucidating the diverse influence of structure within RL.
We then presented seven key patterns following a thorough analysis of the RL land scape - abstraction, augmentation, auxiliary optimization, auxiliary model, warehousing, environment generation, and explicitly designed patterns. These patterns represent strategic approaches for the incorporation of structural knowledge into RL. Although our framework provides a comprehensive starting point, we acknowledge that these patterns are not exhaustive. We envisage this as an impetus for researchers to refine and develop new patterns, thereby expanding the repertoire of design patterns in RL. In conclusion, our work offers a pattern-centric perspective on RL, underlining the critical role of structural decompositions in shaping both present and future paradigms. By promoting this perspective, we aim to stimulate a new wave of research in RL, enriched by a deeper and more structured understanding of the field. While our proposed framework is a novel contribution, it should be viewed as an initial step in an ongoing process.

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
- Source code/blog/twitter thread/other links:

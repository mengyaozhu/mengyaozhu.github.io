+++
title = "Understanding Agentic AI: Agentic Task"
date = 2026-08-25
math = true
tags = ["Agentic AI", "Agentic Task"]
author = ["Mengyao Zhu"]
+++


# Agentic Task

An **agentic task** is a composite task performed by an AI agent through a structured combination of multiple subtasks, where each subtask represents a distinct part of what needs to be accomplished and is fulfilled by an appropriate reusable skill. An agentic task can be represented as $\tau=(\mathcal{T}_{\tau},\mathcal{S}_{\tau},\mathcal{R}_{\tau},\mathcal{M}_{\tau})$, where $\tau$ (**agentic task**) denotes the complete task to be performed, $\mathcal{T}_{\tau}={t_1,t_2,\ldots,t_n}$ (**subtask set**) contains the subtasks that collectively constitute the task, $\mathcal{S}_{\tau}={s_1,s_2,\ldots,s_m}$ (**skill set**) contains the reusable skills available for fulfilling those subtasks, $\mathcal{R}_{\tau}$ (**execution relations**) specifies how the subtasks and their corresponding skills are organized and performed sequentially, iteratively, recursively, or through an appropriate combination of these patterns, and $\mathcal{M}_{\tau}$ (**evaluation metrics**) contains the task-specific measures used to determine whether intermediate results and the overall task outcome satisfy the expected requirements. For each subtask $t_i$ (**subtask**), an appropriate skill $s_j$ (**reusable skill**) may be selected from predefined skills or dynamically engineered during task execution when an existing skill does not adequately address the subtask. This organization can be summarized by the following simple workflow:

$$
\boxed{  
\begin{array}{c}  
\tau;(\text{Agentic Task})\\
\downarrow\\
t_i;(\text{Subtask})\\
\downarrow\\
s_j;(\text{Reusable Skill})\\
\downarrow\\
o_i;(\text{Subtask Output})\\
\downarrow\\
\mathcal{M}_{\tau};(\text{Evaluation Metrics})\\
\downarrow\\
\begin{cases}  
t_{i+1};(\text{Next Subtask}), & \text{if requirements are satisfied}\\
t_i\ \text{or}\ t_k;(\text{Repeated or Related Subtask}), & \text{if further execution is required}  
\end{cases}  
\end{array}  
}
$$

Here, $o_i$ (**subtask output**) denotes the result produced by performing subtask $t_i$, while $t_{i+1}$ (**next subtask**) denotes a subsequent subtask and $t_k$ (**related subtask**) denotes another subtask that may need to be performed or revisited according to the evaluation result. The workflow therefore does not require every subtask to be executed only once or in a fixed linear order: subtasks may be performed sequentially when one result provides the basis for the next, iteratively when a subtask needs to be repeated and refined according to evaluation results, or recursively when performing a subtask gives rise to further subtasks that are handled through the same task–subtask–skill structure. Through these execution patterns, intermediate outputs can be evaluated against $\mathcal{M}_{\tau}$ and used to determine subsequent execution until the combined results of the subtasks allow the overall agentic task $\tau$ to satisfy its specified requirements and expected evaluation criteria.

For an **agentic task to hold**, the task should be sufficiently compositional and execution-oriented to require or meaningfully support decomposition into one or more identifiable subtasks whose coordinated performance contributes to the completion of the overall task. Each required subtask $t_i \in \mathcal{T}_{\tau}$ should have an applicable skill $s_j \in \mathcal{S}_{\tau}$, either predefined and reusable from an existing skill set or dynamically engineered when no suitable existing skill is available, so that the agent has a viable means of performing the required work. The execution relations $\mathcal{R}_{\tau}$ should provide sufficient structure for determining how execution proceeds among subtasks, including when a subsequent subtask should begin, when an earlier subtask should be revisited, when repeated refinement is necessary, or when additional subtasks should be introduced during execution. The evaluation metrics $\mathcal{M}_{\tau}$ should also provide sufficiently clear criteria for assessing whether each relevant output $o_i$ and, ultimately, the overall task outcome meet the expected requirements. Accordingly, an agentic task holds when its necessary subtasks can be identified or dynamically determined, suitable skills can be assigned or engineered to fulfill them, their execution can be coordinated through appropriate sequential, iterative, or recursive relations, and their resulting outputs can be evaluated and progressively used to guide the task toward satisfactory completion.


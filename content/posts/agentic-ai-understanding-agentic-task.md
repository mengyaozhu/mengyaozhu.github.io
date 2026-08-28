+++
title = "Understanding Agentic AI: Agentic Task"
date = 2026-08-24
math = true
tags = ["Agentic AI", "Agentic Task"]
author = ["Mengyao Zhu"]
+++

## Definition of Agentic Task 

An agentic task is a composite task performed by an AI agent through a structured combination of multiple subtasks, where each subtask represents a distinct part of what needs to be accomplished and is fulfilled by an appropriate reusable skill. An agentic task can be represented as $\tau=({T}\_{\tau},{S}\_{\tau},{R}\_{\tau},{M}\_{\tau})$, where $\tau$ (agentic task) denotes the complete task to be performed, ${T}\_{\tau}={t_1,t_2,\ldots,t_n}$ (subtask set) contains the subtasks that collectively constitute the task, ${S}\_{\tau}={s_1,s_2,\ldots,s_m}$ (skill set) contains the reusable skills available for fulfilling those subtasks, ${R}\_{\tau}$ (execution relations) specifies how the subtasks and their corresponding skills are organized and performed sequentially, iteratively, recursively, or through an appropriate combination of these patterns, and ${M}\_{\tau}$ (evaluation metrics) contains the task-specific measures used to determine whether intermediate results and the overall task outcome satisfy the expected requirements. For each subtask $t_i$ (subtask), an appropriate skill $s_j$ (reusable skill) may be selected from predefined skills or dynamically engineered during task execution when an existing skill does not adequately address the subtask. 

## Conditions for an Agentic Task to Hold

For an agentic task to hold, the task should be sufficiently compositional and execution-oriented to require or meaningfully support decomposition into one or more identifiable subtasks whose coordinated performance contributes to the completion of the overall task. Each required subtask $t_i \in {T}\_{\tau}$ should have an applicable skill $s_j \in {S}\_{\tau}$, either predefined and reusable from an existing skill set or dynamically engineered when no suitable existing skill is available, so that the agent has a viable means of performing the required work. The execution relations ${R}\_{\tau}$ should provide sufficient structure for determining how execution proceeds among subtasks, including when a subsequent subtask should begin, when an earlier subtask should be revisited, when repeated refinement is necessary, or when additional subtasks should be introduced during execution. The evaluation metrics ${M}\_{\tau}$ should also provide sufficiently clear criteria for assessing whether each relevant output $o_i$ and, ultimately, the overall task outcome meet the expected requirements. Accordingly, an agentic task holds when its necessary subtasks can be identified or dynamically determined, suitable skills can be assigned or engineered to fulfill them, their execution can be coordinated through appropriate sequential, iterative, or recursive relations, and their resulting outputs can be evaluated and progressively used to guide the task toward satisfactory completion.



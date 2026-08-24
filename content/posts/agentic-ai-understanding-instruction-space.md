+++
title = "Understanding Agentic AI: Instruction Space"
date = 2026-08-24
weight = -1
math = true
tags = ["Agentic AI", "Mathematical Notations", "Instruction Space", "Agentic AI", "Agentic AI Notation"]
author = ["Mengyao Zhu"]
+++


## Definition of Instruction Space

An **instruction space** is the organized set of instructions that may govern, constrain, guide, or otherwise influence the behavior of an AI agent. It can be represented as $I = {i_1, i_2, \ldots, i_n}$, where $I$ denotes the instruction space and each $i_j \in I$ denotes a **unit instruction** expressing an individual rule, requirement, constraint, preference, procedure, condition, or behavioral direction that the agent can interpret and apply. The instruction space may contain instructions originating from different authorized sources or functional levels, such as system instructions $I^{S}$, user instructions $I^{U}$, task instructions $I_{\tau}$, and skill or workflow instructions $I^{K}$, with these instruction sets forming relevant parts of the broader space, for example $I^{S}, I^{U}, I_{\tau}, I^{K} \subseteq I$. The elements of $I$ do not necessarily have equal authority, applicability, or effect: some instructions may apply generally, others only to a particular task $\tau$, state $z_t$, or runtime condition, and some may be overridden, disabled, superseded, or rendered inapplicable according to the governing instruction hierarchy and applicable conditions. Thus, $I$ represents the broader space of instructions potentially relevant to agent behavior, while an active instruction set $I^{*}_{\tau,t} \subseteq I$ can represent the instructions that actually govern or guide the agent for task $\tau$ at execution step $t$.

## Conditions for an Instruction Space to Hold

An instruction space $I$ can be considered to hold for an AI agent when its constituent instructions are available to, accessible by, or otherwise represented within the agent’s operative instructional environment and are capable of being considered under the applicable authority, scope, and runtime conditions. This does not require every $i_j \in I$ to be active simultaneously; rather, the space may contain both currently applicable and conditionally applicable instructions. Let $\alpha(i_j, \tau, z_t, E_t) \in {0,1}$ denote whether instruction $i_j$ is applicable to task $\tau$ under agent state $z_t$ and runtime environment $E_t$, and let $\lambda(i_j, I)$ represent the effect of instruction priority, authorization, conflict resolution, overriding, or disabling rules. The operative instruction set may then be expressed abstractly as $I^{*}_{\tau,t} = {i_j \in I \mid \alpha(i_j, \tau, z_t, E_t) = 1 \land \lambda(i_j, I) = 1}$. Accordingly, the instruction space continues to hold even when some instructions are inactive, provided that the space itself remains defined and available; what changes with the task and runtime conditions is the subset of instructions that actually governs, constrains, or guides the agent’s current behavior.


## Notations for Instruction Space with Relevant Terms

| **Title**                  | **Notation**                                                    | **Convention**                                                                                                                                                                        |
| -------------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Instruction Space          | $\mathcal{I}$                                                   | General set of instructions that may govern, constrain, or guide the behavior of an Ai Agent.                                                                                                |
| System Instructions        | $\mathcal{I}^{S}\subseteq\mathcal{I}$                           | Higher-level instructions that establish persistent task procedures, default behaviors, constraints, and interpretation rules.                                                        |
| User Instructions          | $\mathcal{I}^{U}\subseteq\mathcal{I}$                           | Instructions dynamically supplied by the user for a particular interaction or downstream task.                                                                                        |
| Task-Specific Instructions | $\mathcal{I}_{\tau}\subseteq\mathcal{I}^{U}\cup\mathcal{I}^{S}$ | Instructions specifically relevant to downstream task $\tau$.                                                                                                                         |
| Effective Instructions     | $\mathcal{I}^{*}_{\tau}$                                        | Instructions that remain operative for task $\tau$ after instruction precedence, modifications, replacements, disabling operations, and other applicability rules have been resolved. |



## Explore Instruction Space Relevant Concepts


### Unit Instruction

A **unit instruction** is an individual instruction within an instruction space $I$ that expresses a distinct direction, requirement, constraint, preference, condition, or other guidance for an AI agent when performing a task. For a user task $\tau$, the user’s task instruction at step $t$ can be represented as $I^{U}*{\tau,t} = I^{E}*{\tau,t} \cup I^{I}*{\tau,t} = {i_1, i_2, \ldots, i*{n_t}}$, where each $i_j$ is a unit instruction, $I^{E}*{\tau,t}$ contains **explicit unit instructions** directly stated by the user, and $I^{I}*{\tau,t}$ contains **implicit unit instructions** indirectly expressed by the user and identified through instruction detection, such as semantic matching or contextual interpretation. A unit instruction does not need to correspond to a separate sentence or command; it represents a distinct instructional meaning that can be identified as part of the user’s broader task instruction. Because additional instructions or instructional meanings may arise or become identifiable as the task proceeds, the user’s task instruction can change over time, so $I^{U}_{\tau,t+1}$ may include new unit instructions that were not included or identified at an earlier step.





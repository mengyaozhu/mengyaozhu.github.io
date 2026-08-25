+++
title = "Understanding Agentic AI: Dynamically Engineered Skill"
date = 2026-08-26
math = true
tags = ["Agentic AI", "Dynamically Engineering Skill", "Understanding Agent AI", "Understanding Agentic AI"]
author = ["Mengyao Zhu"]
+++

# Dynamically Engineered Skill

## Definition of Dynamically Engineered Skill

A **dynamically engineered skill** is a new reusable skill constructed during the execution or preparation of an agentic task when a required subtask cannot be adequately fulfilled by any compatible reusable skill already available in the agent’s skill database. For an agentic task $\tau$ with a subtask $t_i$, let $\mathcal{S}={s_1,s_2,\ldots,s_m}$ denote the **existing skill database**, where each $s_j$ (**existing reusable skill**) represents an available skill that can potentially be applied to different tasks and subtasks. Before engineering a new skill, the agent determines whether at least one $s_j\in\mathcal{S}$ is sufficiently compatible with the requirements of $t_i$. This compatibility does not require the skill and subtask to use identical wording; rather, the skill should provide the capabilities, instructions, procedures, tools, input-output handling, and other relevant characteristics needed to perform the subtask as expected. If no existing skill satisfies the required compatibility conditions, a new skill $s_{\mathrm{new}}$ (**dynamically engineered skill**) can be constructed specifically to fulfill $t_i$. Although $s_{\mathrm{new}}$ originates from the requirements of a particular subtask, it should, where appropriate, be defined at a sufficiently general and modular level so that it can subsequently be stored in the skill database and reused for compatible subtasks in other agentic tasks rather than being unnecessarily reconstructed each time a similar requirement occurs.

## Conditions for a Dynamically Engineered Skill to Hold

A **dynamically engineered skill holds** when a required subtask $t_i$ has been identified, its relevant requirements can be determined with sufficient clarity, and systematic examination of the existing skill database $\mathcal{S}$ indicates that no available skill is sufficiently compatible with those requirements. The absence of an appropriate skill should represent a meaningful capability or procedural gap rather than merely a difference in naming, wording, description, or minor configuration, because an existing reusable skill should normally be preferred when it can reliably fulfill the subtask directly or through permitted adaptation. A new skill should therefore be engineered only when the incompatibility is sufficiently important that using existing skills would prevent the subtask from being performed as required or would fail relevant evaluation criteria. The resulting $s_{\mathrm{new}}$ should contain sufficiently defined instructions, procedures, requirements, inputs, outputs, applicable conditions, or other necessary components for performing the target subtask, and its scope should be sufficiently coherent to represent a reusable capability rather than a one-time collection of instructions tied unnecessarily to a single task instance. Once constructed and appropriately validated, $s_{\mathrm{new}}$ can be added to $\mathcal{S}$, thereby extending the available skill database and allowing future compatible subtasks to reuse the newly engineered skill.

## Identification of the Need for a Dynamically Engineered Skill

The need to engineer a new reusable skill can be identified through a **skill filtering and compatibility assessment** that compares the requirements of the target subtask $t_i$ against the existing skills in $\mathcal{S}$. The agent can first obtain the relevant metadata $M(s_j)$ (**skill metadata**) of each existing skill $s_j$, which may include its name, description, intended function, applicable task or subtask types, expected inputs and outputs, required tools, constraints, dependencies, and other information useful for determining its applicability. Different filtering methods can then be applied individually or in combination. **Semantic matching** can use the language-understanding capability of the supporting LLM to determine whether the meaning and requirements of $t_i$ correspond sufficiently closely to the capabilities represented by $M(s_j)$, even when different terminology or expressions are used. **Metadata search** can retrieve candidate skills whose names, descriptions, tags, capabilities, input-output specifications, or other metadata correspond to characteristics of the subtask. Additional rule-based filtering, constraint checking, capability matching, ranking, or evaluation methods can further eliminate incompatible candidates and identify the most appropriate remaining skills. This process can be represented simply as the following pseudo-algorithm:

```markdown
Algorithm: Identify or Dynamically Engineer a Reusable Skill

Input:
    t_i      — Target Subtask
    S        — Existing Skill Database {s_1, ..., s_m}

1. Identify the requirements of t_i.

2. For each existing reusable skill s_j in S:
       Retrieve M(s_j) — Skill Metadata.

3. Apply F(t_i, M(s_j)) — Compatibility Filtering,
   using one or more methods such as:
       - semantic matching,
       - metadata search,
       - rule-based filtering,
       - constraint checking,
       - capability matching.

4. Evaluate the compatible candidate skills.

5. If a sufficiently compatible existing skill s_j is identified:
       Select s_j — Existing Reusable Skill.
   Else:
       Engineer s_new — Dynamically Engineered Skill
       for the requirements of t_i.

6. Validate s_new when a new skill has been engineered.

7. Add the validated s_new to S so that it can be
   reused for compatible subtasks in future agentic tasks.

Output:
    s_j or s_new — Reusable Skill for t_i
```

where $F$ (**compatibility filtering function**) represents one or more filtering methods, such as semantic matching, metadata search, rule-based filtering, constraint checking, or capability matching. A new reusable skill should therefore be engineered only after the available skill database has been examined with appropriate filtering methods and no existing skill has been found to provide sufficient compatibility with the target subtask.



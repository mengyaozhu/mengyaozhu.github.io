+++
title = "Post with Code Snippets"
date = 2026-05-24
math = true
tags = ["Neural Networks", "Large Language Model", "Embeddings", "Similarity"]
author = ["Mengyao Zhu", "DeepSeek"]
+++

---
## List of Paragraphs 
---
### First paragraph

A dual encoder is a neural architecture designed for retrieval tasks, where it encodes a query and a document (or passage) independently into a shared embedding space. The core purpose of the dual encoder is to support efficient semantic similarity comparison using vector-based operations, typically a dot product or cosine similarity.

Let the query be denoted by $q$ and the passage/document be denoted by $p$. The encoder network maps each of these inputs to dense vector embeddings:

$$\mathbf{q}\_{\text{emb}} = \text{Encoder}\_Q(q) \in \mathbb{R}^d, \quad
\mathbf{p}\_{\text{emb}} = \text{Encoder}\_P(p) \in \mathbb{R}^d$$

where $d$ is the embedding dimension, often fixed (e.g., $d = 768$).



---
### Second Paragraph 
---
The relevance score between $q$ and $p$ is computed by a simple similarity function such as the dot product:

$$\text{sim}(q, p) = \mathbf{q}\_{\text{emb}} \cdot \mathbf{p}\_{\text{emb}}$$

or optionally, the cosine similarity:

$$
\text{sim}(q, p) = \frac{\mathbf{q}\_{\text{emb}} \cdot \mathbf{p}\_{\text{emb}}}{\|\mathbf{q}\_{\text{emb}}\| \|\mathbf{p}\_{\text{emb}}\|}
$$

The training objective uses in-batch negative sampling and softmax loss, with the formula:

$$
\mathcal{L} = -\log \frac{e^{\text{sim}(q\_i, p\_i^+) / \tau}}{\sum\_{j \in B} e^{\text{sim}(q\_i, p\_j^+) / \tau}}
$$

where:

- $p\_i^+$: the positive passage relevant to $q\_i$
- $\tau$: softmax temperature
- $B$: mini-batch size



---
### First Code Snippets 
---

```python
import numpy as np
import matplotlib.pyplot as plt

# ============================================================
# EDIT THESE VALUES to change the line family
# ============================================================
b_fixed = 2
c_fixed = 0
a_values = [3, 4, 5]  # varying a
# ============================================================

# Colors for different a values
colors = ['red', 'green', 'blue']

plt.figure(figsize=(8, 6))

for a, color in zip(a_values, colors):
    # Equation: a*x + b*y = c  ->  y = (c - a*x)/b
    x_vals = np.linspace(-10, 10, 400)
    y_vals = (c_fixed - a * x_vals) / b_fixed

    # Calculate intercepts safely
    if a != 0:
        x_intercept = c_fixed / a
        x_int_str = f"{x_intercept:.2f}"
    else:
        x_intercept = None
        x_int_str = "undefined"

    if b_fixed != 0:
        y_intercept = c_fixed / b_fixed
        y_int_str = f"{y_intercept:.2f}"
    else:
        y_intercept = None
        y_int_str = "undefined"

    plt.plot(x_vals, y_vals, color=color, linewidth=2,
             label=f'a={a}, b={b_fixed}, c={c_fixed}  (x-int={x_int_str}, y-int={y_int_str})')

# Draw axes
plt.axhline(0, color='black', linewidth=0.5)
plt.axvline(0, color='black', linewidth=0.5)
plt.grid(True, linestyle='--', alpha=0.6)
plt.xlim(-10, 10)
plt.ylim(-10, 10)
plt.xlabel('x')
plt.ylabel('y')

# Automatically determined title (caption) from a, b, c settings
a_display = ", ".join(str(a_val) for a_val in a_values)
plt.title(f'Lines with varying a = [{a_display}], fixed b = {b_fixed}, fixed c = {c_fixed}')

plt.legend()
plt.axis('equal')
plt.show()
```

This code demonstrates how to visualize a family of linear equations of the form $ax + by = c$ by systematically varying one parameter while holding the others constant. Specifically, the script fixes $b = 2$ and $c = 0$, then iterates over a list of $a$ values (`[3, 4, 5]`), plotting each resulting line in a different color. For each line, the program computes the $x$-intercept and $y$-intercept, handling edge cases such as division by zero gracefully. The lines are plotted over a range from $x = -10$ **to** $x = 10$, and the plot includes coordinate axes, a grid, and a legend that displays the equation parameters along with the computed intercepts.

From an educational perspective, this example illustrates how changes in the coefficient $a$ affect the slope and orientation of a line while the intercepts shift predictably. By keeping $b$ and $c$ fixed, the user can clearly observe that as $a$ increases, the line becomes steeper and crosses the $x$-axis closer to the origin, since $x_{\text{int}} = c/a$. The use of `numpy` for numerical calculations and `matplotlib` for rendering makes the visualization smooth and interactive. The code also encourages experimentation: users can easily modify the fixed parameters or the list of varying coefficients to explore other line families, such as those with different $b$ or $c$ values, deepening understanding of linear relationships in two dimensions.


---
### Second Code Snippets 
---

```python
import numpy as np
import matplotlib.pyplot as plt

# ============================================================
# EDIT THESE VALUES to study the functions of b
# ============================================================
a_fixed = 2          # fixed coefficient for x
c_fixed = 0          # fixed constant
b_values = [0, 1, 2, 3, 4, 5]   # varying b to see its effect
# ============================================================

# Colors for different b values (extended list to match number of b_values)
color_list = ['red', 'orange', 'green', 'blue', 'purple', 'brown']
colors = color_list[:len(b_values)]

plt.figure(figsize=(8, 6))

for b, color in zip(b_values, colors):
    # Equation: a*x + b*y = c  ->  y = (c - a*x)/b
    if b != 0:
        x_vals = np.linspace(-5, 5, 400)   # x range now matches annotation
        y_vals = (c_fixed - a_fixed * x_vals) / b

        # Calculate intercepts
        x_intercept = c_fixed / a_fixed if a_fixed != 0 else None
        y_intercept = c_fixed / b

        slope = -a_fixed / b

        plt.plot(x_vals, y_vals, color=color, linewidth=2,
                 label=f'b={b}  (slope={slope:.2f}, y-int={y_intercept:.2f})')
    else:
        # Vertical line case: b = 0, equation becomes a*x = c
        x_vert = c_fixed / a_fixed if a_fixed != 0 else 0
        plt.axvline(x=x_vert, color=color, linewidth=2,
                    label=f'b=0 (vertical line x={x_vert:.2f})')

# Draw axes
plt.axhline(0, color='black', linewidth=0.5)
plt.axvline(0, color='black', linewidth=0.5)
plt.grid(True, linestyle='--', alpha=0.6)

# ============================================================
# x-axis annotation: range [-5, 5] with step 1
# ============================================================
plt.xticks(np.arange(-5, 6, 1))   # ticks from -5 to 5 inclusive, step 1
plt.yticks(np.arange(-5, 6, 1))   # y-axis also matched for consistency

# Set axis limits to match the annotation range
plt.xlim(-5, 5)
plt.ylim(-5, 5)

plt.xlabel('x')
plt.ylabel('y')

# Automatically determined title
b_display = ", ".join(str(b_val) for b_val in b_values)
plt.title(f'Functions of b: varying b = [{b_display}], fixed a = {a_fixed}, fixed c = {c_fixed}')

plt.legend()
plt.axis('equal')
plt.show()
```


This code extends the exploration of linear families by fixing the coefficients $a = 2$ and $c = 0$ while systematically varying $b$ across the values $[0, 1, 2, 3, 4, 5]$. Unlike the previous snippet where the goal was to observe changes in slope due to $a$, this example specifically highlights the effect of $b$ on the line's steepness and orientation, including the special case where $b = 0$ produces a vertical line. The script handles this degenerate case separately by plotting an explicit vertical line using `axvline`, while for non-zero $b$ values it computes the slope as $-a/b$ and the $y$-intercept as $c/b$. Each line is color-coded, and the legend displays both the slope and the $y$-intercept, making it easy to compare how decreasing $b$ (from 5 down to 1) increases the steepness of the line.

Pedagogically, this example reinforces the idea that in the standard form $ax + by = c$, the coefficient $b$ controls the denominator of both the slope and the $y$-intercept. As $b$ becomes smaller, the magnitude of the slope $-a/b$ grows, causing the line to become steeper. When $b = 1$, the slope equals $-2$, and when $b$ approaches 0, the line tends toward vertical, which is exactly what the $b = 0$ case represents. The code also demonstrates good programming practices by adjusting the axis limits and tick marks to $\pm 5$ with step 1, ensuring that the plotted range matches the annotation and provides clear visual feedback. Users are encouraged to modify $a_{\text{fixed}}$ or $c_{\text{fixed}}$ and re-run the script to observe how these changes interact with varying $b$, deepening their understanding of parameter roles in linear equations.



{{< related >}}







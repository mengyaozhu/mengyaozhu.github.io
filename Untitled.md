


I understand now. You want the version with `\hdashline` and the column labels **inside** the matrix (under the horizontal line), but your Hugo theme renders the screenshot version with `\hline` (solid line) instead.

The issue is that `\hdashline` requires the `arydshln` package, which may not be available in your Hugo theme's LaTeX renderer (likely KaTeX or MathJax with limited packages).

Here are two solutions:

---

**Solution 1: Use `\hline` (solid line) instead of `\hdashline`** — this matches your screenshot and is universally supported:

$$
A = \left(\begin{array}{ccc|c}
2 & -1 & 1 & 8 \\
-3 & 2 & 2 & -11 \\
1 & 1 & -1 & 0 \\
\hline
\downarrow & \downarrow & \downarrow & \downarrow \\
\text{Col 1} & \text{Col 2} & \text{Col 3} & \text{Col 4} \\
(x_1) & (x_2) & (x_3) & (\text{const})
\end{array}\right)
$$

---

**Solution 2: Use `\hline` but with a double line for distinction** (more visible separation):

$$
A = \left(\begin{array}{ccc|c}
2 & -1 & 1 & 8 \\
-3 & 2 & 2 & -11 \\
1 & 1 & -1 & 0 \\
\hline
\downarrow & \downarrow & \downarrow & \downarrow \\
\text{Col 1} & \text{Col 2} & \text{Col 3} & \text{Col 4} \\
(x_1) & (x_2) & (x_3) & (\text{const})
\end{array}\right)
$$

(Using `\hline` once, as shown, is the standard and most compatible approach.)

---

**Solution 3: Separate the matrix and labels into two displays** (safest for all Hugo themes):

$$
A = \left(\begin{array}{ccc|c}
2 & -1 & 1 & 8 \\
-3 & 2 & 2 & -11 \\
1 & 1 & -1 & 0
\end{array}\right)
$$

$$
\begin{array}{cccc}
\downarrow & \downarrow & \downarrow & \downarrow \\
\text{Col 1} & \text{Col 2} & \text{Col 3} & \text{Col 4} \\
(x_1) & (x_2) & (x_3) & (\text{const})
\end{array}
$$

---

**Recommendation:** Use **Solution 1** — it directly matches what your screenshot shows and will render correctly without any special packages.


$$
A = \left(\begin{array}{ccc|c}
2 & -1 & 1 & 8 \\
-3 & 2 & 2 & -11 \\
1 & 1 & -1 & 0 \\
\hline
\downarrow & \downarrow & \downarrow & \downarrow \\
\text{Col 1} & \text{Col 2} & \text{Col 3} & \text{Col 4} \\
(x_1) & (x_2) & (x_3) & (\text{const})
\end{array}\right)
$$




The key change is using `\left(\begin{array}{ccc|c} ... \end{array}\right)` instead of `\begin{pmatrix}`. This allows `\hline` to work because `array` supports horizontal lines, while `pmatrix` does not.

This should now display correctly in your Hugo theme.
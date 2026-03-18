# A New Algebraic Framework for the Collatz Conjecture

![A New Algebraic Framework for the Collatz Conjecture](https://img.shields.io/badge/Status-Research%20Project-blue)
![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-green)

This repository presents a novel algebraic framework that proves universal convergence to the trivial cycle.

## Introduction

The Collatz conjecture concerns the iteration of an elementary function. Starting from any positive integer $n$, apply these rules:
- If $n$ is even, divide it by 2
- If $n$ is odd, multiply it by 3 and add 1

The conjecture states that this process always reaches 1, regardless of the starting number.

Traditional approaches analyze Collatz sequences through iteration and statistical bounds. This framework changes the perspective: our proof transforms the traditional iterative view into a structured algebraic space where convergence becomes a consequence of algebraic structure. 

Every Collatz sequence decomposes uniquely into tuples $[p, f(p), m, 1]$ (Definition 2.3, Theorem 2.14), establishing a bijection $\phi_1: C \rightarrow T_1$ and its inverse $\phi_1^{-1}: T_1 \rightarrow C$ that together, constitute a dynamical isomorphism: it preserves iteration structure, cycles and convergence behavior while transferring the problem into an algebraic tuple space, where hidden structure becomes visible (Theorem 3.13). Within this space, the parameter $m$ governs the dynamics of each sequence. 

Under these conditions, algebraic analysis proves that consecutive repetitions of $m$ can only occur at $m = 0$ (Theorem 4.1), establishing $(4, 2, 1)$ as the unique cycle (Corollary 4.3). Furthermore, the repetitions of $m$, named $m_r$, are not merely observed but structurally necessary for the bijection $\phi_1$ to exist (Theorems 5.5, 5.6, 5.7). These repetitions, consecutive or non consecutive, partition all positive integers into classes $S(m_r)$ (Lemma 6.5), each equipped with invariant properties (Theorems 6.6, 6.7, 6.9) that define a deterministic "wormhole" trajectory (Definition 6.11) from a fixed entry point $e(m_r)$ to $n = 1$ (alternatively, from $m_r$ to $m = 0$). 

From different angle, each $m_r$ value classifies its elements by taxonomic type (Definition 7.3): Type A elements have their global maximum before the pseudocycle, Type B within or at it, and finally, Type C after it. While this taxonomy describes the geometric structure of sequences within each class, it is not required for convergence.

Orthogonal to the taxonomy, the regularity classification (Definition 8.1) determines how each element reaches the entry point $e(m_r)$: regular elements arrive through pure divisions by 2, while irregular elements follow complex trajectories involving $3n+1$ operations. Since both cases subsequently follow the same invariant wormhole (Lemmas 9.1 and 9.2), universal convergence follows (Theorem 9.4), independently of whether the classification into 42 known classes is finite or not (Theorem 9.5).

## Key Results Summary

1. **Dynamical Isomorphism**: $\phi_1$ preserves iteration structure and convergence (Theorem 3.13)
2. **Cycle Uniqueness**: $(4,2,1)$ is the only cycle (Theorem 4.1, Corollary 4.3)
3. **Structural Necessity**: Repetitions are required for bijection (Theorems 5.5, 5.6, 5.7)
4. **Class Partition**: Every $n \in \mathbb{Z}^{+}$ belongs to exactly one $S(m_r)$ (Lemma 6.5)
5. **Invariant Properties**: Each class has fixed $m^*$, $d(m_r)$ and wormhole structure (Theorems 6.6, 6.7, 6.9, Definition 6.11)
6. **Regularity Classification**: Elements and classes are regular or irregular, providing the mechanistic foundation for convergence (Definitions 8.1, 8.2, Lemma 8.3, Corollary 8.4)
7. **Universal Convergence**: Every positive integer reaches $(4,2,1)$ (Theorem 9.4)
8. **Proof Independence**: Convergence holds regardless of $M_{rep}$ finiteness (Theorem 9.5)
9. **Total Stopping Time Prediction**: Wormhole trajectories enable efficient $\sigma(n)$ computation for approximately two-thirds of $\mathbb{Z}^{+}$ (Theorem 10.7)

## Computational Verification

- **Range tested**: Up to $n < 2^{40} \approx 1.1 \times 10^{12}$
- **Classes found**: Exactly 42 $m_r$ values
- **Discovery threshold**: All 42 found before $n > 7287$ (below $2^{13}$)
- **Complete enumeration and properties**: See Appendix A of the paper
- **Additional computational tools**: 
  - [Tuple-based mr pairs finder](https://github.com/hhvvjj/mr-pairs-finder)
  - [Search n values by mr](https://github.com/hhvvjj/search-n-values-by-mr)
  - [Pseudocycle transitions tracer](https://github.com/hhvvjj/pseudocycle-transitions-tracer)
  - [Total stopping-time benchmark](https://github.com/hhvvjj/total-stopping-time-benchmark)

## Framework Components

### Section 2-3: Tuple Transform & Dynamical Isomorphism

The foundation of this framework rests on a deceptively simple observation: every Collatz element can be uniquely decomposed as $c_i = 2m_i + p_i$ (Definition 2.3), where $p_i \in \{1,2\}$ captures parity and $m_i \in \mathbb{Z}^+ \cup \{0\}$ represents scale. This decomposition is not merely notational convenience: it establishes a bijective mapping $\phi_1$ that transforms consecutive pairs $(c_i, c_{i+1})$ into algebraic tuples $[p, f(p), m, 1]$ (Theorem 2.14).

This decomposition creates a bijection $\phi_1$ between:
- **$C$**: The space of Collatz sequences
- **$T_1$**: The space of algebraic tuples $[p, f(p), m, 1]$

What appears as chaotic iteration in the original Collatz space follows deterministic algebraic rules in this tuple space. More remarkably, $\phi_1$ preserves the dynamical structure itself: the commutative relation $\phi_1 \circ f = f_T \circ \phi_1$ proves that iterating the Collatz function in $C$-space is equivalent to iterating the tuple transform in $T$-space (Theorem 3.13). This is not algebraic homomorphism, addition and multiplication are not preserved (Remark 3.9), but rather a dynamical isomorphism: cycles, convergence and iteration structure remain intact under the transformation (Theorem 3.13).

**Key Results**

$\phi_1$ is a structure-preserving bijection that transforms an iterative problem into an algebraic one, revealing topological properties (Theorem 2.14, Theorem 3.13).

**Visual Tools**

[Tuple-Based Transform Calculator](step01-the-tuple-based-transform-calculator/) - Decompose any Collatz sequence into algebraic tuples

### Section 4: Cycle Uniqueness

The tuple-based transform reveals a fundamental structural constraint: consecutive equal $m$-values can occur only at $m = 0$ (Theorem 4.1). This seemingly innocuous algebraic property has profound implications for the Collatz conjecture.

Requiring $m' = m$, consecutive repetition, the tuple transform has four possible evolution rules depending on parity transitions. Each case yields an algebraic equation, and solving these four systems reveals that only $m = 0$ satisfies the constraint. The tuple transform algebraically forbids consecutive parameter repetition at any $m > 0$, making ($4, 2, 1$) the structurally unique cycle (Corollary 4.3).

$$
\begin{align}
6m + 4 = 2m + 1 \quad &\Rightarrow \quad m = -3/4 \quad \text{(invalid)}\\
6m + 4 = 2m + 2 \quad &\Rightarrow \quad m = -1/2 \quad \text{(invalid)} \\
m + 1 = 2m + 1 \quad &\Rightarrow \quad m = 0 \\
m + 1 = 2m + 2 \quad &\Rightarrow \quad m = -1 \quad \text{(invalid)}
\end{align}
$$

**Key Results**

The tuple transform proves that $(4,2,1)$ is the unique cycle: algebraic analysis shows $m_i = m_{i+1}$ holds only when $m = 0$ (Theorem 4.1), making any other periodic orbit structurally impossible under $\phi_1$ (Corollary 4.3).

### Section 5: Necessity of Repetitions

Another subtle but crucial property emerges from the framework: parameter repetitions are not merely observed to occur in all tested sequences. They are proven to be structurally necessary for the bijection $\phi_1$ to exist (Theorems 5.5, 5.6, 5.7).

The proof proceeds by contradiction through the elimination of subsequences. Suppose we could construct a tuple sequence satisfying the local evolution rules $f_T$ but containing no parameter repetitions. Such a sequence would have no corresponding Collatz sequence as its preimage. Elimination breaks both the original Collatz transitions and the transformed tuple transitions, destroying the bijection $\phi_1$ (Theorems 5.5, 5.6, 5.7). Thus, the intervening subsequence cannot be removed.

The technique reveals why: removing intermediate subsequences between repetitions creates structural contradictions. The elimination breaks the Collatz transitions in the original space AND violates the tuple evolution rules in the transformed space. Both sequences collapse together since they cannot exist independently (Remark 5.8).

**Key Results**

Repetitions are not computational events we happen to observe: they are the structural glue that binds the two representations together, ensuring every valid tuple sequence corresponds to exactly one valid Collatz sequence (Theorems 5.5, 5.6, 5.7). Without them, both spaces lose their coherence.

**Visual Tools**

[Dynamical Isomorphism](step02-the-dynamical-isomorphism/) - Visualize the bijective mapping and repetitions necessity

### Section 6-7-8: Pseudocycles, Wormholes, Taxonomy & Regularity

The structural necessity of parameter repetitions leads to a remarkable classification: every positive integer belongs to exactly one equivalence class $S(m_r)$ (Lemma 6.5), determined by which parameter value repeats first in its tuple sequence. This partitions the entire domain $\mathbb{Z}^+$ into disjoint classes, each characterized by invariant properties that persist across all its members.

Computational verification up to $n = 2^{40}$ reveals exactly 42 such classes, a finite classification emerging from an infinite domain. All 42 were discovered before $n > 7287$ (below $2^{13}$), with no new classes appearing despite extensive computational exploration. Whether this finiteness is mathematical necessity or empirical observation remains an open question, though the convergence proof does not depend on the answer (Theorem 9.5).

Under our model, each class exhibits a characteristic structure called pseudocycle, the region between the first and second occurrence of $m_r$ in the tuple sequence. This pseudocycle defines an invariant local maximum $m^*$ which remains the same for all members of the class regardless of their starting value (Theorem 6.9). Moreover, the distance $d(m_r)$ between the first and second occurrence of $m_r$ is constant across all class members (Theorem 6.7). These invariants define what we term "wormholes" (Definition 6.11): deterministic trajectories from the entry point $e(m_r)$ to the terminal value $n = 1$, (alternatively, from $m_r$ to $m = 0$). Once a sequence enters the wormhole at $e(m_r)$, its remaining path is completely determined by the class structure, independent of the starting value $n$ (Theorem 6.7).

**Taxonomic Classification (Section 7)**

Within each class, sequences exhibit three distinct geometric patterns based on where their global maximum $M^*$ appears relative to the pseudocycle region (Definition 7.3):

- **Type A**: $M^*$ occurs before the pseudocycle begins
- **Type B**: $M^*$ occurs within the pseudocycle
- **Type C**: $M^*$ occurs after the pseudocycle

Type evolution within classes follows strict rules: Type C → Type A and Type B → Type A transitions occur as $n$ grows (Lemma 7.9, Corollary 7.10), while Type B ↔ Type C transitions are forbidden (Corollary 7.6).

**Regularity Classification (Section 8)**

Orthogonal to the taxonomic classification (Remark 8.6), elements and classes are further classified by how they reach the entry point $e(m_r)$:

- **Regular elements**: $n = e(m_r) \cdot 2^k$ for some $k \geq 0$, reaching the entry point through pure successive divisions by 2 (Definition 8.1).
- **Irregular elements**: reach $e(m_r)$ through complex trajectories involving both, $n/2$ and $3n+1$ operations (Definition 8.1).

**Class $S(0)$ anomaly:** $S(0)$ contains only Type A elements (Lemma 7.5), and are always irregular except for pure Powers of Two, which satisfy $n = 2^k$, making them regular.

Classes partition accordingly into regular classes (containing only regular elements) and irregular classes (containing both regular and irregular elements) (Definition 8.2). Structurally, every irregular class always contains at least the regular element $e(m_r)$ itself (Lemma 8.3) and no class consists exclusively of irregular elements (Corollary 8.4).

This regularity distinction is not merely descriptive: it provides the two structural mechanisms through which the convergence proof operates in Section 9, with regular and irregular elements following different but equally determinate paths into the invariant wormhole.

**Key Results**

The first repeated parameter $m_r$ partitions $\mathbb{Z}^+$ into classes (Lemma 6.5) with invariant local maximum $m^*$ (Theorem 6.9), invariant distance $d(m_r)$ (Theorem 6.7) and deterministic wormhole trajectories (Definition 6.11). The taxonomic classification (Types A, B or C) describes the geometric structure of sequences within each class (Definition 7.3), while the regularity classification (irregular or regular) provides the structural basis for universal convergence (Definitions 8.1, 8.2).

**Visual Tools**

[mr-Classes Enumeration](step03-mr-classes-enumeration/) - Discover the 42 known classes through systematic exploration

[Taxonomy & Universal Convergence](step04-taxonomy-and-universal-convergence/) - Classify sequences by taxonomic type and regularity, depict pseudocycles, identify invariant properties and visualize convergence pathways for Collatz sequences.

### Section 9: Universal Convergence

With the classification structure established, the convergence proof follows a regularity strategy: rather than analyze every individual integer separately, we prove that both regular and irregular elements converge through the shared wormhole structure, and since every positive integer is one or the other, universal convergence follows.

Every positive integer belongs to exactly one class $S(m_r)$ (Lemma 6.5), and all elements within a class share the same invariant wormhole: the trajectory from entry point $e(m_r)$ to $m = 0$, which depends only on $m_r$ and not on the starting value $n$.

The proof divides into two cases:

- **Irregular elements**: The sequence reaches $e(m_r)$ through a complex trajectory involving $3n+1$ operations, then follows the same invariant wormhole to $m = 0$ (Lemma 9.1).

- **Regular elements** ($n = e(m_r) \cdot 2^k$): The sequence performs exactly $k$ divisions by 2 to reach $e(m_r)$, then follows the invariant wormhole to $m = 0$ (Lemma 9.2).

Once any element reaches $e(m_r)$, its subsequent evolution is identical for all class members, regardless of regularity or taxonomic type. Since every element is either regular or irregular (Definition 8.1), and both types converge, universal convergence follows (Theorem 9.4).

**Independence from classification completeness:**

Crucially, this proof does not depend on whether the 42 known classes are exhaustive. If additional classes exist for $n \geq 2^{40}$, their elements would necessarily be either regular or irregular, and both cases converge through the same mechanisms. The finiteness or infiniteness of $M_{rep}$ affects our understanding of the classification landscape but not the validity of universal convergence (Theorem 9.5).

**Key Result:**

Every positive integer converges to ($4, 2, 1$) via class-specific wormhole trajectories, with the proof holding independently of whether additional classes exist beyond the 42 analyzed values.

**Visual Tools**

[The Collatz Amphora](step06-the-collatz-amphora/) - Interactive 3D visualization integrating the complete framework into a single explorable structure. The amphora demonstrates how all 42 wormholes form a unified partitioned network, providing an interactive visualization of universal convergence.

### Section 10: Total Stopping Time Prediction

The wormhole structure discovered in the convergence proof yields immediate computational benefits. The total stopping time $\sigma(n)$ (Definition 10.1), the number of iterations required to reach 1, can be dramatically optimized by exploiting the invariant trajectories rather than computing each step iteratively. The prediction efficiency $\eta(n)$ (Definition 10.5) measures the fraction of $\sigma(n)$ obtained without iteration:

$$\eta(n) = 1 - \frac{k}{\sigma(n)}$$

where $k$ denotes the number of computed steps (Definition 10.4). Three algorithms emerge from this framework, each targeting different aspects of the class structure:

The **Multiplicities Algorithm** exploits the regular class pattern directly (Definition 8.1): for any $n = e(m_r) \cdot 2^k$ belonging to a regular class $S(m_r)$, the exponent $k = \log_2(n / e(m_r))$ is obtained analytically with no iteration required. Combined with the precomputed wormhole length $\tau(m_r) = \sigma(e(m_r))$ (Definition 10.2), this yields $\sigma(n) = k + \tau(m_r)$ (Theorem 10.7) in $O(1)$ time with $\eta(n) = 1$.

Pure Powers of Two ($n = 2^k$) are a special subcase, corresponding to the degenerated case $e(0) = 1$ and $\tau(0) = 0$, so $\sigma(2^k) = k$ is obtained analytically with $\eta(n) = 1$ despite their $S(0)$ class membership (Section 10.4.1).

The **Wormhole Algorithm** generalizes this approach to arbitrary starting values. Rather than computing the entire trajectory to 1, the algorithm iterates only until encountering any value that appears as an entry point in the pre-computed wormhole dictionary (Definition 10.6). At that moment, computation halts and the remaining path is retrieved: $\sigma(n) = k + \tau(m_r)$, where $k$ is the number of computed steps and $\tau(m_r)$ is the pre-stored wormhole length (Definition 10.2). Efficiency is $\eta(n) = \tau(m_r) / \sigma(n)$, varying depending on how quickly the wormhole is entered.

The **Standard Algorithm** applies when neither optimization is possible: sequences in $S(0)$ that never reach a known entry point before reaching 1 ($m_r = 0$). All $\sigma(n)$ steps must be iterated, maintaining $O(\sigma(n))$ complexity with $\eta(n) = 0$ (Section 10.4). This occurs for approximately one-third of all positive integers.

Empirical analysis for $n < 2^{40}$ shows that the Wormhole Algorithm applies to $\approx 65.4\%$ of integers and the Multiplicities Algorithm to a negligible but perfectly efficient subset. The overall prediction efficiency across all integers reaches approximately  $12.2\%$, declining as $n$ grows since wormhole lengths become shorter relative to total stopping times. The Standard Algorithm, required for  $\approx 34.6\%$ of integers, provides no computational savings (Remark 10.15).

Together, these algorithms transform stopping time calculation from an iterative process of unbounded complexity into a hybrid approach with guaranteed finite dictionary lookups (Section 10.5).

**Key Results**

The wormhole structure enables three complementary algorithms. The Multiplicities Algorithm provides instant $O(1)$ calculation with $\eta(n) = 1$ for regular classes (Theorem 10.7), including pure Powers of Two as the degenerate case with $e(0) = 1$ and $\tau(0) = 0$ (Section 10.4.1). The Wormhole Algorithm offers variable savings with $\eta(n) = \tau(m_r)/\sigma(n)$, covering $\approx 65\%$ of all integers. The Standard Algorithm handles the remaining $\approx 35\%$ with $\eta(n) = 0$ (Remark 10.15).

**Visual Tools**

[Total Stopping Time Predictor](step05-total-stopping-time-predictor/) - Optimize computation using multiplicities and wormhole algorithms

### Section 11: Conclusions & Open Questions

This framework proves universal convergence to $(4, 2, 1)$ by transforming an iterative problem into an algebraic one. The tuple-based transform $\phi_1$ reveals structural invariants: cycle uniqueness (Theorem 4.1, Corollary 4.3), necessary repetitions (Theorems 5.5, 5.6, 5.7), invariant wormhole properties (Theorems 6.6, 6.7, 6.9) and the regularity classification of elements and classes (Definitions 8.1, 8.2, Lemma 8.3, Corollary 8.4), that force convergence as a topological consequence rather than a computational observation. Universal convergence follows from the fact that every positive integer is either regular or irregular (Definition 8.1), and both types reach the entry point $e(m_r)$ and follow the same invariant wormhole to $m = 0$ (Lemmas 9.1, 9.2), making the framework robust to discovery of additional $S(m_r)$ classes beyond the 42 computationally verified (Theorem 9.5).

**Open Questions**:

1. **Algebraic Characterization of $M_{\text{rep}}$**: Computational verification for $n < 2^{40}$ identifies exactly 42 distinct parameter values. Whether $M_{\text{rep}}$ is finite or could contain additional values for larger $n$ remains open. Determining membership in $M_{\text{rep}}$ from first principles, without computational enumeration, would provide deeper insight into Collatz dynamics. Proving or disproving finiteness would be a significant theoretical advance, though convergence remains valid regardless (Theorem 9.5).

2. **Negative integers**: The Collatz function extends naturally to $\mathbb{Z}^-$, where additional non-trivial cycles exist beyond $(4,2,1)$, such as $(-1) \to (-2) \to (-1)$ and $(-5) \to (-14) \to (-7) \to (-20) \to (-10) \to (-5)$. Adapting the framework to characterize the complete cycle structure and convergence behavior for $n < 0$ is a natural extension.

3. **Generalized functions**: The framework may extend to functions of the form $f(n) = n/d$ for $d|n$ and $f(n) = an+b$ otherwise. Characterizing which parameter choices $(a, b, d)$ yield convergent dynamics could illuminate the broader class of Collatz-like problems.

## Research Paper

**Title**: On the Convergence of Collatz Sequences: A New Algebraic Framework

**Author**: Javier Hernández (Independent Researcher, Spain)

**Abstract**: We present a novel algebraic framework for analyzing the Collatz conjecture based on the tuple-based transform $\phi_1$, a bijection between Collatz sequences and sequences of algebraic tuples. This transform decomposes each Collatz value as $c_i = 2m_i + p_i$, isolating a bounded parity component $p_i \in \{1, 2\}$ from a parameter $m_i$ that encodes the dynamics of the sequence. The transform constitutes a dynamical isomorphism, preserving cycles and convergence properties while exposing the algebraic structure underlying sequence evolution.

Within this framework, we prove that consecutive equal values of the parameter $m$ occur only when $m = 0$, establishing $(4, 2, 1)$ as the unique cycle. More fundamentally, we show that parameter repetitions are structurally necessary for the dynamical isomorphism to exist, implying that every Collatz sequence must contain at least one repeated parameter value, and each such repetition defines a wormhole, an invariant trajectory structure that terminates at $m = 0$.

The convergence proof follows from element regularity: every positive integer belongs to exactly one of 42 known classes $S(m_r)$ determined by its first repeated parameter and converges regardless of whether it is regular (reaching the entry point through pure divisions by 2) or irregular (reaching it through complex trajectories involving $3n+1$ operations). In both cases, the invariant wormhole structure from the entry point forces convergence to the unique cycle $(4, 2, 1)$. The proof is independent of the finiteness of these 42 parameter values and extends to any potential new repetition classes.

The framework also enables stopping time prediction through invariant wormhole structure, applicable to approximately two-thirds of positive integers.

[Read the full paper](https://doi.org/10.5281/zenodo.15546925)

## Citation

If you use this framework in your research, please cite:

```bibtex
@software{hernandez2026anewalgebraicframeworkforthecollatzconjecture,
  title={A New Algebraic Framework for the Collatz Conjecture},
  author={Hernandez, Javier},
  year={2026},
  url = {https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture},
  note={Implementation based on research DOI: 10.5281/zenodo.15546925}
}
```

## License

This project is licensed under the terms specified in the [LICENSE](https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture/blob/main/LICENSE) file.

## Author

**Javier Hernández**  
Independent Researcher  
Email: 271314@pm.me  
GitHub: [@hhvvjj](https://github.com/hhvvjj)

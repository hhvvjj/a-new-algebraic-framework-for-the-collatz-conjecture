# A New Algebraic Framework for the Collatz Conjecture

![A New Algebraic Framework for the Collatz Conjecture](https://img.shields.io/badge/Status-Research%20Project-blue)
![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-green)

This repository presents a novel algebraic framework that proves universal convergence to the trivial cycle.

## Introduction

The Collatz Conjecture, also known as the $3n+1$ problem, is one of mathematics' most deceptively simple unsolved problems. Starting from any positive integer $n$, apply these rules:
- If $n$ is even, divide it by 2
- If $n$ is odd, multiply it by 3 and add 1

The conjecture states that this process always reaches 1, regardless of the starting number.

Our proof transforms the traditional iterative view into a structured algebraic space where convergence becomes a consequence of topological properties rather than computational iteration: every Collatz sequence decomposes uniquely into tuples $[p, f(p), m, 1]$, where the parameter $m$ must repeat. These repetitions partition all positive integers into $S(m_r)$ classes with invariant properties, specifically deterministic "wormhole" trajectories from a fixed entry point $e(m_r)$ to convergence. Proving that representative elements from each class converge establishes universal convergence, with the result holding independently of whether the $S(m_r)$ classification is finite or infinite.

## Key Results Summary

1. **Dynamical Isomorphism**: $\phi_1$ preserves iteration structure and convergence
2. **Cycle Uniqueness**: $(4,2,1)$ is the only cycle
3. **Structural Necessity**: Repetitions are required for bijection
4. **Class Partition**: Every $n \in \mathbb{Z}^{+}$ belongs to exactly one $S(m_r)$
5. **Invariant Properties**: Each class has fixed $m^\*$, $d(m_r)$ and wormhole structure
6. **Universal Convergence**: Every positive integer reaches $(4,2,1)$
7. **Proof Independence**: Convergence holds regardless of $M_{rep}$ finiteness
8. **Total Stopping Time Prediction**: Wormhole trajectories enable efficient $\sigma(n)$ computation for approximately two-thirds of $\mathbb{Z}^{+}$

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

### From Iteration to Structure

Traditional approaches analyze Collatz sequences through iteration and statistical bounds. This framework inverts the perspective: instead of computing sequences step-by-step, we decompose them algebraically and prove that the decomposition itself guarantees convergence.

The core innovation is the Tuple-based Transform $\phi_1: C \rightarrow T_1$, where $\phi_1$ is a dynamical isomorphism which preserves iteration structure, cycles and convergence, while revealing algebraic patterns invisible in the original sequence space.

### Section 2-3: Tuple Transform & Dynamical Isomorphism

The foundation of this framework rests on a deceptively simple observation: every Collatz element can be uniquely decomposed as $c_i = 2m_i + p_i$, where $p_i \in \\{1,2\\}$ captures parity and $m_i \in \mathbb{Z}^+ \cup \\{0\\}$ represents scale. This decomposition is not merely notational convenience: it establishes a bijective mapping $\phi_1$ that transforms consecutive pairs $(c_i, c_{i+1})$ into algebraic tuples $[p, f(p), m, 1]$.

This decomposition creates a bijection $\phi_1$ between:
- **$C$**: The space of Collatz sequences
- **$T_1$**: The space of algebraic tuples $[p, f(p), m, 1]$

What appears as chaotic iteration in the original Collatz space follows deterministic algebraic rules in this tuple space. More remarkably, $\phi_1$  preserves the dynamical structure itself: the commutative relation $\phi_1 \circ f = f_T \circ \phi_1$ proves that iterating the Collatz function in $C$-space is equivalent to iterating the tuple transform in $T$-space. This is not algebraic homomorphism, addition and multiplication are not preserved, but rather a dynamical isomorphism, cycles, convergence and iteration structure remain intact under the transformation.

**Key Results**

$\phi_1$ is a structure-preserving bijection that transforms an iterative problem into an algebraic one, revealing topological properties.

**Visual Tools**

[Tuple-Based Transform Calculator](step01-the-tuple-based-transform-calculator/) - Decompose any Collatz sequence into algebraic tuples

### Section 4: Cycle Uniqueness

The tuple-based transform reveals a fundamental structural constraint: consecutive equal $m$-values can occur only at $m = 0$. This seemingly innocuous algebraic property has profound implications for the Collatz conjecture. 

Requiring $m' = m$ (consecutive repetition), the tuple transform has four possible evolution rules depending on parity transitions. Each case yields an algebraic equation, and solving these four systems reveals that only $m = 0$ satisfies the constraint. The tuple transform algebraically forbids consecutive parameter repetition at any $m > 0$, making ($4, 2, 1$) the structurally unique cycle.

$$
\begin{align}
6m + 4 = 2m + 1 \quad &\Rightarrow \quad m = -3/4 \quad \text{(invalid)}\\
6m + 4 = 2m + 2 \quad &\Rightarrow \quad m = -1/2 \quad \text{(invalid)} \\
m + 1 = 2m + 1 \quad &\Rightarrow \quad m = 0 \\
m + 1 = 2m + 2 \quad &\Rightarrow \quad m = -1 \quad \text{(invalid)}
\end{align}
$$


**Key Results**

The tuple transform proves that $(4,2,1)$ is the unique cycle: algebraic analysis shows $m_i = m_{i+1}$ holds only when $m = 0$, making any other periodic orbit structurally impossible under $\phi_1$.

### Section 5: Necessity of Repetitions

Another subtle but crucial property emerges from the framework: parameter repetitions are not merely observed to occur in all tested sequences. They are proven to be structurally necessary for the bijection $\phi_1$ to exist.

The proof proceeds by contradiction through the elimination of subsequences. Suppose we could construct a tuple sequence satisfying the local evolution rules $f_T$​ but containing no parameter repetitions. Such a sequence would have no corresponding Collatz sequence as its preimage. Elimination breaks both the original Collatz transitions and the transformed tuple transitions, destroying the bijection $\phi_1$. The intervening subsequence cannot be removed.

The technique reveals why: removing intermediate subsequences between repetitions creates structural contradictions. The elimination breaks the Collatz transitions in the original space AND violates the tuple evolution rules in the transformed space. Both sequences collapse together since they cannot exist independently.

**Key Results**

Repetitions are not computational events we happen to observe: they are the structural glue that binds the two representations together, ensuring every valid tuple sequence corresponds to exactly one valid Collatz sequence. Without them, both spaces lose their coherence.


**Visual Tools**

[Dynamical Isomorphism](step02-the-dynamical-isomorphism/) - Visualize the bijective mapping and repetitions necessity

### Section 6-7: Pseudocycles, Wormholes & Taxonomy

The structural necessity of parameter repetitions leads to a remarkable classification: every positive integer belongs to exactly one equivalence class $S(m_r)$, determined by which parameter value repeats first in its tuple sequence. This partitions the entire domain $\mathbb{Z}^+$ into disjoint classes, each characterized by invariant properties that persist across all its members.

Computational verification up to $n = 2^{40}$ reveals exactly 42 such classes, a finite classification emerging from an infinite domain. All 42 were discovered before $n > 7287$ (below $2^{13}$), with no new classes appearing despite extensive computational exploration. Whether this finiteness is mathematical necessity or empirical observation remains an open question, though the convergence proof does not depend on the answer.

Under our model, each class exhibits a characteristic structure called pseudocycle, the region between the first and second occurrence of $m_r$ in the tuple sequence. This pseudocycle defines an invariant local maximum $m^\*$ which remains the same for all members of the class regardless of their starting value. Within each class, sequences exhibit three distinct geometric patterns based on where their global maximum $M^\*$ appears relative to this pseudocycle region:

- **Type A**: $M^\*$ occurs before the pseudocycle begins

- **Type B**: $M^\*$ occurs within the pseudocycle

- **Type C**: $M^\*$ occurs after the pseudocycle

The 42 known classes divide into two structural categories: regular classes (every member expressible as $e(m_r) \cdot 2^k$) and irregular classes (members reach entry points through complex trajectories). 

Within each class, individual elements are further classified by their maximum position relative to parameter repetition:

**Type evolution within classes:**

- Type C → Type A and Type B → Type A transitions occur as n grows
- Type B ↔ Type C transitions are forbidden
- Classes containing Type C elements are always regular
- Classes containing Type B elements can be regular or irregular

**Class S(0) anomaly:**
S(0) contains only Type A elements (maximum always precedes $m = 0$) and are always irregular, except for one predictable subset: pure powers of 2 ($n = 2^k$), which are Type A but satisfy $\tau(2^k) = k$, making them predictable despite their irregular classification.

This dual classification reveals a fundamental principle: all sequences eventually evolve to Type A behavior (maximum before repetition) as $n$ increases within their class, but class regularity is an invariant structural property determined by the algebraic form of class membership, independent of individual element types.

Moreover, each class possesses invariant properties that remain fixed regardless of which member $n$ we examine: the local maximum $m^\*$ is the same for all class members and the distance $d(m_r)$ between the first and second occurrence of $m_r$ is constant. These invariants define what we term "wormholes": deterministic trajectories from the entry point $e(m_r)$ to the terminal values $m = 0$ or $n = 1$. Once a sequence enters the wormhole at $e(m_r)$, its remaining path is completely determined by the class structure, independent of the starting value $n$.

**Key Results**

The first repeated parameter $m_r$ partitions $\mathbb{Z}^+$ into classes with invariant local maximum $m^\*$ and deterministic wormhole trajectories that govern convergence independent of the starting value.

**Visual Tools**

[mr-Classes Enumeration](step03-mr-classes-enumeration/) - Discover the 42 known classes through systematic exploration

[Taxonomy & Universal Convergence](step04-taxonomy-and-universal-convergence/) - Classify sequences, depict pseudocycles, identify invariant properties, and visualize convergence pathways

### Section 8: Universal Convergence

With the classification structure established, the convergence proof follows a representative strategy: rather than analyze every individual integer, we prove that each class $S(m_r)$ contains at least one element whose convergence can be demonstrated directly, and all other class members inherit this convergence through the shared wormhole structure.

The proof divides into three exhaustive cases corresponding to the class structure:

- $\text{ Class } S(m_r), \text{ where } m_r = 0$: These sequences reach $m_r = 0$ directly without encountering any other repeated parameter, ensuring immediate convergence to the terminal cycle.

- $\text{ Classes } S(m_r), \text{ where } m_r > 0 \text{ and irregular}$ : The property $M^\* = m^\*$ provides a direct upper bound: the global maximum coincides with the local maximum within the pseudocycle, forcing bounded descent toward $m = 0$ after the wormhole begins.

- $\text{ Classes } S(m_r), \text{ where } m_r > 0\text{ and regular}$ : The structural pattern $n = e(m_r) \cdot 2^k$ guarantees that all members reach the entry point through successive divisions by 2, after which the wormhole trajectory ensures convergence.

**The power of invariance:**

The elegance of this approach lies in its use of invariance. Since $m\^*$, $d(m_r)$ and the wormhole trajectory $W(m_r)$ are identical for all members of a class $S(m_r)$, proving convergence for a single representative element, whether Type B or Type C, proves it for the entire class. Type A elements, which dominate asymptotically as $n$ grows, inherit their convergence automatically: they enter the same wormhole as their Type B or Type C counterparts and follow the same deterministic path to $m = 0$.

**Independence from classification completeness:**

Crucially, this proof does not depend on whether the 42 known classes are exhaustive. If additional classes exist for values of $n \ge 2^{40}$, they would necessarily contain either Type B or Type C representative elements, since every class must have at least one such element by the structural taxonomy. These representatives would prove convergence for their respective classes through the same mechanisms: bounded descent via $M\* = m\*$ for irregular classes or structured entry via $e(m_r) \cdot 2^k$ for regular classes. The finiteness or infiniteness of $M_{rep}$ affects our understanding of the classification landscape but not the validity of universal convergence.

**Key Result:**

Every positive integer converges to ($4, 2, 1$) via class-specific wormhole trajectories, with the proof holding independently of whether additional classes exist beyond the 42 analyzed values.

**Visual Tools**

[The Collatz Amphora](step06-the-collatz-amphora/) - Interactive 3D visualization integrating the complete framework into a single explorable structure. The amphora demonstrates how all 42 wormholes form a unified partitioned network, providing visual proof of universal convergence.

### Section 9: Total Stopping Time Prediction

The wormhole structure discovered in the convergence proof yields immediate computational benefits. The total stopping time  $\sigma(n)$, the number of iterations required to reach 1, can be dramatically optimized by exploiting the invariant trajectories rather than computing each step iteratively. Thus, three algorithms emerge from this framework, each targeting different aspects of the class structure:

The **Multiplicities Algorithm** exploits the regular class pattern directly: for any $n$ belonging to a regular class $S(m_r)$, the total stopping time decomposes algebraically as $\sigma(n) = L + k$, where $L$ is the pre-computed base stopping time for the entry point $e(m_r)$ and $k$ counts the factors of 2 in $n=e(m_r) \cdot 2^k$. This calculation is instantaneous with $O(1)$  complexity regardless of how large $\sigma(n)$ might be, achieving $100\\%$ computational efficiency for all regular class members. The algorithm simply identifies the entry point, counts the powers of 2, and retrieves the pre-stored value, enabling instant prediction

The **Wormholes Algorithm** generalizes this approach to arbitrary starting values. Rather than computing the entire trajectory to 1, the algorithm iterates only until encountering any value that appears as an entry point in the pre-computed wormhole dictionary. At that moment, computation halts and the remaining path is retrieved: $\sigma(n) = k + \tau(m_r)$, where $k$ is the number of computed steps and $\tau(m_r)$ is the pre-stored tail length from that entry point to 1. The efficiency varies depending on how quickly the wormhole is entered: sequences beginning at an entry point achieve $100\\%$ savings, while others save a portion proportional to the wormhole length.

The **Standard Algorithm** applies when neither optimization is possible: sequences that never reach a known entry point before arriving at 1 ($m = 0$). This occurs for approximately one-third of all positive integers. The algorithm iterates the complete Collatz trajectory

```math
n \to f(n) \to f^{(2)}(n) \to \cdots \to 1
```
computing every step without shortcuts. Since no pre-computed data is used, the efficiency is $0\\%$ (no computational savings), requiring full iteration to obtain each sequence's stopping time.

Pure powers of 2 ($n = 2^k$) is a special subcase of Standard Algorithm. They belong to $S(0)$ and require full iteration through $k$ successive divisions by 2. However, unlike other Standard sequences, powers of 2 are predictable via the formula $\sigma(2^k) = \log_2(2^k) = k$, making them mathematically determined despite requiring standard iteration. This predictability exceptionally provides a $100\\%$ of efficiency.

Empirical analysis of values up to $n < 2^{40}$ reveals an overall efficiency of approximatelly $20\\%$ for the wormhole approach (on average, more than four-fifths of the computational steps are not eliminated by retrieving pre-calculated trajectories). The multiplicities algorithm achieves perfect efficiency within its domain but applies only to a reduced subset of integers. The standard algorithm, required for approximately one-third of all integers, provides no computational savings except for the predictability property of powers of 2.

Together, these algorithms transform stopping time calculation from an iterative process of unbounded complexity into a hybrid approach with guaranteed finite dictionary lookups.

**Key Results**

The wormhole structure enables three complementary algorithms that transform stopping time computation from unbounded iteration into efficient dictionary-based prediction, achieving approximately 20% overall efficiency across the range $n < 2^{40}$. The Multiplicities Algorithm provides instant $O(1)$ calculation with $100\\%$ efficiency for regular classes, while the Wormholes Algorithm offers variable savings by halting at known entry points, covering $\approx 65\\%$ of all integers.

**Visual Tools**

[Total Stopping Time Predictor](step05-total-stopping-time-predictor/) - Optimize computation using multiplicities and wormhole algorithms

### Section 10: Conclusions & Open Questions

This framework proves universal convergence to ($4, 2, 1$) by transforming an iterative problem into an algebraic one. The tuple-based transform $\phi_1$ reveals structural invariants (cycle uniqueness, necessary repetitions and invariant wormhole properties) that force convergence as a topological consequence rather than a computational observation. Universal convergence follows from algebraic structure, not exhaustive classification, making the framework robust to discovery of additional $S(m_r)$ classes beyond the 42 computationally verified.

**Open Questions**:
1. **Finiteness of $M_{\text{rep}}$**: Are the 42 classes exhaustive or do additional repetitions exist for $n \geq 2^{40}$?
2. **Algebraic characterization**: Can $M_{\text{rep}}$ membership be determined algebraically without enumeration?
3. **Negative integers**: Extension of the framework (additional cycles exist in $\mathbb{Z}^-$)
4. **Generalized functions**: Does the framework extend to $f(n) = an + b$ for $a \neq 3, b \neq 1$?

## Research Paper

**Title**: On the Convergence of Collatz Sequences: A New Algebraic Framework

**Author**: Javier Hernández (Independent Researcher, Spain)

**Abstract**: We present a novel algebraic framework for analyzing the Collatz conjecture based on the \emph{tuple-based transform} $\phi_1$, a bijection between Collatz sequences and sequences of algebraic tuples. This transform decomposes each element as $c_i = 2m_i + p_i$, separating a finite residue component from an unbounded scale parameter and constitutes a dynamical isomorphism preserving cycles and convergence behavior.

Within this framework, we prove that consecutive equal values of the parameter $m$ occur only when $m = 0$, establishing ($4, 2, 1$) as the unique cycle. More fundamentally, we show that parameter repetitions are structurally necessary for the bijection to exist. This necessity has immediate consequences: every Collatz sequence must contain at least one repeated parameter value, which precludes divergence. The repeated parameter defines a wormhole, an invariant structure with fixed trajectory that terminates at $m = 0$.

The convergence proof follows from an exhaustive trichotomy: every positive integer belongs to a class determined by its first repeated parameter $m_r$ and, whether $m_r = 0$, $m_r > 0$ irregular or $m_r > 0$ regular, the wormhole structure forces the sequence to reach the unique cycle ($4, 2, 1$).

The framework also enables stopping time prediction through invariant wormhole structures, applicable to approximately two-thirds of positive integers.

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

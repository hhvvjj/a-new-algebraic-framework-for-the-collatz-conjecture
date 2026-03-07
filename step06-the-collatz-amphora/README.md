# The Collatz Amphora

![The Collatz Amphora](https://img.shields.io/badge/Status-Research%20Project-blue) ![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-green) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## What It Does

Comprehensive 3D visualization integrating the entire framework. Shows how all Collatz sequences converge through 42 pre-computed wormhole pathways arranged in an amphora-shaped structure.

1. Computes sequence until reaching a known entry point $e(m_r)$
2. Classifies into taxonomy type (A, B or C) based on position of $M^*$ relative to the pseudocycle
3. Detects regularity (Definition 8.1)
4. Visualizes your sequence path through the amphora with color-coded spheres
5. Shows computational savings from wormhole optimization
6. Demonstrates universal convergence visually

## Live Demo

🔗 <a href="https://hhvvjj.github.io/a-new-algebraic-framework-for-the-collatz-conjecture/step06-the-collatz-amphora/" target="_blank">Launch Tool ↗</a>

## How to Use

### Input Parameters
- **$n$**: Starting positive integer (required)

## What You Get

### Sequence Metrics
- Entry point $m_r$ class membership
- Pseudocycle ends (first and second occurrence of $m_r$)
- Number of elements and total steps $\sigma(n)$
- Computed steps $k$ (pre-wormhole) and saved steps $\tau(m_r)$
- Max Value / $M^*$ (global maximum of Colatz sequence and parameter sequence)
- $m^*$ (invariant local maximum of the pseudocycle. `-` for $S(0)$)
- Taxonomy type (A, B or C), the position of $M^*$ relative to the pseudocycle (Definition 7.3)
- Regularity,  Regular if $n = e(m_r) \cdot 2^k$, Irregular otherwise (Definition 8.1)

### Computational Analysis

For regular elements $n = e(m_r) \cdot 2^k$, the exponent $k = \log_2(n / e(m_r))$ is obtained analytically with no iteration. Combined with the precomputed wormhole length $\tau(m_r)$:

$$\sigma(n) = k + \tau(m_r)$$

This yields **Computed Steps = 0** and **Saved Steps = Total Steps**, 100% efficiency, $O(1)$ complexity.

For irregular elements, $k$ steps are iterated to reach $e(m_r)$, then $\tau(m_r)$ steps are recovered from the precomputed wormhole (Wormhole Algorithm, Section 10.3).

### 3D Interactive Amphora
- 42 wormhole curves forming the amphora structure
- Color-coded spheres for your sequence (see Color Scheme below)
- **Navigation**: Previous/Next buttons to step through sequence values
- **Controls**: Rotate (X/Y/Z axes), zoom (mouse wheel), reset camera
- Your path highlighted as it intersects the wormhole structure

### Visual proof

Every sequence eventually enters one of the known wormholes, guaranteeing convergence to $(4, 2, 1)$. The 42 pre-computed paths represent all classes discovered up to $2^{40}$; any potential new class would simply add another convergent pathway (Theorem 9.5).

Key results visualized:
- **Theorem 6.7** (Distance Invariance): the pseudocycle length $d(m_r)$ is invariant across all $n \in S(m_r)$
- **Theorem 6.9** (Local Maximum Invariance): $m^*$ depends only on $m_r$, not on $n$
- **Definition 7.3** (Taxonomic Types A, B or C): position of $M^*$ relative to the pseudocycle
- **Definition 8.1** (Regularity): $n = e(m_r) \cdot 2^k$
- **Theorem 9.4** (Universal Convergence): every $n \in \mathbb{Z}^+$ converges to $(4, 2, 1)$
- **Section 10** (Total Stopping Time): $\sigma(n) = k + \tau(m_r)$ for any $n \in S(m_r)$

## Citation

If you use this tool in your research, please cite:
```bibtex
@software{hernandez2026thecollatzamphora,
  title = {The Collatz Amphora},
  author = {Hernandez, Javier},
  year = {2026},
  url = {https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture/tree/main/step06-the-collatz-amphora},
  note={Implementation based on research DOI: 10.5281/zenodo.15546925}
}
```

## License

This project is licensed under the terms specified in the [LICENSE](https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture/blob/main/LICENSE) file.

## Author

**Javier Hernandez**  
Email: 271314@pm.me  
GitHub: [@hhvvjj](https://github.com/hhvvjj)

---

[← Back](https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture)

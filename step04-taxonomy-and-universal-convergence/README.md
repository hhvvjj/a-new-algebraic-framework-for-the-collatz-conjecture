# Step 04: Taxonomy and Universal Convergence

![Taxonomy and Universal Convergence](https://img.shields.io/badge/Status-Research%20Project-blue) ![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-green) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## What It Does

Interactive classification tool that analyzes Collatz sequences through their taxonomic structure. For any $n$:

1. Identifies which $S(m_r)$ class it belongs to
2. Determines its taxonomic type (A, B or C) based on the position of global maximum $M^\*$
3. Classifies the class as Regular or Irregular
4. Visualizes the convergence pathway through the wormhole structure
5. Compares with other class members to show invariant properties

All 42 known classes (discovered up to $2^{40}$) are included with pre-defined cases.

**Universal Convergence**: Every positive integer falls into exactly one of three cases:
- **$m_r = 0$**: Reaches terminal cycle ($4, 2, 1$) directly
- **$m_r > 0$ irregular** (Type B+A classes): Wormhole converges via bounded trajectory
- **$m_r > 0$ regular** (Type C+A or Type B+A classes): Entry point reached by divisions by 2, then wormhole

All three cases terminate at $m = 0$, proving universal convergence.

## Live Demo

🔗 <a href="https://hhvvjj.github.io/a-new-algebraic-framework-for-the-collatz-conjecture/step04-taxonomy-and-universal-convergence/" target="_blank">Launch Tool ↗</a>

## How to Use

### Input Parameters
- **$n$**: Starting positive integer (required)

### What You Get

**Classification Summary**:
- Class membership: $S(m_r)$
- Regularity: Regular (multiples of $2^k$) or Irregular
- Taxonomic type: A, B or C
- Key invariants: $m_r$, $m^\*$ (local max), $M^\*$ (global max) and entry point $e(m_r)$

**Visual m-Sequence Diagram**:
- Color-coded parameter evolution
- Highlights pseudocycle region (where $m_r$ repeats)
- Shows global maximum $M^\*$ and local maximum $m^\*$
- Traces wormhole to terminal cycle ($4, 2, 1$)

**Class Examples**:
- Multiple members of the same $S(m_r)$
- Demonstrates $m^\*$ invariance across all members
- Shows structural patterns (regular vs irregular)

## Citation

If you use this tool in your research, please cite:
```bibtex
@software{hernandez2026taxonomyanduniversalconvergence,
  title = {Taxonomy and Universal Convergence},
  author = {Hernandez, Javier},
  year = {2026},
  url = {https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture/tree/main/step04-taxonomy-and-universal-convergence},
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

[← Back to Main](https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture)

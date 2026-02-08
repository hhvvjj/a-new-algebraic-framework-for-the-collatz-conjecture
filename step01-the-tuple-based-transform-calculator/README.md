# Step 01: The Tuple-Based Transform Calculator

![The Tuple-Based Transform Calculator](https://img.shields.io/badge/Status-Research%20Project-blue)
![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-green)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## What It Does

Interactive calculator that transforms Collatz sequences into tuple representations. For any starting value $n$ and parameter $q$, it:

1. Generates the complete Collatz sequence
2. Transforms each consecutive pair $(c_i, c_{i+1})$ into tuples $[p, f(p), m, q]$
3. Shows step-by-step validation of the decomposition $c_i = 2qm + p$
4. Extracts parameter sequences ($p$ and $m$)

## Live Demo

🔗 <a href="https://hhvvjj.github.io/a-new-algebraic-framework-for-the-collatz-conjecture/step01-the-tuple-based-transform-calculator/" target="_blank">Launch Tool ↗</a>

## How to Use

### Input Parameters
- **$n$**: Starting positive integer (required)
- **$q$**: Odd transformation parameter (optional, default = 1)

### What You Get

**Collatz Sequence**: Full trajectory from $n$ to 1

**Transformation Details**: For each pair:
- All candidate $p$ values tested
- Validation checks (congruence + integrality)
- Selected tuple $[p, f(p), m, q]$
- Reconstruction verification

**Parameter Sequences**:
- $\{p_i\}$: residue sequence
- $\{m_i\}$: scale parameter sequence

## Citation

If you use this tool in your research, please cite:
```bibtex
@software{hernandez2026thetuplebasedtransformcalculator,
  title = {The Tuple-Based Transform Calculator},
  author = {Hernandez, Javier},
  year = {2026},
  url = {https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture/tree/main/step01-the-tuple-based-transform-calculator},
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

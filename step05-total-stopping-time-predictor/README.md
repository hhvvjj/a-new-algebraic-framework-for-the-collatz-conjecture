# Step 05: Total Stopping Time Predictor

![Total Stopping Time Predictor](https://img.shields.io/badge/Status-Research%20Project-blue) ![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-green) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## What It Does

Calculates total stopping time $\sigma(n)$ (steps to reach 1) using three algorithms:

1. **Multiplicities**: Instant $O(1)$ calculation for $n = e(m_r) \cdot 2^k$ (100% efficiency). 
2. **Wormholes**: Iterates only until reaching entry point, then uses pre-computed tail (~23-66% efficiency)
3. **Standard**: Full iteration when no optimization applies (~35% of cases). Special case: Pure powers of 2 ($e(m_r)=1, L=0$) are Standard sequences predicted as $\sigma(2^k) = k$

Shows which algorithm was used and computational savings achieved.

## Live Demo

🔗 <a href="https://hhvvjj.github.io/a-new-algebraic-framework-for-the-collatz-conjecture/step05-total-stopping-time-predictor/" target="_blank">Launch Tool ↗</a>

## How to Use

### Input Parameters
- **$n$**: Starting positive integer (required)

### What You Get

**Results Display**:
- **$\sigma(n)$**: Total stopping time
- **Algorithm used**: Which optimization applied
- **Prediction type**:
  - `multiplicity_found`: Instant calculation (0 iterations)
  - `entry_point_found`: Wormhole optimization (partial iteration)
  - `no_entry_point`: Standard algorithm (full iteration)
  - `trivial`: Input was $n = 1$

**Efficiency Metrics**:
- Steps computed vs steps saved
- Computational efficiency percentage
- Entry point reached (if applicable)

**Complexity**: 

| Algorithm | Time Complexity | Space Complexity | Best Case | Worst Case |
|-----------|----------------|------------------|-----------|------------|
| **Standard** | $O(\sigma(n))$ | $O(\sigma(n))$ | $\sigma(n)$ iterations | $\sigma(n)$ iterations |
| **Multiplicities** | $O(1)$ | $O(1)$ | 0 iterations (instant) | Not applicable |
| **Wormholes** | $O(j)$ | $O(\sigma(n))$ | 0 iterations (instant) | $\sigma(n)$ iterations |

## Citation

If you use this tool in your research, please cite:
```bibtex
@software{hernandez2026totalstoppingtimepredictor,
  title = {Total Stopping Time Predictor},
  author = {Hernandez, Javier},
  year = {2026},
  url = {https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture/tree/main/step05-total-stopping-time-predictor},
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

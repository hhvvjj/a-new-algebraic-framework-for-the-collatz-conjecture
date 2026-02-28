# Step 05: Total Stopping Time Predictor

![Total Stopping Time Predictor](https://img.shields.io/badge/Status-Research%20Project-blue) ![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-green) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## What It Does

Calculates total stopping time $\sigma(n)$ (steps to reach 1) using three algorithms:

1. **Multiplicities**: Instant analytical calculation for $n = e(m_r) \cdot 2^k$ (100% efficiency). 
   Special case $S(0)$ for pure powers of 2, where $n = 2^k$, $e(m_r)=1$ and $\tau(m_r)=0$.
2. **Wormholes**: Iterates only until reaching entry point, then uses pre-computed tail. The efficiency decreases with $n$: for $n < 2^{10}$ it is $\approx 69\%$ and for $n < 2^{40}$ it is $\approx18\%$.
3. **Standard**: Full iteration when no optimization applies (0% efficiency).

## Live Demo

🔗 <a href="https://hhvvjj.github.io/a-new-algebraic-framework-for-the-collatz-conjecture/step05-total-stopping-time-predictor/" target="_blank">Launch Tool ↗</a>

## How to Use

### Input Parameters

- **$n$**: Starting positive integer (required)

## What You Get

### Results Display

- **$\sigma(n)$**: Total stopping time
- **Algorithm used**: Which optimization applied
- **Prediction type**:
  - `multiplicity_found`: Instant analytical calculation (0 iterations, includes pure powers of 2)
  - `entry_point_found`: Wormhole optimization (partial iteration)
  - `no_entry_point`: Standard algorithm (full iteration)

### Efficiency Metrics

- Computed steps $k$ vs saved steps $\tau(m_r)$
- Class $S(m_r)$
- Computational efficiency $\eta$

### Complexity Metrics

| Algorithm | Time Complexity | Space Complexity | Best Case | Worst Case |
|-----------|----------------|------------------|-----------|------------|
| **Standard** | $O(\sigma(n))$ | $O(1)$ | $\sigma(n)$ iterations | $\sigma(n)$ iterations |
| **Multiplicities** | $O(1)$ | $O(1)$ | 0 iterations (instant) | $\emptyset$  |
| **Wormholes** | $O(k)$ | $O(1)$ | 0 iterations (instant when $n = e(m_r)$) | $\sigma(n) - \tau(m_r)$ iterations |

### Wormhole Efficiency vs Scale

Wormhole coverage remains stable (~65%) across tested $n < 2^{40}$, but efficiency $\eta = \tau(m_r)/\sigma(n)$ 
deteriorates as $n$ grows: precomputed $\tau(m_r)$ values are fixed while $\sigma(n)$ increases, so the saved fraction 
shrinks progressively. However, since $\tau(m_r) > 0$ always, wormhole prediction never reaches $\eta = 0$.

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

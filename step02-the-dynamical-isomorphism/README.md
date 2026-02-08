# Step 02: The Dynamical Isomorphism

![The Dynamical Isomorphism](https://img.shields.io/badge/Status-Research%20Project-blue) ![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-green) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## What It Does

Interactive visualization demonstrating that the tuple-based transform $\phi_1$ preserves Collatz dynamics. Shows:

1. **Commutative diagram**: How $f$ (Collatz function) and $f_T$ (tuple function) correspond
2. **Bidirectional mapping**: Forward ($\phi$) and inverse ($\phi^{-1}$) transformations
3. **Pseudocycle detection**: Identifies first $m$-parameter repetition
4. **Pruning experiment**: Demonstrates that removing pseudocycles breaks the isomorphism

## Live Demo

🔗 <a href="https://hhvvjj.github.io/a-new-algebraic-framework-for-the-collatz-conjecture/step02-the-dynamical-isomorphism/" target="_blank">Launch Tool ↗</a>

## How to Use

### Input Parameters
- **$n$**: Starting positive integer (required)

### What You Get

**Dual-Track Visualization**:
- **Top row**: Collatz sequence ($c_1, c_2, \ldots$)
- **Bottom row**: Tuple sequence ($\tau_1, \tau_2, \ldots$)

**Arrow System**:
- **Horizontal green arrows**: 
  - $f$ transitions (Collatz space)
  - $f_T$ transitions (tuple space)
- **Vertical arrows**:
  - Solid green ($\phi$): Collatz → Tuple
  - Dashed green ($\phi^{-1}$): Tuple → Collatz

**Interactive Features**:
- **Hover arrows**: See validation equations
- **Click ✂️ on cyan blocks**: Prune/unprune the first pseudocycle
  - **Red arrows appear**: Show where commutativity breaks ($\phi \circ f \neq f_T \circ \phi$)
  - **Demonstrates**: Pseudocycles are structurally necessary for the isomorphism
- **Export**: Save diagram as PNG

**Color Coding**:
- **Blue**: Standard Collatz elements
- **Purple**: Standard tuples
- **Orange**: Cycle $(2, 1, 4)$ where $m=0$
- **Cyan + ✂️**: First pseudocycle (repeated $m$-value)
- **Red arrows**: Invalid transitions (appear after pruning)

## Citation

If you use this tool in your research, please cite:
```bibtex
@software{hernandez2026thedynamicalisomorphism,
  title = {The Dynamical Isomorphism},
  author = {Hernandez, Javier},
  year = {2026},
  url = {https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture/tree/main/step02-the-dynamical-isomorphism},
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

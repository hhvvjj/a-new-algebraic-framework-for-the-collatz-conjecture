# The Collatz Amphora

![The Collatz Amphora](https://img.shields.io/badge/Status-Research%20Project-blue) ![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-green) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## What It Does

Comprehensive 3D visualization integrating the entire framework. Shows how all Collatz sequences converge through 42 pre-computed wormhole pathways arranged in an amphora-shaped structure.

For any $n$ (up to 10 billion):

1. Computes sequence until reaching a known entry point
2. Classifies into taxonomy type (A, B or C)
3. Visualizes your sequence path through the amphora
4. Shows computational savings from wormhole optimization
5. Demonstrates universal convergence visually

## Live Demo

🔗 <a href="https://hhvvjj.github.io/a-new-algebraic-framework-for-the-collatz-conjecture/step06-the-collatz-amphora/" target="_blank">Launch Tool ↗</a>

## How to Use

### Input Parameters
- **$n$**: Starting positive integer (required)

### What You Get

**Sequence Metrics**:
- Total sequence length
- Entry point $m_r$ (class membership)
- Taxonomy type (A, B or C)
- Global maximum value
- Pseudocycle positions (first and second occurrence of $m_r$)

**Computational Analysis**:
- Total stopping time $\sigma(n)$
- Steps computed (pre-wormhole)
- Steps saved (from pre-computed tail)
- Efficiency percentage

**3D Interactive Amphora**:
- 42 wormhole curves forming amphora structure
- Color-coded spheres for your sequence
- **Navigation**: Previous/Next buttons to step through sequence
- **Controls**: Rotate (X/Y/Z), zoom (mouse wheel), reset camera
- Your path highlighted as it intersects the wormhole structure

**Visual proof**: Every sequence eventually enters one of the known wormholes, guaranteeing convergence to ($4, 2, 1$). The 42 pre-computed paths represent all classes discovered up to $2^{40}$; any potential new class would simply add another convergent pathway.

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

[← Back to Main](https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture)

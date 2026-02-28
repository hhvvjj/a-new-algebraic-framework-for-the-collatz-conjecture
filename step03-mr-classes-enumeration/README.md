# Step 03: mr-Classes Enumeration

![mr-Classes Enumeration](https://img.shields.io/badge/Status-Research%20Project-blue) 
![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-green) 
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## What It Does

Interactive enumeration tool that discovers $m_r$ values by processing consecutive integers. For each $n$:

1. Computes the Collatz sequence and tuple transform
2. Identifies the first repeated $m$-value ($m_r$)
3. Records only new $m_r$ values (ignores duplicates)
4. Visualizes the discovery process in real-time

Browser-based tool designed for interactive and conceptual exploration. All 42 known $m_r$ values will appear before $n = 7287$ ($n < 2^{13}$). For large-scale enumeration, use [mr-pairs-finder](https://github.com/hhvvjj/mr-pairs-finder).

## Live Demo

🔗 [Launch Tool ↗](https://hhvvjj.github.io/a-new-algebraic-framework-for-the-collatz-conjecture/step03-mr-classes-enumeration/)

## How to Use

### Input Parameters

- **n**: Starting positive integer (required)
  - Start small (100-1000) to watch how new $m_r$ discoveries slow down rapidly
  - Use 8192 ($2^{13}$) to find all 42 known classes

## What You Get

### Real-Time Discovery Panel

- Current $n$ being processed
- Current $m_r$ value
- Total unique $m_r$ classes found
- Progress bar

### Visual Grid

- Card for each discovered $m_r$ class
- **Hover**: See first $n$ where this $m_r$ appeared
- **Animation**: Cards flash when first discovered
- Auto-organized responsive layout

## Citation

If you use this tool in your research, please cite:
```bibtex
@software{hernandez2026mrclassesenumeration,
  title = {mr-Classes Enumeration},
  author = {Hernandez, Javier},
  year = {2026},
  url = {https://github.com/hhvvjj/a-new-algebraic-framework-for-the-collatz-conjecture/tree/main/step03-mr-classes-enumeration},
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

# EMDA Holographic QCP: Supplemental Computational Materials

[![arXiv](https://img.shields.io/badge/arXiv-2507.07899-b31b1b.svg)](https://arxiv.org/abs/2507.07899)
[![Mathematica](https://img.shields.io/badge/Mathematica-12.0+-orange.svg)](https://www.wolfram.com/mathematica/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626.svg)](https://jupyter.org/)

This repository contains the complete computational pipeline for "Capturing quantum phase transition in the ultraviolet region by holography".

## Table of Contents
- [🎯 Project Overview](#-project-overview)
- [📁 Repository Structure](#-repository-structure)  
- [📊 Key Physical Results](#-key-physical-results)
- [🔬 Computational Methodology](#-computational-methodology)
- [🚀 Quick Start Guide](#-quick-start-guide)
- [📈 Physical Context & Results](#-physical-context--results)
- [🔧 Technical Details](#-technical-details)
- [📝 Citation & References](#-citation--references)
- [🤝 Contributing & Open Source](#-contributing--open-source)
- [❓ Frequently Asked Questions](#-frequently-asked-questions)
- [🔍 Validation & Quality Assurance](#-validation--quality-assurance)

## 🎯 Project Overview

**Einstein-Maxwell-Dilaton-Axion (EMDA) Holographic Analysis**

- **Theoretical framework**: Study of quantum phase transitions using holographic correspondence (AdS/CFT)
- **Novel approach**: UV observables encodes the information of the quantum criticality.
- **Physical system**: 4D bulk gravity theory with fields $\{U, V_1, V_2, a, \varphi\}$ corresponding to 3D boundary field theory
- **Key insight**: High-energy (UV) physics at the AdS boundary ($z \to 0$) provides clearer quantum critical signatures than low-energy (IR) physics near the horizon ($z \to 1$)

## 📁 Repository Structure

```
arXiv_supplemental_notebooks/
├── README.md                              # This file - comprehensive project overview
├── data/                                  # Essential computational data files
│   ├── README.md                         # Data file documentation  
│   ├── eom                               # Equations of motion for 5 bulk fields 
│   ├── BG                                # Background solutions {Tlist, klist} 
│   ├── dBG                               # Perturbed background solutions
│   └── deomall                           # Complete EOM with perturbations
├── Analytical_Boundary_Expansions.ipynb  # Systematic boundary analysis (Appendix D)
├── UV_Observables_and_Validation.ipynb   # Physical observables & numerical validation
├── boundary_solutions.mx                 # [Legacy] Pre-computed Mathematica boundary data
└── UV_observables_results.mx             # [Legacy] Stored UV observable numerical results
```

## 📊 Key Physical Results

### UV Observables for Quantum Phase Transition Diagnosis
1. In the UV region, **$S$**: Entanglement entropy ($S = V_1[1]$) - shows extrema at critical points
2. In the UV region, **$I = E_W = U[3] - V_1[3] - 2V_2[3]$**: Information measure- quantum critical signatures  
3. **$\sigma_{AC}$**: High-frequency conductivity ($\omega \gg T$) - UV regime response function

### Critical Parameters
- **Chemical potential**: $\mu \approx 3.44, 3.33, 3.21$ (3 MachinePrecision)
- **Momentum values**: $k \in \{147/395, 339/790, 192/395\}$ 
- **Temperature relation**: $T = \frac{12-\mu^2}{16\pi\mu}$ 

## 🔬 Computational Methodology

### Mathematical Framework
- **Series expansions**: Each bulk field has the form $f(z) = f_0 + f_1 z + f_2 z^2 + f_3 z^3 + \mathcal{O}(z^4)$
- **Bulk fields**: $\{U[z], V_1[z], V_2[z], a[z], \varphi[z]\}$ where:
  - $U, V_1, V_2$: Metric components
  - $a$: Axion field  
  - $\varphi$: Dilaton field
- **Boundary conditions**: $\{U[0] \to 1, V_1[0] \to 1, V_2[0] \to 1, a[0] \to 1\}$

### Boundary Expansion Analysis
- **Systematic approach**: $z \to 0$ series expansions for bulk fields $\{U, V_1, V_2, a, \varphi\}$ 
- **Order-by-order solving**: Incorporating constraints according to equations of motion from $z^{-1}$ through $z^2$ terms
- **Boundary conditions**: $\{U[0] \to 1, V_1[0] \to 1, V_2[0] \to 1, a[0] \to 1\}$

### Holographic Framework  
- **AdS coordinate**: $z \in [0,1]$ (boundary at $z=0$, horizon at $z=1$)
- **Metric ansatz**: $P = U(1-z)(1+z+z^2-\mu^2 z^3/4)$
- **Field equations**: Pre-computed EMDA equations of motion from 4D action
- **UV/IR correspondence**: $z \to 0$ (UV/high-energy) ↔ $z \to 1$ (IR/low-energy)

## 🚀 Quick Start Guide

### Prerequisites & System Requirements
- **Wolfram Mathematica 12.0+** (primary computational environment)
- **Jupyter Notebook support** for Wolfram Language kernels (optional but recommended)
- **System requirements**:
  - Memory: ≥8GB RAM (16GB+ recommended for high-precision calculations)
  - Storage: ~100GB for full raw dataset
  - CPU: Multi-core processor recommended for faster symbolic computation
- **Working precision**: Calculations maintain $\geq$ 3 MachinePrecision

### Installation & Setup

1. **Download repository**:
   
   ```bash
   git clone https://github.com/physicsuniverse/EMDA-UV-QPT
   cd EMDA-UV-QPT
   ```
   
2. **Verify file structure**:
   
   ```bash
   ls -la  # Should show data/, *.ipynb files, README.md
   ```
   
3. **Mathematica setup**:
   
   ```mathematica
   (* Set working directory to repository root *)
   SetDirectory[NotebookDirectory[]];
   (* Verify data files exist *)
   FileExistsQ["data/eom"] && FileExistsQ["data/BG"]
   ```

## 📝 Citation & References

If you use this computational framework, please cite:

```bibtex
@article{EMDA_UV_2025,
  title={Capturing quantum phase transition in the ultraviolet region by holography},
  author={Cheng, Fang-Jing and Yang, Zhe and Ling, Yi and Wu, Jian-Pin and Cao, Zhou-Jian and Liu, Peng},
  journal={arXiv preprint arXiv:2507.07899},
  year={2025}
}
```

For full documentation including detailed analysis, troubleshooting, and additional examples, see the complete project documentation.
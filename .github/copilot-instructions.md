# Hydrological Twin Documentation Repository

This repository contains the comprehensive **White Book** documentation for **Hydrological Twin** (HydrologicalTwin), a digital twin framework for hydrological systems.

## Overview of Hydrological Twin

Hydrological Twin establishes a new epistemic regime for hydrological modelling. It replaces loosely coupled numerical experiments by synchronized, stateful, traceable and reproducible anchored estimations. It is multi-dataset and multi-model by construction, natively compatible with Bayesian and AI methodologies, and structurally committed to audit given a native open-source design.

By isolating physical model parameterizations as the only potentially private component, Hydrological Twin reconciles scientific openness with operational and economic constraints. In doing so, it provides a rigorous and future-proof foundation for digital hydrology, at the intersection of physics, data science, and distributed versioned infrastructures.

Hydrological Twin is a digital twin of hydrological systems implemented as a Python package following a monolithic architectural approach. It is conceived as a persistent artefact evolving in the ontological **space-state** continuum (not "space-time").

Each Hydrological Twin instance is linked to a complex ecosystem of Git repositories encompassing databases, models, and configuration artefacts, each of them being carefully registered and versioned in terms of space-state.

## Core Concepts

### Architecture

One instance of a Hydrological Twin is composed of **six functional layers**:

1. **Model Layer** - process-based physical models, software, spatial and temporal supports (grid)
2. **Data Layer** - observations, reanalyses, forcings, inner parameters (private)
3. **Estimation Layer** - comparison, filtering, Bayesian inference
4. **Analysis Layer** - temporal and spatial transformations, extraction (on demand)
5. **Cartographic Layer** - visualization and spatial representation
6. **Git-Synchronized Registry** - identity, provenance, versioning

### Key Components

- **GitSynchroRecord**: Captures repository provenance (commit, branch, tag/describe, dirty state, remote URL) and computes reproducible version fingerprints through deterministic Git provenance and environment fingerprinting
- **HydroTwin**: Top-level orchestrator containing compartments, twin-wide layers
- **Compartment**: Sub-unit within a HydroTwin
- **Simulation**: Numerical model execution results
- **NumPy Hypercube**: Data storage structure
- **Universal Git Registry**: Immutable, hash-chained ledger of validation events

### Access Control

Hydrological Twin implements a dual-access paradigm:
- **Public users**: Access aggregated visualizations and statistical summaries through rendering layer (no authentication)
- **Private-key holders**: Unlock raw data access, parameter modification, simulation execution, and advanced calibration workflows (authentication required)

### Backend Integration

HydrologicalTwin serves as the monolithic backend infrastructure for **CaWaQS-Viz** (a QGIS plugin), providing:
- Unified data access through consistent API
- Space-state traceability with GitSynchroRecord fingerprints
- Performance optimization via centralized data management
- Composable API primitives for visualization and analysis

## Repository Structure

This is a **LaTeX documentation project** structured as follows:

```
/
├── .github/                    # GitHub configuration
│   └── copilot-instructions.md # This file
├── MASTER.tex                  # Main LaTeX document (entry point)
├── Setup/                      # LaTeX configuration
│   ├── Packages.tex            # Package imports
│   ├── Shortcuts.tex           # Custom commands and shortcuts
│   └── Messages_pkg/           # Package messages
├── Backmatter/                 # Front and back matter
│   ├── Cover.tex               # Document cover
│   ├── Abstract.tex            # Comprehensive abstract
│   ├── Structure.tex           # Repository structure docs
│   └── ...
├── Mainmatter/                 # Main content chapters
│   ├── 1_HT_Foundations_and_scope.tex        # Chapter 1: Foundations
│   ├── 2_HT_Architectural_decomposition.tex  # Chapter 2: Architecture
│   ├── 2b_HT_Use_case.tex                    # Chapter 2b: Use Cases
│   ├── 3_HT_Technical_Specification.tex      # Chapter 3: Technical Spec
│   ├── 4_HT_UserGuide.tex                    # Chapter 4: User Guide
│   ├── 5_HT_Proto_HydroTwin_Alpha.tex        # Chapter 5: Proto Implementation
│   └── DevelopmentLog.tex                    # Current Development
├── Bibliography/               # References
│   └── References.tex
├── Figures/                    # Images and logos
│   ├── Logo.png
│   ├── LogoHT.png
│   └── ...
└── .gitignore                  # Git ignore rules
```

### Document Structure

**MASTER.tex** is the main entry point that:
- Defines document version (currently 3.50)
- Includes Setup files (Packages, Shortcuts)
- Contains front matter (Cover, Abstract, TOC, LOF, LOT, Listings)
- Organizes content into two parts:
  - **Part I: Ontology** (Chapters 1, 2, 2b)
  - **Part II: HydrologicalTwin as Backend of CaWaQS-Viz** (DevelopmentLog, Chapter 5)
- Includes back matter (Structure, References)

## Key Terminology and Conventions

### Naming Standards

- **Prose**: Use "Hydrological Twin" (with space)
- **Code references**: Use `HydrologicalTwin` (no space) or `\hydrot` LaTeX command
- **Space-state**: Use "space-state" (single hyphen), NOT "space-time" or "space--state" (the double hyphen renders as en-dash)
- **Identity**: Use "GitSynchroRecord" (not "IdCard") for identity and traceability

### LaTeX Commands

Key shortcuts defined in `Setup/Shortcuts.tex`:
- `\hydrot` → Renders as HydrologicalTwin (code font)
- `\cw` → CaWaQS
- `\cwv` → CaWaQS-Viz
- `\cwl` → CaWaQS-Loing
- `\cws` → CaWaQS-Seine
- `\script{text}` → Code/keyword formatting
- `\gui{text}` → GUI element formatting
- `\ie` → i.e.
- `\eg` → e.g.
- `\via` → via

### Generic Terminology

Use **generic terms** instead of specific tool names:
- ✅ "frequency-domain calibration" (not "HYMIT")
- ✅ "time-domain Bayesian inference" (not "DREAM")
- ✅ "time-domain forward model" (not "NIHM")
- ✅ `run_bayesian_inference()` method name (not `run_dream()`)
- ✅ `run_frequency_calibration()` method name (not `run_hymit()`)
- ✅ `'bayesian_inference'` algorithm identifier (not `'dream'`)
- ✅ `'multi_stage_bayesian'` algorithm identifier (not `'multi_stage_dream'`)

### Documentation Style

This is a formal **White Book** following academic style:
- Structured sections with clear hierarchy
- Formal language and technical precision
- Comprehensive technical descriptions
- Use `\chapter`, `\section`, `\subsection`, `\subsubsection`
- Custom headers with `\fancyhead` for each chapter
- No informal notes or TODO lists in final text
- Use `\phantomsection`, `\addstarredchapter` for unnumbered chapters

## Content Organization

### Part I: Ontology

1. **Chapter 1 - Foundations and Transformative Scope**: Core concepts, architectural principles, foundational transformation from physically-based models to physically-based estimation
2. **Chapter 2 - Architectural Decomposition**: Layered architecture, core object hierarchy, inter-layer interactions, access control
3. **Chapter 2b - Use Cases**: Organized by access level (public/private), demonstrating reproducible workflows

### Part II: HydrologicalTwin as Backend of CaWaQS-Viz

1. **DevelopmentLog (Current Development)**: Backend integration with CaWaQS-Viz, API design, singleton pattern, performance optimizations
2. **Chapter 5 - Proto HydroTwin Alpha**: Simplified public-use implementation (α.x series) without authentication or calibration, for CaWaQS-Viz

### Key Features Documented

- **Multi-stage calibration workflow**: (1) frequency-domain calibration, (2) temporal recharge optimization, (3) hydrogeological reference fitting, (4) Bayesian inference with adaptive meshing
- **Private-key authentication**: Required for operations that modify parameters or execute simulations
- **Immutable registry**: All validation events are append-only and hash-chained
- **Deterministic provenance**: All objects reproducible through Git commit hashes and dependency locks
- **Self-fitting method**: Native calibration operation requiring private-key authentication

## Development Guidelines

### Working with LaTeX

1. **Main entry point**: Always compile from `MASTER.tex`
2. **Chapter inclusion**: Chapters are included via `\include{Mainmatter/filename}` (no .tex extension in include)
3. **Package management**: Add packages to `Setup/Packages.tex`
4. **Custom commands**: Add shortcuts to `Setup/Shortcuts.tex`
5. **Figures**: Place in `Figures/` directory, reference with `\includegraphics`

### Editing Guidelines

- Maintain formal academic style throughout
- Preserve existing LaTeX structure and commands
- Use existing shortcuts (`\hydrot`, `\cwv`, etc.) consistently
- Follow hyphenation standards: use "space-state" with single hyphen, never "space--state" with double hyphen
- Include citations and cross-references where appropriate
- Use `\label{}` and `\ref{}` for internal references

### Version Control

- Document version is defined in MASTER.tex: `\newcommand{\version}{3.50}`
- CaWaQS version in shortcuts: `\newcommand{\cversion}{3.55}`
- All changes tracked via Git with GitSynchroRecord philosophy
- .gitignore excludes: `*.bak` files

## Building the Documentation

This is a LaTeX book project. To build:

```bash
# Standard LaTeX compilation
pdflatex MASTER.tex
pdflatex MASTER.tex  # Run twice for references
```

The output will be `MASTER.pdf` containing the complete White Book.

## Related Projects

- **HydrologicalTwin** (Python package): The actual implementation of the digital twin framework
- **CaWaQS**: Hydrological modeling platform
- **CaWaQS-Viz**: QGIS plugin using HydrologicalTwin as backend
- Various Git repositories for: databases, models, configuration artifacts

## Key Architectural Principles

1. **Deterministic provenance**: All objects reproducible through Git commit hashes
2. **Layer symmetry**: Estimation, analysis, and cartographic layers exist at both twin and compartment levels
3. **Strict separation of concerns**: Model, Data, and Numerical storage are distinct but synchronized
4. **Append-only registry**: Validation events are immutable and hash-chained
5. **Priority of reproducibility over convenience**

## Memory for Future Sessions

This repository is the **documentation** for Hydrological Twin, not the implementation. The implementation is a separate Python package. This repo contains LaTeX source for a comprehensive academic White Book describing the architecture, use cases, and technical specifications of the HydrologicalTwin framework.

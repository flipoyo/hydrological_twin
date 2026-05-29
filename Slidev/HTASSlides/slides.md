---
# try also 'default' to start simple
#theme: default
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /figures/terre_vue_du_ciel.jpg
# some information about your slides (markdown enabled)
title: Hydrological Twin
info: |
  ## Slidev Starter Template
  Concepts and use cases

  Learn more at [Sli.dev](https://sli.dev)
# apply UnoCSS classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable Comark Syntax: https://comark.dev/syntax/markdown
comark: true
# duration of the presentation
duration: 35min
---

# Hydrological Twin

Distributed Scientific Infrastructure for Water Resources

Reproducible framework EPL2.0 for environmental data integration, multi-scale   hydrological simulation, distributed provenance and decision support.

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-xl">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="slidev-icon-btn">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: default
background: white
class: text-slate-800
---

---
transition: fade-out
---

# A scientific, model agnostic, multi-scale, digital twin for water resources

<div class="text-right text-xl">
Observe → Analyze → Predict → Decide
</div>

<center>

<img
  src="./figures/HTASOverview.png"
  class="w-75%"
/>

</center>

<!--HydrologicalTwin transforms heterogeneous environmental datasets into actionable knowledge for sustainable water resources management.-->

---

# Hydrological Twin

<div class="grid grid-cols-[28%_72%] gap-6 h-[78%]">

<div class="flex flex-col justify-center">

<div class="text-xl text-sky-700 font-semibold mb-6">

A scientific, model-agnostic, multi-scale digital twin for water resources

</div>

<div class="text-base text-slate-600 leading-relaxed">

• Hydrosystems

• Multi-Scale

• HPC

• Traceability

• Sovereignty

• Decision Support

</div>

</div>

<div class="flex justify-end items-center h-full">

<img
  src="./figures/InfographieHydrologicalTwin.png"
  class="h-full max-h-[650px] object-contain"
/>

</div>

</div>



---

# Pipeline

<div class="grid grid-cols-[45%_55%] gap-8 items-center">

<div>

## Model-Agnostic Preprocessing

```mermaid
flowchart TD

A[CawSAR]
B[HydroWatershed]
C[QGridder]

A --> D[Standardized Objects]
B --> D
C --> D
```
</div>

<div class="flex justify-center mt-4">

<img
  src="./figures/multiEchelle.png"
  class="w-62%"
/>

</div>


</div>

## CaWaQS Orchestration Loop

```mermaid
flowchart LR

D[Standardized Objects]
F[HydrologicalTwin]
E[CawFormatter]
G[CawOrchestrator]
C[CaWaQS Core]

D --> F
F --> E
E --> G
G --> C
C --> F

V[CaWaQS-ViZ]

F -. HTTPS API .-> V

classDef twin fill:#005b96,color:white,stroke:#005b96
classDef gui fill:#d9edf7,stroke:#31708f
class F twin
class V gui
```

---

# ComplexGitSync

<div class="grid grid-cols-[65%_35%] gap-8 items-center">

<div>

```mermaid
flowchart LR

CGS[ComplexGitSync]

CGS <--> P[GitTree]

P --> R1[Parent]
P --> R2[Parent]

R1 --> R11[Leaf]
R1 --> R12[Leaf]
R1 --> R13[Leaf]

R2 --> R21[Leaf]
R2 --> R22[Parent]

R22 --> R221[Repo]
R22 --> R222[Repo]

classDef cgs fill:#005b96,color:white,stroke:#005b96
class CGS cgs
```

</div>

<div>

### Ensures

- Provenance
- Synchronization
- Traceability
- Versioning
- Reproducibility

</div>

</div>

---

# Distributed Infrastructure

```mermaid
flowchart LR

CS[Compute Server]
DS[Data Server]
GR[Distributed Registry]

CS <--> DS
DS <--> GR
```

### Compute Server

* Executes simulations
* Hosts HTAS services

### Data Server

* Stores datasets
* Stores metadata

### Distributed Registry

* Provenance
* Simulation outputs
* Object addresses
* Version history

---

# Service Layer

```mermaid
flowchart LR

HTAS --> API[Python / HTTPS API]

API --> QGIS[CaWaQS-ViZ]

API --> APPS[External Applications]

API --> AI[Future AI Agents]
```

---

# Typical Use Cases

### Multi-scale Water Allocation

Optimize resource sharing under competing demands over various spatial and temporal scales.

### Drought Management

Anticipate shortages and assess mitigation strategies.

### Flood Risk Assessment

Simulate extreme hydrological events for basin wide planning

### Groundwater Management

Evaluate sustainability of abstractions.

### Climate Adaptation

Explore long-term hydroclimatic scenarios.

---

# Core Principles

| Principle        | Description                          |
| ---------------- | ------------------------------------ |
| Determinism      | Reproducible scientific workflows    |
| Provenance       | Full lineage of data and simulations |
| Modularity       | Separation of concerns               |
| Interoperability | Open APIs                            |
| Scalability      | HPC and distributed execution        |
| Transparency     | Auditable results                    |

---

# Expected Outcomes

<div class="grid grid-cols-3 gap-8 mt-12">

<div class="text-center">

## 💧

### Water Security

</div>

<div class="text-center">

## 🌍

### Climate Adaptation

</div>

<div class="text-center">

## 🌱

### Ecosystem Preservation

</div>

<div class="text-center">

## 📈

### Risk Anticipation

</div>

<div class="text-center">

## ⚖️

### Sustainable Allocation

</div>

<div class="text-center">

## 🏛️

### Territorial Resilience

</div>

</div>

<br>

<div class="text-center text-2xl text-blue-700">

From environmental data to actionable knowledge

</div>

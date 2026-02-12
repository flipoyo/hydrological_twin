# Hydrological Twin


Hydrodrological Twinestablishes a new epistemic regime for hydrological modelling. It replaces loosely coupled numerical experiments by synchronized, stateful, traceable and reproductible anchored estimations. It is multi--dataset and multi--model by construction, natively compatible with Bayesian and AI methodologies, and structurally committed to audit given a native open--source design.

By isolating physical model parameterizations as the only potentially private component, Hydrodrological Twinreconciles scientific openness with operational and economic constraints. In doing so, it provides a rigorous and future-proof foundation for digital hydrology, at the intersection of physics, data science, and distributed versioned infrastructures.

Hydrodrological Twinis a digital twin of hydrological systems implemented as a Python package following a monolithic architectural approach. It is conceived as a persistent artefact evolving in the ontological space--state continuum.

Each Hydrodrological Twininstance is linked to a complex ecosystem of Git repositories encompassing databases, models, and configuration artefacts, each of them being carefully registered and versioned in terms of space--state.

At its core, Hydrodrological Twinrelies on a small number of conceptual classes that formalize identity, versioning, spatial supports, observations, simulations, and model configurations. In particular, identity and traceability are enforced through a \texttt{GitSynchroRecord} that captures repository provenance (commit, branch, tag/describe, dirty state, and remote URL) and uses it to compute a reproducible version fingerprint through deterministic Git provenance and environment fingerprinting.

This Repo is the documentation of Hydrological Twin

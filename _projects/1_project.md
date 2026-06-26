---
layout: page
title: Alchemical ML-IAM for Polymer-Grafted Nanoparticles
description: A generalized machine-learning framework for developing alchemical many-body interaction models that capture how effective interactions between polymer-grafted nanoparticles depend on key physicochemical attributes, integrated with digital alchemy inverse design.
img: assets/img/publication_preview/smd.gif
importance: 1
category: research
---

Polymer-grafted nanoparticles (PGNs) are a versatile class of nanomaterials whose self-assembly behavior depends on a rich set of physicochemical attributes — graft density, polymer chain length, core size, and more. Predicting how these attributes influence effective interactions is essential for rational nanomaterial design but remains computationally challenging with traditional simulation approaches.

In this project, I extended the Chebyshev Interaction Model for Efficient Simulation (ChIMES) — a machine-learned interaction model (ML-IAM) — to capture how many-body effective interactions between PGNs depend on key design parameters. By treating these parameters as alchemical variables in the model, we can efficiently sweep across design space without re-running expensive all-atom simulations for each new parameter combination.

Key contributions:
- Extended ChIMES to describe attribute-dependent effective interactions between PGNs
- Integrated the alchemical ML-IAM with digital alchemy inverse design for efficient optimization of particle attributes toward target self-assembled structures
- Developed an adaptive parallel meshing algorithm for training data generation that reduces required data volume by ~100x

**Publication:** Zhang, M. Y.\*, Lee, S. K. A.\*, Glotzer, S., and Lindsey, R. *J. Chem. Theory Comput.* 2025. [DOI: 10.1021/acs.jctc.5c00901](https://doi.org/10.1021/acs.jctc.5c00901)

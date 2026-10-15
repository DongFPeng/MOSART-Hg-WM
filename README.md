# MOSART-Hg-WM

MOSART-Hg-WM is a coupled modeling framework developed within CESM2.1.3 for simulating mercury transport across terrestrial and riverine systems, including mercury delivery from land to rivers, in-stream transport, retention, and human perturbations.

The repository integrates modified CLM and MOSART components through Git submodules, allowing the land and river mercury modules to retain their independent development histories while being assembled within a unified CESM framework.

## Important Notice

**This repository is provided solely for peer review and scientific evaluation.**

The source code, model modifications, configuration information, unpublished implementation details, documentation, figures, and other materials contained in this repository are not released for unrestricted public reuse.

Any reuse, redistribution, adaptation, incorporation into other models or software, derivative development, or use of unpublished materials from this repository requires **prior written permission** from **Dong Peng or the corresponding author(s)** of the associated work.

If you wish to reuse or reference repository-specific materials or unpublished implementation details, please contact the authors before doing so.

These restrictions apply to the authors' original modifications and materials in this repository and do not supersede the licenses or terms governing upstream CESM, CLM, MOSART, or other third-party software.

## Repository structure

```text
MOSART-Hg-WM/
└── components/
    ├── clm/       -> CLM-Hg
    └── mosart/    -> MOSART-Hg
```

The two major components are maintained as independent Git repositories:

- **CLM-Hg**: terrestrial mercury processes and land-to-river mercury inputs
- **MOSART-Hg**: riverine mercury transport, transformation, retention, and routing

This repository records the specific versions of these two components used in the coupled MOSART-Hg-WM framework.

## Model framework

MOSART-Hg-WM extends the CESM2.1.3 modeling system by coupling terrestrial mercury cycling with river transport processes.

The framework is designed to represent:

- terrestrial mercury storage and mobilization
- mercury transport associated with runoff and soil erosion
- delivery of mercury from land to river networks
- particulate and dissolved mercury transport in rivers
- riverine mercury retention and release
- reservoir regulation and mercury trapping
- anthropogenic mercury inputs
- historical and future changes in riverine mercury export

The framework can be used to investigate how climate change, land-use change, reservoir regulation, and anthropogenic emissions and releases alter mercury transport from land to ocean.

## Git submodules

This repository uses Git submodules for the CLM-Hg and MOSART-Hg components.

Clone the repository together with its submodules:

```bash
git clone --recurse-submodules git@github.com:DongFPeng/MOSART-Hg-WM.git
```

If the repository has already been cloned without submodules:

```bash
git submodule update --init --recursive
```

To inspect the component versions used by the current model configuration:

```bash
git submodule status
```

## Updating component versions

Development of CLM-Hg and MOSART-Hg should normally be performed within their respective repositories.

After updating either component, record the new submodule commit in MOSART-Hg-WM:

```bash
git status
git add components/clm components/mosart
git commit -m "Update CLM-Hg and MOSART-Hg versions"
git push
```

The outer MOSART-Hg-WM repository therefore records the exact combination of CLM-Hg and MOSART-Hg used for each coupled model configuration.

## Model base

```text
CESM version: 2.1.3
Land model:   CLM5
River model:  MOSART
```

Additional modifications include mercury-specific terrestrial and riverine processes and water-management-related mercury transport mechanisms.

## Typical applications

MOSART-Hg-WM is intended for studies of:

- global riverine mercury budgets
- land-to-river mercury transfer
- mercury transport under changing climate
- soil erosion effects on particulate mercury export
- reservoir and dam impacts on mercury transport
- historical reconstruction of riverine mercury fluxes
- future mercury projections under emission and climate scenarios
- source attribution of anthropogenic and legacy mercury

## Publications

The development and application of MOSART-Hg-WM are described in the following studies:

1. **Peng, D. et al. (2025). Human perturbations to mercury in global rivers. _Science Advances_, 11, eadw0471.**  
   DOI: `10.1126/sciadv.adw0471`

2. **Peng, D. et al. (2026). Tracing Mercury from Land to River: Global Sources, Retention, and Implications for Sustainability. _Environmental Science & Technology_, 60, 21885–21900.**  
   DOI: `10.1021/acs.est.6c03367`

Additional publications and research outputs are available through the author's ResearchGate profile.

## Data and model input

Large CESM input datasets, NetCDF forcing files, model outputs, restart files, and temporary processing files are not maintained in this repository.

Users should obtain the required CESM input datasets separately and configure local paths according to their computing environment.

## License and use restrictions

This repository contains modifications based on CESM, CLM, and MOSART. Use of the underlying model components remains subject to their respective licenses and terms of use.

The original modifications, documentation, configurations, and unpublished materials developed by the authors are provided for **review and evaluation purposes only** unless explicit written permission for further use has been granted.

Permission requests should be directed to Dong Peng or the corresponding author(s) of the associated publication.

## Contact

**Dong Peng**  
Email: dongpeng506@gmail.com  
ResearchGate: **Dong Peng (Dong-Peng-4)** （https://www.researchgate.net/profile/Dong-Peng-4)

For questions regarding MOSART-Hg-WM, requests for reuse, or permission to use repository-specific materials, please contact the authors before use.

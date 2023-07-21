---
title: "Storey Loss Function Generator"
excerpt: "Generate storey loss functions for simplified loss assessment and design of buildings"
collection: software
---

Performance-based earthquake engineering (PBEE) has become an important framework for quantifying seismic losses. However, due to its computationally expensive implementation through a typically detailed component-based approach (i.e. FEMA P-58), it has primarily been used within academic research and specific studies.

A simplified alternative more desirable for practitioners is based on storey loss functions (SLFs), which estimate a building’s expected monetary loss per storey due to seismic demand. These simplified SLFs reduce the data required compared to a detailed study, which is especially true at a design stage, where detailed component information is likely yet to be defined. A Python-based toolbox (illustrated below) for the development of user-specific and customisable SLFs for use within seismic design and assessment of buildings has been proposed in Shahnazaryan et al. (2020).

It outlines the implementation procedure alongside a comparative demonstration of its application where dependency and correlation of damage states between different components are considered. Finally, a comparison of SLF-based and component-based loss estimation approaches is carried out through the application to a real case-study school building. The agreement and consistency of the attained loss metrics demonstrate the quality and ease of the SLF-based approach in achieving accurate results for a more expedite assessment of building performance.

<img src="/images/slfs.JPG"  width="500px">

For the latest version of the tool, please visit the Github page [here](https://github.com/davitshahnazaryan3/SLFGenerator).


## Relevant references:
1. Shahnazaryan D, **O’Reilly GJ**, Monteiro R. Story loss functions for seismic design and assessment: Development of tools and application. Earthquake Spectra 2021; 37(4): 2813–2839. DOI: 10.1177/87552930211023523. [[PDF](http://gerardjoreilly.github.io/files/Journal/J21-2021.pdf)][[Link](https://journals.sagepub.com/doi/10.1177/87552930211023523)]
1. Shahnazaryan D, **O’Reilly GJ**, Monteiro R. Development of a Python-Based Storey Loss Function Generator. COMPDYN 2021 - 8th International Conference on Computational Methods in Structural Dynamics and Earthquake Engineering, 2021. DOI: 10.7712/120121.8659.18567. [[PDF](http://gerardjoreilly.github.io/files/Conference/C18-2021.pdf)]

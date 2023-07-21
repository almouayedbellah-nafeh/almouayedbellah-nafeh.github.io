---
title: "Non-Linear Response Estimation for Infilled RC Frames"
excerpt: "Estimate the dynamic response non-ductile RC frames with masonry infills using just the results of pushover analysis"
collection: software
---

## Overview
Different methods exist to estimate the dynamic behaviour of a structure with knowledge of just its static behaviour. They relate a structure’s static pushover analysis (SPO) results to non-linear dynamic analysis using a library of empirical fitting coefficients for the different branches of the idealised SPO backbone, as shown below. It permits the quantification of structural performance up to structural collapse as a function of seismic intensity in a simple and efficient manner.

<img src="/images/infilled-rc.jpg" style="width:800px">

They has been developed for ductile structures that can be represented via a SPO backbone with a ductile post-yield hardening followed by a post-peak degradation, as shown above. This behaviour is quite representative of ductile RC and steel moment-resisting frames and has resulted in the tool being widely adopted. However, considering the peculiar behaviour of infilled RC frames (below) where a high strength and stiffness contribution from the infill panels is initially present. Upon the local collapse of a storey's infill panels, and the formation of a weak storey mechanism (below), the strength and stiffness properties of the frame change significantly, which has a notable impact in the seismic response up to collapse.

<img src="/images/spo2ida.jpg" style="width:500px;">

## Development of an Unbiased Response Estimation Tool (RET) for Infilled RC Frames
The assessment of seismic performance, within modern performance-based earthquake engineering (PBEE), requires an adequate quantification of the exceedance of a structural performance level typically related to a structural demand level, quantified via an engineering demand parameter (EDP).  Fragility curves are typically used for this purpose as they represent the interface between the intensity of ground-shaking described by an intensity measure (IM) and the probability that a damage level, or EDP threshold, is exceeded. Analytical fragility functions require the numerical modelling of a case-study structure, ground-motion selection and extensive non-linear dynamic analyses. These elements of performance assessment can be demanding in terms of computational effort, specifically related to the time required for identifying suitable ground motion records and conducting non-linear dynamic analysis. To overcome this, simplified tools for the assessment of RC frame structures have provided an efficient alternative to implement in practice while offering a trade-off between simplicity and accuracy.

Amongst the methodologies mentioned, only the empirical relationships developed by [Dolšek and Fajfar [2004]](https://onlinelibrary.wiley.com/doi/10.1002/eqe.410) apply to infilled RC structures to our knowledge. However, their procedure was based on the spectral acceleration at the fundamental period of the structure, which has been shown to be a poor intensity measure for non-ductile infilled RC frame structures [[O'Reilly, 2021]](https://link.springer.com/article/10.1007/s10518-021-01071-7). Moreover, their analysis used an equivalent SDOF model with infinite ductility capacity, meaning the median collapse intensity of the structural system is likely to be overestimated, as shown recently by [Nafeh et al. [2020]](https://link.springer.com/article/10.1007/s10518-019-00758-2). These simplified approaches utilise the so-called $R-\mu-T$ relationships for a direct estimation of the seismic demand on the non-linear systems; $R$ represents the strength ratio, or the strength reduction factor, relating the elastic spectral acceleration demand to the spectral acceleration which causes yielding of the structural system. In EC8, for example, it is encountered as part of the behaviour factor accounting for the deformation and energy dissipation capacity of the structural system; $T$ is the initial period and $\mu$ denotes ductility demand.

However, tools such as SPO2IDA and other $R-\mu-T$ relationships typically utilise extensive results of incremental dynamic analyses (IDA) on single-degree-of-freedom (SDOF) systems for the quantification of seismic response and employ IMs that may be sub-optimal for certain structural systems, namely the spectral acceleration at first mode period, $Sa(T_1)$. Furthermore, studies have highlighted the influence of amplitude scaling of records adopted in dynamic analysis procedures such as IDA on the response.

<img src="/images/ret.png" style="width:500px">

A simplified Response Estimation Tool (RET) is proposed based on empirical relationships using the pushover backbone response of a structure. The tool is tailored specifically for non-ductile infilled RC frame structures by employing a large set of representative SDOF systems. Moreover, the approach addresses the shortcomings of the choice of IM and dynamic procedures requiring amplitude scaling of records and the potentially biasing influence on the response. That is, it developed based on the novel IM average spectral acceleration, $Sa_{avg}$ [[Eads et al., 2015]](https://onlinelibrary.wiley.com/doi/10.1002/eqe.2575). The empirical relationships derived and implemented in the simplified tool provided have been further validated in terms of accurately quantifying collapse and non-collapse response predictions when compared with extensive dynamic analysis results.

<img src="/images/ret_spo.png" style="width:700px">

<img src="/images/ret_fff.png" style="width:700px">

For the latest version of the tool, please visit the Github page [here](https://github.com/gerardjoreilly/Infilled-RC-Building-Response-Estimation).

## Extension of SPO2IDA to Infilled RC Frames
Given the limitations of the original SPO2IDA tool when applied to infilled RC frames, a new library of empirical coefficients have been fitted and proposed by considering a large database of representative backbones to result in an Extended SPO2IDA proposal for infilled RC frames. Comparison with actual IDA shown below illustrate the effectiveness of the tool.

<img src="/images/extended-spo2ida-example.jpg" style="width:400px;">

This has also been verified through a case study application to an existing school building in Italy, shown below. A static pushover analysis of the building was carried out (below left) and the Extended SPO2IDA was utilised. The result (below right) was a set of fragility curves for the building limit states obtained from Extended SPO2IDA. When compared with fragility functions obtained using extensive non-linear dynamic analyses with hazard-consistent ground motion records, the accuracy of the simplified tool is apparent.

<img src="/images/extended-spo2ida-example2.jpg" style="width:400px;">

For the latest version of the tool, please visit the Github page [here](https://github.com/gerardjoreilly/InfilledRC-SPO2IDA).



## Relevant references:
1. Nafeh AMB, **O’Reilly GJ**. Unbiased simplified seismic fragility estimation of non-ductile infilled RC structures. Soil Dynamics and Earthquake Engineering 2022; 157: 107253. DOI: 10.1016/j.soildyn.2022.107253. [[PDF](http://gerardjoreilly.github.io/files/Journal/J31.pdf)][[Link](https://www.sciencedirect.com/science/article/pii/S0267726122001026?via%3Dihub)]
1. Nafeh AMB, **O’Reilly GJ**, Monteiro R. Simplified seismic assessment of infilled RC frame structures. Bulletin of Earthquake Engineering 2020; 18(4): 1579–1611. DOI: 10.1007/s10518-019-00758-2. [[PDF](http://gerardjoreilly.github.io/files/Journal/J13-2020_Nafeh, O’Reilly, Monteiro_Simplified seismic assessment of infilled RC frame structures.pdf)][[Link](https://link.springer.com/article/10.1007/s10518-019-00758-2)]

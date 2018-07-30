# Geospatial Modelling of Australia's National Electricity Market
## Overview
Code in this repository compiles information related to the operation of Australia's National Electricity Market (NEM). The NEM's topology is based on geospatial datasets obtained from Geosience Australia [1, 2, 3]. Data describing the technical and economic parameters related to NEM participants are obtained from the Australian Energy Market Operator (AEMO). Public tables within AEMO's Market Management System Data Model (MMSDM) [4] contain basic generator parameters, such as registered capacities and fuel types. Economic parameters for generators are obtained from AEMO's National Transmission Network Development Plan (NTNDP) database [5].

Load signals are obtained from [4], however these data are only given for each of the NEM's five regions (SA, NSW, QLD, TAS, VIC). Disaggregation of these regional load signals to individual nodes used methods presented in [6, 7], where the geospatial distribution of electricity demand is assumed to follow that of population. Data from the Australian Bureau of Statistics (ABS) describing the geospatial distribution of population within Australia are obtained from [8], while state and territory boundaries are obtained from [9]. Dispatch signals are also obtained from [4], and are used to construct nodal power injection signals for intermittent renewable generators. These dispatch data can also be used to benchmark market models against realised outcomes - a unique feature of this dataset.

The code used to construct the network and generator datasets, and also implement power-flow and unit commitment models, is contained within several Jupyter Notebooks, with a summary of each presented below.

| Notebook Name | Description |
| :----------- | :----------- |
| assemble_network | Compile network information from GA and ABS  |
| collate_generator_data | Compile generator information from AEMO's MMSDM and NTNDP database |
| extract_load_and_dispatch_signals | Extract regional load signals and generator dispatch profiles from AEMO's MMSDM database |
| DCOPF | Run direct-current optimal power-flow (DCOPF) model |
| UC | Run unit commitment (UC) model |
| plotting | Plot results |

## Zenodo link
Network and generator datasets constructed using code in this repository are  also listed at the following repository: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1218806.svg)](https://doi.org/10.5281/zenodo.1218806)



## Caveats
* This dataset does not contain information related to power system components that provide reactive power support to the grid e.g. capacitor banks. Information related to these network elements may be included in the future if additional data become available.


## References
[1] - Commonwealth of Australia (Geoscience Australia), Electricity Transmission Lines (2017), at [http://pid.geoscience.gov.au/dataset/ga/83105](http://pid.geoscience.gov.au/dataset/ga/83105)

[2] - Commonwealth of Australia (Geoscience Australia), Electricity Transmission Substations (2017), at [http://pid.geoscience.gov.au/dataset/ga/83173](http://pid.geoscience.gov.au/dataset/ga/83173)

[3] - Commonwealth of Australia (Geoscience Australia), Power Stations (2017), at [http://pid.geoscience.gov.au/dataset/ga/82326](http://pid.geoscience.gov.au/dataset/ga/82326)


[4] - Australian Energy Markets Operator. Data Archive (2018). at [http://www.nemweb.com.au/#mms-data-model](http://www.nemweb.com.au/#mms-data-model)

[5] - Australian Energy Markets Operator. NTNDP Database. (2018). at [https://www.aemo.com.au/Electricity/National-Electricity-Market-NEM/Planning-and-forecasting/National-Transmission-Network-Development-Plan/NTNDP-database](https://www.aemo.com.au/Electricity/National-Electricity-Market-NEM/Planning-and-forecasting/National-Transmission-Network-Development-Plan/NTNDP-database)

[6] - Zhou, Q. & Bialek, J. W. Approximate model of european interconnected system as a benchmark system to study eﬀects of cross-border trades. IEEE Trans. Power Syst. 20, 782–788 (2005).

[7] - Jensen, T. V. & Pinson, P. RE-Europe, a large-scale dataset for modeling a highly renewable European electricity system. Sci. Data 4, 170175 (2017).

[8] - Australian Bureau of Statistics. Regional Population Growth, Australia, 2014-15. (2016). at [http://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/3218.02014-15?OpenDocument](http://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/3218.02014-15?OpenDocument)

[9] - Australian Bureau of Statistics. Local Government Areas ASGS Ed 2016 Digital Boundaries in ESRI Shapeﬁle Format. (2016). at [http://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/1270.0.55.003July%202016?OpenDocument](http://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/1270.0.55.003July%202016?OpenDocument)

## Creative Commons Attributions
Geospatial datasets obtained from Geoscience Australia are made available under the following license:

[![License: CC BY 4.0](https://licensebuttons.net/l/by/4.0/80x15.png)](https://creativecommons.org/licenses/by/4.0/) © Commonwealth of Australia (Geoscience Australia) 2017. With the exception of the Commonwealth Coat of Arms, and where otherwise noted, this product is provided under a Creative Commons Attribution 4.0 International Licence. [http://creativecommons.org/licenses/by/4.0/legalcode](http://creativecommons.org/licenses/by/4.0/legalcode)

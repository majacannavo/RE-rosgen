---
layout: page
title: RE- Replication of Rosgen Stream Classification
---


**Replication of**
# A classification of natural rivers

Original study *by* Rosgen, D. L.
*in* *CATENA* 22 (3):169–199. https://linkinghub.elsevier.com/retrieve/pii/0341816294900019.

and Replication by: Kasprak, A., N. Hough-Snee, T. Beechie, N. Bouwes, G. Brierley, R. Camp, K. Fryirs, H. Imaki, M. Jensen, G. O’Brien, D. Rosgen, and J. Wheaton. 2016. The Blurred Line between Form and Process: A Comparison of Stream Channel Classification Frameworks ed. J. A. Jones. *PLOS ONE* 11 (3):e0150293. https://dx.plos.org/10.1371/journal.pone.0150293.

Replication Authors:
Maja Cannavo, Zach Hilgendorf, Joseph Holler, and Peter Kedron.

Replication Materials Available on GitHub at: [majacannavo/RE-rosgen](https://github.com/majacannavo/RE-rosgen).

Created: `23 March 2021`
Revised: `23 March 2021`

## Introduction/Motivation

In this analysis we replicated the work of Rosgen ([1994](https://www.sciencedirect.com/science/article/pii/0341816294900019?via%3Dihub)) and Kasprak et al. ([2016](https://dx.plos.org/10.1371/journal.pone.0150293)) to classify river channels in the Middle Fork John Day River in Oregon, USA. Kasprak et al. implemented the Rosgen Classification System (detailed in Rosgen, 1994) in addition to the River Styles Framework, Natural Channel Classification, and "a channel form-based statistical classification" to classify 33 sites in the Middle Fork John Day Basin and compare the results (Kasprak et al., 2016, p. 1). Kasprak et al. ultimately found that the various classification systems placed stream channels into similar groupings; disagreement among the frameworks tended to occur "in locations where valley setting was not a reliable predictor of channel form" (Kasprak et al., 2016, p. 27). We sought to replicate Kasprak et al.'s Rosgen Classification System analysis using open-source software, namely [GRASS GIS](https://grass.osgeo.org/) and [R](https://www.r-project.org/). A main goal of our replication was to determine the extent to which such a study is possible using just GIS analysis, without collecting any new data in the field.

## Methods

We were each randomly assigned a single location in the Middle Fork John Day River and employed the [Rosgen Classification System](https://www.sciencedirect.com/science/article/pii/0341816294900019?via%3Dihub) to classify the stream channel at our location. My location was the site with loc_id = 12, as identified in the Columbia Habitat and Monitoring Program (CHaMP) [dataset](https://github.com/majacannavo/RE-rosgen/tree/main/data/raw/public). We started with 1-meter resolution LiDAR elevation data and the CHaMP dataset and ran our analysis in GRASS as detailed in the [research protocol](https://github.com/majacannavo/RE-rosgen/blob/main/procedure/protocols/1-Research_Protocol_GRASS.pdf) prepared by Zach Hilgendorf and Joseph Holler. Steps 3-10 on pages 8-9 of the research protocol were automated with [this GRASS model](https://github.com/majacannavo/RE-rosgen/blob/main/procedure/code/visualize.gxm), and steps 1-8 on pages 16-17 of the protocol were automated with [this GRASS model](https://github.com/majacannavo/RE-rosgen/blob/main/procedure/code/center_line_length.gxm). (Both models were written by Joseph Holler.) Kasprak et al. also used the CHaMP dataset but employed 10-meter and 0.1-m resolution digital elevation models (DEMs), as well as 1-m resolution aerial imagery and on-the-ground data collection, in their analysis (Kasprak et al., 2016, p. 9), so our data differs somewhat from theirs.

Following our GRASS analysis, we moved into RStudio to make graphs and further analyze the data we produced in GRASS, following this [R Markdown document](https://github.com/majacannavo/RE-rosgen/blob/main/procedure/code/2-ProfileViewer.Rmd). Using the results of our R and GRASS analyses in addition to the CHaMP dataset, we produced a table of site measurements, which enabled us to perform Level I and II Rosgen classifications (see Results/Discussion section). One deviation I made from the R Markdown document was to recalculate channel slope myself as (change in distance)/(change in elevation), based on the beginning and ending elevations from the [longitudinal profile](https://github.com/majacannavo/RE-rosgen/blob/main/data/derived/public/longprof.txt) I generated in GRASS.

## Replication Results

For each hypothesis examined, present separately the results of the replication attempt.
1.	Briefly describe how the replication protocol outlined above was implemented reporting key information (e.g., sample size).
2.	State whether the original hypothesis was or was not supported by the replication
   - Provide key statistics produced by the replication.
   - Provide key measures (e.g., matching effect direction/size, significance) used to make the decision.
   - Highlight any contradictory results with a brief explanation
3.	State whether any hypothesis linked to a planned deviation from the original study was supported. Provide key statistics and related reasoning.

Figures to Include:
- map of the study site shaded elevation
- map of the study site slope
- Map of the study site stream/river centerlines and final mean centerline
- Map of the study site valley centerlines and final mean centerline
- Longitudinal profile graph with elevation and slope
- Cross-sectional profile graph

Tables to Include:

Table 1. Site Measurements
| Variable | Value | Source |
| :-: | :-: | :-: |
| Bankfull Width | | |
| Bankfull Depth | | |
| Valley Width | | |
| Valley Depth | | |
| Stream/River Length | | |
| Valley Length | | |
| Median Channel Material Particle Diameter | | |

Table 2. Rosgen Level I Classification
| Criteria | Value |
| :-: | :-: |
| Entrenchment Ratio | -- |
| Width / Depth Ratio | -- |
| Sinuosity | -- |
| Level I Stream Type | -- |

Table 3. Rosgen Level II Classification
| Criteria | Value |
| :-: | :-: |
| Slope | -- |
| Channel Material | -- |
| Level II Stream Type | -- |


## Unplanned Deviations from the Protocol

Identify and describe any unplanned deviations from the original replication protocol the occurred during the course of the replication. Explain the rationale behind any deviations. Finally, provide the details and results of any sensitivity analyses conducted to assess whether these deviations may have impacted the results of the replication.

## Discussion

Provide a summary and interpretation of the key findings of the replication *vis-a-vis* the original study results. If the attempt was a failure, discuss possible causes of the failure. These may include:
- Practical Causes – related to lack of data, code, details in the original analysis
- Informative Causes – related to absence of effect, change in population, or location.

Discuss an interpretation of your results.
- Were the Level I and Level II results internally and logically consistent? That is, did all the parameters for the identified stream type conform to expectations outlined in Rosgen?
- Were your results consistent with previous evaluations of the same stream reach reported by Kasperak et al?

Discuss a response to the following prompt: Quantifying uncertainty in geomorphic systems and in GIScience is of paramount importance, not only for creating error bars on a graph, but for realistically communicating the reliability and legitimacy of an output dataset. Error bars do not (necessarily) reflect on the researcher. They stem from collection constraints, processing constraints, subjective decision making, and many, many more sources. Given what you have learned in this module, discuss at least three sources of error and uncertainty and how they could impact the classification of your stream. Where does uncertainty stem from? Why is uncertainty a problem? What could be done (or has been done) to fix or reduce uncertainty? In a perfect world, how could this uncertainty be removed?

## Conclusion

Restate the key findings and discuss their broader societal implications or contributions to theory.
Do the research findings suggest a need for any future research?

## References

Include any referenced studies or materials in the [AAG Style of author-date referencing](https://www.tandf.co.uk//journals/authors/style/reference/tf_USChicagoB.pdf).

####  Report Template References & License

This template was developed by Peter Kedron and Joseph Holler with funding support from HEGS-2049837. This template is an adaptation of the ReScience Article Template Developed by N.P Rougier, released under a GPL version 3 license and available here: https://github.com/ReScience/template. Copyright © Nicolas Rougier and coauthors. It also draws inspiration from the pre-registration protocol of the Open Science Framework and the replication studies of Camerer et al. (2016, 2018). See https://osf.io/pfdyw/ and https://osf.io/bzm54/

Camerer, C. F., A. Dreber, E. Forsell, T.-H. Ho, J. Huber, M. Johannesson, M. Kirchler, J. Almenberg, A. Altmejd, T. Chan, E. Heikensten, F. Holzmeister, T. Imai, S. Isaksson, G. Nave, T. Pfeiffer, M. Razen, and H. Wu. 2016. Evaluating replicability of laboratory experiments in economics. Science 351 (6280):1433–1436. https://www.sciencemag.org/lookup/doi/10.1126/science.aaf0918.

Camerer, C. F., A. Dreber, F. Holzmeister, T.-H. Ho, J. Huber, M. Johannesson, M. Kirchler, G. Nave, B. A. Nosek, T. Pfeiffer, A. Altmejd, N. Buttrick, T. Chan, Y. Chen, E. Forsell, A. Gampa, E. Heikensten, L. Hummer, T. Imai, S. Isaksson, D. Manfredi, J. Rose, E.-J. Wagenmakers, and H. Wu. 2018. Evaluating the replicability of social science experiments in Nature and Science between 2010 and 2015. Nature Human Behaviour 2 (9):637–644. http://www.nature.com/articles/s41562-018-0399-z.

# MGGG Communities of Interest Data Products

This repository contains released shapefile and image outputs from [MGGG's communities of interest analysis pipeline](https://github.com/mggg/coi-states).

## Using COI data

These data products can be used as inputs to a COI preservation analysis pipeline. Score functions for COI analysis can be found in the [plan-evaluation-processing repository](https://github.com/mggg/plan-evaluation-processing/pull/9). These functions can be used for both geoclusters and individual COI submissions.

The COI data products for each state include a few dozen geoclusters that were made through a deterministic clustering process based on census geography. That is, from hundreds or thousands of areas that were "painted" by members of the public and paired with a community narrative, we produce 25-35 larger regions, each supported by a multiplicity of public submissions. For instance, Wisconsin cluster C1 is called Whitewater, and it is a synthesis of 98 mapped areas in the southwest corner of the state. In many states, redistricting plans are supposed to "respect" communities of interest. We have built a family of scores for COI preservation based on either the larger geoclusters or the more numerous original public submissions.

Because of the manner in which they were created, the geoclusters vary greatly in their land area and their population. Fix a level of districting and an inclusion threshold parameter 0 < T ≤ 100. Our scores award a point for a cluster if either some district contains T% of the population of the cluster _or_ some district has T% of its population in the cluster. This score varies from 0 to the number of clusters. Note that for very large clusters and/or small districts, it is easy to get a point under the second condition. Accordingly, we have a variant that awards fractional points to the cluster according to the formula by replacing the second bullet with (number of districts T% contained in cluster) / (cluster population / ideal district population).

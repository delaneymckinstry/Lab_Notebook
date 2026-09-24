**Network Segregation**

**Research Question**

Does opioid use disorder (OUD) alter the segregation and organization of large-scale functional brain networks?

This analysis examined whether individuals with OUD showed differences in functional network segregation compared with individuals without OUD, and whether these differences were related to duration of opioid use.

**Participants**

Resting-state fMRI data were pooled across multiple studies and included individuals with OUD and non-OUD comparison participants.

Participants with excessive head motion (mean framewise displacement > 0.5 mm) were excluded. The final analytic sample included:

* Non-OUD: n = 60
* OUD: n = 125

**Imaging**

Resting-state fMRI data were preprocessed in MATLAB using a pipeline adapted from Ciric et al. (2018). Preprocessing included motion correction, slice-time correction, structural image processing and registration, nuisance signal regression, despiking, temporal filtering, spatial smoothing, and normalization to Montreal Neurological Institute (MNI) space.

Functional connectivity was calculated using the Power-264 atlas, which defines 264 spherical regions of interest (ROIs) assigned to 13 canonical functional networks. These networks were further grouped into association, sensorimotor, and other network categories.

**Analysis**

For each participant, Fisher Z-transformed Pearson correlations between ROI time courses were used to generate functional connectivity matrices. Network segregation was quantified as the difference between within-network and between-network connectivity, with only positive correlations included.

Segregation was calculated for individual networks, as well as for the association and sensorimotor network categories. ROI-level segregation scores were also calculated for networks showing significant group differences.

Exploratory graph-theoretical analyses were conducted in R to evaluate network organization without relying solely on the canonical Power-264 network assignments. Connectivity matrices were binarized across sparsity thresholds ranging from 0.09 to 0.50. At each threshold, network communities were identified using the Louvain algorithm, which was repeated 100 times to account for stochastic variation.

Three graph-theoretical measures were calculated across thresholds:

* **Modularity:** degree to which the network can be divided into internally dense and externally sparse communities.
* **Normalized mutual information (NMI):** similarity between the empirically derived network partition and the canonical Power-264 organization.
* **Global efficiency:** whole-brain network integration based on shortest path lengths.

Values were averaged across sparsity thresholds to generate participant-level summary measures.

Statistical analyses were conducted in R (v4.5.2). Linear mixed-effects models compared network segregation between OUD and non-OUD groups while adjusting for age, sex, race, tobacco use, stimulant use, scanner parameters, and mean framewise displacement, with study included as a random effect. False discovery rate (FDR) correction was applied to analyses of individual association and sensorimotor networks.

Exploratory analyses examined relationships between network segregation and years of opioid use, as well as effects of age, sex, overdose history, and medication for OUD.

**Results**

Individuals with OUD showed significantly lower segregation of both **association networks** and **sensorimotor networks** compared with non-OUD participants.

* **Association network:** OUD = 0.25 [0.22, 0.27] vs. non-OUD = 0.29 [0.26, 0.31], *F*(1,241.57) = 12.27, *p* < 0.001
* **Sensorimotor network:** OUD = 0.41 [0.37, 0.45] vs. non-OUD = 0.46 [0.42, 0.50], *F*(1,209.83) = 13.14, *p* < 0.001

Within the association network, lower segregation in OUD was observed in the **cingulo-opercular, default mode, and ventral attention networks** after FDR correction. Within the sensorimotor category, lower segregation was observed in the **hand and visual networks**.

At the ROI level, OUD was associated with lower segregation in regions including the dorsal anterior cingulate cortex, right anterior insula, bilateral precentral and postcentral gyri, bilateral middle temporal gyri, and bilateral fusiform gyri.

Within the OUD group, longer opioid use was associated with lower association-network segregation (*F*(1,115.00) = 4.05, *p* = 0.046; slope = −2.21 × 10⁻³).


**Code**

Analysis and statistical code used for preprocessing, network segregation, graph-theoretical analyses, and statistical modeling is available in the `code/` directory.

**Related Publication**

McKinstry D, et al. Opioid Use Disorder is Associated with Lower Resting-State Brain Network Segregation. medRxiv. 2026; preprint: 10.64898/2026,08.04.26359717

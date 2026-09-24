**Episodic Memory**

**Research Question**

Does opioid use disorder (OUD) and a history of non-fatal overdose affect episodic memory performance or hippocampal neural activity during memory encoding?

**Participants**

Participants were drawn from the structural and functional MRI cohort and included:

* Healthy controls (HC): n = 4
* OUD without non-fatal overdose (OUD-NOD): n = 4
* OUD with non-fatal overdose (OUD-OD): n = 6

**Imaging**

Structural MRI data were acquired using T1-weighted MPRAGE sequences on 3T Siemens MRI scanners. Functional MRI data were acquired on a 3T Siemens Prisma using a T2*-weighted BOLD EPI sequence during an episodic memory encoding task.

Functional images were preprocessed using SPM12, including slice-time correction, motion correction, coregistration to structural MRI, normalization to MNI space, and spatial smoothing.

**Analysis**

**Episodic Memory Performance**

Participants completed an episodic memory task consisting of an encoding phase during fMRI and a retrieval phase approximately 30 minutes later.

During encoding, participants made semantic judgments about 176 objects. During retrieval, participants identified previously presented ("old") and novel ("new") objects using a five-point confidence scale.

Memory performance was quantified using the area under the receiver operating characteristic curve (ROC AUC), calculated from true- and false-positive rates across response thresholds.

**Hippocampal Neural Activity**

Encoding trials were categorized as **remembered** or **forgotten** based on subsequent memory performance. First-level general linear models included task conditions, motion parameters, and run-specific constants. Neural activity associated with successful memory encoding was assessed using the **remembered > forgotten** contrast.

The resulting contrast value within the hippocampus, defined using the Neuromorphometrics atlas, was extracted for group-level analysis.

Statistical analyses were conducted in R (v4.2.2). One-way ANOVAs were used to examine group differences in episodic memory performance and hippocampal neural activity.

**Results**

Episodic memory performance, measured by ROC AUC, did not significantly differ across groups (*F*(2,11) = 0.40, *p* = 0.68, η² = 0.07).

Mean ROC AUC was:

* HC: 0.83 [0.68, 0.98]
* OUD-NOD: 0.80 [0.65, 0.95]
* OUD-OD: 0.75 [0.63, 0.87]

Although the overall group effect was not significant, an exploratory post hoc comparison showed a medium effect size (Cohen's *d* = 0.56) for lower memory performance in the OUD-OD group compared with healthy controls.

Hippocampal neural activity during successful memory encoding also did not significantly differ across groups (*F*(2,11) = 0.90, *p* = 0.43, η² = 0.14).

Mean hippocampal remembered-versus-forgotten contrast values were:

* HC: −0.06 [−0.59, 0.47]
* OUD-NOD: 0.28 [−0.25, 0.80]
* OUD-OD: −0.13 [−0.56, 0.30]

Given the small sample size, these findings should be interpreted as exploratory.


**Episodic Memory Performance**

![Episodic memory performance](Figures/Memory_Performance.png)

**Figure 1.** Episodic memory performance, quantified using ROC AUC, across healthy controls, OUD-NOD, and OUD-OD groups.

**Hippocampal Neural Activity**

![Hippocampal neural activity during memory encoding](Figures/Hippocampal_Activity.png)

**Figure 2.** Hippocampal neural activity associated with successful memory encoding (remembered > forgotten) across groups.

**Code**

Analysis code used to calculate episodic memory performance, extract hippocampal task-related activity, and perform group-level statistical analyses is available in the `code/` directory.

**Related Publication**
McKinstry D, et al. Hippocampal volume and brain tau pathology in opioid use disorder: associations with non-fatal opioid overdose. Addict Neurosci. 2026;19:100253. PMID: 41947888

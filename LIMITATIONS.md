# Research Limitations

## 1. Introduction

This document records the limitations identified during the current investigation of machine learning pipeline reliability and debugging.

It distinguishes between:

1. Limitations of existing research and tools.
2. Limitations of the current research investigation.
3. Potential limitations of the future proposed approach.

The final research contribution has not yet been selected. Therefore, potential limitations of the proposed approach will be updated after the research question and methodology are established.

## 2. Limitations of Existing Research

The literature review has identified several important considerations.

### 2.1 Continuous Integration Failure Diagnosis

Existing research and tools already investigate:

- CI failure classification.
- Flaky-test detection.
- Persistent test failures.
- Failure co-occurrence.
- Log-based root-cause analysis.
- Automated failure remediation.

Consequently, developing another general-purpose CI failure diagnosis system would require a clearly differentiated research contribution.

### 2.2 Machine Learning Pipeline Performance Diagnosis

Existing research has investigated:

- Pipeline performance prediction.
- Root-cause attribution for model performance.
- Hyperparameter intervention.
- Dataset-complexity analysis.

A proposed project involving only model-performance prediction or hyperparameter recommendations would substantially overlap with existing work.

### 2.3 Training-Data Debugging

Research systems such as Rain, Rain++, and DataScope investigate training-data attribution and debugging.

Therefore, general identification of influential or problematic training examples cannot independently establish a novel contribution.

### 2.4 Pipeline Inspection and Provenance

Existing systems such as mlinspect, ArgusEyes, and MLflow2PROV provide capabilities related to pipeline inspection, data validation, and provenance.

A new system that merely records pipeline operations or tracks data lineage would not be sufficient to establish novelty.

### 2.5 Data-Error Detection and Repair

Existing research already investigates data-error identification, attribution, debugging, and repair across machine learning pipelines.

A proposed contribution must therefore address a specific limitation beyond general data-quality checking.

## 3. Limitations of the Current Research Investigation

The following limitations apply to the work completed so far.

### 3.1 Incomplete Research-Gap Validation

The current literature review is an initial investigation rather than an exhaustive systematic review.

Additional publications, recent preprints, conference proceedings, and existing implementations must be examined before selecting the final research problem.

### 3.2 Incomplete Implementation Comparison

The capabilities of identified systems have not all been independently tested.

Repository availability and published descriptions do not establish that a system can reproduce every reported capability in the intended experimental environment.

### 3.3 Dataset Selection Is Pending

No final dataset or benchmark has been selected.

Dataset suitability, licensing, availability, size, quality, and compatibility with available hardware must be investigated.

### 3.4 No Independent Experimental Reproduction

The reported results of the reviewed research papers have not been independently reproduced.

Published performance values are therefore treated as reported findings rather than results obtained by this project.

### 3.5 No Proposed Method Has Been Implemented

The project has not entered the implementation stage.

There are currently no experimental results demonstrating the performance of a proposed technique.

## 4. Potential Limitations of the Future Research

The following issues may affect the eventual study, depending on the selected research problem.

### 4.1 Dataset Representativeness

A limited set of datasets may not represent the diversity of real-world machine learning pipelines.

### 4.2 Synthetic Fault Realism

If controlled fault injection is used, synthetic faults may not fully represent naturally occurring data-processing errors.

### 4.3 Framework Dependency

A technique developed for particular Python libraries may not generalise to other machine learning frameworks or data-processing environments.

### 4.4 Computational Constraints

Large datasets, repeated pipeline executions, and complex model training may require more computational resources than are available locally.

### 4.5 Evaluation Bias

An evaluation based on a limited set of fault types or datasets may produce results that do not generalise to unseen scenarios.

### 4.6 Baseline Reproducibility

Differences in software versions, configurations, datasets, and execution environments may affect the fairness of comparisons with existing methods.

## 5. Threats to Validity

The eventual experiments must consider the following threats.

|         Threat        |         Potential Impact            |                Mitigation                    |
|-----------------------|-------------------------------------|----------------------------------------------|
| Dataset bias          | Limited generalisation              | Use diverse datasets where feasible          |
| Fault-injection bias  | Unrealistic experimental conditions | Document fault-generation procedures         |
| Data leakage          | Inflated evaluation results         | Apply appropriate data separation            |
| Baseline differences  | Unfair comparison                   | Standardise experimental conditions          |
| Random variation      | Inconsistent results                | Control random seeds and repeat experiments  |
| Hardware limitations  | Incomplete experiments              | Use appropriately sized datasets             |
| Implementation errors | Incorrect conclusions               | Validate components and experimental outputs |

## 6. Mitigation Strategy

The following practices will be adopted:

1. Validate the research gap before implementation.
2. Compare against relevant existing systems.
3. Use documented and reproducible datasets.
4. Maintain consistent experimental conditions.
5. Record software versions and configurations.
6. Evaluate multiple relevant scenarios.
7. Analyse false positives and false negatives.
8. Report negative and inconclusive results.
9. Clearly state the scope of the experiments.
10. Avoid claiming generalisation beyond the available evidence.

## 7. Current Status

|             Area                 |             Status             |
|----------------------------------|--------------------------------|
| CI research limitations          | Identified                     |
| ML pipeline research limitations | Initial analysis completed     |
| Existing-system limitations      | Further investigation required |
| Dataset limitations              | Pending dataset selection      |
| Proposed-method limitations      | Not yet established            |
| Experimental threats to validity | Preliminary list established   |
| Mitigation strategy              | Initial plan established       |

## 8. Conclusion

This document establishes the limitations that must be considered during the research investigation and future experimentation.

The final limitations of the proposed method will be documented only after the research question, implementation, and experimental evaluation have been completed.

All conclusions will be restricted to the evidence obtained through the study.
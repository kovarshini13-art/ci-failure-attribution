# Research Project: Machine Learning Pipeline Reliability

## Overview

This repository contains the research and experimental development of a project investigating reliability and debugging challenges in machine learning pipelines.

The investigation began with Continuous Integration (CI) failure attribution. However, an initial literature review identified substantial overlap with existing research and tools in CI failure diagnosis, flaky-test detection, and automated root-cause analysis.

Consequently, the research direction was broadened to investigate machine learning pipeline reliability and debugging.

The current investigation focuses on understanding whether specific data-processing faults can be detected and localised when a machine learning pipeline executes successfully but produces unexpected downstream behaviour.

**Important:** The final research question and contribution have not yet been established. They will be selected only after further literature review, comparison of existing implementations, and research-gap validation.

## Research Objectives

1. Study existing research on machine learning pipeline debugging and reliability.
2. Understand how data-processing operations affect downstream machine learning behaviour.
3. Examine existing pipeline inspection, lineage, and debugging systems.
4. Identify limitations that are not adequately addressed by existing approaches.
5. Develop a measurable and reproducible research question.
6. Design controlled experiments to evaluate the proposed contribution.

## Current Research Direction

The investigation is currently examining the following areas:

- Silent semantic errors in data preprocessing.
- Interactions between multiple data transformations.
- Fault propagation across machine learning pipeline stages.
- Differences between training-time and inference-time transformations.
- Operation-level tracing and fault localisation.
- Limitations of existing pipeline inspection and validation systems.

These are candidate investigation areas, not confirmed research gaps.

## Literature Review

The literature review examines two major research areas.

### 1. Continuous Integration Reliability

Research areas reviewed include:

- Persistent CI test failures.
- Flaky-test detection.
- Failure co-occurrence.
- CI workflow failure classification.
- LLM-based CI failure diagnosis.
- Automated failure remediation.

### 2. Machine Learning Pipeline Reliability

Research areas reviewed include:

- Machine learning debugging techniques.
- Data distribution debugging.
- Training-data attribution.
- Pipeline provenance and lineage.
- Data-error detection and repair.
- Pipeline root-cause analysis.
- Existing pipeline inspection systems.

The detailed literature review is maintained in:

`research/literature_review.md`

## Repository Structure

project-root/
│
├── README.md
├── METHODOLOGY.md
├── LIMITATIONS.md
│
├── datasets/
│   └── README.md
│
├── experiments/
│   └── experiment_plan.md
│
├── research/
│   └── literature_review.md
│
├── results/
│   └── README.md
│
└── src/
    ├── data_collection/
    ├── features/
    ├── models/
    └── preprocessing/


## Research Approach

The project will follow a research-driven development process:

1. Literature review and problem investigation.
2. Identification of existing research limitations.
3. Research-gap validation.
4. Definition of the research question and hypothesis.
5. Dataset and benchmark selection.
6. Experimental design.
7. Baseline implementation.
8. Proposed method development.
9. Controlled experimentation.
10. Evaluation, analysis, and documentation.

## Technology Considerations

The final technology stack will depend on the validated research question.

Potential technologies include:

- Python
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Jupyter Notebook
- Git and GitHub

No technology will be selected merely for the sake of including additional tools.

## Research Principles

This project follows these principles:

- Research before implementation.
- Evidence before novelty claims.
- Reproducible experiments.
- Comparison against existing approaches.
- Clear separation between observations and hypotheses.
- Honest reporting of limitations and negative results.
- Feasibility within available computing resources.

## Current Project Status

|           Component              |          Status          |
|----------------------------------|--------------------------|
| Initial CI research              | Reviewed                 |
| CI tool comparison               | Initial review completed |
| ML debugging literature          | Initial review completed |
| ML pipeline debugging systems    | Initial review completed |
| Detailed research-gap validation | In progress              |
| Final research question          | Not selected             |
| Dataset selection                | Pending                  |
| Experimental methodology         | Pending                  |
| Implementation                   | Not started              |

## Expected Outcome

The objective is to develop a technically defensible research contribution supported by reproducible experiments and quantitative evaluation.

The project will proceed to implementation only after the research problem has been sufficiently validated.
# Research Methodology

## 1. Introduction

This document describes the planned research methodology for investigating reliability and debugging challenges in machine learning pipelines.

The research direction is currently under investigation. The final research question, proposed technique, and experimental method will be determined only after validating a specific research gap against existing publications and implementations.

Therefore, this document defines the research process rather than claiming that a final solution has already been developed.

## 2. Research Objectives

The methodology aims to:

1. Investigate specific debugging challenges in machine learning pipelines.
2. Understand how data-processing operations influence downstream pipeline behaviour.
3. Examine the capabilities and limitations of existing debugging and inspection systems.
4. Identify a technically meaningful and measurable research gap.
5. Design controlled experiments to investigate the selected problem.
6. Evaluate the proposed approach against appropriate baseline methods.

## 3. Research Design

The study will follow an experimental research approach.

The research process will consist of the following stages:

### Stage 1: Literature Review

A systematic investigation of relevant publications, research implementations, and benchmarks will be conducted.

Research areas include:

- Machine learning system debugging.
- Data distribution debugging.
- Data lineage and provenance.
- Data transformation tracking.
- Training and inference consistency.
- Data-error detection and attribution.
- Pipeline-level fault localisation.

The purpose is to understand existing solutions and identify limitations that require further investigation.

### Stage 2: Existing-System Analysis

Relevant research systems will be examined to understand their actual capabilities.

Initial systems identified include:

- mlinspect
- ArgusEyes
- DataScope
- MLflow2PROV
- AutoLineage

The comparison will investigate:

- Supported libraries and frameworks.
- Pipeline operations that can be observed.
- Level of transformation tracking.
- Types of faults that can be detected.
- Ability to localise the source of an error.
- Evidence provided for debugging.
- Reproducibility and implementation availability.

The final baseline selection will depend on detailed implementation and documentation analysis.

### Stage 3: Research-Gap Validation

Candidate research problems will be investigated individually.

The validation process will include:

1. Searching for closely related publications.
2. Reviewing recent conference papers and preprints.
3. Examining existing open-source implementations.
4. Comparing documented capabilities and limitations.
5. Identifying suitable public datasets or reproducible experimental setups.
6. Determining whether a measurable technical limitation remains.

A candidate will be selected only when sufficient evidence supports its relevance and differentiation.

### Stage 4: Research Question and Hypothesis

After validating the research gap, the study will define:

- A precise research problem.
- A primary research question.
- One or more testable hypotheses.
- Independent and dependent variables.
- Experimental conditions.
- Evaluation criteria.

The hypothesis must be measurable and capable of being supported or rejected through experiments.

### Stage 5: Dataset and Experimental Setup

The experimental data will be selected according to the final research question.

Possible sources include:

- Public machine learning datasets.
- Existing pipeline benchmarks.
- Controlled synthetic datasets.
- Reproducible machine learning pipelines.

If synthetic faults are introduced, their definitions, locations, expected effects, and generation procedures will be documented.

The experimental setup will prioritise reproducibility and compatibility with available computing resources.

### Stage 6: Baseline Development

Appropriate existing methods will be selected as baselines.

The baseline implementation will be used to establish measurable reference performance.

Baseline selection will depend on:

- Relevance to the validated research problem.
- Availability of source code or reproducible methodology.
- Compatibility with the selected datasets.
- Fairness of comparison.

### Stage 7: Proposed Approach

A proposed technique will be designed only after the research gap is established.

Its design will specify:

- Required inputs.
- Processing stages.
- Internal representations.
- Detection or localisation procedure.
- Outputs and supporting evidence.
- Computational requirements.

The proposed method must address a clearly defined limitation rather than simply combine existing libraries or tools.

### Stage 8: Experimental Evaluation

The proposed method will be evaluated against selected baselines using controlled experiments.

Potential evaluation measures, depending on the final research problem, include:

- Detection precision.
- Detection recall.
- F1-score.
- Fault-localisation accuracy.
- Top-k localisation accuracy.
- False-positive rate.
- Execution time.
- Memory consumption.
- Reproducibility across repeated runs.

Only metrics relevant to the final research question will be used.

### Stage 9: Result Analysis

The results will be analysed to determine:

- Whether the hypotheses are supported.
- Whether the proposed approach improves upon the baselines.
- Which experimental conditions affect performance.
- Where the approach fails.
- Whether the results generalise beyond the tested examples.

Negative and inconclusive results will also be documented.

## 4. Experimental Principles

The experiments will follow these principles:

1. Controlled experimental conditions.
2. Consistent evaluation datasets.
3. Fair baseline comparisons.
4. Reproducible execution procedures.
5. Clear documentation of parameters.
6. Separation of training, validation, and test data where applicable.
7. Appropriate prevention of data leakage.
8. Transparent reporting of results.

## 5. Tools and Technologies

The following technologies are under consideration:

|    Technology    |             Potential Purpose              |
|------------------|--------------------------------------------|
| Python           | Research implementation                    |
| NumPy            | Numerical operations                       |
| Pandas           | Data processing                            |
| Scikit-learn     | Machine learning experiments               |
| Matplotlib       | Result visualisation                       |
| Jupyter Notebook | Experimental analysis                      |
| Git              | Version control                            |
| GitHub           | Research documentation and code management |

The final stack will be selected according to the validated problem.

## 6. Reproducibility

To support reproducibility:

- Dataset sources will be documented.
- Data preprocessing procedures will be recorded.
- Experimental configurations will be maintained.
- Random seeds will be controlled where applicable.
- Baseline implementations will be documented.
- Evaluation procedures will be repeatable.
- Results will be stored with relevant experiment details.

## 7. Threats to Validity

Potential threats include:

- Limited dataset diversity.
- Synthetic faults that may not represent real-world failures.
- Bias in benchmark selection.
- Differences between experimental and production environments.
- Limited generalisability across libraries and model families.
- Implementation differences between baselines.
- Hardware and resource constraints.

These threats will be considered during experimental design and result interpretation.

## 8. Current Methodology Status

|       Research Component       |          Status          |
|--------------------------------|--------------------------|
| Initial literature review      | Completed                |
| Existing-system identification | Initial review completed |
| Detailed system comparison     | Pending                  |
| Research-gap validation        | In progress              |
| Research question              | Not finalised            |
| Hypothesis                     | Pending                  |
| Dataset selection              | Pending                  |
| Baseline selection             | Pending                  |
| Proposed technique             | Pending                  |
| Experimental implementation    | Not started              |
| Evaluation                     | Pending                  |

## 9. Conclusion

This methodology establishes a research-driven process for investigating machine learning pipeline reliability.

The final experimental methodology will be refined after selecting and validating a specific research question.

No proposed method or performance improvement is claimed at this stage.
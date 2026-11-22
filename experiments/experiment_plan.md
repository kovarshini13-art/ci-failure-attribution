# Experimental Plan

## 1. Purpose

This document defines the planned experimental process for the research investigation into machine learning pipeline reliability and debugging.

The final research problem has not yet been selected. Therefore, this plan describes the experiments that will be designed after validating a specific research gap.

No experimental results or performance improvements are claimed at this stage.

## 2. Research Objectives

The experiments will aim to:

1. Investigate a clearly defined machine learning pipeline debugging problem.
2. Reproduce selected fault scenarios under controlled conditions.
3. Evaluate the capabilities of existing approaches.
4. Develop and evaluate a proposed technique, if a valid research gap is established.
5. Compare results using appropriate quantitative metrics.
6. Analyse the strengths and limitations of the investigated methods.

## 3. Experimental Design Status

|         Component        |           Current Status          |
|--------------------------|-----------------------------------|
| Research question        | Not finalised                     |
| Research hypothesis      | Pending                           |
| Dataset                  | Not selected                      |
| Fault categories         | Under investigation               |
| Baseline methods         | Not selected                      |
| Proposed method          | Not designed                      |
| Evaluation metrics       | Preliminary candidates identified |
| Experimental environment | To be finalised                   |
| Results                  | Not available                     |

## 4. Planned Experimental Phases

### Phase 1: Research Problem Validation

Before conducting experiments:

- Complete the detailed literature review.
- Compare relevant research implementations.
- Identify a specific technical limitation.
- Define the research question.
- Establish the expected research contribution.

**Expected output:** A validated research problem and measurable research objectives.

### Phase 2: Dataset and Pipeline Selection

After selecting the research problem:

- Identify suitable datasets.
- Select relevant machine learning pipelines.
- Examine the data-processing operations involved.
- Document the experimental environment.
- Establish reproducible pipeline execution procedures.

**Expected output:** A documented dataset and experimental pipeline.

### Phase 3: Fault Scenario Design

If the selected research question involves fault detection or localisation, controlled fault scenarios may be designed.

Possible candidate scenarios include:

- Incorrect data-type conversion.
- Unexpected missing-value handling.
- Incorrect feature transformation.
- Unintended changes in feature distributions.
- Inconsistent transformation sequences.
- Training-time and inference-time preprocessing differences.

These scenarios are preliminary examples. They will be retained only if they are relevant to the validated research problem and are not already adequately addressed by existing methods.

Each selected scenario will document:

- Fault definition.
- Fault location.
- Fault-generation procedure.
- Expected behaviour.
- Ground-truth information.
- Expected observable effect.

### Phase 4: Baseline Evaluation

Appropriate existing approaches will be selected and evaluated.

Potential systems for investigation include:

- mlinspect.
- ArgusEyes.
- Other relevant tools identified during research-gap validation.

The final baseline set will depend on compatibility, reproducibility, and relevance to the selected problem.

### Phase 5: Proposed Method Evaluation

If a differentiated research contribution is established, the proposed method will be implemented and evaluated.

The evaluation will examine:

- Detection capability.
- Localisation accuracy.
- Quality of diagnostic evidence.
- Execution time.
- Memory requirements.
- Behaviour across different experimental conditions.

### Phase 6: Comparative Analysis

The proposed approach will be compared against selected baselines using the same experimental conditions wherever possible.

The comparison will examine:

- Correctly identified cases.
- Missed cases.
- False positives.
- Localisation errors.
- Computational overhead.
- Generalisation across tested scenarios.

### Phase 7: Result Interpretation

The results will be analysed to determine:

- Whether the research hypothesis is supported.
- Whether the proposed method addresses the identified limitation.
- Whether improvements are consistent.
- Which scenarios remain difficult.
- What limitations affect the conclusions.

Negative results will be documented rather than excluded.

## 5. Potential Evaluation Metrics

The final metrics will depend on the research question.

|           Metric            |                                  Purpose                                       |
|-----------------------------|--------------------------------------------------------------------------------|
| Precision                   | Measures the proportion of predicted positive cases that are correct           |
| Recall                      | Measures the proportion of actual positive cases identified                    |
| F1-score                    | Balances precision and recall                                                  |
| Accuracy                    | Measures overall classification correctness                                    |
| Top-k localisation accuracy | Measures whether the actual fault location appears among the top-k predictions |
| False-positive rate         | Measures incorrect positive predictions                                        |
| Execution time              | Measures computational runtime                                                 |
| Memory usage                | Measures resource consumption                                                  |

Not every metric will necessarily be applicable to the final study.

## 6. Experimental Reproducibility

The experiments will maintain:

- Dataset source and version.
- Software and library versions.
- Experimental configurations.
- Random seeds where applicable.
- Fault-generation procedures.
- Baseline configurations.
- Evaluation scripts.
- Raw and processed results.

All experimental procedures should be repeatable.

## 7. Computing Constraints

The experimental design will consider the available local computing environment.

Priority will be given to:

- Small and medium-sized datasets.
- Efficient Python implementations.
- CPU-compatible experiments where possible.
- Limited and controlled repeated executions.
- Memory-efficient data processing.

Large-scale experiments will be considered only if they are necessary and feasible.

## 8. Result Storage

Experimental outputs will be maintained in the "results/" directory.

The following may be stored after experiments begin:

- Raw experimental measurements.
- Processed evaluation results.
- Comparison tables.
- Visualisations.
- Experiment configurations.
- Error analysis.
- Reproducibility notes.

No placeholder performance values will be presented as actual results.

## 9. Expected Deliverables

The completed experimental study is expected to produce:

1. A clearly defined research problem.
2. A reproducible experimental setup.
3. Documented baseline implementations.
4. A proposed approach, if justified by the research gap.
5. Quantitative evaluation results.
6. Comparative analysis.
7. Error and failure-case analysis.
8. A discussion of limitations and threats to validity.

## 10. Current Status

The experimental plan is preliminary.

Experiments will begin only after the research question, dataset, baselines, and methodology have been established.
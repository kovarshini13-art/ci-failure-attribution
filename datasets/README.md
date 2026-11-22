# Dataset Documentation

## 1. Purpose

This directory will contain datasets used for research and experimentation in machine learning pipeline reliability and debugging.
The final research question and experimental requirements have not yet been established. Therefore, no dataset has been selected or downloaded at this stage.

## 2. Dataset Selection Criteria

Datasets will be selected according to the following criteria:

1. Relevance to the validated research question.
2. Public availability and accessibility.
3. Clear licensing and usage permissions.
4. Sufficient data quality and documentation.
5. Suitability for reproducible experiments.
6. Compatibility with the available computing resources.
7. Availability of appropriate labels or ground truth, where required.

## 3. Potential Dataset Sources

The following sources may be investigated after the research problem is finalised:

| Source                         | Potential Use                                                  |
|--------------------------------|----------------------------------------------------------------|
| OpenML                         | Public machine learning datasets and experiments               |
| UCI Machine Learning Repository| Benchmark datasets                                             |
| Hugging Face Datasets          | Public datasets for machine learning                           |
| Kaggle                         | Public datasets, subject to licensing and access conditions    |
| Existing research benchmarks   | Reproducible evaluation of pipeline behaviour                  |

These are potential sources, not confirmed selections.

## 4. Dataset Categories Under Investigation

Depending on the final research question, relevant data may include:

- Structured tabular datasets.
- Data used in preprocessing pipelines.
- Training and inference datasets.
- Pipeline execution records.
- Transformation metadata.
- Controlled synthetic datasets.
- Existing machine learning debugging benchmarks.

## 5. Data Preparation

Once datasets are selected, the following procedures will be documented:

1. Dataset source and download information.
2. Original file format and size.
3. Feature and target descriptions.
4. Missing-value analysis.
5. Duplicate-record analysis.
6. Data-type validation.
7. Preprocessing operations.
8. Train, validation, and test separation, where applicable.

Any modifications to the original dataset will be recorded.

## 6. Synthetic Experimental Data

If the final methodology requires controlled fault injection, synthetic experimental data may be generated.

Such data will be used to evaluate specific, predefined fault scenarios.

The documentation will include:

- Fault type.
- Fault-generation procedure.
- Affected data or pipeline operation.
- Expected behaviour.
- Ground-truth fault location.
- Expected downstream effect.

Synthetic data will be clearly distinguished from naturally occurring data.

## 7. Directory Structure

The directory may eventually contain:

datasets/
│
├── README.md
│
├── raw/
│
├── processed/
│
├── synthetic/
│
└── metadata/


The subdirectories will be created only when required by the selected experimental design.

Large datasets will not be committed directly to GitHub unless their size and licensing permit it. Dataset download instructions, source references, and checksums may be maintained instead.

## 8. Data Integrity and Reproducibility

The following practices will be followed:

- Preserve original datasets wherever possible.
- Document all preprocessing steps.
- Record dataset versions and sources.
- Use consistent data splits.
- Avoid accidental data leakage.
- Maintain reproducible data-generation scripts.
- Record random seeds where applicable.

## 9. Current Status

|         Component          |          Status         |
|----------------------------|-------------------------|
| Dataset sources identified | Initial list prepared   |
| Final dataset selected     | Pending                 | 
| Dataset downloaded         | Not started             |
| Data preprocessing         | Not started             |
| Synthetic fault generation | Pending research design |
| Dataset validation         | Pending                 |
| Experimental data ready    | No                      |

## 10. Conclusion

Dataset selection will take place only after the research question and experimental requirements have been validated.

The purpose of this directory is to maintain transparent, reproducible, and well-documented experimental data.
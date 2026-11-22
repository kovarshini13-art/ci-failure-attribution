Literature Review
1. Introduction
Continuous Integration (CI) systems are an important part of modern software development. They automatically build, test and validate software changes. However, CI pipelines frequently encounter failures caused by software defects, flaky tests, configuration problems, dependency issues, environmental differences and infrastructure failures.

Understanding the causes of these failures is important because repeated or unexplained failures can delay development, increase debugging effort and reduce confidence in automated testing.

Several research studies and tools already investigate CI failure detection, flaky-test identification, log analysis and automated root-cause diagnosis. Therefore, a new research contribution must be evaluated against existing approaches rather than simply developing another failure-diagnosis tool.

This literature review initially investigates CI failure diagnosis and subsequently examines machine learning pipeline debugging as a potential alternative research direction.

The objectives of this review are:
- Identify relevant research publications.
- Examine existing methodologies, datasets and findings.
- Study available research implementations and tools.
- Identify limitations in existing approaches.
- Determine whether a specific, measurable research gap exists.
2. Existing Research
2.1 Research on Continuous Integration Failure Diagnosis
Paper 01: Test Alert Snooze: An Empirical Study of Consecutive Test Failures on CI (2026)
Authors: Ayane Shirakawa, Tatsuya Shirai, Yutaro Kashiwa, Masanari Kondo, Yasutaka Kamei and Hajimu Iida.

Publication: ESEM 2026.

DOI: https://doi.org/10.4230/LIPIcs.ESEM.2026.24

Research Objective:

To empirically investigate persistent test failures across consecutive software revisions in continuous integration environments.

Dataset:

27 open-source Python and Java projects using GitHub Actions, observed over a 90-day period.

Methodology:
- Collection of GitHub Actions execution histories.
- Extraction of individual test failures from CI logs.
- Identification of consecutive test failures.
- Analysis of commit histories and resolution activities.
Key Findings:
- 42.9% of observed test failures belonged to persistent failure episodes.
- Median persistence was two consecutive revisions.
- Median persistence duration was approximately one day.
- Some extreme cases persisted across 11 commits and 16 days.
- Only a small proportion of developer activity during snooze periods involved fixing the failures.
Limitations:
- Limited number of projects exhibiting persistent failures.
- Restricted to Python and Java projects using GitHub Actions.
- Failure persistence was measured without determining the underlying failure cause.
- The study did not directly distinguish flaky tests from genuine software regressions.
Relevance to Our Research:

This paper establishes the existence and industry relevance of persistent CI test failures. It provides a foundation for investigating whether individual failures within persistent episodes can be attributed to their underlying causes.

Research Status: Reviewed.
Paper 02: LogSage: An LLM-Based Framework for CI/CD Failure Detection and Remediation with Industrial Validation (2025)
Authors: Weiyuan Xu, Juntao Luo, Tao Huang, Kaixin Sui, Jie Geng, Qijun Ma, Isami Akasaka, Xiaoxue Shi, Jing Tang and Peng Cai.

Publication: 40th IEEE/ACM International Conference on Automated Software Engineering (ASE 2025).

DOI: https://doi.org/10.1109/ASE63991.2025.00310

Research Objective:

To develop an LLM-based framework for diagnosing and remediating CI/CD pipeline failures.

Dataset:

A curated benchmark of 367 GitHub CI/CD failures, with additional industrial validation at ByteDance.

Methodology:
- CI log preprocessing and noise removal.
- LLM-based root-cause analysis.
- Retrieval-Augmented Generation for historical fix retrieval.
- Tool calling for automated remediation.
Key Findings:
- More than 98% precision in the reported RCA benchmark.
- Near-perfect recall in the reported evaluation.
- More than 1.07 million industrial executions processed.
- More than 80% end-to-end precision in the industrial deployment.
Limitations and Research Considerations:

The general CI/CD diagnosis and automated remediation problem is already substantially investigated. Any new contribution must demonstrate a clearly differentiated research question, evaluation method or capability.

Relevance to Our Research:

This paper is a critical baseline for evaluating whether a proposed persistent test-failure attribution approach offers anything beyond existing CI/CD root-cause diagnosis systems.

Research Status: Reviewed.
Paper 03: Systemic Flakiness: A Study of Flaky Test Failure Co-Occurrence Using Java and Python Projects (2026)
Authors: Owain Parry, Gregory M. Kapfhammer, Michael Hilton and Phil McMinn.

Publication: IEEE Transactions on Software Engineering, 2026.

DOI: https://doi.org/10.1109/TSE.2026.3750452

Research Objective:

To investigate whether flaky test failures co-occur across multiple test cases due to shared underlying causes.

Dataset:

36 open-source Java and Python projects with repeated test-suite executions.

Methodology:
- Collection of repeated test execution results.
- Clustering of flaky tests based on failure co-occurrence.
- Analysis of test execution rerun budgets.
- Machine learning to predict failure co-occurrence.
- Qualitative investigation of shared failure causes.
Key Findings:
- 77% of flaky tests belonged to a cluster.
- Mean cluster size was 21.1.
- Extra Trees achieved a mean R² of 0.79 for predicting failure co-occurrence.
Identified Limitations and Considerations:
- Failure co-occurrence does not necessarily establish causal relationships.
- Clusters only partially approximate the full-run clusters under reduced rerun budgets.
- Further investigation is needed to establish how predicted relationships translate into actionable diagnosis.
Relevance to Our Research:

This work directly overlaps with ML-based identification of related flaky test failures. Any proposed research must distinguish its failure-attribution objective from existing co-occurrence prediction.

Research Status: Reviewed.
Paper 04: An Empirical Study of Detected and Undetected Flaky Test Failures in Real-World CI Pipelines (2026)
Authors: Fabian Leinen, Martin Gruber, Saadet Sena Erdogan, Andreas Stahlbauer and Alexander Pretschner.

Publication: IEEE Transactions on Software Engineering, 2026.

DOI: https://doi.org/10.1109/TSE.2026.3729363

Research Objective:

To investigate flaky test failures that remain undetected by conventional CI retry mechanisms.

Dataset:
- 8.8 billion test executions from four industry-scale projects.
- The released dataset contains approximately 154,000 flaky test cases and 1.7 million flaky failures.
Methodology:
- Collection of real-world CI test execution records.
- Validation of apparently deterministic failures through reruns.
- Analysis of temporal failure patterns.
- Investigation of test-level and environment-specific flakiness.
- Manual root-cause analysis of selected temporal spikes.
Key Findings:
- Undetected flaky failures accounted for 9.8–16.3% of failed pipeline runs in the studied projects.
- Flakiness rates varied by up to 3x across environments.
- Certain code changes and test reordering triggered temporary increases in flaky failures.
- A small subset of test cases accounted for a substantial proportion of failures.
Dataset Availability:

https://github.com/tum-i4/flaky-tests-in-ci

Limitations and Research Considerations:
- The study covers four industry-scale projects.
- The full dataset requires approximately 430 GB of storage.
- Full replication requires substantial computing resources.
- Root-cause analysis of temporal spikes was performed manually rather than establishing a general automated attribution solution.
Relevance to Our Research:

This work provides a substantial real-world dataset and directly overlaps with flaky-failure detection, temporal analysis, environmental effects and selected root-cause investigations. It must be treated as a major baseline.

Research Status: Reviewed.
Paper 05: How Far Are We from Detecting Flaky Tests? On the Limits of Code-Based Detection (2026)
Authors: Ömer Oktay Gültekin, Alexander Berndt, Jonathan Bell, Thomas Bach and Sebastian Baltes.

Publication: arXiv preprint, July 2026.

Paper: https://arxiv.org/abs/2607.09345

Research Objective:

To investigate the limitations of code-based flaky-test detection and evaluate whether existing machine learning detectors generalise to unseen software projects.

Datasets:
- C-IDoFT: 54,468 unit tests from 57 projects.
- FlakeCI: 86 confirmed flaky end-to-end tests from 26 repositories.
- More than 450,000 GitHub Actions CI runs mined during dataset construction.
Methodology:
- Reproduction of three existing flaky-test detectors.
- Controlled dataset construction.
- Repeated test executions.
- Project-disjoint model evaluation.
- Analysis of CI logs and runtime failure evidence.
- Manual root-cause categorisation of selected flaky tests.
Key Findings:
- Existing detector performance was substantially affected by dataset shortcuts and evaluation protocols.
- Code-based detectors did not meaningfully outperform simple baselines on C-IDoFT under project-disjoint evaluation.
- Causes could be attributed for 42% of the 86 FlakeCI tests using test code and CI logs.
- The remaining 58% required additional execution evidence.
Limitations and Research Considerations:
- FlakeCI contains only 86 confirmed flaky end-to-end tests.
- Root-cause categorisation was performed manually.
- Test code and CI logs alone were insufficient for most cases.
- Execution evidence and environment perturbation are identified as important directions for further investigation.
Relevance to Our Research:

This paper directly overlaps with failure-level classification and CI failure diagnosis. It also highlights the limitations of relying only on static code and logs. A new project must demonstrate a more specific contribution than general CI failure classification.

Research Status: Reviewed.
Paper 06: Why Do GitHub Actions Workflows Fail? An Empirical Study (2026)
Authors: Lianyu Zheng, Shuang Li, Xi Huang, Jiangnan Huang, Bin Lin, Jinfu Chen and Jifeng Xuan.

Publication: ACM Transactions on Software Engineering and Methodology, 2026.

DOI: https://doi.org/10.1145/3749371

Research Objective:

To identify and classify the root causes of GitHub Actions workflow failures in real-world open-source projects.

Dataset:
- 260 open-source Java projects.
- 15,355 valid workflow failure records collected.
- 375 failed workflow executions manually analysed.
- 151 valid developer survey responses.
Methodology:
- Collection of GitHub Actions execution logs.
- Random sampling of failed workflow executions.
- Independent manual annotation by researchers.
- Card-sorting methodology for failure classification.
- Developer survey to validate the failure taxonomy.
Key Findings:
- 16 distinct workflow failure categories were identified.
- 32% of analysed failures were software testing failures.
- 84% were attributed to project-related factors.
- 370 of 375 sampled failures occurred during CI.
Limitations:
- Focused on Java projects using GitHub Actions.
- Detailed manual analysis was limited to 375 failures.
- Developed a failure taxonomy rather than a validated automated ML root-cause attribution system.
- Survey response rate was relatively low.
Relevance to Our Research:

This study establishes a comprehensive taxonomy of CI workflow failures. It provides an important baseline for distinguishing workflow-level diagnosis from individual test-level failure attribution.

Research Status: Reviewed.
2.2 Existing Tools and Public Implementations
1. ci-doctor
Repository: https://github.com/ci-doctor/ci-doctor

Purpose:

Automated investigation of GitHub, GitLab and Forgejo CI failures.

Capabilities:
- Deterministic failure-phase attribution.
- Optional LLM-based explanations.
- Evidence-backed diagnostic reports.
- Suggested remediation.
Relevance:

Directly overlaps with general-purpose CI failure diagnosis.

Research Consideration:

Repository availability does not establish peer-reviewed validation or widespread industry adoption. Its actual performance must be evaluated independently.
2. GitHub Agentic Workflows - CI Doctor
Repository: https://github.com/githubnext/agentics

Purpose:

Agent-based investigation of failed GitHub Actions workflows.

Capabilities:
- Failure-log analysis.
- Correlation with commits and workflow configuration.
- Root-cause recommendations.
- Investigation issue creation and updates.
Relevance:

Demonstrates an existing agentic CI diagnosis workflow.
3. LogSage
Paper: https://arxiv.org/abs/2506.03691

Purpose:

LLM-based CI/CD failure diagnosis and remediation.

Capabilities:
- Log preprocessing.
- Root-cause analysis.
- Retrieval-Augmented Generation.
- Automated remediation.
Relevance:

Major overlap with AI-based CI failure diagnosis.
4. LogSieve
Paper: https://doi.org/10.1145/3793302.3793380

Purpose:

Task-aware reduction of CI logs for efficient LLM analysis.

Capabilities:
- Semantic log filtering.
- Reduction of irrelevant log lines.
- Preservation of diagnostic information.
- Embedding-based relevance classification.
Relevance:

Existing work on intelligent CI log preprocessing.
5. LogDx-CI
Website: https://logdx-bench.github.io/

Repository: https://github.com/eyuansu62/LogDx

Purpose:

Benchmarking CI log reduction methods for downstream root-cause diagnosis.

Capabilities:
- Real CI failure examples.
- Multiple log-context methods.
- Cross-model diagnosis evaluation.
- Holdout and stress-test cases.
Relevance:

Provides an existing benchmark for evaluating AI-based CI diagnosis.

Research Consideration:

The benchmark's ground-truth construction and validation process must be considered when interpreting its results. Its AI-assisted annotations should not automatically be treated as independently human-validated ground truth.
6. FailSift
Marketplace: https://github.com/marketplace/actions/failsift-ci-failure-diagnosis

Purpose:

Local CI log analysis and root-cause reporting.

Relevance:

Demonstrates an existing implementation of automated failure triage.
2.3 Research on Machine Learning Pipeline Debugging
Paper 07: A Systematic Survey on Debugging Techniques for Machine Learning Systems (2025)
Authors: Thanh-Dat Nguyen, Haoye Tian, Bach Le, Patanamon Thongtanunam and Shane McIntosh.

Publication: arXiv preprint, 2025.

Paper: https://arxiv.org/abs/2503.03158

Research Objective:

To systematically investigate existing debugging techniques for machine learning systems, identify recurring debugging challenges and evaluate how well current techniques address developer needs.

Research Coverage:

The survey examined 96 research papers:
- 62 papers in the open-coding set.
- 34 papers in the validation set.
The researchers initially collected a larger set of publications before applying their selection and analysis process.

Methodology:
- Systematic literature review.
- Identification and classification of ML debugging challenges.
- Analysis of existing debugging techniques.
- Comparison of research solutions against developer-reported problems.
- Investigation of practical debugging problems reported by developers.
Key Findings:
- 46.9% of identified ML debugging challenges remained unresolved or unmentioned by the surveyed techniques.
- The study identified a gap between practical developer problems and existing research solutions.
- The authors identified multiple challenges requiring further investigation.
Limitations and Research Considerations:
- The existence of unresolved challenges does not automatically establish that a particular new technique is novel.
- Each potential challenge must be compared against closely related research and existing tools.
- The survey's identified challenges need to be examined individually before selecting a research problem.
Relevance to Our Research:

This survey provides a foundation for investigating ML pipeline debugging. It motivates a closer examination of specific problems involving data transformations, pipeline behaviour and debugging evidence.

Research Status: Initial review completed.
2.4 Existing Research Systems for ML Pipeline Debugging
1. mlinspect
Repository: https://github.com/stefan-grafberger/mlinspect

Purpose:

Inspection and debugging of machine learning pipelines.

Research Background:

The system is associated with research on data distribution debugging in ML pipelines.

Capabilities and Research Relevance:
- Represents ML pipelines as dataflow graphs.
- Inspects data transformations.
- Tracks information through pipeline operations.
- Supports investigation of data distribution problems.
Relevance:

This is an important existing baseline for data-processing observability and pipeline debugging.
2. DataScope
Repository: https://github.com/easeml/datascope

Research Paper:

DataScope: Data Debugging with Shapley Importance over End-to-End ML Pipelines.

Publication: ICLR 2024.

Purpose:

Data valuation and identification of problematic training examples.

Research Relevance:
- Investigates the importance of individual training examples.
- Uses data valuation to support ML pipeline debugging.
- Demonstrates existing techniques for investigating the contribution of training data to machine learning outcomes.
Relevance:

A potential new contribution involving problematic training examples must be compared against DataScope and related data-debugging methods.
3. AutoLineage
Research Type: 2026 preprint and software implementation.

Purpose:

Operation-level data lineage for Python machine learning pipelines.

Research Relevance:
- Tracks dataframe transformations.
- Investigates lineage across Python ML pipelines.
- Provides a potential implementation to examine when studying data transformation observability.
Research Considerations:
- It is a preprint/software implementation, not an established peer-reviewed research result.
- Implementation limitations and supported libraries must be examined before using it as a baseline.
2.5 Additional Closely Related Research
Paper 08: From Diagnosis to Repair: A Model-Driven Framework for Root Cause Analysis of Machine Learning Pipelines (2026)
Authors: Emmanuel Charleson Dapaah and Jens Grabowski.

Publication: Innovations in Systems and Software Engineering, Volume 22, Article 17 (2026).

Publication Date: 19 June 2026.

DOI: https://doi.org/10.1007/s11334-026-00642-8

Research Objective:

To develop a model-driven framework for identifying factors associated with machine-learning pipeline performance and estimating the effects of potential hyperparameter interventions.

Dataset and Experimental Setup:
- 270 OpenML datasets.
- 300 hyperparameter configurations.
- 81,000 pipeline runs for each evaluated model family.
- Decision Tree and Multilayer Perceptron model families.
- Balanced Accuracy used as the performance metric.
Methodology:
- Extraction of dataset-complexity descriptors.
- Representation of learner hyperparameters.
- Construction of a meta-dataset from pipeline execution results.
- Explainable Boosting Machine (EBM) for interpretable performance prediction.
- Local additive attribution for root-cause analysis.
- Structural Causal Model (SCM) for estimating hyperparameter interventions.
- Empirical validation through pipeline reruns.
Key Findings:
- Reported MAE was 0.080 for Decision Trees and 0.087 for MLPs.
- The framework uses structured dataset and configuration descriptors to predict pipeline performance.
- Local additive attributions are used to identify factors contributing to individual predicted outcomes.
- The intervention module estimates post-intervention performance for selected hyperparameter changes.
- The paper reports a mean absolute intervention error of approximately 0.036.
Limitations and Research Considerations:
- Evaluation covers only Decision Trees and MLPs.
- The descriptor set is restricted to selected dataset-complexity features and hyperparameters.
- Results may not generalise to other model families or richer configuration spaces.
- Causal intervention estimates depend on the specified structural causal model and its assumptions.
Relevance to Our Research:

This publication directly overlaps with ML pipeline performance diagnosis, root-cause attribution and hyperparameter intervention. A proposed project involving prediction of pipeline performance, identification of problematic hyperparameters or counterfactual configuration recommendations would need to demonstrate a clearly differentiated contribution.

Research Status: Publication and methodology reviewed; independent reproduction not performed.

Research Implementation:

https://gitlab.gwdg.de/emmanuelcharleson.dapaah/ml-pipeline-rca-diagnosis-to-repair
Paper 09: Complaint-Driven Training Data Debugging for Query 2.0 (2020)
Authors: Weiyuan Wu, Lampros Flokas, Eugene Wu and Jiannan Wang.

Publication: ACM SIGMOD International Conference on Management of Data (SIGMOD 2020).

DOI: https://doi.org/10.1145/3318464.3389696

Research Objective:

To identify problematic training examples that may have caused unexpected outputs in machine-learning-powered database queries.

Methodology:
- Users specify complaints about intermediate or final inference-query outputs.
- Influence-function-based methods estimate the contribution of training examples to the complaint.
- The system searches for a small set of training examples whose removal would resolve the complaint.
- The paper studies heuristic approaches intended to avoid exponential retraining.
Key Contribution:

Rain connects unexpected downstream query results with potentially problematic training examples. It establishes complaint-driven training-data debugging as an existing research direction.

Relevance to Our Research:

A proposed approach involving downstream model-output complaints and training-example attribution must be compared against Rain and its influence-function-based methods.

Research Status: Related publication identified and abstract reviewed.

Paper:

https://arxiv.org/abs/2004.05722
Paper 10: Complaint-Driven Training Data Debugging at Interactive Speeds (2022)
Authors: Lampros Flokas, Weiyuan Wu, Yejia Liu, Jiannan Wang, Nakul Verma and Eugene Wu.

Publication: ACM SIGMOD International Conference on Management of Data (SIGMOD 2022), pages 369–383.

DOI: https://doi.org/10.1145/3514221.3517849

Research Objective:

To improve the scalability and execution speed of complaint-driven training-data debugging introduced by Rain.

Methodology:
- Precomputation of information that is independent of a particular complaint.
- Optimisation of influence-based debugging computations.
- Support for cases where the queried database is known in advance.
- Optimisations for standing queries over streaming databases.
Key Findings:
- The original Rain approach can be expensive for large models because of second-order derivative computations.
- Rain++ uses precomputation to reduce the dependence of debugging latency on model size.
- The paper reports interactive debugging latency of approximately 1 ms on evaluated models with millions of parameters.
Relevance to Our Research:

This work demonstrates that training-data debugging has already been studied for scalability and interactive response. Any proposed data-error localisation method must be compared against Rain++ as well as Rain.

Research Status: Related publication identified and abstract reviewed.
Paper 11: Capturing End-to-End Provenance for Machine Learning Pipelines (2025)
Authors: Marius Schlegel and Kai-Uwe Sattler.

Publication: Information Systems, Volume 132, July 2025, Article 102495.

DOI: https://doi.org/10.1016/j.is.2024.102495

Research Objective:

To capture end-to-end provenance information across machine-learning pipeline development workflows by combining MLflow and Git activities.

Research Contribution:
- Introduces a PROV-compliant provenance model.
- Captures relationships between ML pipeline artifacts.
- Tracks data, model, metadata and software artifacts.
- Presents MLflow2PROV for extracting provenance graphs from MLflow and Git resources.
- Supports querying and analysing collected provenance information.
Limitations Identified by the Paper:

The paper identifies incomplete traces, coarse-grained provenance and limited query capabilities in existing artifact-management systems as problems motivating its approach.

Relevance to Our Research:

This publication is important when investigating whether existing pipeline lineage systems can identify the operation or change associated with an unexpected downstream result. Provenance capture should not be mistaken for automatic fault diagnosis; the distinction must be tested against the actual capabilities of the tool.

Research Status: Publication and implementation identified.

Implementation:

https://github.com/mariusschlegel/mlflow2prov
2.6 Additional Existing System: ArgusEyes
Proactively Screening Machine Learning Pipelines with ArgusEyes (2023)
Authors: Sebastian Schelter, Stefan Grafberger, Shubha Guha, Bojan Karlaš and Ce Zhang.

Publication: ACM SIGMOD '23 Companion, pages 91–94.

DOI: https://doi.org/10.1145/3555041.3589682

Purpose:

ArgusEyes enables data scientists to proactively screen machine-learning pipelines for data-related issues as part of continuous integration.

Capabilities Demonstrated:
- Instruments and executes ML pipelines.
- Screens pipelines for declaratively specified issues.
- Analyses data artifacts and their provenance.
- Demonstrates detection of mislabeled images.
- Demonstrates detection of data leakage.
- Demonstrates screening for fairness violations.
Relevance to Our Research:

ArgusEyes is a significant existing baseline for proactive ML pipeline screening. A proposed system that checks preprocessing stages, data leakage, label quality or fairness must be compared with its documented capabilities and implementation.

Research Status: Peer-reviewed conference companion demonstration identified.

Paper:

https://ssc.io/pdf/arguseyes-demo.pdf

Implementation:

https://github.com/amsterdata/arguseyes-demo
2.7 Research Tutorial: Navigating Data Errors in Machine Learning Pipelines
Event: ACM SIGMOD 2025 Tutorial.

Presenters: Bojan Karlaš, Babak Salimi and Sebastian Schelter.

Resource:

https://navigating-data-errors.github.io/

Research Scope:

The tutorial consolidates research on data errors throughout the machine-learning lifecycle.

Its topics include:
1. Identifying data errors using data attribution.
2. Debugging errors across ML pipelines.
3. Prioritising impactful data repairs.
4. Reasoning about uncertainty when data errors cannot be fully resolved.
5. Understanding how upstream data errors affect downstream predictions.
Research Relevance:

This tutorial is a useful consolidated entry point to related research on data quality, data attribution and pipeline debugging. It demonstrates that data-error identification and repair are established research areas and that a new contribution must be more specific than general data-quality checking.

Research Status: Tutorial and its linked bibliography identified.
2.8 Implications of the Additional Literature
The additional publications establish substantial overlap in the following areas:
Research Problem	Existing Research
ML pipeline performance prediction	Dapaah and Grabowski (2026)
Pipeline-level root-cause attribution	Dapaah and Grabowski (2026)
Hyperparameter intervention	Dapaah and Grabowski (2026)
Training-data error attribution	Rain (2020)
Scalable training-data debugging	Rain++ (2022)
End-to-end pipeline provenance	MLflow2PROV (2025)
Proactive pipeline screening	ArgusEyes (2023)
Data-error identification and repair	SIGMOD 2025 tutorial


Preliminary Research Assessment:

The following broad ideas cannot independently be claimed as novel:
- Predicting ML pipeline performance.
- Identifying problematic hyperparameters.
- Explaining model-performance failures using dataset descriptors.
- Recommending configuration changes.
- Identifying influential training examples.
- Tracking data lineage.
- Screening for data leakage, label errors or fairness issues.
- Detecting general data-quality problems in ML pipelines.
A potential research contribution must identify a more specific technical limitation that is not adequately addressed by these existing approaches.

Research Status: Additional related literature identified. Detailed comparative analysis pending.
3. Comparison of Existing Studies

3.1 Comparison of CI Research
|                  Research                   |            Main Focus             |           Methodology              |            Important Contribution             |

|---------------------------------------------|-----------------------------------|------------------------------------|-----------------------------------------------|

|Test Alert Snooze (2026)                     |Persistent test failures           |Empirical CI analysis               |Studies consecutive test failure episodes      |

|LogSage (2025)                               |CI/CD diagnosis and remediation    |LLM, RAG and tool calling           |Automated diagnosis and remediation            |

|Systemic Flakiness (2026)                    |Flaky-test co-occurrence           |Clustering and ML                   |Identifies relationships between flaky tests   |

|Detected and Undetected Flaky Failures (2026)|Undetected flakiness               |Large-scale execution analysis      |Studies flakiness across real-worldenvironments|

|Limits of Code-Based Detection (2026)        |Flaky-test detection generalisation|Project-disjoint evaluation         |Demonstrates limitations of code-baseddetectors|

| Why Do GitHub Actions Workflows Fail? (2026)|Workflow failure causes            |Empirical study and developer survey|Develops a workflow failure taxonomy           |


3.2 Comparison of ML Debugging Research
|       Research/System     |          Main Focus           |          Existing Capability                 |             Research Relevance                 |

|---------------------------|-------------------------------|----------------------------------------------|------------------------------------------------|

| ML Debugging Survey (2025)|ML debugging research landscape|Classifies existing debugging challenges      |Helps identify candidate research gaps          |

| mlinspect                 |ML pipeline inspection         |Dataflow and transformation inspection        |Baseline for pipeline observability             | 

| DataScope (2024)          |Data debugging                 |Data valuation and training-example importance|Baseline for data-centric debugging             |

| AutoLineage (2026)        |Data lineage                   |Operation-level transformation tracking       |Related implementation for lineage investigation|

3.3 Overall Comparison
The reviewed research covers two major areas.

Continuous Integration Reliability

Existing studies investigate:
- Persistent test failures.
- Flaky-test detection.
- Failure co-occurrence.
- CI workflow failure classification.
- LLM-based root-cause analysis.
- Intelligent CI log preprocessing.
- Automated CI failure remediation.
The research publications and public implementations demonstrate that general-purpose CI failure diagnosis is already an active research and development area.

Machine Learning Pipeline Reliability

Existing research investigates:
- ML pipeline debugging.
- Data lineage and transformation inspection.
- Data quality and data valuation.
- Detection of pipeline-related issues.
- Debugging challenges reported by developers.
This area also contains established tools and research approaches. Therefore, a potential contribution must be compared with existing pipeline inspection, data validation and debugging techniques.
4. Research Gaps Identified
Research Status: Preliminary. No final research gap has been established.

The reviewed literature suggests several candidate areas for further investigation.
4.1 Silent Semantic Errors in ML Preprocessing Pipelines
A preprocessing operation may execute successfully while producing data that does not represent the intended meaning.

Potential investigation:
- Incorrect transformations that do not raise runtime exceptions.
- Unexpected changes in feature distributions.
- Differences between intended and actual preprocessing behaviour.
Existing data validation and pipeline inspection techniques must be examined before claiming a gap.
4.2 Errors Introduced by Interactions Between Multiple Data Transformations
An individual transformation may appear valid while a sequence of transformations introduces an unexpected result.

Potential investigation:
- Interactions between preprocessing operations.
- Propagation of unexpected values through pipeline stages.
- Identification of the transformation responsible for a downstream problem.
Existing lineage and dataflow debugging systems must be compared against this idea.
4.3 Differences Between Training-Time and Inference-Time Data Transformations
Machine learning systems may process training and inference data through different execution paths.

Potential investigation:
- Inconsistent preprocessing operations.
- Differences in feature representation.
- Transformation inconsistencies between training and deployment.
Existing work on training-serving skew, feature consistency and ML monitoring must be reviewed before treating this as a research gap.
4.4 Limitations of Existing Pipeline Inspection and Validation Tools
Existing tools provide different levels of visibility into data transformations and pipeline behaviour.

Potential investigation:
- What information existing tools capture.
- Which failure types they can identify.
- Whether they can localise the source of a silent error.
- Whether their outputs provide sufficient evidence for debugging.
A comparative evaluation is required before proposing an additional technique.
4.5 Reproducible Evaluation of ML Pipeline Debugging Methods
A research contribution must be evaluated using reproducible experiments and measurable outcomes.

Potential investigation:
- Availability of public datasets.
- Reproducible synthetic fault injection.
- Comparison against established baselines.
- Measurement of detection and localisation performance.
Research Gap Validation Requirements
Before selecting any of the candidate areas, the following must be completed:
1. Search for closely related peer-reviewed publications.
2. Examine relevant preprints and recent conference proceedings.
3. Inspect existing implementations and their documented capabilities.
4. Identify public datasets and reproducible benchmarks.
5. Define exactly what existing methods cannot accomplish.
6. Establish a measurable experimental contribution.
These candidate areas are investigation directions, not claims of novelty.
5. Proposed Research Contribution
Final research contribution: Not yet selected.

The current investigation focuses on machine learning pipeline reliability and the possibility of detecting specific silent data-processing errors.

The final research question will be selected only after completing the literature and implementation comparison.
5.1 Research Selection Criteria
The selected research problem must satisfy the following conditions:
- A clearly defined technical problem.
- A demonstrable limitation in existing approaches.
- A contribution beyond simply combining existing libraries.
- Availability of reproducible datasets or experimental data.
- A measurable evaluation methodology.
- Feasibility on the available computing resources.
- Practical relevance to software engineering or machine learning systems.
5.2 Experimental Requirements
The eventual project should include:
- A clearly defined research hypothesis.
- A reproducible dataset or experimental pipeline.
- Suitable baseline methods.
- A controlled experimental setup.
- Quantitative evaluation metrics.
- Analysis of failure cases.
- Limitations and threats to validity.
5.3 Expected Research Outcome
The expected outcome is a technically defensible research contribution supported by experiments.

No implementation, novelty claim or industry-impact claim will be made before the research gap is validated.
6. References
Continuous Integration and Flaky-Test Research
1. Shirakawa, A., Shirai, T., Kashiwa, Y., Kondo, M., Kamei, Y. and Iida, H. (2026). Test Alert Snooze: An Empirical Study of Consecutive Test Failures on CI. ESEM 2026.
   https://doi.org/10.4230/LIPIcs.ESEM.2026.24
2. Xu, W., Luo, J., Huang, T., Sui, K., Geng, J., Ma, Q., Akasaka, I., Shi, X., Tang, J. and Cai, P. (2025). LogSage: An LLM-Based Framework for CI/CD Failure Detection and Remediation with Industrial Validation. ASE 2025.
   https://doi.org/10.1109/ASE63991.2025.00310

   https://arxiv.org/abs/2506.03691
3. Parry, O., Kapfhammer, G. M., Hilton, M. and McMinn, P. (2026). Systemic Flakiness: A Study of Flaky Test Failure Co-Occurrence Using Java and Python Projects. IEEE Transactions on Software Engineering.
   https://doi.org/10.1109/TSE.2026.3750452
4. Leinen, F., Gruber, M., Erdogan, S. S., Stahlbauer, A. and Pretschner, A. (2026). An Empirical Study of Detected and Undetected Flaky Test Failures in Real-World CI Pipelines. IEEE Transactions on Software Engineering.
   https://doi.org/10.1109/TSE.2026.3729363

   Dataset: https://github.com/tum-i4/flaky-tests-in-ci
5. Gültekin, Ö. O., Berndt, A., Bell, J., Bach, T. and Baltes, S. (2026). How Far Are We from Detecting Flaky Tests? On the Limits of Code-Based Detection.
   https://arxiv.org/abs/2607.09345
6. Zheng, L., Li, S., Huang, X., Huang, J., Lin, B., Chen, J. and Xuan, J. (2026). Why Do GitHub Actions Workflows Fail? An Empirical Study. ACM Transactions on Software Engineering and Methodology.
   https://doi.org/10.1145/3749371
Machine Learning Pipeline Debugging Research
7. Nguyen, T.-D., Tian, H., Le, B., Thongtanunam, P. and McIntosh, S. (2025). A Systematic Survey on Debugging Techniques for Machine Learning Systems.
   https://arxiv.org/abs/2503.03158
8. Grafberger, S., Groth, P., Stoyanovich, J. and Schelter, S. (2022). Data Distribution Debugging in Machine Learning Pipelines. The VLDB Journal.
   https://doi.org/10.1007/s00778-021-00726-w
9. DataScope: Data Debugging with Shapley Importance over End-to-End ML Pipelines (2024). International Conference on Learning Representations (ICLR).
   https://github.com/easeml/datascope
Additional ML Pipeline Debugging Research
10. Dapaah, E. C. and Grabowski, J. (2026). From Diagnosis to Repair: A Model-Driven Framework for Root Cause Analysis of Machine Learning Pipelines. Innovations in Systems and Software Engineering, 22, Article 17.
    https://doi.org/10.1007/s11334-026-00642-8
11. Wu, W., Flokas, L., Wu, E. and Wang, J. (2020). Complaint-Driven Training Data Debugging for Query 2.0. ACM SIGMOD 2020.
    https://doi.org/10.1145/3318464.3389696
12. Flokas, L., Wu, W., Liu, Y., Wang, J., Verma, N. and Wu, E. (2022). Complaint-Driven Training Data Debugging at Interactive Speeds. ACM SIGMOD 2022.
    https://doi.org/10.1145/3514221.3517849
13. Schlegel, M. and Sattler, K.-U. (2025). Capturing End-to-End Provenance for Machine Learning Pipelines. Information Systems, 132, Article 102495.
    https://doi.org/10.1016/j.is.2024.102495
14. Schelter, S., Grafberger, S., Guha, S., Karlaš, B. and Zhang, C. (2023). Proactively Screening Machine Learning Pipelines with ArgusEyes. ACM SIGMOD '23 Companion, 91–94.
    https://doi.org/10.1145/3555041.3589682
15. Karlaš, B., Salimi, B. and Schelter, S. (2025). Navigating Data Errors in Machine Learning Pipelines: Identify, Debug, and Learn. ACM SIGMOD 2025 Tutorial.
    https://navigating-data-errors.github.io/
Existing Tools and Implementations
16. ci-doctor.
    https://github.com/ci-doctor/ci-doctor
17. GitHub Agentic Workflows.
    https://github.com/githubnext/agentics
18. LogSieve.
    https://doi.org/10.1145/3793302.3793380
19. LogDx-CI.
    https://logdx-bench.github.io/

    https://github.com/eyuansu62/LogDx
20. FailSift.
    https://github.com/marketplace/actions/failsift-ci-failure-diagnosis
21. mlinspect.
    https://github.com/stefan-grafberger/mlinspect
22. AutoLineage.
    Publication and implementation details require further verification before inclusion as a final academic reference.
7. Research Review Status
|               Area                  |            Current Status             |

|-------------------------------------|---------------------------------------|

| CI failure diagnosis literature     | Initial review completed              |

| Flaky-test research                 | Initial review completed              |

| Existing CI tools                   | Initial implementation scan completed |

| ML debugging survey                 | Initial review completed              |

| ML pipeline debugging tools         | Initial review completed              |

| Detailed ML research-gap validation | Pending                               |

| Dataset and benchmark selection     | Pending                               |

| Final research question             | Pending                               |

| Proposed methodology                | Pending                               |

| Experimental implementation         | Not started                           | 

Current Decision:

The original CI failure-attribution direction has substantial overlap with existing research and tools. Machine learning pipeline reliability is being investigated as an alternative direction, but it has not yet been established as a novel research problem.

The final project will be selected only after a sufficiently detailed comparison of existing research, implementations, datasets and experimental methods.
# NovaCred Credit Application Governance Analysis

## DEGO 2606 — Data Ecosystems and Governance in Organizations  
MSc Business Analytics | Nova SBE

Acting as a Data Governance Task Force, our team evaluates a credit application dataset from three connected perspectives: data quality, fairness in lending outcomes, and privacy and regulatory governance. The project is set in a credit approval context in which poor data quality, biased decision patterns, and weak governance controls would all create material operational, ethical, and regulatory risk.

Rather than treating these topics as separate exercises, the project approaches them as one governance problem. Weak input quality affects the credibility of fairness analysis, while fairness concerns and the handling of personal data raise broader obligations under GDPR and the EU AI Act.

## Team Members and Roles

| Name | Student Number | Role | Main Responsibility |
|---|---:|---|---|
| Eda Jülide Pürsün | 74935 | Product Lead | Repository documentation, project framing, presentation preparation, final integration |
| João Marques Roque | 73047 | Data Engineer | Data loading, cleaning logic, technical preparation of the dataset |
| Maddalena Manfredi | 71946 | Data Scientist | Bias and fairness analysis, interpretation of disparities and statistical results |
| Lucas Galilei | 70270 | Governance Officer | Privacy, GDPR, and policy-oriented governance layer |

## Repository Structure

| Path | Purpose |
|---|---|
| `Data/` | Project data resources |
| `Notebooks/01-data-quality.ipynb` | Data quality assessment and remediation logic |
| `Notebooks/02-bias-analysis.ipynb` | Fairness and bias analysis |
| `Notebooks/03-privacy-demo.ipynb` | Privacy, GDPR, and governance extension |
| `README.md` | Project overview and summary of findings |

## Analytical Workflow

The project is organised in three analytical layers.

The first layer evaluates whether the raw credit application data is sufficiently reliable for downstream use. Before fairness or governance conclusions can be drawn, the dataset must be assessed for completeness, validity, plausibility, and internal consistency.

The second layer investigates whether approval outcomes differ systematically across demographic groups. This part moves from data preparation into fairness assessment and asks whether the observed decisions raise potential bias concerns.

The third layer extends the analysis into privacy and governance. In a credit decision setting, analytical outputs alone are not enough. The broader decision pipeline must also be assessed in terms of accountability, lawful processing, minimisation, retention, documentation, and oversight.

## Executive Summary

The project shows that governance risks in credit decisioning cannot be reduced to model output alone. The data quality analysis finds that the dataset is usable for analysis, but affected by concentrated missingness, duplicate primary identifiers, and selected validity and formatting issues. A governance-oriented de-duplication step reduces the working dataset from 502 to 500 records by keeping the most complete record for duplicated application IDs.

The fairness analysis identifies meaningful disparities in approval outcomes across demographic groups. Female applicants receive approvals at a lower rate than male applicants, and the Disparate Impact ratio falls below the common four-fifths threshold. Age-based differences are also visible, with younger applicants showing weaker approval outcomes than the middle-age range. The strongest subgroup disparity appears among younger applicants.

Taken together, the project suggests that reliable records, fair treatment across groups, and defensible handling of personal data must be treated as interdependent requirements rather than separate workstreams.

## Dataset Overview

| Metric | Value |
|---|---:|
| Raw records | 502 |
| Records after de-duplication | 500 |
| Duplicate application IDs removed | 2 |
| Project focus areas | Data quality, fairness, privacy/governance |

## Notebook 1 — Data Quality Assessment

The first notebook evaluates whether the raw credit application data is sufficiently robust for downstream use. The nested JSON structure is flattened into a tabular format and then assessed across key quality dimensions including completeness, uniqueness, validity, plausibility, and cross-field consistency.

A major strength of this notebook is its governance-aware remediation logic. High-missingness columns are removed where they add little analytical value, while governance-sensitive fields such as identifiers, PII attributes, timestamps, decision outcomes, and rejection reasons are intentionally not imputed. Missingness indicators are created before imputation in order to preserve transparency around original data limitations.

### Data Quality Highlights

| Area | Main Finding | Governance Interpretation |
|---|---|---|
| Uniqueness | Duplicate `_id` values were conflicting, not identical | Record integrity issue rather than simple ingestion duplication |
| Remediation | Most complete record per duplicated `_id` retained | Traceability preserved while restoring primary-key uniqueness |
| Missingness | Columns with ≥90% missing values removed | Weak capture governance or low analytical value |
| Imputation policy | Governance-sensitive fields were not imputed | Prevents fabrication of audit-relevant information |

### Data Quality Summary Table

| Metric | Value |
|---|---:|
| Raw dataset size | 502 |
| Final dataset size after de-duplication | 500 |
| Duplicate records removed | 2 |
| High-missingness threshold | 90% |
| Governance-sensitive fields imputed | No |

## Notebook 2 — Bias and Fairness Analysis

The second notebook investigates whether loan approval outcomes differ systematically across demographic groups. The analysis focuses primarily on gender and age and uses approval-rate comparisons, Disparate Impact ratios, chi-square testing, subgroup analysis, and exploratory proxy-risk checks.

The clearest fairness signal concerns gender. Female applicants have a lower approval rate than male applicants, and the resulting DI ratio falls below the four-fifths threshold. The chi-square test further indicates that this disparity is statistically significant.

Age-based patterns are also visible. The notebook reports that applicants aged 18–35 show significantly weaker approval outcomes than those aged 36–65. The interaction analysis suggests that the gender gap is especially pronounced among younger applicants, which makes subgroup-level fairness monitoring particularly relevant.

### Fairness Highlights

| Test / Metric | Result | Interpretation |
|---|---:|---|
| Female approval rate | 127 / 251 ≈ 50.6% | Lower than male approval rate |
| Male approval rate | 163 / 248 ≈ 65.7% | Higher approval outcome |
| Gender DI ratio | 0.77 | Below the 0.80 threshold |
| Gender chi-square p-value | 0.0009 | Statistically significant disparity |
| Age 18–35 vs 36–65 p-value | 0.0004 | Significant age-related disparity |
| Young subgroup gender p-value | 0.0088 | Strongest gender difference among younger applicants |

### Fairness Interpretation

The gender results indicate potential adverse impact rather than random fluctuation. The age analysis shows that fairness concerns are not confined to one protected attribute. The interaction analysis is especially important because it shows that aggregate fairness metrics can hide where disparities are concentrated most strongly.

## Notebook 3 — Privacy and Governance

The third notebook is intended to extend the project into privacy, GDPR, and AI governance. This component connects the analytical findings to broader governance questions such as data minimisation, lawful processing, retention, documentation, transparency, and human oversight.

At the current repository stage, this part is still being consolidated. The governance layer will be expanded and finalised in the final project version, where it will be linked more explicitly to the findings from the data quality and fairness notebooks.

### Governance Scope

| Governance Area | Current Focus |
|---|---|
| Privacy | Personal-data handling in a credit decision context |
| GDPR | Lawful processing, minimisation, transparency, accountability |
| AI Governance | Oversight, documentation, and defensibility of decision logic |
| Finalisation status | To be completed in final project version |

## Main Findings

| Theme | Main Conclusion |
|---|---|
| Data Quality | The dataset is usable, but not uniformly reliable across all fields |
| Record Integrity | Duplicate identifiers weaken traceability and confidence in downstream use |
| Fairness | Approval outcomes differ meaningfully by gender and age |
| Governance | Data quality, fairness, and privacy are structurally linked |

## Governance Relevance

The broader implication of the project is that governance begins before any model is deployed. If the input records are weak, fairness analysis becomes less credible. If approval outcomes differ systematically across groups, the organisation faces stronger obligations around monitoring, review, and explainability. If personal data is used in a sensitive financial context, privacy-by-design and accountability expectations cannot be treated as optional.

For that reason, the credit application pipeline should not be understood simply as a technical workflow. It should be treated as a governance object that requires documentation, defensible design choices, and continuous oversight across the full lifecycle of data collection, analysis, and decision-making.

## Figures

The following visuals are intended to be added once the final plot exports are uploaded to the repository.

### Planned Figure 1 — Approval Rate by Gender
<!-- Example after upload:
![Approval Rate by Gender](reports/approval_rate_by_gender.png)
-->

### Planned Figure 2 — Approval Rate by Age Group
<!-- Example after upload:
![Approval Rate by Age Group](reports/approval_rate_by_age_group.png)
-->

### Planned Figure 3 — Approval Rate by Age Group and Gender
<!-- Example after upload:
![Approval Rate by Age Group and Gender](reports/approval_rate_by_age_gender.png)
-->

## Next Step

The final project version will complete the governance layer and connect the privacy and regulatory assessment more explicitly to the data quality and fairness findings already established in the first two notebooks.

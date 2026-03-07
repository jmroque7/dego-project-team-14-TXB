# DEGO Project – Team 14

## Team Members
- Eda Jülide Pürsün
- [Name]
- [Name]
- [Name]

## Project Description
This project examines data quality, fairness, and governance risks in a credit decision dataset. The analysis is structured in two main parts. First, we assess core data quality dimensions such as completeness, uniqueness, validity, plausibility, and cross-field consistency. Second, we evaluate potential bias in lending outcomes, with a particular focus on gender- and age-related disparities, as well as possible proxy discrimination through non-protected variables.

## Research Objective
The objective is to assess whether the dataset is sufficiently reliable for analytical use and whether the approval outcomes show patterns that may raise fairness or governance concerns.

## Repository Structure
- `Data/` – project data folder
- `Notebooks/` – Jupyter notebooks used for the analysis

## Main Analytical Components
1. Data quality assessment
2. Bias and fairness analysis
3. Proxy risk evaluation
4. Governance implications and recommendations

## Key Preliminary Findings
The data quality review indicates uneven field reliability, particularly for variables with high missingness and duplicate identifiers. The fairness analysis suggests that approval outcomes differ across demographic groups, with evidence of potential adverse impact for female applicants and lower approval rates among younger applicants. Proxy analysis further suggests that non-protected variables may still carry demographic signal.

## Tools Used
- Python
- Jupyter Notebook
- pandas
- numpy
- scipy

## Governance Relevance
The project highlights that data quality and fairness should not be treated separately. Weak data capture, inconsistent identifiers, and proxy-sensitive features can materially affect both analytical validity and governance compliance in credit decision systems.

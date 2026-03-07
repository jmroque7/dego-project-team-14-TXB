# DEGO Project – Team 14 (TXB)

## Team Members

Eda Jülide Pürsün (74935)
Lucas Galilei (70270)  
João Marques Roque (73047)  
Maddalena Manfredi (71946)

## Project Description

This project examines governance risks in an automated credit application setting. Using a structured credit decision dataset, the team evaluates three connected dimensions of responsible data use: data quality, fairness in decision outcomes, and privacy and regulatory compliance. The work is framed as an audit of a credit approval pipeline in which unreliable data, biased approval patterns, and weak privacy controls can create both operational and legal risk.

## Project Objective

The objective is to assess whether the dataset and decision process are sufficiently reliable, fair, and compliant from a data governance perspective. The analysis therefore addresses three questions. First, are the underlying records complete, valid, and internally consistent enough to support downstream analytics? Second, do approval outcomes differ systematically across demographic groups in ways that raise fairness concerns? Third, does the handling of personal data meet the governance expectations implied by GDPR and the EU AI Act in a high-risk financial use case?

## Repository Structure

`Data/` contains the project data resources.  
`Notebooks/` contains the three analytical notebooks used for the project.  
`.gitignore` defines which files should not be tracked by Git.  
`README.md` documents the project scope, structure, and main findings.

## Analytical Components

### 1. Data Quality Assessment

The first notebook focuses on the quality of the underlying application records. It examines missingness, duplicates, datatype inconsistencies, validity issues, plausibility problems, outliers, and cross-field consistency checks. The purpose of this stage is to determine whether the dataset is robust enough for further fairness and governance analysis.

### 2. Bias and Fairness Analysis

The second notebook evaluates whether approval outcomes differ across relevant demographic groups. It includes approval-rate comparisons, disparate impact analysis, statistical testing, and subgroup analysis. Particular attention is given to gender- and age-related differences, as well as the possibility that non-protected variables may still act as indirect proxies.

### 3. Privacy and Regulatory Assessment

The third notebook extends the project into privacy, GDPR, and AI governance. It identifies personal data fields, evaluates pseudonymisation and access control logic, and assesses whether the credit scoring context should be treated as a high-risk AI use case. It also highlights gaps in human oversight, transparency, and operational compliance.

## Key Findings

The data quality analysis suggests that the dataset is usable, but not all fields are equally reliable. Missingness is concentrated in selected variables, and duplicate identifiers create an important record-integrity concern.

The fairness analysis indicates that approval outcomes are not evenly distributed across all groups. In particular, the results point to meaningful gender- and age-related disparities, which makes further review of decision logic and feature usage necessary.

The privacy and governance review shows that the project context goes beyond technical analytics. Because credit assessment involves personal and potentially sensitive information, governance controls such as minimisation, pseudonymisation, auditability, and human review are essential rather than optional.

## Governance Relevance

A central conclusion of the project is that data quality, fairness, and privacy cannot be treated as separate topics. Weak data capture affects the credibility of fairness analysis. At the same time, a system can produce analytically useful outputs while still creating legal and ethical risks if personal data is handled poorly or if protected-group disparities are left unmonitored. The project therefore approaches credit decisioning as a combined governance problem rather than a purely technical modelling exercise.


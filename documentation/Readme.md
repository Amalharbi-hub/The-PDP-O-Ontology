# PDP-O Evaluation Documentation

This folder contains the full evaluation documentation for the **Date Palm Pest and Disease Ontology (PDP-O)**. The documentation describes the domain expert evaluation, competency question formulation, reasoning-based evaluation, traceability matrices, workshop notes, and draft competency questions used during the ontology evaluation process.

---

## Contents

| Document / Section | Description |
| --- | --- |
| [Full Evaluation Document](./evaluation_document.md) | Complete evaluation document containing domain expert information, CQs, SPARQL queries, PDP-O answers, evaluation results, traceability matrices, workshop notes, and draft CQs. |
| Domain Experts’ Information | Information about the 11 domain experts involved in the evaluation, including specialization, experience, and affiliation. |
| Final 90 Competency Questions | Main competency questions grouped into Disease/Pest, Control Methods, Symptom, Causal Agents, and Others categories. |
| Enhanced Reasoning CQs | 20 additional competency questions designed to test OWL/SWRL reasoning capabilities. |
| Domain Expert Evaluation Results | Statistical results of expert evaluation, including mean, standard deviation, relative weight, degree, and rank. |
| Traceability Matrices | Mapping between CQs, use cases, reasoning types, ontology classes, SPARQL queries, and expected answers. |
| Workshop Notes | Notes from CQ elicitation, refinement, categorization, and validation workshops. |
| Draft CQs | Initial set of 120 draft competency questions before refinement into the final 90 CQs. |

> **Note:** If your full document has a different filename, replace `evaluation_document.md` in the links above with the actual file name.

---

## Evaluation Overview

The evaluation of PDP-O was conducted using domain expert review and competency-question-based testing. The evaluation focused on whether PDP-O can correctly represent and retrieve knowledge about date palm diseases, pests, symptoms, causal agents, control methods, susceptible varieties, outbreak timing, and affected plant parts.

The evaluation also included enhanced reasoning tests to verify that the ontology supports more advanced OWL/SWRL reasoning patterns.

---

## Domain Expert Panel

| Item | Description |
| --- | --- |
| Number of domain experts | 11 |
| Entomologists | 6 |
| Pathologists | 5 |
| Ontology engineers involved | 3 |
| Experience range | More than 5 years to more than 25 years |
| Main affiliations | King Saud University, King Abdulaziz University, King Faisal University, University of Tabuk, Date Palm Research Center of Excellence |

---

## Competency Questions

The final competency question set contains **90 CQs** distributed across five categories.

| Category | Number of CQs | Purpose |
| --- | ---: | --- |
| Disease / Pest | 25 | Diagnose diseases or pest damages from observed symptoms. |
| Control Methods | 20 | Retrieve chemical, biological, cultural, and application-related control information. |
| Symptom | 15 | Retrieve symptoms, definitions, and symptom characteristics. |
| Causal Agents | 20 | Retrieve causal agents, scientific names, environmental factors, agricultural practices, and transmission modes. |
| Others | 10 | Retrieve outbreak time, susceptible cultivars, and affected plant parts. |
| **Total** | **90** | Main PDP-O evaluation CQs. |

---

## Enhanced Reasoning Competency Questions

In addition to the main 90 CQs, the documentation includes **20 enhanced reasoning CQs**. These were designed to test specific ontology reasoning capabilities.

| Reasoning Type | Purpose |
| --- | --- |
| Subsumption | Tests class hierarchy reasoning and inferred class membership. |
| Property hierarchy | Tests retrieval through parent properties and subproperties. |
| Inverse properties | Tests inverse relations such as `has_Symptom` / `indicates` and `has_Effect` / `is_Effect_Of`. |
| Transitivity | Tests part-whole reasoning, especially plant-part hierarchy reasoning. |
| SWRL Rule 17 | Tests inferred disease symptoms from causal-agent effects. |
| SWRL Rule 18 | Tests inferred pest-damage symptoms from causal-agent effects. |

---

## Domain Expert Evaluation Summary

The following table summarizes the expert evaluation results by category.

| Category | Mean | SD | Relative Weight (%) | Degree |
| --- | ---: | ---: | ---: | --- |
| Disease / Pest | 5.68 | 0.79 | 81.09 | Agree |
| Control Methods | 4.88 | 2.01 | 69.71 | Somewhat agree |
| Symptom of Disease / Pest | 5.87 | 0.84 | 83.84 | Agree |
| Causal Agents | 6.13 | 0.55 | 87.53 | Strongly agree |
| Others | 5.67 | 0.64 | 81.04 | Agree |
| Enhanced Reasoning CQs | 6.05 | 0.79 | 86.43 | Strongly agree |

### Degree Scale

| Degree | Relative Weight Range |
| --- | --- |
| Strongly agree | 100% to greater than 85.7% |
| Agree | 85.6% to greater than 71.4% |
| Somewhat agree | Less than 71.3% to greater than 57.1% |

---

## Traceability Matrices

The documentation includes two traceability matrices:

| Matrix | Description |
| --- | --- |
| Traceability Matrix for Enhanced Reasoning CQs | Maps each enhanced CQ to its reasoning type, use case source, ontology classes, abbreviated SPARQL query, and expected answer. |
| Traceability Matrix for 90 CQs | Maps each of the 90 final CQs to its category and originating use case. |

These matrices help demonstrate that the evaluation questions were derived from real agricultural use cases and that the reasoning-focused CQs are linked to explicit OWL/SWRL constructs.

---

## Workshop Documentation

The documentation includes notes from the CQ elicitation and validation process.

| Workshop / Session | Date | Duration | Main Output |
| --- | --- | ---: | --- |
| Workshop 1: Use Case Collection | 2024-11-10 | 4 hours | 25 use cases and prioritized disease/pest list |
| Workshop 2: Draft CQ Formulation | 2024-11-17 | 4 hours | 120 draft CQs |
| Workshop 3: Refinement and Categorization | 2024-11-24 | 3 hours | 90 final CQs |
| Enhanced Reasoning CQ Session | 2026-05-05 | 2 hours | 20 enhanced reasoning CQs |

---

## Evaluation Files

If available, the following supporting files should be stored in this folder or linked from this folder.

| File | Description |
| --- | --- |
| `evaluation_document.md` | Full evaluation documentation. |
| `final_90_cqs.csv` | Final 90 competency questions with SPARQL queries and PDP-O answers. |
| `final_20_cqs.csv` | Enhanced reasoning CQs with SPARQL queries and PDP-O answers. |
| `draft_cqs_120.txt` | Initial 120 draft competency questions. |
| `expert_ratings.csv` | Questionnaire responses from domain experts. |
| `ratings_anonymised.xlsx` | Anonymized individual expert ratings. |

---

## Recommended Folder Structure

```text
documentation/
├── README.md
├── evaluation_document.docs
├── ../workshops/final_90_cqs.csv
├── ../workshops/final_20_cqs.csv
├── ../workshops/draft_cqs_120.txt
├── ../workshops/expert_ratings.csv

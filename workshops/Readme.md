# Workshop Notes – PDP-O Competency Question Elicitation

This document summarizes the workshop process used to elicit, refine, categorize, and validate the competency questions (CQs) for the PDP-O ontology.

---

## Overview

| Item | Description |
| --- | --- |
| Purpose | Elicit competency questions for evaluating the PDP-O ontology. |
| Domain | Date palm diseases and pests in Saudi Arabia. |
| Participants | Domain experts and ontology engineers. |
| Main Outputs | 90 final competency questions and 20 enhanced reasoning competency questions. |
| Validation Method | Domain expert review using a 7-point Likert scale. |

---

## Workshop 1 – Use Case Collection

| Item | Details |
| --- | --- |
| Workshop | Workshop 1 |
| Duration | 4 hours |
| Date | 2024-11-10 |
| Participants | 11 domain experts: 6 entomologists and 5 pathologists; plus 3 ontology engineers |
| Main Focus | Collection of real-world diagnostic and management use cases for date palm diseases and pests. |

### Objectives

| Objective ID | Objective |
| --- | --- |
| O1 | Identify the most frequent and economically damaging date palm diseases and pests in Saudi Arabia. |
| O2 | Collect real-world diagnostic scenarios from extension manuals. |
| O3 | Collect diagnostic and management scenarios from expert field experience. |
| O4 | Establish the main knowledge areas that the competency questions should cover. |

### Key Outputs

| Output ID | Output |
| --- | --- |
| W1-O1 | A list of 25 use cases was collected. |
| W1-O2 | A prioritized list of the top 10 pests and diseases was produced. |
| W1-O3 | Priority pests and diseases included Red palm weevil, Bayoud disease, Fusarium wilt, Inflorescence rot, Black scorch, and others. |
| W1-O4 | The group decided that CQs must cover symptom identification, causal agents, control methods, outbreak timing, and susceptible varieties. |

---

## Workshop 2 – Draft CQ Formulation

| Item | Details |
| --- | --- |
| Workshop | Workshop 2 |
| Duration | 4 hours |
| Date | 2024-11-17 |
| Participants | Domain experts and ontology engineers |
| Main Focus | Translation of use cases into draft natural-language competency questions. |

### Process

| Step | Description |
| --- | --- |
| 1 | Experts translated each use case into one to three natural-language questions that a farmer, researcher, or extension officer might ask. |
| 2 | Questions were written in a user-oriented form rather than in OWL or SPARQL syntax. |
| 3 | Repeated diagnostic scenarios were grouped for comparison. |
| 4 | A preliminary set of 120 draft competency questions was produced. |

### Example

| Use Case | Draft Competency Question |
| --- | --- |
| Farmer sees white powder on inflorescence. | What disease causes white powder on inflorescence? |

### Key Outputs

| Output ID | Output |
| --- | --- |
| W2-O1 | 120 draft competency questions were produced. |
| W2-O2 | Draft questions were stored in `draft_cqs_120.txt`. |

### Observations

| Observation ID | Observation |
| --- | --- |
| W2-OBS1 | Many questions were repetitive, especially questions of the form “What disease causes symptom X?” |
| W2-OBS2 | Some questions required only direct instance lookup. |
| W2-OBS3 | Some questions required reasoning, such as inferring a causal agent from an observed effect. |
| W2-OBS4 | The draft CQs needed refinement, deduplication, and categorization. |

---

## Workshop 3 – Refinement and Categorization

| Item | Details |
| --- | --- |
| Workshop | Workshop 3 |
| Duration | 3 hours |
| Date | 2024-11-24 |
| Participants | Domain experts and ontology engineers |
| Main Focus | Refinement, deduplication, categorization, and prioritization of competency questions. |

### Actions

| Action ID | Action |
| --- | --- |
| A1 | Removed duplicate competency questions. |
| A2 | Merged similar questions. |
| A3 | Reworded questions for clarity and consistency. |
| A4 | Categorized questions into five groups. |
| A5 | Prioritized CQs according to economic impact and domain relevance. |
| A6 | Moved low-priority questions to future work. |

### CQ Categories

| Category ID | Category |
| --- | --- |
| C1 | Disease / Pest |
| C2 | Control Methods |
| C3 | Symptom |
| C4 | Causal Agents |
| C5 | Others |

### Key Outputs

| Output ID | Output |
| --- | --- |
| W3-O1 | Duplicate and overlapping questions were removed or merged. |
| W3-O2 | CQs were organized into five categories. |
| W3-O3 | High-priority CQs were retained in the final evaluation set. |
| W3-O4 | Final count: 90 competency questions. |
| W3-O5 | Final CQs were stored in `final_90_cqs.csv`. |

---

## Enhanced Reasoning CQ Session

A separate session was conducted to design competency questions specifically targeting ontology reasoning.

| Item | Details |
| --- | --- |
| Session | Enhanced Reasoning CQ Design Session |
| Duration | 2 hours |
| Date | 2026-05-05 |
| Participants | Domain experts and ontology engineers |
| Main Focus | Design of reasoning-focused CQs for evaluating OWL/SWRL reasoning behavior. |
| Output | 20 enhanced reasoning competency questions. |

### Reasoning Types Covered

| Reasoning Type ID | Reasoning Type | Description |
| --- | --- | --- |
| R1 | Subsumption | Tests class hierarchy and inferred class membership. |
| R2 | Property hierarchy | Tests retrieval through parent properties and subproperties. |
| R3 | Inverse properties | Tests inverse relations such as symptom-to-problem and effect-to-agent. |
| R4 | Transitivity | Tests part-whole reasoning, especially plant-part hierarchies. |
| R5 | SWRL rules | Tests rule-based inference, including inferred symptoms from causal-agent effects. |

### Key Decisions

| Decision ID | Decision |
| --- | --- |
| D1 | Enhanced reasoning CQs should be separate from the main 90 CQs. |
| D2 | Each reasoning-focused CQ should map to a specific OWL or SWRL construct. |
| D3 | Queries should explicitly show the reasoning path tested. |
| D4 | The final enhanced reasoning set should include 20 CQs. |

---

## Expert Validation Protocol

| Item | Details |
| --- | --- |
| Validation Participants | Domain experts |
| Material Reviewed | Natural-language definitions and HTML tables |
| OWL Syntax Shown to Experts | No |
| Query Answer Rating | Experts rated SPARQL query answers |
| Rating Scale | 7-point Likert scale |
| Passing Criterion | Mean score greater than 5.0 |
| Follow-up Criterion | Standard deviation greater than 1.5 led to follow-up discussion |

### Validation Procedure

| Step | Description |
| --- | --- |
| 1 | Experts reviewed the natural-language representation of CQs and answers. |
| 2 | Experts evaluated whether the returned PDP-O answers were correct and useful. |
| 3 | Each CQ answer was rated using a 7-point Likert scale. |
| 4 | Mean and standard deviation were calculated for each CQ. |
| 5 | CQs with mean score greater than 5.0 were considered passed. |
| 6 | CQs with high disagreement, indicated by SD greater than 1.5, were flagged for discussion. |
| 7 | Feedback was used to refine CQ wording, expected answers, and ontology coverage. |

---

## Workshop Timeline

| Date | Activity | Duration | Output |
| --- | --- | ---: | --- |
| 2024-11-10 | Workshop 1: Use case collection | 4 hours | 25 use cases and priority disease/pest list |
| 2024-11-17 | Workshop 2: Draft CQ formulation | 4 hours | 120 draft CQs |
| 2024-11-24 | Workshop 3: Refinement and categorization | 3 hours | 90 final CQs |
| 2026-05-05 | Enhanced reasoning CQ session | 2 hours | 20 enhanced reasoning CQs |

---

## Generated Files

| File | Description |
| --- | --- |
| `draft_cqs_120.txt` | Initial set of 120 draft competency questions produced during Workshop 2. |
| `final_90_cqs.csv` | Final set of 90 competency questions after refinement and categorization. |
| `expert_ratings.csv` | Questionnaire responses from domain expert evaluation. |
| `ratings_anonymised.xlsx` | Anonymized individual expert ratings. |

---

## Summary of Outputs

| Output | Description |
| --- | --- |
| 25 use cases | Real-world disease and pest diagnosis or management scenarios collected from experts and extension sources. |
| Top 10 priority pests/diseases | High-impact date palm pests and diseases prioritized for CQ coverage. |
| 120 draft CQs | Initial natural-language competency questions. |
| 90 final CQs | Refined and categorized main competency questions. |
| 20 enhanced reasoning CQs | Additional CQs targeting OWL/SWRL reasoning constructs. |
| Expert validation ratings | Evaluation data collected using a 7-point Likert scale. |

---

## Notes

- The CQ elicitation process was grounded in domain expert knowledge and real agricultural use cases.
- The final CQ set covers diagnostic, causal, management, temporal, varietal susceptibility, and plant-part-related knowledge.
- The enhanced reasoning CQs were designed to evaluate whether PDP-O supports reasoning beyond direct instance retrieval.

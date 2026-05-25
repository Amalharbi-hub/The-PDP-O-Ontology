# PDP-O: Plant Disease and Pest Ontology

[![Ontology](https://img.shields.io/badge/Ontology-OWL-blue)](ontology/PDP-O.owl)
[![SPARQL](https://img.shields.io/badge/SPARQL-Queries-green)](sparql_queries/)
[![Evaluation](https://img.shields.io/badge/Evaluation-CQs-orange)](evaluation/)
[![Status](https://img.shields.io/badge/Status-Research%20Prototype-lightgrey)]()

## Overview

PDP-O (Plant Diseases and Pests Ontology) is a domain-specific ontology designed to semantically represent knowledge related to plant diseases, pests, their symptoms, causal agents, environmental conditions, and treatment strategies. Developed using OWL 2 DL and compatible with reasoning engines, PDP-O enables intelligent diagnosis, knowledge sharing, and decision support in the agricultural domain.

This repository contains the supplementary material for **PDP-O**, the Plant Disease and Pest Ontology. PDP-O is designed to formally represent knowledge about plant diseases and pests, with a focus on supporting disease/pest diagnosis from visible symptoms and retrieving related causal, contextual, and control knowledge.

The repository provides:

- the PDP-O ontology file;
- competency questions for domain coverage;
- competency questions for enhanced reasoning evaluation;
- SPARQL queries and ontology-generated answers;
- traceability matrices linking CQs to use cases, ontology classes, and reasoning types;
- expert-validation results;
- workshop and CQ-development documentation.

The supplementary material is organized to support transparency and reproducibility of the ontology evaluation.

---

## Repository Structure

```text
The-PDP-O-Ontology/
│
├── ontology/                 # PDP-O ontology files
├── competency_questions/     # Domain and reasoning competency questions
├── sparql/                   # SPARQL queries used in the evaluation
├── traceability/             # CQ-to-use-case/class/reasoning mappings
├── evaluation/               # Expert-validation protocol and results
├── workshops/                # CQ-development workshop summaries
└── images/                   # Diagrams and workflow figures
└── documentation/            # Additional ontology documentation


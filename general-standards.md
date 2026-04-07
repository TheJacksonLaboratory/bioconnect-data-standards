# Annotation Standards for Studies, Assays, Samples, and Related Entities

## Overview

This page provides general guidance on annotation standards for studies, assays, samples, and related entities. The goal is to support consistent, traceable, and standards-compliant metadata annotation across the documentation.

### Annotation Workflow

```text
Idea or new annotation need
        |
        v
Check existing approved terms
        |
        +----> Term exists -----------------> Use approved term
        |
        v
No suitable term found
        |
        v
Request new term
        |
        v
Review and validation by Data Standards Group
        |
        v
Approved term used in study, sample, and assay annotations
```

## ISA Model Basics

The ISA model organizes metadata across investigations, studies, and assays:

- **Investigation**: A collection of studies organized around a shared theme, such as a disease, pathway, treatment, or related research topic.
- **Study**: Based on a cohort and links sources to samples and assays.
- **Assay**: Based on a measurement type (for example, RNA-seq) and links samples to measured results.

## Source and Sample Identifiers

A **source** must have an origin that maintains its identifier. A source (for example, an animal, human, or cell line) is initially registered with a lab for inclusion in a study. The initial registry—such as an Excel spreadsheet, Climb database, or digital lab notebook—is expected to serve as the database of record for source ID numbers.

A **sample** must also have an origin that maintains its identifier, but this does not need to be the same origin used for the source.

- **Source origin** is set for every study.
- **Sample origin** is set for every assay.

## Source Metadata vs. Sample Metadata

Annotations that apply to a **source** must apply to the whole source; in other words, they must describe a characteristic of every part of that source. For example, genotype, sex, date of birth, date of death, and strain all apply to the whole animal and all of its parts.

Annotations for **samples** must record sample-specific metadata.

In addition, either the **source** or the **sample** must be annotated with a **study factor value**.

## Source Metadata Requirements by Source Kind

### Mouse

Required metadata:
- Origin
- Source ID
- Genotype
- Sex
- Date of birth
- Date of death
- Strain

### Human

Required metadata:
- Origin
- Source ID

### Cell Line

Required metadata:
- Origin
- Source ID
- Nomenclature

## Sample Metadata Requirements

Sample metadata requirements depend on the needs of the assay. At a minimum, sample records should include:

- Origin
- Sample ID
- Source ID
- Sample type
- Any additional metadata required by the service

Both **source ID** and **sample ID** are required so that the source and sample remain linked. If the sample is a whole animal, the tissue type should be recorded as **"Whole animal."**

## Term List Requirements

This page should also describe:

- How to check for existing terms
- How to request new terms

## Activity

Document the required activities for annotation review, term validation, and standards compliance as needed.

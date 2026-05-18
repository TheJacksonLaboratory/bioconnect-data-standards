# Single Cell Biology Lab Data Standards

## Sample Sheets
The Single Cell Biology Lab uses sample sheets that include the columns listed below. Details about each column are listed below, including whether the field is required based on the `metadata` sheet in `scbl_data_standards.xlsx`.

The columns are as follows:

- **Sample (specimen) ID**
  - **Requirement:** Required

- **Sample (specimen) Name**
  - **Requirement:** Required

- **Sample (specimen) Type**
  - **Requirement:** Required

- **Age**
  - **Requirement:** Present

- **Sex**
  - **Requirement:** Present

- **Strain**
  - **Requirement:** Present

- **Name of Pool to which this sample belongs**
  - **Requirement:** Required if samples are to be pooled

- **Experimental Condition (Condition/Disease)**
  - **Requirement:** Present (user-defined)
  - **Note:** Treatment vs Condition: Recommend separate columns for experimental condition and treatment. Use NCIT as ontology source when term is available. Suggest adding list of most commonly used terms, but allow for free text when needed (`other` option).

- **Preservation Method**
  - **Requirement:** Conditional

- **Embedding Matrix**
  - **Requirement:** Conditional

- **Has this been submitted to SCBL before?**
  - **Requirement:** Required if Applicable

- **Organism**
  - **Requirement:** Required

- **Tissue**
  - **Requirement:** Conditional
  - **Conditional On:** `Sample Type = "tissue"`

- **Cell Type**
  - **Requirement:** Conditional
  - **Conditional On:** `Sample Type = "cells" or "cell pellet"`

- **Antibody Manufacturer**
  - **Requirement:** Required for Antibody Conjugation and/or validation only

- **Antibody Catalog #**
  - **Requirement:** Required for Antibody Conjugation and/or validation only

- **Antibody Clone**
  - **Requirement:** Required for Antibody Conjugation and/or validation only

- **Will SCBL Purchase?**
  - **Requirement:** Required for Antibody Conjugation and/or validation only

- **Target Reads per Cell (k)**
  - **Requirement:** Conditional

- **Storage Location**
  - **Requirement:** Present

- **Storage Location Details**
  - **Requirement:** Present

- **Storage Buffer**
  - **Requirement:** Present

- **iLab Request ID**
  - **Requirement:** Present

- **Parent ID**
  - **Requirement:** Present

- **Notes**
  - **Requirement:** Present

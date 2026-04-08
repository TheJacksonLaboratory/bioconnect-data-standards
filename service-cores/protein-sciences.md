# Protein Sciences Data Standards

Should we consider keeping source and sample metadata that are not relevant to the service core in a separate "metadata only" assay?

## Sample Sheets
The Protein Sciences Lab uses one sample sheet for all assay types. The columns are as follows:

- **Customer Sample Name**
  - **Requirement:** Required (alphanumeric only)
  - (-) keep this as is for now because we can map to sample ID in the background.

- **L7 Customer Sample Name**
  - **Requirement:** Display only
  - **Note:** Special characters and spaces are replaced by underscores.

- **Organism**
  - **Requirement:** Required
  - (+) choices: Homo sapiens, Mus musculus, other

- Other Organism
  - free text

- **Animal ID #**
  - (+) **Requirement:** Required for tissues (this is not necessarily correct, not really required)
  - (-) we would like to change this to "Source ID," but for now it will remain as is
  - we can consider removing this and replace with Source ID

- **Genotype #**
  - (+) **Requirement:** 

- **Strain #**
  - (+) **Requirement:** 

- **Date of Birth**
  - **Requirement:** Animal samples only
  - enforce formatting, this is currently enforced in ESP
  - (-) prefer to use ISO 8601 as YYYY-MM-DD standard __some__ standard needs to be enforced

- **Date of Collection**
  - **Requirement:** Required
  - enforce formatting, this is currently enforced in ESP, ISO 8601 as above

- **Sample Type**
  - **Requirement:** Required
  - (+) recommend a drop down with "tissue", "cell", "fluid", and "other" as options. How does this impact the lab's workflows? PS has even assayed bedding chips.
  - Brian says this is good to go and is how iLab is set up. 

- **Other Sample Type**
  - free text

- **Fluid/Tissue Type**
  - **Requirement:** Required for tissues
  - whis is this metadata used for?
  - (+) we can provide a list of controlled terms for the most popular options, but should we split out to fluid and tissue separately?
  - it's ok to separate these into two columns
  - supernatent is more like cell media
  - Fluid types: urine, plasma, media, serum, cerebrospinal fluid, other (whole blood goes into other)
  - For tissue if you have every major organ that is a good start, there might be a few others form the list. Look at research necropsy, they will have all the terms!!!
  - Some terms can be structures from different tissue. E.g., medulla is a structure in the brain and the kidney. 

- **Other Fluid/Tissue Type**
  - free text

- **Cell Type**
  - **Requirement:** Optional
  - Many of the cell types in historical data are not cell types. Is this overloaded for other purposes?
  - (+) something needs to change, but it's not clear what
  - keep this as free text for now. Even cell lines are varable. We could standardize on a list of the major cell types and cell lines, and then expand over time.
  - Brian says we can restrict this to a cell line-standard nomenclature. Would strain and genotype cover cell line? There are commercial cell lines, then lines from individual harvest. Check in with NYSCF folks. 

- **Cell Line**
  - **Requirement:** Optional
  - separate from cell type

- **Other Cell Type**
  - free text

- **Cell Count**
  - **Requirement:** Optional
  - (+) enforce that this be integer only, user would type in the approximate count
  - current values range from 5k to millions

- **Sample Buffer**
  - **Requirement:** Required
  - most are snap frozen and so don't have a buffer
  - (-) there should be some controlled list including:
    - 50mM HEPES with 6M Urea
    - EDTA
    - StemFlex media
    - none (snap frozen, cell pellet) break this out further?

- **Other Sample Buffer**
  - free text

- **Sex**
  - **Requirement:** Optional
  - (+) make as a controlled term list

- **Condition / Treatment**
  - **Requirement:** Optional
  - (+) we need to find a way to standardize this when it is filling many roles including study factor values
  - is this needed by protein sciences?
  - what should the controlled term options be?
  - is this study metadata?
  - can this be removed?
  - Brian says we can get rid of "condition" and just use "treatment"
  - We may have to allow users to allow multiple values in this column, e.g., diet and drug.

- **Sample Weight (mg)**
  - **Requirement:** Required for protein samples
  - **Note:** Protein samples: fill all that apply.
  - (+) enforce float only, no units to be entered

- **Sample Conc. (ng/µL)**
  - **Requirement:** Required for protein samples
  - **Note:** Protein samples: fill all that apply.
  - (+) enforce float only, no units to be entered
  - customers have not used this. is this column needed?
  - Brian says that if people do their own concentration then this is needed, but PS usually does this in house.

- **Sample Volume (µL)**
  - **Requirement:** Required for protein samples
  - **Note:** Protein samples: fill all that apply.
  - (+) enforce float only, no units to be entered

- **Group #**
  - **Requirement:** Optional
  - (-) what is this for? is this a cohort? pooled samples? ages? timepoints? sex? generation number? are these study factors?
  - Brian says restrict this to numeric values - this would be used for comparrison of samples during in-house analysis.

- **Additional Comments (barcode)**
  - **Requirement:** Optional
  - pools are usually indicated here. 


## File Type
To be determined. We will want to work through the different assay outputs, but can do this separately. 
For the protein and metabolite assays, the column headings are sample IDs, but do these column headings have other info as well? Ideally for the analyst, the headings would be only and exacly the sample ID so that it can be matched up with the metadata. 


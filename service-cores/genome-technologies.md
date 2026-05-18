# Genome Technologies Data Standards

## Sample Sheets
The Genome Technologies group uses sample sheets that include the columns listed below. Details about each column are listed below, including whether the field is required based on the first worksheet (`Clarity Samples August 2025 - F`) in `GT_data_standards.xlsx`.

The columns are as follows:

- **Sample Name**
  - **Requirement:** Required on the Form

- **Customer Sample Name**
  - **Requirement:** Required on the Form

- **Organism**
  - **Requirement:** Not marked as required on the Form
  - Examples noted: mouse, human, fly, marmoset.

- **Other Organism**
  - **Requirement:** Present on the Form
  - This could be the place to enter an organism that is not yet in the list.

- **Sample Type**
  - **Requirement:** Required on the Form
  - We need a specific set of sample types that are required by L7/ESP.
  - Select a subset of terms using enums.

- **Tissue**
  - **Requirement:** Required on the Form, if tissue selected as Sample Type
  - We are not using a full tree from UBERON.

- **Cell Type**
  - **Requirement:** Required on the Form, if `cells` or `cell pellet` selected as Sample Type
  - Keep as free text for now.
  - Split out `Cell Type` from `Cell Line`.
  - This needs to be managed by the data standards group with a robust feedback process.

- **Cell Count**
  - **Requirement:** Required on the Form, if `cells` or `cell pellet` selected as Sample Type
  - Integer, in millions

- **Sample Buffer**
  - **Requirement:** Required on the Form
  - This is currently free text. Should this be updated to a fixed list?

- **Sex**
  - **Requirement:** Present on the Form

- **Sample Conc. (ng/µl)**
  - **Requirement:** Present on the Form

- **DNA Sample Size (bp)**
  - **Requirement:** Required on the Form, if `BAC` or `plasmid` selected as Sample Type
  - DNA samples: `bp`.
  - Size is one per sample/library.

- **Index #**
  - **Requirement:** Required on the Form, if `library` selected as Sample Type
  - The customer includes the barcode, which comes from a kit that they purchase, and then the spreadsheet maps to the library index number.
  - Is this a characteristic category that we could pull in from another specialized database?
  - How can this be done in bulk?

- **Comments**
  - **Requirement:** Present on the Form

- **Condition / Treatment**
  - **Requirement:** Present on the Form

- **Plate Name**
  - **Requirement:** Required on some Sanger Forms
  - This is only for Sanger sequencing, not used for NGS.
  - This will always be free text and can be anything.

- **Pool ID**
  - **Requirement:** Present on the Form

- **Reads Requested (M)**
  - **Requirement:** Required on the Form, for Illumina samples
  - Integer field, in millions.

- **Well Position**
  - **Requirement:** Required for Sanger samples
  - Only for Sanger.
  - Validation would not be needed on this (for example, `A:10`, `B:6`).

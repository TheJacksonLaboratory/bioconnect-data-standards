# Genome Technologies Data Standards

## Sample Sheets
The Genome Technologies group uses sample sheets that include the columns listed below. Notes captured for specific columns are preserved under each field.

The columns are as follows:

- **Sample ID**
  - We will want to add `Source ID` for connection to the source cell line or organism.

- **Sample Name**
  - Do we need both a name and an ID?

- **Organism**
  - Examples noted: mouse, human, fly, marmoset.

- **Other Organism**
  - This could be the place to enter an organism that is not yet in the list.

- **Sample Type**
  - We need a specific set of sample types that are required by L7/ESP.
  - Select a subset of terms using enums.

- **Tissue**
  - We are not using a full tree from UBERON.

- **Cell Type**
  - Keep as free text for now.
  - Split out `Cell Type` from `Cell Line`.
  - This needs to be managed by the data standards group with a robust feedback process.

- **Cell Count**
  - Integer, in millions

- **Sample Buffer**
  - This is currently free text. Should this be updated to a fixed list?

- **Sample Size**
  - DNA samples: `bp`.
  - Size is one per sample/library.

- **Index Number**
  - The customer includes the barcode, which comes from a kit that they purchase, and then the spreadsheet maps to the library index number.
  - Is this a characteristic category that we could pull in from another specialized database?
  - How can this be done in bulk?

- **Plate Name**
  - This is only for Sanger sequencing, not used for NGS.
  - This will always be free text and can be anything.

- **Reads Requested**
  - Integer field, in millions.

- **Well Position**
  - Only for Sanger.
  - Validation would not be needed on this (for example, `A:10`, `B:6`).

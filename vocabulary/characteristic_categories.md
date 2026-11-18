# Characteristic Category Vocabulary

**Definition:** Characteristic Category is a grouping for the kinds of sample, subject, experimental, or handling metadata represented by the term lists in this directory.

Each entry corresponds to a populated term-list Markdown file, with an `id` matching the filename without `.md`. The README, this category list, and empty files are excluded.

## biospecimen

```yaml
id: biospecimen
label: biospecimen
description: "Biospecimen is the anatomical tissue source or tissue-derived material associated with a sample."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings: []
```

## cell line

```yaml
id: cell_line
label: cell line
description: "A cell population that represents a genetically stable population of cultured cells with a common history."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings: []
```

## cell type

```yaml
id: cell_type
label: cell type
description: "The distinct morphological or functional form of cell."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT_C12508
  accession_url: http://purl.obolibrary.org/obo/NCIT_C12508
```

## embedding matrix

```yaml
id: embedding_matrix
label: embedding matrix
description: "The substance used to support and surround a biological sample."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings: []
```

## measurement type

```yaml
id: measurement_type
label: measurement type
description: "Measurement Type is the assay or other measurement-generating process used to produce information about a sample or material entity."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings: []
```

## organism

```yaml
id: organism
label: organism
description: "Organism is the biological entity or taxon from which a sample, specimen, or observation is derived."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: OBI_0100026
  accession_url: http://purl.obolibrary.org/obo/OBI_0100026
```

## preservation method

```yaml
id: preservation_method
label: preservation method
description: "Preservation Method is the preparation or processing technique used for storage or downstream use of a physical sample."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings: []
```

## sample buffer

```yaml
id: sample_buffer
label: sample buffer
description: "Buffer or solution in which the sample is stored or submitted."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings: []
```

## sample type

```yaml
id: sample_type
label: sample type
description: "General form of material, such as tissue/biospecimen, cells, or fluid."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT_C70713
  accession_url: http://purl.obolibrary.org/obo/NCIT_C70713
```

## sex

```yaml
id: sex
label: sex
description: "Sex of the source organism."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: PATO:0000047
  accession_url: http://purl.obolibrary.org/obo/PATO_0000047
```

## storage temperature

```yaml
id: storage_temperature
label: storage temperature
description: "Storage Temperature is the temperature at which a sample is stored. Options are in degrees Celsius."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings: []
```

## strain

```yaml
id: genetic_background
label: genetic background
description: "The complete genetic composition of a strain or individual."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: EFO:0005135
  accession_url: http://www.ebi.ac.uk/efo/EFO_0005135
```

## treatment

```yaml
id: experimental_condition
label: experimental condition
description: "The Experimental Condition is an intervention, exposure, factor, or condition applied with the intent to modify or alter a characteristic of an organism, individual, sample, or experimental system."
parent: characteristic_category
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: EFO:0000727
  accession_url: http://www.ebi.ac.uk/efo/EFO_0000727
```

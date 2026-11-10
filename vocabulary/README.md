# Vocabulary

This directory contains proposed controlled vocabularies for sample, source organism, experimental, and handling metadata. Each term-list file includes a category definition and individual terms represented as YAML blocks.

All current entries have `status: proposed`. Some descriptions and external mappings are incomplete, and curation notes record open questions. An external mapping does not by itself indicate that an entry has been approved.

## Vocabulary index

[Characteristic categories](characteristic_categories.md) lists the categories represented by the populated term-list files below. Its entry IDs match the filenames without `.md`.

| Vocabulary | Definition |
| --- | --- |
| [biospecimen](biospecimen.md) | Biospecimen is the anatomical tissue source or tissue-derived material associated with a sample. |
| [cell_line](cell_line.md) | Cell Line identifies the cell line associated with a sample. |
| [cell_type](cell_type.md) | Type of cell present in or represented by the sample. |
| [embedding_matrix](embedding_matrix.md) | Embedding Matrix is the material used to embed a sample. |
| [fluid_type](fluid_type.md) | Fluid Type is the liquid biological material or fluid medium associated with a sample; organism-derived fluids. |
| [measurement_type](measurement_type.md) | Measurement Type is the assay or other measurement-generating process used to produce information about a sample or material entity. |
| [organism](organism.md) | Organism is the biological entity or taxon from which a sample, specimen, or observation is derived. |
| [preservation_method](preservation_method.md) | Preservation Method describes how a sample is preserved. |
| [sample_buffer](sample_buffer.md) | Buffer or solution in which the sample is stored or submitted. |
| [sample_type](sample_type.md) | General form of material, such as tissue, cells, or fluid. |
| [sex](sex.md) | Sex of the source organism, when applicable. |
| [storage_temperature](storage_temperature.md) | Storage Temperature is the temperature at which a sample is stored. |
| [strain](strain.md) | Named strain or genetic background of the source organism. |
| [treatment](treatment.md) | Treatment is an intervention, exposure, or condition applied with the intent to modify or alter a characteristic of an organism, individual, sample, or experimental system. |

## Term entry format

Each term appears under a Markdown heading, followed by a YAML block with these fields:

| Field | Meaning |
| --- | --- |
| `id` | Local identifier for the term within its vocabulary. |
| `label` | Display name of the term. |
| `description` | Definition or explanation of the term, where provided. |
| `parent` | Category identifier recorded for the term. |
| `status` | Curation status; all current entries are `proposed`. |
| `notes` | Curation comments, questions, or proposed changes. |
| `related_to` | Related terms, where recorded; currently represented as empty lists. |
| `external_mappings` | External references, each with an `accession_id` and `accession_url`. |

A blank YAML value indicates that no value is recorded. An empty list (`[]`) records no items. Some external mapping entries also contain blank accession fields; mappings are not complete for every term.

## Submission fields

The following fields currently have brief definitions here without corresponding term-list files in this directory. They are retained separately from the controlled vocabulary index.

| Field                      | Definition |
|----------------------------| --- |
| sample_id                  | User-provided identifier for the submitted sample. |
| source_id                  | Identifier for the biological source from which the sample came. |
| genotype                   | Relevant genotype or genetic modification of the source organism. |
| date_of_birth              | Birth date of the source organism. |
| date_of_death              | Death date of the source organism, when applicable. |
| age                        | Age of the source organism at sample collection. |
| age_unit                   | Unit used for age, such as days, weeks, months, or years. |
| cell_count                 | Number of cells in the submitted sample. |
| experimental_condition     | Treatment, disease, exposure, or other experimental condition. |
| date_of_collection         | Date on which the sample was collected. |
| comment                    | Additional notes or context about the sample. |
| target_reads_per_cell_k    | Target sequencing depth, in thousands of reads per cell. |
| new_submission             | Indicates whether this record is part of a new sample submission. |
| antibody_manufacturer      | Company that manufactured the antibody. |
| antibody_catalog_num       | Manufacturer's catalog number for the antibody. |
| antibody_clone             | Clone name or identifier of the antibody. |
| purchase_clone             | Whether the requested antibody clone needs to be purchased. |
| storage_location           | General location where the sample is stored. |
| storage_location_details   | Additional details needed to locate the stored sample. |
| storage_buffer             | Buffer or solution in which the sample is stored. |
| ilab_request_id            | Identifier for the associated request in iLab. |
| parent_id                  | Identifier for the parent sample from which this sample was derived. |
| pool_id                    | Identifier for the pool containing this sample. |
| sample_concentration_ng_ul | Concentration of the submitted sample, in nanograms per microliter. |
| dna_sample_size_bp         | Expected size of the DNA fragments or molecules, in base pairs. |
| index_num                  | Index sequence or identifier associated with the sequencing library. |
| plate_name                 | Name or identifier of the plate containing the sample. |
| reads_requested_M          | Requested sequencing output, in millions of reads. |
| well_position              | Position of the sample within a plate, such as A1 or B12. |
| comments                   | Additional notes or context about the sample. |

## Naming and curation notes

- `condition` includes treatment, disease, exposure, and other experimental conditions. The separate `treatment` vocabulary describes interventions applied to modify an organism, sample, or experimental system; the two names are not treated as interchangeable.
- Both `comment` and `comments` are retained as existing field names pending naming review.

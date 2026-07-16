# Sample Type Vocabulary

**Definition:** Sample Type is the kind of biospecimen or biological material collected, stored, or used for testing, diagnostics, propagation, treatment, or research. See: [NCIT:C70713 Biospecimen Type](https://www.ebi.ac.uk/ols4/api/ontologies/ncit/terms?obo_id=NCIT%3AC70713).

## amplicon

```yaml
id: amplicon
label: amplicon
description: A method for targeted DNA sequencing that uses oligonucleotide primers to amplify regions of interest, followed by next-generation sequencing (NGS) for deep coverage of the region.
parent: sample_type
status: proposed
notes:
- definition of the amplicon sequencing method
related_to: []
external_mappings:
- accession_id: NCIT:C204813
  accession_url: http://purl.obolibrary.org/obo/NCIT_C204813
```

## BAC

```yaml
id: bac
label: BAC
description: Based upon the natural F plasmid of E. coli. Inserts up to 300 Kb can be cloned and stably maintained as circular molecules.
parent: sample_type
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT:C1860
  accession_url: http://purl.obolibrary.org/obo/NCIT_C1860
```

## blood

```yaml
id: blood
label: blood
description: 'NCIT: A liquid tissue; its major function is to transport oxygen throughout the body. It also supplies the tissues with nutrients, removes waste products, and contains various components of the immune system defending the body against infection. UBERON: A fluid that is composed of blood plasma and erythrocytes.'
parent: sample_type
status: proposed
notes:
- Consider mapping to Sample Type = tissue and Tissue = blood for consistency
- Which one should we use. NCIT, UBERON or both?'
related_to: []
external_mappings:
- accession_id: NCIT:C12434
  accession_url: http://purl.obolibrary.org/obo/NCIT_C12434
- accession_id: UBERON:0000178
  accession_url: http://purl.obolibrary.org/obo/UBERON_0000178
```

## cell pellet

```yaml
id: cell_pellet
label: cell pellet
description: A cell sample collected and compacted by centrifugation of a liquid suspension.
parent: sample_type
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT:C113745
  accession_url: http://purl.obolibrary.org/obo/NCIT_C113745
```

## cells

```yaml
id: cells
label: cells
description: The smallest units of living structure capable of independent existence, composed of a membrane-enclosed mass of protoplasm and containing a nucleus or nucleoid.
parent: sample_type
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT:C12508
  accession_url: http://purl.obolibrary.org/obo/NCIT_C12508
```

## FFPE Section

```yaml
id: ffpe_section
label: FFPE Section
description: A tissue section that has been fixed with formalin and embedded in a paraffin block.
parent: sample_type
status: proposed
notes:
- Also appears in Sample Buffer — consolidate to Sample Type only
related_to: []
external_mappings:
- accession_id: NCIT:C200850
  accession_url: http://purl.obolibrary.org/obo/NCIT_C200850
```

## fluid

```yaml
id: fluid
label: fluid
description: Material produced by living organisms; it can be a necessary constituent of, or product of an organismal process.
parent: sample_type
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT:C13236
  accession_url: http://purl.obolibrary.org/obo/NCIT_C13236
```
## gDNA

```yaml
id: gdna
label: gDNA
description: The DNA that is part of the normal chromosomal complement of an organism.
parent: sample_type
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT:C95940
  accession_url: http://purl.obolibrary.org/obo/NCIT_C95940
```

## library

```yaml
id: library
label: library
description: A collection of DNA molecules that have been cloned in vectors.
parent: sample_type
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT:C16223
  accession_url: http://purl.obolibrary.org/obo/NCIT_C16223
```

## lysate

```yaml
id: lysate
label: lysate
description: The cellular debris and fluid produced by lysis of a cell.
parent: sample_type
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT:C62004
  accession_url: http://purl.obolibrary.org/obo/NCIT_C62004
```

## plasmid

```yaml
id: plasmid
label: plasmid
description: A small cellular inclusion consisting of a ring of DNA that is not in a chromosome but is capable of autonomous replication.
parent: sample_type
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT:C754
  accession_url: http://purl.obolibrary.org/obo/NCIT_C754
```

## rna

```yaml
id: rna
label: rna
description: A class of RNA molecule containing protein-coding information in its nucleotide sequence that can be translated into the amino acid sequence of a protein.
parent: sample_type
status: proposed
notes:
- mRNA definition
related_to: []
external_mappings:
- accession_id: NCIT:C813
  accession_url: http://purl.obolibrary.org/obo/NCIT_C813
```

## tissue

```yaml
id: tissue
label: tissue
description: An anatomical structure consisting of similarly specialized cells and intercellular matrix, aggregated according to genetically determined spatial relationships, performing a specific function.
parent: sample_type
status: proposed
notes:
related_to: []
external_mappings:
- accession_id: NCIT:C12801
  accession_url: http://purl.obolibrary.org/obo/NCIT_C12801
```


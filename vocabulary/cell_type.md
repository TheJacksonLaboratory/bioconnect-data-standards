# Cell Type Vocabulary

## bone marrow-derived macrophage

```yaml
id: bone_marrow_derived_macrophage
label: bone marrow-derived macrophage
description: Bone marrow-derived macrophages (BMM) are primary macrophage cells, derived from bone marrow cells in vitro in the presence of growth factors.
parent: cell_type
status:
notes:
- do we want to deviate from our chosen ontologies in order to better accommodate terms?
- submitted as "induced bone marrow-derived macrophage"
- should possibly be moved from Cell Type to Cell Line if we opt for a designated Cell Line column
related_to: []
external_mappings:
- accession_id: BTO:0004732
  accession_url: http://purl.obolibrary.org/obo/BTO_0004732
```

## dendritic cell

```yaml
id: dendritic_cell
label: dendritic cell
description: A cell of hematopoietic origin, typically resident in particular tissues, specialized in the uptake, processing, and transport of antigens to lymph nodes for the purpose of stimulating an immune response via T cell activation. These cells are lineage negative (CD3-negative, CD19-negative, CD34-negative, and CD56-negative).
parent: cell_type
status:
notes:
related_to: []
external_mappings:
- accession_id: CL:0000451
  accession_url: http://purl.obolibrary.org/obo/CL_0000451
```

## endothelial cell

```yaml
id: endothelial_cell
label: endothelial cell
description: An endothelial cell comprises the outermost layer or lining of anatomical structures and can be squamous or cuboidal. In mammals, endothelial cell has vimentin filaments and is derived from the mesoderm.
parent: cell_type
status:
notes:
related_to: []
external_mappings:
- accession_id: CL:0000115
  accession_url: http://purl.obolibrary.org/obo/CL_0000115
```

## ESC

```yaml
id: esc
label: ESC
description: A stem cell of embryonic origin.
parent: cell_type
status:
notes:
related_to: []
external_mappings:
- accession_id: CL:0002322
  accession_url: http://purl.obolibrary.org/obo/CL_0002322
```

## fibroblasts

```yaml
id: fibroblasts
label: fibroblasts
description: A connective tissue cell which secretes an extracellular matrix rich in collagen and other macromolecules. Flattened and irregular in outline with branching processes; appear fusiform or spindle-shaped.
parent: cell_type
status:
notes:
related_to: []
external_mappings:
- accession_id: CL:0000057
  accession_url: http://purl.obolibrary.org/obo/CL_0000057
```

## glioblast

```yaml
id: glioblast
label: glioblast
description: A non-terminally differentiated cell that develops from the neuroectoderm. Glioblasts have the potential to differentiate into various types of glial cells, including astrocytes and oligodendrocytes, and are primarily found in the central nervous system.
parent: cell_type
status:
notes:
- unsure if this is correct, someone with more expertise should double-check me here
related_to: []
external_mappings:
- accession_id: CL:0000030
  accession_url: http://purl.obolibrary.org/obo/CL_0000030
```

## HEK293

```yaml
id: hek293
label: HEK293
description:
parent: cell_type
status:
notes:
- should be moved from Cell Type to Cell Line if we opt for a designated Cell Line column
related_to: []
external_mappings:
- accession_id: CLO:0001230
  accession_url: http://purl.obolibrary.org/obo/CLO_0001230
```

## Hep G2 cell

```yaml
id: hep_g2_cell
label: Hep G2 cell
description:
parent: cell_type
status:
notes:
- should be moved from Cell Type to Cell Line if we opt for a designated Cell Line column
related_to: []
external_mappings:
- accession_id: CLO:0003704
  accession_url: http://purl.obolibrary.org/obo/CLO_0003704
```

## immortal proximal tubule-derived cell line cell

```yaml
id: immortal_proximal_tubule_derived_cell_line_cell
label: immortal proximal tubule-derived cell line cell
description: An immortal cell line cell that derives from proximal tubule.
parent: cell_type
status:
notes:
- unsure if the line is immortal or not (was submitted as just "proximal tubule cell line"
- should be moved from Cell Type to Cell Line if we opt for a designated Cell Line column
related_to: []
external_mappings:
- accession_id: CLO:0000370
  accession_url: http://purl.obolibrary.org/obo/CLO_0000370
```
## induced neurons

```yaml
id: induced_neurons
label: induced neurons
description: The basic cellular unit of nervous tissue. Each neuron consists of a body, an axon, and dendrites. Their purpose is to receive, conduct, and transmit impulses in the nervous system.
parent: cell_type
status:
notes:
- Induced neurons (iN); provenance (directly converted) should be captured in a Model System field - Need CL and CLO to record that this is a Neuron (CL:0000540) derived from an iPSC (CLO:0037307)
related_to: []
external_mappings:
- accession_id: CL:0000540
  accession_url: http://purl.obolibrary.org/obo/CL_0000540
```

## iPSC

```yaml
id: ipsc
label: iPSC
description: A stem cell line cell that is pluripotent and is generated from an adult somatic cell.
parent: cell_type
status:
notes:
related_to: []
external_mappings:
- accession_id: CLO:0037307
  accession_url: http://purl.obolibrary.org/obo/CLO_0037307
```

## luminal epithelial cell of mammary gland

```yaml
id: luminal_epithelial_cell_of_mammary_gland
label: luminal epithelial cell of mammary gland
description: A mammary epithelial cell that occurs in the lumen of the ductal and alveoli structure in the breast, performing functions including synthesis, storage, and secretion of milk.
parent: cell_type
status:
notes:
- luminal epithelial cells / human mammary epithelial cell
related_to: []
external_mappings:
- accession_id: CL:0002326
  accession_url: http://purl.obolibrary.org/obo/CL_0002326
```

## M-1 cell

```yaml
id: m_1_cell
label: M-1 cell
description: Immortal mouse collecting duct of renal tubule-derived cell line.
parent: cell_type
status:
notes:
- should be moved from Cell Type to Cell Line if we opt for a designated Cell Line column
related_to: []
external_mappings:
- accession_id: CLO:0007449
  accession_url: http://purl.obolibrary.org/obo/CLO_0007449
```

## macrophage

```yaml
id: macrophage
label: macrophage
description: A mononuclear phagocyte present in a variety of tissues, typically differentiated from monocytes, capable of phagocytosing a variety of extracellular particulate material, including immune complexes, microorganisms, and dead cells.
parent: cell_type
status:
notes:
related_to: []
external_mappings:
- accession_id: CL:0000235
  accession_url: http://purl.obolibrary.org/obo/CL_0000235
```

## MCF 10A cell

```yaml
id: mcf_10a_cell
label: MCF 10A cell
description: A spontaneously immortalized, but nontransformed human mammary epithelial cell line derived from the breast tissue of a patient with fibrocystic changes.
parent: cell_type
status:
notes:
- should be moved from Cell Type to Cell Line if we opt for a designated Cell Line column
related_to: []
external_mappings:
- accession_id: CLO:0007599
  accession_url: http://purl.obolibrary.org/obo/CLO_0007599
```

## MEF cell line

```yaml
id: mef_cell_line
label: MEF cell line
description: Mouse embryonic fibroblast cell line.
parent: cell_type
status:
notes:
- do we want to deviate from our chosen ontologies in order to better accommodate terms?
- should be moved from Cell Type to Cell Line if we opt for a designated Cell Line column
related_to: []
external_mappings:
- accession_id: EFO:0004037
  accession_url: http://www.ebi.ac.uk/efo/EFO_0004037
```

## mESC

```yaml
id: mesc
label: mESC
description: Mouse embryonic stem cell.
parent: cell_type
status:
notes:
related_to: []
external_mappings:
- accession_id: EFO:0004038
  accession_url: http://www.ebi.ac.uk/efo/EFO_0004038
```

## neural progenitor cell

```yaml
id: neural_progenitor_cell
label: neural progenitor cell
description: An undifferentiated cell derived from a neural stem cell, with a limited capacity to self-renew and the ability to generate multiple types of lineage-restricted progenitors, contributing to the formation of neurons, astrocytes, and oligodendrocytes.
parent: cell_type
status:
notes:
related_to: []
external_mappings:
- accession_id: CL:0011020
  accession_url: http://purl.obolibrary.org/obo/CL_0011020
```

## neuron

```yaml
id: neuron
label: neuron
description: The basic cellular unit of nervous tissue. Each neuron consists of a body, an axon, and dendrites. Their purpose is to receive, conduct, and transmit impulses in the nervous system.
parent: cell_type
status:
notes:
related_to: []
external_mappings:
- accession_id: CL:0000540
  accession_url: http://purl.obolibrary.org/obo/CL_0000540
```

## OV56

```yaml
id: ov56
label: OV56
description: Cell line established from ascitic fluid derived from a patient diagnosed with stage IV, poorly differentiated ovarian cancer.
parent: cell_type
status:
notes:
- should be moved from Cell Type to Cell Line if we opt for a designated Cell Line column
related_to: []
external_mappings:
- accession_id: EFO:0006458
  accession_url: http://www.ebi.ac.uk/efo/EFO_0006458
```

## pancreatic beta cell

```yaml
id: pancreatic_beta_cell
label: pancreatic beta cell
description: One of the cells that compose the bulk of the islets of Langerhans and secrete insulin.
parent: cell_type
status:
notes:
- No ontology term for the specific line submitted (EndoCpH3 Cells)
- if we change the term from the "pancreatic beta cell" umbrella to the specific line, should be moved from Cell Type to Cell Line if we opt for a designated Cell Line column
related_to: []
external_mappings:
- accession_id: BTO:0000783
  accession_url: http://purl.obolibrary.org/obo/BTO_0000783
```

## PBMC

```yaml
id: pbmc
label: PBMC
description: A leukocyte with a single non-segmented nucleus in the mature form found in the circulatory pool of blood.
parent: cell_type
status:
notes:
related_to: []
external_mappings:
- accession_id: CL:2000001
  accession_url: http://purl.obolibrary.org/obo/CL_2000001
```

## Thymic Epithelial Cell

```yaml
id: thymic_epithelial_cell
label: Thymic Epithelial Cell
description: 'CL: An epithelial cell of the thymus. Epithelial reticular cells are pleomorphic, stellate, non-phagocytic cells which seem to be supportive in function and are held together by desmosomes. NCIT: A reticular epithelial cell generated in the thymus that affects T-lymphocyte cell production. Thymic epithelial cells are organized in a three-dimensional network rather than as a sheet of cells on a basement membrane.'
parent: cell_type
status:
notes:
- Which one should we use. NCIT, CL or both?
related_to: []
external_mappings:
- accession_id: CL:0002293
  accession_url: http://purl.obolibrary.org/obo/CL_0002293
- accession_id: NCIT:C33771
  accession_url: http://purl.obolibrary.org/obo/NCIT_C33771
```


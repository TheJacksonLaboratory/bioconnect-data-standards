# FAIR Data Maturity Model Assessment for BioConnect

# 1. Findable (F)

## F1

### F1-01M
- Text: Metadata is identified by a persistent identifier
- Priority: Essential
- Score: 1
- Evidence: When packaging metadata in an RO-Crate, we assign an identifier to each metadata object. This is used to identifiy the object in the package, and resolves to a human readable HTML page. For example:
https://bioconnect.jax.org/search/metadata-search-browse/detail-view/study/757
- Gap: The identifier is dependent on a specific angular route in the front end BioConnect application. These identifiers should be independent of a specific application or front end route in order to be truly persistent.
- Recommendation: Jax/JDS needs to commit to a persistant root URL domain and the infrastructure to support minting and serving persistent identifiers. The root URL and infrastructure should be stable over the coming years so that data remain findable. The identifier should be a URL resolvable to a human readable HTML page or machine readable response (depending on content negotiation).

### F1-01D
- Text: Data is identified by a persistent identifier
- Priority: Essential
- Score: 1
- Evidence: Same as above. Example:
https://bioconnect.jax.org/search/metadata-search-browse/detail-view/data/157088
- Gap: Same as F1-01M
- Recommendation: Same as F1-01M

### F1-02M
- Text: Metadata is identified by a globally unique identifier
- Priority: Essential
- Score: 1
- Evidence: The identifer assigned to metadata objects in BioConnect is globally unique in that it is constructed using the entity type and entity unique ID. The combination of these two values is guaranteed to be unique. In addition, the identifier is also dependent on the environmennt. For example, the identifier for a metadata object in the DEV environment is different from the identifier for the same metadata object in the PRD environment.
- Gap: As with F1-01M, the identifier is dependent on a specific angular route in the front end BioConnect application. These identifiers should be independent of a specific application or front end route in order to be truly globally unique.
- Recommendation: Implement a globally unique identifier scheme for metadata objects that is independent of the front end application and independent of environment (eg DEV, SQA, PRD). Uniqueness should be based on a dedicated root URL in combination with an entity type and an ID that is unique within the context of the entity type.

### F1-02D
- Text: Data is identified by a globally unique identifier
- Priority: Essential
- Score: 1
- Evidence: Same as F1-02M. Example: /data/157088
- Gap: Same as F1-02M
- Recommendation: Same as F1-02M

## F2

### F2-01M
- Text: Rich metadata is provided to allow discovery
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

## F3

### F3-01M
- Text: Metadata includes the identifier for the data
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

## F4

### F4-01M
- Text: Metadata is offered in such a way that it can be harvested and indexed
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

---

# 2. Accessible (A)

## A1

### A1-01M
- Text: Metadata contains information to enable the user to get access to the data
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

### A1-02M
- Text: Metadata can be accessed manually (i.e. with human intervention)
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### A1-02D
- Text: Data can be accessed manually (i.e. with human intervention)
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### A1-03M
- Text: Metadata identifier resolves to a metadata record
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### A1-03D
- Text: Data identifier resolves to a digital object
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### A1-04M
- Text: Metadata is accessed through standardised protocol
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### A1-04D
- Text: Data is accessible through standardised protocol
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### A1-05D
- Text: Data can be accessed automatically (i.e. by a computer program)
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

## A1.1

### A1.1-01M
- Text: Metadata is accessible through a free access protocol
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### A1.1-01D
- Text: Data is accessible through a free access protocol
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

## A1.2

### A1.2-02D
- Text: Data is accessible through an access protocol that supports authentication and authorisation
- Priority: Useful
- Score:
- Evidence:
- Gap:
- Recommendation:

## A2

### A2-01M
- Text: Metadata is guaranteed to remain available after data is no longer available
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

---

# 3. Interoperable (I)

## I1

### I1-01M
- Text: Metadata uses knowledge representation expressed in standardised format
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

### I1-01D
- Text: Data uses knowledge representation expressed in standardised format
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

### I1-02M
- Text: Metadata uses machine-understandable knowledge representation
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

### I1-02D
- Text: Data uses machine-understandable knowledge representation
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

## I2

### I2-01M
- Text: Metadata uses FAIR-compliant vocabularies
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

### I2-01D
- Text: Data uses FAIR-compliant vocabularies
- Priority: Useful
- Score:
- Evidence:
- Gap:
- Recommendation:

## I3

### I3-01M
- Text: Metadata includes references to other metadata
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

### I3-01D
- Text: Data includes references to other data
- Priority: Useful
- Score:
- Evidence:
- Gap:
- Recommendation:

### I3-02M
- Text: Metadata includes references to other data
- Priority: Useful
- Score:
- Evidence:
- Gap:
- Recommendation:

### I3-02D
- Text: Data includes qualified references to other data
- Priority: Useful
- Score:
- Evidence:
- Gap:
- Recommendation:

### I3-03M
- Text: Metadata includes qualified references to other metadata
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

### I3-04M
- Text: Metadata include qualified references to other data
- Priority: Useful
- Score:
- Evidence:
- Gap:
- Recommendation:

---

# 4. Reusable (R)

## R1

### R1-01M
- Text: Plurality of accurate and relevant attributes are provided to allow reuse
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

## R1.1

### R1.1-01M
- Text: Metadata includes information about the licence under which the data can be reused
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### R1.1-02M
- Text: Metadata refers to a standard reuse licence
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

### R1.1-03M
- Text: Metadata refers to a machine-understandable reuse licence
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

## R1.2

### R1.2-01M
- Text: Metadata includes provenance information according to community-specific standards
- Priority: Important
- Score:
- Evidence:
- Gap:
- Recommendation:

### R1.2-02M
- Text: Metadata includes provenance information according to a cross-community language
- Priority: Useful
- Score:
- Evidence:
- Gap:
- Recommendation:

## R1.3

### R1.3-01M
- Text: Metadata complies with a community standard
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### R1.3-01D
- Text: Data complies with a community standard
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### R1.3-02M
- Text: Metadata is expressed in compliance with a machine-understandable community standard
- Priority: Essential
- Score:
- Evidence:
- Gap:
- Recommendation:

### R1.3-02D
- Text: Data is expressed in compliance with a machine-understandable community standard
- Priority:
- Score:
- Evidence:
- Gap:
- Recommendation:

---

# Summary Table

| Principle | Score | Notes |
|----------|------|------|
| Findable |      |      |
| Accessible |    |      |
| Interoperable | |      |
| Reusable |     |      |

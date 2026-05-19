# FAIR Data Maturity Model Assessment for BioConnect
This assessment is based on the [FAIR Data Maturity Model](https://www.rd-alliance.org/system/files/FAIR%20Data%20Maturity%20Model_%20specification%20and%20guidelines_v0.90.pdf), which provides a framework for evaluating the FAIRness of data and metadata. The assessment is organized according to the four FAIR principles: Findable, Accessible, Interoperable, and Reusable. Each principle is further broken down into specific criteria, which are evaluated based on evidence from the BioConnect application. The assessment includes scores for each criterion, as well as identified gaps and recommendations for improvement.

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
- Evidence: Same as F1-01M. Example: data/157088
- Gap: Same as F1-01M
- Recommendation: Same as F1-01M

### F1-02M
- Text: Metadata is identified by a globally unique identifier
- Priority: Essential
- Score: 1
- Evidence: The identifer assigned to metadata objects in BioConnect is globally unique in that it is constructed using the entity type and entity primary key. The combination of these two values and the bioconnect domain is guaranteed to be unique. 
- Gap: As with F1-01M, the identifier is dependent on a specific angular route in the front end BioConnect application. These identifiers should be independent of a specific application or front end route in order to be truly globally unique. In addition, the identifier is also dependent on the environmennt. For example, the identifier for a metadata object in the DEV environment is different from the identifier for the same metadata object in the PRD environment, because the root url is different.
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
- Score: 3
- Evidence: The metadata model for BioConnect is designed to capture metadata in compliance with the ISA community standard. All data are connected to a study and assay. Study metadata includes information about the design, factors, contacts, and the publications associated with the study. Assay metadata includes the measurement type, equipment, protocols, and samples. This rich metadata allows users to discover relevant data based on their research interests and needs.
- Gap: N/A
- Recommendation: N/A

## F3

### F3-01M
- Text: Metadata includes the identifier for the data
- Priority: Essential
- Score: 3
- Evidence: All data in BioConnect are connected to an assay, which is always connected to a study. Data always travel with their metadata, and the metadata always includes the identifier for the data. 
BioConnect uses the RO-Crate package format for data export, which includes a linked data (JSON-LD) metadata file. When exporting a data package from BioConnect, the RO-Crate metadata file includes the identifier of each data file (via "hasPart"), and that identifier is linked to all of the metadata via a linked data graph.
- Gap: N/A
- Recommendation: N/A

## F4

### F4-01M
- Text: Metadata is offered in such a way that it can be harvested and indexed
- Priority: Essential
- Score: 1
- Evidence: Study based RO-Crate data packages can be exported from BioConnect, and these packages include metadata in a standard format (JSON-LD) that can be harvested and indexed by search engines and other data discovery tools.
- Gap: The BioConnect API end points that serve metadata are not designed to be harvested and indexed by search engines or other data discovery tools. In addition, the end points require authentication, which makes it difficult for search engines to access the metadata.
- Recommendation: To fully comply with this principle, metadata that have been shared publicly should be made available through open API end points that are designed to be harvested and indexed by data discovery tools. These end points should not require authentication, and should be designed to support content negotiation so that metadata can be accessed in both human readable and machine readable formats. Metadata should be served in a standard format (JSON-LD/RDF).
Additionally, an RO-Crate data package repository could be implemented to support harvesting and indexing metadata. Because RO-Crate metadata are in a standard JSON-LD format, they lend themselves to data discovery. An example of this is WorkflowHub.

---

# 2. Accessible (A)

## A1

### A1-01M
- Text: Metadata contains information to enable the user to get access to the data
- Priority: Important
- Score: 1
- Evidence: Data are always associated with a study. Studies are access controlled using Fine Grained Authorization (FGA). So we are capturing access control rules in the metadata. In addition, study contacts (along with their roles) are included in the metadata, which provides users with information about who to contact to request access to the data.
- Gap: Though metadata captures access control rules, BioConnect users must have at least read access to the study in order to view the metadata. This means that users cannot access metadata for studies that they do not have access to, and therefore cannot determine whether they should request access to the data.
- Recommendation: To fully comply with this principle, at least some study metadata should be made available to users even if they do not have access to the underlying data. This could be achieved by providing a summary version of the metadata that includes only high level information such as study title and contacts. 

### A1-02M
- Text: Metadata can be accessed manually (i.e. with human intervention)
- Priority: Essential
- Score: 3
- Evidence: Metadata can be accessed manually through the BioConnect user interface, which allows users to view and download metadata for studies they have access to. For example, after logging in, users can view study metadata by navigating to the study detail page, and they can download metadata in RO-Crate format from the same page.
- Gap: N/A
- Recommendation: N/A

### A1-02D
- Text: Data can be accessed manually (i.e. with human intervention)
- Priority: Essential
- Score: 3
- Evidence: Data are inlcuded, along with their metadata, in RO-Crate data packages that can be downloaded through the BioConnect user interface.
- Gap: N/A
- Recommendation: N/A

### A1-03M
- Text: Metadata identifier resolves to a metadata record
- Priority: Essential
- Score: 1
- Evidence: We are generating an identifier for each individual metadata record in a study when generating a data package. These identifiers resolve to a human readable HTML page that displays the metadata record. For example:
https://bioconnect.jax.org/search/metadata-search-browse/detail-view/study/757
- Gap: Though this is implemented for data package exports, the identifiers are generated on the fly and have dependencies that mean they are not stable over time. In addition, the identifiers do not resolve to a machine readable metadata record, which is necessary for programmatic access to the metadata.
- Recommendation: To fully comply with this principle, we need to implement a stable identifier scheme for metadata records. Each record (studies, assays, contacts, samples, etc) should be "born" with a permanent, unique http URI. This URI can be used from anywhere to dereference the object in either human or machine readable format. Uniqueness should be based on a dedicated root URL in combination with an entity type and a GUID. These URIs should resolve to both human readable HTML pages and machine readable metadata records (depending on content negotiation).

### A1-03D
- Text: Data identifier resolves to a digital object
- Priority: Essential
- Score: 1
- Evidence: Data files in BioConnect are either stored in a BioConnect Google Cloud Storage bucket or are referenced by an external URL. In either case, the identifier for a data file does not resolve to the data file itself, but rather to a human readable HTML page that provides information about the data file and includes a link to download the data file. For example:
https://bioconnect.jax.org/search/metadata-search-browse/detail-view/data/157530
- Gap: The identifiers do not resolve to the data file itself, which is necessary for programmatic access to the data. In addition, the identifiers are generated on the fly and have dependencies that mean they are not stable over time.
- Recommendation: The Software and Platforms team is currently evaluating the [Data Repository Service (DRS)](https://www.ga4gh.org/product/data-repository-service-drs/) as a potential solution for serving data files across JDS. If implemented, this service would provide stable, resolvable identifiers for data files and handle file retrieval.

### A1-04M
- Text: Metadata is accessed through standardised protocol
- Priority: Essential
- Score: 3
- Evidence: All BioConnect metadata is available via the BioConnect API, which is a RESTful API that serves metadata over https.
- Gap: N/A
- Recommendation: N/A

### A1-04D
- Text: Data is accessible through standardised protocol
- Priority: Essential
- Score: 3
- Evidence: Data files in BioConnect are either stored in a BioConnect Google Cloud Storage bucket or are referenced by an external URL. In either case, data files can be accessed through standardised protocols (either https or gsutil).
- Gap: N/A
- Recommendation: N/A

### A1-05D
- Text: Data can be accessed automatically (i.e. by a computer program)
- Priority: Important
- Score: 1
- Evidence: When BioConnect builds a data package, the API uses the jax-cs-storage library to download assay data files using the file metadata. Each ISA Data records is optionally attached to a stored file record, which represents a data file in the BioConnect Google Cloud Storage bucket. If a data file is attached to the ISA Data record, then the API can use the jax-cs-storage library to download the data file and include it in the data package. However, this functionality is currently only implemented for data package exports, and is not available through a standardised protocol that can be accessed by external programs.
Some Data records represent external data files that are not stored in the BioConnect Google Cloud Storage bucket. In this case, the Data record includes a URL that points to the external data file. However, there is no standardised protocol for accessing these external data files, and the URLs may not be stable over time.
- Gap: Applications external to BioConnect cannot download files on a machine to machine basis.
- Recommendation: Integrate BioConnect with the Data Repository Service (DRS) to provide stable, resolvable URLs and programmatic access to data files.

## A1.1

### A1.1-01M
- Text: Metadata is accessible through a free access protocol
- Priority: Essential
- Score: 3
- Evidence: Metadata in BioConnect are available via HTTPS protocols, which means there is no cost to access the metadata. However, users must have at least read access to the metadata in order to retrieve it.
- Gap: N/A
- Recommendation: N/A

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
- Score: 3
- Evidence: All requests for data go through HTTPS end points that require an Auth0 access token. This access token is validated and used to do a check request to the Fine Grained Authorization (FGA) service to determine whether the user has access to the data. If the user has access, then the data is returned. If the user does not have access, then an error is returned.
- Gap: N/A
- Recommendation: N/A

## A2

### A2-01M
- Text: Metadata is guaranteed to remain available after data is no longer available
- Priority: Essential
- Score: 0
- Evidence: N/A
- Gap: Metadata for a data record in BioConnect is deleted when the data record is deleted. There is currently no mechanism to ensure that metadata remains available after the data is no longer available.
- Recommendation: To comply with this indicator, the Data Assets team has designed a PID (Persistent Identifier) service that will mint and manage persistent identifiers for metadata records. This service will store metadata permanently to ensure that metadata records remain available even if the underlying data file is deleted. When a data record gets created, its metadata will be conveyed to the PID service, which will store it and return a PID. From that point on, the PID will always be resolvable to the metadata record, even if the underlying data is deleted. Deleted data records' PIDs will come with a status to indicate that it has been deleted (aka "tombstone" record).

---

# 3. Interoperable (I)

## I1

### I1-01M
- Text: Metadata uses knowledge representation expressed in standardised format
- Priority: Important
- Score: 3
- Evidence: Metadata in BioConnect adheres to a community standard schema: the ISA (Investigation, Study, Assay) model. This schema is widely used in the life sciences domain and provides a structured way to represent metadata about studies, assays, samples, and data files. By using this standardized format, BioConnect metadata can be more easily understood and used by other applications and researchers. A standard schema makes the metadata more interoperable because it provides a common structure and vocabulary for representing metadata across different systems and applications. In addition, the ISA model allows for almost any entity to be annotated with ontology terms, and the BioConnect curation UI supports the management of a standard set of ontology and vocabulary terms. Professional curators maintain the list of controlled terms and carefully manage the ontology sources used to annotate metadata.
- Gap: N/A
- Recommendation: N/A

### I1-01D
- Text: Data uses knowledge representation expressed in standardised format
- Priority: Important
- Score: 3
- Evidence: Where applicable, data files in BioConnect are defined using the Frictionless Data standard, which means that each column in a tabular data file is defined with metadata that describes the column name, description, data type, format, min/max values and other information relevant to analysis of the file. In addition, when a user downloads data from BioConnect, the data come in an RO-Crate data package. RO-Crate is a standard format for packaging data and metadata together, and includes a JSON-LD metadata file that describes the data files and metadata in the package. If any of the data files is mapped to a Frictionless Data definition, this is included in the data package.
- Gap: N/A
- Recommendation: N/A

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

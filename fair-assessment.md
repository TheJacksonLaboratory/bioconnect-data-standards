# FAIR Data Maturity Model Assessment for BioConnect
This assessment is based on the [FAIR Data Maturity Model](https://www.rd-alliance.org/system/files/FAIR%20Data%20Maturity%20Model_%20specification%20and%20guidelines_v0.90.pdf), which provides a framework for evaluating the FAIRness of data and metadata. The assessment is organized according to the four FAIR principles: Findable, Accessible, Interoperable, and Reusable. Each principle is further broken down into specific criteria, which are evaluated based on evidence from the BioConnect application. The assessment includes scores for each criterion, as well as identified gaps and recommendations for improvement.

# 1. Findable (F)

## F1

### F1-01M
- Text: Metadata is identified by a persistent identifier
- Priority: Essential
- Score: 1
- Evidence: Metadata objects are assigned an identifier when referenced in a data package, but these do not fully meet the criteria for this indicator. The Data Assets team has designed a Persistent Identifier (PID) service that will mint and manage persistent identifiers for metadata records. This service will store metadata permanently to ensure that metadata records remain available even if the underlying entity is deleted. When a metadata record gets created, it will be conveyed to the PID service, which will store it and return a PID. From that point on, the PID will always be resolvable to the metadata record, even if the underlying data is deleted. Deleted metadata records' PIDs will come with a status to indicate that it has been deleted.
- Gap: BioConnect currently assigns a metadata identifier for each entity in a data package, but these identifiers are generated on the fly and have dependencies that mean they are not stable over time. They are dependent on specific environments and are dependent on a specific front end route that could change over time.
- Recommendation: Implement the PID service as designed.

### F1-01D
- Text: Data is identified by a persistent identifier
- Priority: Essential
- Score: 1
- Evidence: Similar to F1-01M. The PID service will also mint and manage persistent identifiers for data records.
- Gap: Same as F1-01M
- Recommendation: Same as F1-01M

### F1-02M
- Text: Metadata is identified by a globally unique identifier
- Priority: Essential
- Score: 1
- Evidence: The proposed PID service will mint globally unique identifiers, regardless of entity type.
- Gap: The identifiers currently assigned to metadata objects in a BioConnect data package are globally unique in that they are constructed using the entity type and entity primary key. The combination of these two values and the bioconnect domain is guaranteed to be unique. But as with F1-01M, the identifier is dependent on a specific route in the front end BioConnect application. These identifiers should be independent of a specific application or front end route in order to be truly globally unique. In addition, the identifier is also dependent on the environment. For example, the identifier for a metadata object in the DEV environment is different from the identifier for the same metadata object in the PRD environment, because the root url is different.
- Recommendation: Implement the PID service as designed.


### F1-02D
- Text: Data is identified by a globally unique identifier
- Priority: Essential
- Score: 1
- Evidence: Same as F1-02M. The PID service will mint globally unique identifiers for data records.
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
- Score: 2
- Evidence: All data in BioConnect are connected to an assay, which is always connected to a study. Data always travel with their metadata, and the metadata always includes the identifier for the data. BioConnect uses the RO-Crate package format for data export, which includes a linked data (JSON-LD) metadata file. When exporting a data package from BioConnect, the RO-Crate metadata file includes the identifier of each data file (via "hasPart"), and that identifier is linked to all of the metadata via a linked data graph.
- Gap: The identifiers are not globally unique or persistent.
- Recommendation: Once the PID service is implemented, the metadata should be updated to include the persistent identifier for each data record. This will ensure that the metadata includes a stable identifier for the data that can be used for discovery and access.

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
- Evidence: Data files that have been uploaded to BioConnect are included, along with their metadata, in RO-Crate data packages that can be downloaded through the BioConnect user interface. In cases where data files are not stored in BioConnect, the metadata includes a URL that points to the external data file, where it can be downloaded.
- Gap: N/A
- Recommendation: N/A

### A1-03M
- Text: Metadata identifier resolves to a metadata record
- Priority: Essential
- Score: 1
- Evidence: We are currently generating an identifier for each individual metadata record in a study when generating a data package. These identifiers resolve to a human readable HTML page that displays the metadata record. For example:
https://bioconnect.jax.org/search/metadata-search-browse/detail-view/study/757
- Gap: Though this is implemented for data package exports, the identifiers are generated on the fly and have dependencies that mean they are not stable over time. In addition, the identifiers do not resolve to a machine readable metadata record, which is necessary for programmatic access to the metadata.
- Recommendation: To fully comply with this indicator, we will implement the PID service. Each record (studies, assays, contacts, samples, etc) will be "born" with a permanent, unique PID. This PID is a URL that can be used from anywhere to dereference the object in either human or machine readable format. Uniqueness should be based on a dedicated root URL in combination with a globally unique token. These URIs should resolve to both human readable HTML pages and machine readable metadata records (depending on content negotiation).

### A1-03D
- Text: Data identifier resolves to a digital object
- Priority: Essential
- Score: 1
- Evidence: Data files in BioConnect are either stored in a BioConnect Google Cloud Storage bucket or are referenced by an external URL. In either case, the identifier for a data file does not resolve to the data file itself, but rather to a human readable HTML page that provides information about the data file and includes a link to download the data file.
- Gap: The identifiers do not resolve to the data file itself, which is necessary for programmatic access to the data. In addition, the identifiers are generated on the fly and have dependencies that mean they are not stable over time.
- Recommendation: The Software and Platforms team is currently implementing the [Data Repository Service (DRS)](https://www.ga4gh.org/product/data-repository-service-drs/) as a solution for serving data files across JDS. This service will provide resolvable identifiers for data files and handle file retrieval. The PID service will assign a persistent identifier for the file metadata, and the DRS service will assign a URL for file retrieval. Include the DRS URL with the data record metadata.

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
- Evidence: Data files in BioConnect are either stored in a BioConnect Google Cloud Storage bucket or are referenced by an external URL. BioConnect data files are included in the RO-Crate data package exports, which can be downloaded through standard HTTPS protocol.
- Gap: BioConnect supports references to data stored in external systems that are outside of its control. For externally managed data, BioConnect cannot guarantee that access is provided through a standardized protocol.
- Recommendation: Establish a managed data commons that provides persistent access to hosted datasets through HTTPS download mechanisms. Where data are externally managed, capture and validate access information to allow for the use of open protocols.

### A1-05D
- Text: Data can be accessed automatically (i.e. by a computer program)
- Priority: Important
- Score: 1
- Evidence: When BioConnect builds a data package, the API uses the jax-cs-storage library to download assay data files using the file metadata. Each ISA Data record is optionally attached to a stored file record, which represents a data file in the BioConnect Google Cloud Storage bucket. If a data file is attached to the ISA Data record, then the API can use the jax-cs-storage library to download the data file and include it in the data package. However, this functionality is currently only implemented for data package exports, and is not available through a standardised protocol that can be accessed by external programs.
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
- Score: 2
- Evidence: BioConnect provides access to data files through HTTPS download mechanisms. Files stored in the BioConnect managed Google Cloud Storage bucket can be retrieved using standard web protocols and downloaded as part of a data package zip file. HTTPS is a free and open protocol supported by a wide range of software systems.
- Gap: BioConnect supports references to data stored in external systems that are outside of its control. For externally managed data, BioConnect cannot guarantee that access is provided through open protocols.
- Recommendation: Same as A1-04D

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
- Evidence: Where applicable, data files in BioConnect are defined using the [Frictionless Data standard](https://frictionlessdata.io/) (see I1-02D below). BioConnect provides a user friendly interface for building Frictionless file definitions, including the ability to import an existing file as the basis for a file type definition. In addition, when a user downloads data from BioConnect, the data come in an [RO-Crate data package](https://www.researchobject.org/ro-crate/). RO-Crate is a standard format for packaging data and metadata together, and includes a JSON-LD metadata file that describes the data files and metadata in the package.
- Gap: N/A
- Recommendation: N/A

### I1-02M
- Text: Metadata uses machine-understandable knowledge representation
- Priority: Important
- Score: 1
- Evidence: When downloading a data package from BioConnect, the RO-Crate data package includes a JSON-LD metadata file that describes the data files and metadata in the package. This file is human and machine readable JSON-LD per the RO-Crate specification. 
- Gap: Though the RO-Crate metadata file itself is machine readable, not all of the metadata in BioConnect is currently available in a machine readable format.
- Recommendation: Once the PID service is implemented, all metadata should be updated to include the persistent identifier for each record. This will ensure that all metadata records have a stable identifier that can be used in a machine readable way to support a linked data ecosystem. PIDs will be used to reference metadata in the RO-Crate metadata file, making it fully machine readable.

### I1-02D
- Text: Data uses machine-understandable knowledge representation
- Priority: Important
- Score: 3
- Evidence: Using the Frictionless Data standard, each column in a tabular data file is defined with metadata that describes the column name, description, data type, format, min/max values and other information relevant to analysis of the file. Columns are mapped via rdf_type to machine readable objects such as ontology annotation accession URLs, making the data compatible with linked data standards. If any of the data files is mapped to a Frictionless Data definition, the Frictionless resource is included in the data package. The RO-Crate metadata for the file includes a "conformsTo" property that machines can use to infer the structure and format of the data file from the Frictionless resource.
- Gap: N/A
- Recommendation: N/A

## I2

### I2-01M
- Text: Metadata uses FAIR-compliant vocabularies
- Priority: Important
- Score: 1
- Evidence: BioConnect metadata can be annotated with ontology terms from any ontology source (eg UBERON, EFO). However, not all terms are FAIR compliant. The Data Assets team is currently working on designing an application ontology for use within the JDS ecosystem. The application ontology design is based on "Ten simple rules for making a vocabulary FAIR" (https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1009041). Once the application ontology is implemented, we will update the BioConnect curation UI to require that metadata be annotated with terms from the application ontology. Where applicable, terms can still be mapped to external ontology terms, but the application ontology allows us to ensure that all terms are resolvable and can be used in a machine readable way that supports a linked data ecosystem.
- Gap: The BioConnect curation UI supports the management of a standard set of ontology and vocabulary terms, though it is not required that they be linked to a FAIR compliant ontology term. Sometimes it is just a stand alone character string (eg 10% fat diet). Not all terms are resolvable or machine readable.
- Recommendation: Implement the application ontology service.

### I2-01D
- Text: Data uses FAIR-compliant vocabularies
- Priority: Useful
- Score: 1
- Evidence: Same as I2-01M
- Gap: Same as I2-01M
- Recommendation: Same as I2-01M

## I3

### I3-01M
- Text: Metadata includes references to other metadata
- Priority: Important
- Score: 3
- Evidence: All metadata in BioConnect references other metadata. Even the metadata from one study can be related to that of another study via an investigation. See I3-03M for details about the representations of relationships.
- Gap: N/A
- Recommendation: N/A

### I3-01D
- Text: Data includes references to other data
- Priority: Useful
- Score: 2
- Evidence: Data files are attached to assays, and assays contain a process sequence. Each process sequence has a set of inputs and outputs. Data files may be used as inputs or outputs in the process sequence, which creates a reference from one file to another via a process. For example, a process might represent running a script that transforms raw data to derived data. The raw data file would be an input to the process, and the derived data file would be an output of the process. These references are carried through to the machine readable RO-Crate metadata file. In addition, Frictionless Data definitions can be used to indicate that one column is the source of another column within a file.
- Gap: Because BioConnect does not manage data within the file itself, it does not currently support internal references within the data.
- Recommendation: Evaluate the feasibility of supporting internal references within data files.

### I3-02M
- Text: Metadata includes references to other data
- Priority: Useful
- Score: 2
- Evidence: In addition to a study's metadata referencing the data collected as part of the study's assays, BioConnect also supports attaching context data files to a study, a protocol, or a resource. Context data files represent images, documents, or other files that provide additional context for the data. For example, a context data file attached to an instrument might be a picture of the instrument.
- Gap: Context data files are not currently included in the RO-Crate metadata file, so these references are not currently available in a machine readable way that supports a linked data ecosystem.
- Recommendation: Update the RO-Crate generation logic to include context data files.

### I3-02D
- Text: Data includes qualified references to other data
- Priority: Useful
- Score: 0
- Evidence: N/A
- Gap: Though one data file can be related to another data file via a process, there is currently no way to create a qualified relationship among data files.
- Recommendation: Implement a mechanism to qualify the relationship of one data file to another.

### I3-03M
- Text: Metadata includes qualified references to other metadata
- Priority: Important
- Score: 3
- Evidence: The ISA model defines explicit relationship types among metadata entities, including study-assay containment, sample lineage, protocol usage, ontology annotation, and investigation-study relationships. These relationships carry defined semantics and therefore constitute qualified references.
- Gap: N/A
- Recommendation: N/A

### I3-04M
- Text: Metadata includes qualified references to other data
- Priority: Useful
- Score: 1
- Evidence: Per I3-02M, BioConnect supports attaching context data files to a study, a protocol, or a resource. These context data files provide additional information about the study, protocol, or resource, but are only references.
- Gap: These relationships are not qualified; the nature of the relationship between the metadata and the context file is not explicitly represented.
- Recommendation: Extend the metadata model to allow for explicit representation of the relationship between the metadata and the context file.

---

# 4. Reusable (R)

## R1

### R1-01M
- Text: Plurality of accurate and relevant attributes are provided to allow reuse
- Priority: Essential
- Score: 2
- Evidence: BioConnect uses the ISA (Investigation, Study, Assay) metadata model to capture rich experimental metadata. Metadata includes study descriptions, publications, protocols, contacts, ontology annotations, sample characteristics, experimental factors, assay measurement types, technology types, process provenance, and data file information. The metadata model supports domain specific attributes through material attributes, factor values, and ontology annotations, allowing studies to capture the information necessary for interpretation and reuse. The ISA framework is a widely adopted life science metadata standard designed to support reproducibility and data reuse.
- Gap: BioConnect does not currently evaluate metadata completeness against specific community reporting standards or guidelines.
- Recommendation: Select an appropriate community standard for metadata completeness and implement a means to evaluate BioConnect metadata against that standard. This could be implemented as a completeness score that is included in the metadata and can be used to filter data packages based on metadata completeness.

## R1.1

### R1.1-01M
- Text: Metadata includes information about the licence under which the data can be reused
- Priority: Essential
- Score: 1
- Evidence: BioConnect data packages contain a license link, directing the user to https://bioconnect.jax.org/assets/Cube%20Consortium%20Data%20Access%20and%20Publishing%20Guidelines.pdf
- Gap: The license being used is specific to the Cube initiative. It is the only license available, and so there is no way to indicate different reuse licenses for different data packages.
- Recommendation: Implement support for multiple licenses to allow different data packages to specify different reuse terms.

### R1.1-02M
- Text: Metadata refers to a standard reuse licence
- Priority: Important
- Score: 0
- Evidence: N/A
- Gap: The license being used is specific to the Cube initiative and is not a standard reuse license such as Creative Commons or Open Data Commons.
- Recommendation: Evaluate standard reuse licenses and select one or more to support in BioConnect.

### R1.1-03M
- Text: Metadata refers to a machine-understandable reuse licence
- Priority: Important
- Score: 0
- Evidence: N/A
- Gap: The license being used is specific to the Cube initiative and is not machine-understandable.
- Recommendation: Evaluate machine-understandable licenses and select one or more to support in BioConnect.

## R1.2

### R1.2-01M
- Text: Metadata includes provenance information according to community-specific standards
- Priority: Important
- Score: 3
- Evidence: BioConnect captures provenance using the ISA metadata model, which is specific to and understandable by the scientific community. ISA process sequences explicitly represent the inputs, outputs, and protocols associated with assay data collection. Metadata captures the relationships between sources, samples, and resulting datasets.
- Gap: N/A
- Recommendation: N/A

### R1.2-02M
- Text: Metadata includes provenance information according to a cross-community language
- Priority: Useful
- Score: 0
- Evidence: N/A
- Gap: Provenance information is represented using ISA constructs but is not currently exposed using a dedicated provenance ontology such as W3C PROV-O. This limits the cross community reuse of the data.
- Recommendation: To improve the cross-community actionability of the RO-Crate metadata, we should represent provenance information using a standard provenance ontology such as W3C PROV-O. This would allow us to represent provenance information in a more domain agnostic way. It would require mapping ISA entities and relationships to PROV-O.

## R1.3

### R1.3-01M
- Text: Metadata complies with a community standard
- Priority: Essential
- Score: 3
- Evidence: BioConnect metadata complies with the ISA (Investigation, Study, Assay) community standard for life science metadata. Core metadata entities, including studies, assays, samples, protocols, process sequences, and ontology annotations, are modeled using ISA concepts and relationships. BioConnect further supports interoperability by exposing metadata through machine-readable RO-Crate exports.
- Gap: N/A
- Recommendation: N/A

### R1.3-01D
- Text: Data complies with a community standard
- Priority: Essential
- Score: 2
- Evidence: BioConnect supports the storage and management of data in community recognized formats that are commonly used within the life sciences. These include tabular datasets and scientific file formats. Tabular data schemas may be validated using Frictionless Data specifications to ensure consistency with expected structures and value constraints. In addition, custom validation is run to ensure that terms comply with controlled vocabularies.
- Gap: BioConnect does not currently require datasets to conform to specific domain reporting standards or scientific file formats.
- Recommendation: Expand validation capabilities beyond tabular data sets.

### R1.3-02M
- Text: Metadata is expressed in compliance with a machine-understandable community standard
- Priority: Essential
- Score: 2
- Evidence: BioConnect generates machine readable RO-Crate metadata in the ro-crate-metadata.json linked data file, which can be interpreted by machines.
- Gap: The generation and distribution model for RO-Crate data packages limits the degree to which machines can automatically discover and consume the metadata. Each user generates a data package on the fly and downloads it to their local machine. The RO-Crate metadata is machine-readable once a system obtains and opens the zip file. However, there is no stable, machine-accessible location where external systems can discover or retrieve the crate.
- Recommendation: Provide persistent, machine accessible access to RO-Crates through PID based resolution or API endpoints. This would allow external systems to automatically discover, retrieve, and process RO-Crate metadata without requiring manual download and distribution by users.

### R1.3-02D
- Text: Data is expressed in compliance with a machine-understandable community standard
- Priority: Important
- Score: 1
- Evidence: BioConnect supports machine readable data through structured tabular files described using Frictionless Data schemas. These schemas provide machine actionable definitions of columns including data types, roles, constraints, and relationships. BioConnect also supports automated validation against the definitions, enabling data consumers to interpret values consistently. Data and associated schemas are included in generated RO-Crate packages to facilitate machine processing and reuse.
- Gap: Though BioConnect supports machine actionability for tabular data, it does not currently provide mechanisms to transform or export datasets into research specific exchange formats. Data intended for repositories such as GEO or SRA must be manually transformed prior to submission.
- Recommendation: Build support for allowing researchers to generate machine readable submission packages directly from BioConnect. These exports would improve interoperability, reduce manual effort, and allow compliance with community standard data formats.

---

# Summary Table

| Principle | Avg Score (out of 3) | Indicators | Notes |
|-----------|---------------------|------------|-------|
| Findable | 1.4 | 7 | Strength: rich ISA metadata (F2-01M, score 3). Key gaps: PIDs not yet implemented; metadata endpoints require authentication and are not designed for automated harvesting. |
| Accessible | 2.0 | 12 | Strengths: manual access via UI and standardised protocols are fully compliant. Critical gap: metadata is permanently deleted with data (A2-01M, score 0). |
| Interoperable | 1.9 | 12 | Strengths: ISA model, Frictionless Data schemas, machine-readable RO-Crate exports. Key gaps: FAIR-compliant vocabularies not enforced; no qualified data-to-data references (I3-02D, score 0). |
| Reusable | 1.4 | 10 | Strengths: ISA community standard compliance and provenance representation. Key gaps: no standard or machine-readable license (R1.1-02M, R1.1-03M, both score 0); no cross-community provenance language (R1.2-02M, score 0). |

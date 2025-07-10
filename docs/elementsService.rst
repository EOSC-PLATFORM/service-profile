
.. _service:

Service
=======
A Service is a digital resource or capability that supports research activities, accessible via EOSC Nodes, and accessible through APIs and/or web interfaces. Examples of services include computing, storage, analytics, access to resources, data management services, scientific workflow engines, Virtual Research Environment.


Specialization
~~~~~~~~~~~~~~
* :ref:`datasource` profile.

In addition to the properties defined by the EOSC Resource Profile (TODO ADD LINK), the EOSC Service profile defines the following properties:

.. list-table:: 
   :header-rows: 1

   * - Group
     - Element name
     - Description
     - Type
     - Multiplicity
     - Mandatory
     - Suggestions
   * - Basic
     - serviceOwner
     - The name (or abbreviation) of the organisation that manages or delivers the Service, or that coordinates Service delivery in a federated scenario.
     - string
     - 1
     - M
     - 
   * - 
     - serviceProviders
     - The name(s) (or abbreviation(s)) of Provider(s) that manage or deliver the Service in federated scenarios.
     - string
     - 0..n
     - R
     - 
   * - 
     - webpage
     - Webpage with information about the Service usually hosted and maintained by the Provider.
     - anyURI
     - 1
     - M
     - 
   * - 
     - logo
     - Link to the logo/visual identity of the Service. The logo will be visible at the Portal. If there is no specific logo for the Service the logo of the Provider may be used.
     - anyURI
     - 0..1
     - R
     - 
   * - Classification
     - scientificDomains
     - The branch of science, scientific discipline that is related to the Service.
     - tns:serviceProviderDomain Vocabularies: Domain / Subdomain.
     - 0..n
     - R
     - 
   * - 
     - category
     - 
     - tns:serviceCategory
     - 0..n
     - R
     - 
   * - 
     - tags
     - free text Keywords associated to the Service to simplify search by relevant keywords.
     - string
     - 0..n
     - R
     - 
   * - 
     - Jurisdiction
     - The property defines the jurisdiction of the users of the data source, based on the vocabulary for this property
     - Vocabulary: Jurisdiction
     - 1
     - M
     - 
   * - Maturity and Management
     - TRL
     - The Technology Readiness Level of the Service (to be further updated in the context of the EOSC).
     - string Vocabulary.
     - 1
     - M
     - 
   * - 
     - termsOfUse
     - Webpage describing the rules, Service conditions and usage policy which one must agree to abide by in order to use the Service.
     - anyURI
     - 1
     - O
     - 
   * - 
     - privacyPolicy
     - Link to the privacy policy applicable to the Service.
     - anyURI
     - 1
     - O
     - 
   * - 
     - accessPolicy
     - Information about the access policies that apply.
     - anyURI
     - 1
     - O
     - 
   * - Order
     - orderType
     - Information on the order type (requires an ordering procedure, or no ordering and if fully open or requires authentication).
     - string
     - 0..1
     - M
     - 
   * - 
     - order
     - Webpage through which an order for the Service can be placed.
     - anyURI
     - 0..1
     - O
     - 
   * - Contacts
     - contacts
     - The main researchers involved in producing the data, or the authors of the publication, in priority order. To supply multiple contacts, repeat this property.
     - object
     - 1...n
     - M
     - 
   * - 
     - contactName
     - The full name of the contact
     - string
     - 1
     - M
     - Surname, Name
   * - 
     - contactRole
     - The role of the contact
     - Credit vocabulary
     - 1
     - O
     - 
   * - 
     - contactPIDSchema
     - PID schema
     - 
     - 
     - O
     - e.g. ORCID, ROR.org
   * - 
     - contactPID
     - Uniquely identifies an individual or legal entity, according to various schemes.
     - string
     - 1
     - O
     - 
   * - 
     - affiliations
     - The organizational or institutional affiliation of the contact.
     - object
     - 0..n
     - O
     - 
   * - 
     - affiliationName
     - Name of the organisation
     - string
     - 1
     - M
     - 
   * - 
     - affiliationIdentifier
     - Uniquely identifies the organizational affiliation of the contact.
     - string
     - 1
     - O
     - ROR.org, ISNI, Wikidata
   * - 
     - email
     - email of the contact
     - string
     - 0..1
     - O
     - 

:: _datasource:

Data Source
===========

A Data Source is a special kind of EOSC Service that offers storage, preservation, discovery, and access to Research Products metadata and files (if available). Examples are thematic repositories (e.g. PANGAEA data archive), institutional repositories (e.g. HAL French repository), catch-all repositories (e.g. Zenodo.org), software repositories (e.g. GitHub), data source registries (e.g. re3data.org, FAIRSharing.og), adapters catalogues (e.g. EOSC Beyond Adapter Catalogue), Training material (e.g. OpenPlato.eu), etc. 

Specialization
~~~~~~~~~~~~~~
* :ref:`catalogue` profile.

* main profile is :ref:`service`

.. list-table:: 
   :header-rows: 1
   :widths: 10, 25, 60, 15, 15, 10, 20

   * - Group
     - Element name
     - Description
     - Type
     - Multiplicity
     - Mandatory
     - Suggestions
   * - Policies
     - Submission policy URL
     - This policy provides a comprehensive framework for the contribution of research products. Criteria for submitting content to the repository as well as product preparation guidelines can be stated. Concepts for quality assurance may be provided.
     - URL
     - 0..1
     - R
     - 
   * - 
     - Preservation policy URL
     - This policy provides a comprehensive framework for the long-term preservation of the research products. Principles aims and responsibilities must be clarified. An important aspect is the description of preservation concepts to ensure the technical and conceptual utility of the content
     - URL
     - 0..1
     - R
     - 
   * - 
     - Version control
     - If data versioning is supported: the data source explicitly allows the deposition of different versions of the same object
     - Boolean
     - 1
     - O
     - 
   * - 
     - Persistent Identity Systems
     - The persistent identifier systems that are used by the Data Source to identify the ProductType it supports
     - 
     - 0..n
     - R
     - 
   * - 
     - Persistent Identity ProductType
     - Specify the ProductType to which the persistent identifier is referring to.
     - Vocabulary: Research Product Type
     - 1
     - M
     - 
   * - 
     - Persistent Identity ProductType Scheme
     - Specify the list of persistent identifier schemes used to refer to other research-related entities (e.g., authors, organizations, etc.)
     - Vocabulary: Persistent Identity Scheme
     - 1
     - M
     - 
   * - Content
     - Data Source Classification
     - The specific type of the data source based on the vocabulary defined for this property
     - Vocabulary: Data Source Classification
     - 1
     - M
     - 
   * - 
     - Research Product Type
     - The types of OpenAIRE products managed by the data source, based on the vocabulary for this property
     - Vocabulary: Research Product Type
     - 1..n
     - M
     - 
   * - Thematic
     - Thematic
     - Boolean value specifying if the data source is dedicated to a given discipline or is instead discipline agnostic
     - Boolean
     - 1
     - M
     - 
   * - Metadata 
     - Metadata License description
     - Metadata Policy for information describing items in the repository: Access and re-use of metadata
     - 
     - 0..1
     - R
     - specifying under which license all metadata in the repository can be accessed, used, and repurposed
   * - 
     - Metadata License Name
     - Name of the license
     - string
     - 0..1
     - R
     - 
   * - 
     - Metadata License URL
     - URL of the license
     - URL
     - 0..1
     - R
     - 

Catalogue
===========

A catalogue is a Data Source that is responsible for an EOSC Node to collect (via aggregation activities or manual ingestion) and provide access to metadata records about EOSC Resources that fall under the jurisdiction of the EOSC Node. EOSC Node catalogues typically (but not always) do not offer access to content but provide metadata with links to the Data Sources that offer access to content. Examples include the CESSDA Data Catalogue and the NIFOS catalogue, among others.

* main profile is :ref:`datasource`

.. list-table:: 
   :header-rows: 1

 * - Element name
   - Description
   - Type
   - Multiplicity
   - Mandatory
   - Suggestions
 * - type of catalogue
   - 
   - string
   - 1
   - M
   - vocabulary: {service catalogue, research product catalogue}

  

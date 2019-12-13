#Issues and Recommendations for BICCN regarding use of DOI’s and data citation

**Purpose:**  To document standards, best practices and recommendations for supporting the FAIR principles and data citation in data archives associated with the BICCN

##Citing the Resource

Each repository should contain standard citation language for for citing the use of the resource or any associated tools using the Research Resource Identifier [(RRID)](https://dknet.org/about/rrid)  
e.g., Data was accessed via the BRAIN Cell Data Center (RRID:SCR_017266).  
A list of RRIDs for each of the R24 archives can be found at [NIF](https://neuinfo.org/rin/suggested-data-repositories?p1=SCR_006770). 

New resources can be registered here to receive an RRID
* First search the [NIF Resource Registry](https://neuinfo.org/Resources/search?q=%2A&l=)to make sure it does not exist already
* Register a new resource [here](https://neuinfo.org/about/resource)

##Citing a data set
Each repository should provide the necessary information to cite individual data sets, collections or subsets of data according to the Data Citation Principles.  e.g., “The data set of Ferguson et al., (2019) was downloaded from the Open Data Commons for Spinal Cord Injury (RRID:SCR_016673).”

The full citation is included in the reference list: Ferguson, A.R., Irvine,K.-A., Gensel, J.C., Nielson, J.L., Lin, A., Ly, J., Segal, M.R., Ratan, R.R., Bresnahan, J.C., Beattie, M.S. (2019) Cervical (C5), unilateral spinal cord injury with diverse injury modalities, multiple behavioral outcomes, and histopathology. Open Data Commons for Spinal Cord Injury. ODC-SCI:26 http://doi.org/10.7295/W9T72FMZ

Data citation elements:
- Authors
- Publication year
- Title of data set
- Version
- Repository
- Identifier

##Use of identifiers for data sets
Each repository for the BICCN should provision of a globally unique and persistent identifier for a data submission by an individual investigator to adhere to the FAIR and Data Citation Principles (principle #4). 
Globally unique:  The identifier points to only one thing in the world;  accession numbers are generally not globally unique unless effort is made to make them so (see 4 below)
Persistent:  the same identifier can never be reused to identify something else
Because of the persistence requirement, URLs are generally not good PIDs
The most robust technology and the only proven technology for long term sustainability is the DOI at this point. If using accession numbers, we recommend that you make them into PIDs via the CURIE system, i.e., identify and register a unique prefix for your repository,  and register them with identifiers.org or N2T. These IDs must be immutable, that is, they cannot change once registered and may not be reassigned. 
The identifier system used by each repository should be included in their charters.  The charters should also state how they are supporting data citation, i.e., if someone uses data from their repository, how will the author of the data get credit?  How will a reference to the exact data used be created and maintained. (See the previous presentation for information on citing dynamic data sets).
The identifier should be actionable, that is, you should be able to plug it into a web based resolver (e.g. dx.doi.org, n2t.net, identifiers.org) and it should resolve to the metadata + data set.
Whether using DOIs or some other identifier, it is the responsibility of the repository to make sure that the PIDs continue to resolve by updating their links with the registration authority any time the links change.  PIDs are a social contract between the requester and the issuer.

##Landing pages:
We recommend that a landing page be created for each data set that provides descriptive metadata, including information on how to cite the data. Identifiers should resolve to a landing page that provides descriptive metadata and additional context for the data rather than directly to the data set.  Such pages can support content negotiation so the data can be accessed directly if desired.  
The landing page should contain a standard set of metadata, where applicable, e.g., [the dkNET rich metadata schema](https://docs.google.com/document/d/1E1fA2AJDvvmxlS8g8yvpnt6BIayvZVOR7dMYe-hWIiU/edit#heading=h.z356s1so2kcy).  Note that the majority of these fields are present in the major cataloguing schemas:  Dublin Core, Data Cite, Schema.org, Bioschema.org.  We have extended these basic elements with more biospecific features + data citations.
As part of the above metadata, the repositories should tag the collection belonging to the BICCN by allowing data sets to be tagged or through a metadata field that specifies a collection. The recommendation is to create a metadata field for “Consortium” and also to include the RRID for the consortium.
The repository should provide a full citation so that the data set can be properly acknowledged:
e.g.,:  Ferguson, A.R., Irvine,K.-A., Gensel, J.C., Nielson, J.L., Lin, A., Ly, J., Segal, M.R., Ratan, R.R., Bresnahan, J.C., Beattie, M.S. (2018) Cervical (C5), unilateral spinal cord injury with diverse injury modalities, multiple behavioral outcomes, and histopathology. Open Data Commons for Spinal Cord Injury. ODC-SCI:26 http://doi.org/10.7295/W9T72FMZ
Some repositories provide data citation export in major formats supported by reference managers, e.g., Signalling Pathway Project
If repositories do not have landing pages, then the BCDC should maintain a landing page and assign the PID + metadata.
DOIs can be assigned by the BCDC if they are a member of Data Cite
DOIs can be assigned by other entities by registering the data set with Zenodo or  Open Science Framework and others
Advantage:  Free and mature user interface
Disadvantage:  “zenodo” will appear in the DOI;  you have to upload at least one file to receive a DOI so it is somewhat fraudulent to use this route.
DOIs can be assigned by the Neuroscience Information Framework at UCSD for the BCDC through its relationship with the California Digital Library.
DOIs or other PIDs should be assigned at the level of granularity required by data citation.  Each version of the data set should have its own DOI.  The landing pages for the different versions should point to each other so that users are aware there are different versions of the same data set.  
A data set may be comprised of multiple parts each of which may have its own PID.  The landing page should specify how each part relates to the whole data set and how the whole data set relates to its parts, i.e., relationships should be bidirectional. The Data Cite schema has relationships for relating parts of data.  Here is an example of how Rebuilding the Kidney handles the citation of collections.
A data set may be a slice of a larger data set;  the relationship to the parent data set should be specified.  
Data Cite uses isPartOf and hasPart (pg 51 of Metadata schema)
If these parts reside in different repositories, the BCDC will maintain a landing page for the complete data set and assign the PID. The landing page will describe the overall data set and its parts.  
If data sets are removed for some reason, the repository will maintain its landing page + metadata (known as a tombstone page - https://support.datacite.org/docs/tombstone-pages) and provide on that landing page the disposition of that data, i.e., why was it removed;  are there copies elsewhere.
Each release of the BICCN data should have its own descriptive landing page that describes the contents of the release.  Ideally, each release would have its own DOI and would point to the set of DOIs for individual data sets comprising that release, so that someone analyzing it in aggregate could cite it and others would be able to retrieve that data set for the purposes of reproducibility.  We understand, however, that as the BCDC grows, maintaining such documents may become unwieldy.  However, at minimum, the BICCN could assign a DOI to a manifest that describes each release so that it become referenceable.

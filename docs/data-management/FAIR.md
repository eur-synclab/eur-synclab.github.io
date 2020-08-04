# The FAIR principles

In the data management world, making data "FAIR" is the ideal situation. Making your data FAIR facilitates knowledge discovery by assisting humans and machines in their discovery of and access to the data. See also [this video](https://vimeo.com/162062013).

FAIR stands for: Findable, Accessible, Interoperable and Reusable.

:tada: The below information is a summary of the principles on the [GO FAIR website](https://www.go-fair.org/fair-principles/).

### Findable by both humans and machines
Include metadata that allow the discovery of interesting datasets: the dataset should be findable with a google datasets search
1. (Meta)data have a globally unique and persistent identifier. Most repositories do this automatically through a handle or DOI
2. Data are described with rich metadata, including descriptive information about the context, quality and condition, or characteristics of the data
3. Metadata include the identifier of the data they describe: metadata and dataset should link to each other
4. (Meta)data are registered or indexed in a searchable resource (e.g., a repository)

To do:
- select a data repository early on and check its data format and metadata requirements
- make sure the (meta)data can get a persistent identifier so that it can be cited
- maybe select a catalogue to make your data more findable, especially if the repository is more generic in nature

### Accessible: stored for the long term with well-definede access conditions
Think about the security, legal conditions, sustainability and access conditions of the data
1. (Meta)data are retrievable by their identifier using a standardized communication procotol, e.g., http or ftp, without specialised tools or communication methods. So, clearly define who can access the actual data, and specify how  
 a. The protocol is open, free, and universally implementable to facilitate data retrieval. Anyone with a computer and an internet connection can access at least the metadata.      
 b. The protocol allows for an authentication and authorization where necessary: specify the conditions under which the data are accessible
2. Metadata are accessible even when the data is no longer available


To do:  
- guarantee longevity of the data, e.g., by submitting it to a repository that has a certification like the Data Seal of Approval or an ISO certification
- check and describe the legal conditions under which the data can be made available
- establish an embargo period if necessary
- make sure your ICT infrastructure will keep the data available even in case of equipment failure or human error


### Interoperable: ready to be combined with other datasets
Think about the software, documentation standards (e.g., the same labels for the same variables) and formats. This differs for different disciplines.
1. (Meta)data use a formal, accessible, shared and broadly applicable language for knowledge representation:  the metadata should be readable for machines without the need for specialized or ad hoc algorithms, translators, or mappings
2. (Meta)data use vocabularies that follow the FAIR principles
3. (Meta)data include qualified references to other (meta)data: meaningful links between (meta)data, e.g. X regulates Y instead of X associated with Y

To do:
- select commonly used data formats
- select commonly used vocabularies for data items

### Reusable
Think about the licensing and provenance (can you trust this data?) of the data
1. (Meta)data are richly described with a plurality of accurate and relevant attributes, i.e., the context under which the data was generated, e.g.,: scope/purpose of the data, particularities/limitations, date of generation/collection, lab conditions, who prepared the data, parameter settings, name and version of the software used, raw or processed data, explain non-self-explanatory variable names, version  
a. (Meta)data are released with a clear and accessible data usage license  
b. (Meta)data are associated with detailed provenance: where did it come from? Who generated or collected it? How has it been processed? Has it been published before? Does it contain data from someone else that you may have transformed or completed?  
c. (Meta)data meet domain-relevant community standards: use a common template and common vocabulary 

To do:
- make sure you keep proper provenance information: details about how and where the data was generated, including machine settings, and details about all processing steps, such as the software tools with their versions and parameters
- select the right minimal metadata standard and collect the necessary metadata, see [link](https://fairsharing.org/)
- select a license for the data (preferably an open license) and the associated software tools
- make sure the important conclusions of your study will not only be available in a paper in narrated form, but also in a digital file (e.g., a nanopublication)

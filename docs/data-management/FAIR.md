# The FAIR principles

In the data management world, making data "FAIR" is the ideal situation. Making your data FAIR facilitates knowledge discovery by assisting humans and machines in their discovery of and access to the data.

<iframe width="560" height="315" src="https://www.youtube.com/embed/2uZxFu9SFi8?start=5" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 

The below information is a summary of the principles on the [GO FAIR website](https://www.go-fair.org/fair-principles/). See also this [FAIR data checklist](https://www.lcrdm.nl/files/lcrdm/2019-07/HOW FAIR IS YOUR DATA_flyer_2.pdf).

### Findable by both humans and machines
Include metadata that allow the discovery of interesting datasets: the dataset should be findable with a google datasets search.

<ol>
    <li>(Meta)data have a <a href=https://www.youtube.com/watch?v=PgqtiY7oZ6k&feature=emb_title>persistent identifier</a>. Most repositories do this automatically through a handle or DOI.</li>
    <li>Data are described with rich metadata, including descriptive information about the context, quality and condition, or characteristics of the data</li>
    <li>Metadata include the identifier of the data they describe: metadata and dataset should link to each other</li>
    <li>(Meta)data are registered or indexed in a searchable resource (e.g., a repository)</li>
</ol>




To do:

- select a data repository early on and check its data format and metadata requirements
- make sure the (meta)data can get a persistent identifier so that it can be cited
- maybe select a catalogue to make your data more findable, especially if the repository is more generic in nature



### Accessible: stored for the long term with well-defined access conditions
Think about the security, legal conditions, sustainability and access conditions of the data.

<ol>
    <li>(Meta)data are retrievable by their identifier using a standardized communication procotol, e.g., http or ftp, without specialised tools or communication methods.</li>
    <ol type="a">
        <li>The protocol is open, free, and universally implementable to facilitate data retrieval. Anyone with a computer and an internet connection can access at least the metadata.  </li>
    <li> The protocol allows for an authentication and authorization: specify the conditions under which the data are accessible</li></ol>
    <li>Metadata are accessible even when the data is no longer available</li>
</ol>




To do:  

- guarantee longevity of the data, e.g., by submitting it to a repository that has a certification like the Data Seal of Approval or an ISO certification
- check and describe the legal conditions under which the data can be made available
- establish an embargo period if necessary
- make sure your ICT infrastructure will keep the data available even in case of equipment failure or human error


### Interoperable: ready to be combined with other datasets
Think about the software, documentation standards (e.g., the same labels for the same variables) and formats. This differs for different disciplines.

<ol>
<li>(Meta)data use a formal, accessible, shared and broadly applicable language for knowledge representation:  the metadata should be readable for machines without the need for specialized or ad hoc algorithms, translators, or mappings</li>
    <li>(Meta)data use vocabularies that follow the FAIR principles</li>
    <li>(Meta)data include qualified references to other (meta)data: meaningful links between (meta)data, e.g. X regulates Y instead of X associated with Y</li>
</ol>
</ol>

To do:



- select commonly used data formats
- select commonly used vocabularies for data items

### Reusable
Think about the licensing and provenance (can you trust this data?) of the data.
<ol>
<li>(Meta)data are richly described, e.g.: scope/purpose of the data, particularities/limitations, date of generation/collection, lab conditions, who prepared the data, parameter settings, name and version of the software used, raw or processed data, explain non-self-explanatory variable names, version</li>
    <ol type=a><li>There is a a clear and accessible data usage license</li>
    <li>(Meta)data are associated with detailed provenance: where did it come from? Who generated or collected it? How has it been processed? Has it been published before? Does it contain data from someone else that you may have transformed or completed?</li>
    <li>(Meta)data meet domain-relevant community standards: use a common template and common vocabulary</li></ol>
</ol>


</ol>



To do:



- make sure you keep proper provenance information: details about how and where the data was generated, including machine settings, and details about all processing steps, such as the software tools with their versions and parameters
- select the right minimal metadata standard and collect the necessary metadata, see [link](https://fairsharing.org/)
- select a license for the data (preferably an open license) and the associated software tools
- make sure the important conclusions of your study will not only be available in a paper in narrated form, but also in a digital file (e.g., a nanopublication)

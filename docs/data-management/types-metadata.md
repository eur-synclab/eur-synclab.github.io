# Metadata

Metadata is *data about data*: in a broad sense, metadata is all the information that you provide about your project, dataset, variables, code, etc. Read some nice examples [here](https://dataedo.com/kb/data-glossary/what-is-metadata). Providing metadata is incredibly important, since metadata makes data:

- Findable
- Readable
- Interpretable
- Manageable

Without metadata, a lot of data are just numbers that cannot be interpreted.

<p style="text-align:center"><img src="../img/metadatacat.png" style="zoom:50%;"  alt="Source: https://dataedo.com/kb/data-glossary/what-is-metadata"/></p>

## Example research metadata

<ol>
    <li>A project readme containing the information below. Often in a <code>readme.txt</code>. Find an example <a href=https://cornell.app.box.com/v/ReadmeTemplate>template here</a> or use the information below:</li>
    <ol>
        <li><b>Creator</b> (PI): name and affiliation of PI</li>
        <li><b>Title</b>: project title</li>
        <li><b>Funding sources</b>: names of funders, incl. grant numbers and related acknowledgements</li>
        <li><b>Data collector/producer</b>: who is responsible for data collection + date and location of data production</li>
        <li><b>Description</b>: project description, incl. relevant publications</li>
        <li><b>Sample and sampling procedures</b>: target population and methods to sample it (or link to document describing this), retention rates for longitudinal studies</li>
        <li><b>Coverage</b>: topics, time period and location covered</li>
        <li><b>Source</b>: if relevant, citations to original source from which data were obtained</li>
    </ol>
    <li>Metadata for a specific data file, containing, for example, file description, data format, relationship with other files, date of creation and versioning information, etc. This can be a <code>readme.txt</code> or other filetypes, such as <code>nameofdatafile.json</code> or <code>nameofdatafile.xml</code></li>
    <li>A codebook (data dictionary), which specifies what all variables in your dataset mean. See the <a href=codebooks.md>codebook chapter</a> for more information.</li>
    <ol type="a"><li><b>Question wording</b> or <b>meaning</b></li>
        <li><b>Variable text</b>: question text or item number</li>
        <li><b>Respondent</b>: who was asked the question? </li>
        <li><b>Meaning of codes</b>: interpretation of the codes assigned to each variable</li>
        <li><b>Missing data codes</b>, e.g., <code>999</code></li>
        <li><b>Summary statistics</b> for both valid and missing cases</li>
        <li><b>Imputation and editing</b>: identify data that have been estimated or extensively edited</li>
        <li><b>Constructed and weight variables</b>: how were they constructed</li>
        <li><b>Location in the data file</b>: field or column location, if relevant</li>
        <li><b>Variable groupings</b>: if you categorize variables into conceptual groupings</li>
    </ol>
    <li>Metadata in systems, such as a data repository. This type of metadata is often enforced and interoperable so that you don't have to manually create this type of metadata.</li></ol>



## Interoperable metadata

### Metadata standards

Metadata standards are frameworks for metadata fields. They describe how metadata fields should be formatted, so that they will become machine-readable and therefore interoperable. An enormous amount of metadata standards is available which all [differ per discipline](https://www.dcc.ac.uk/guidance/standards/metadata), but the best known metadata standards for the social sciences are:

- Dublin Core: this is a set of [basic elements](https://www.dublincore.org/specifications/dublin-core/usageguide/elements/) to describe a wide range of networked resources, among which Title, Creator, Subject, Description, Publisher, Contributor, Date, Type, Format, Identifier, etc. (see readme information above). Note this Dublin Core [metadata file generator](https://nsteffel.github.io/dublin_core_generator/generator_nq.html) to see the elements.
- [Data Documentation Initiative](https://ddialliance.org/) (DDI) is a standard often used in the social, behavioral, economic, and health sciences. It knows several sub-profiles that are based on DDI, but may be more extensive. One of those is [CESSDA](https://www.cessda.eu/) (Consortium of European Social Science Data Archives). CESSDA's metadata model can be found [here](https://zenodo.org/record/3543756#.X7aNSmhKi71)

As an individual researcher, you are often not directly confronted with these standards. It is just good to know that different repositories can use different standards. See more standards [here](https://fairsharing.org/standards/).



### Controlled vocabularies

Where metadata standards tell us what to call the metadata fields, controlled vocabularies come in handy when we have to **fill in** those fields. Using controlled vocabularies enables machines to identify identical values, instead of everyone using a different term for the same thing. 

Whereas some fields have very extensive controlled vocabularies, psychology does not have many. A few links:

- Controlled vocabularies from the [DDI](https://ddialliance.org/controlled-vocabularies)
- [CESSDA vocabularies](https://vocabularies.cessda.eu/) (large overlap with DDI)
- [ELSST](https://elsst.cessda.eu/) – European Language Social Science Thesaurus
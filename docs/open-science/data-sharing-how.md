# Sharing research data: how?

Sharing data is becoming the golden standard in science. It enables others to reproduce your results and prevent fraud and honest mistakes in data analysis. Moreover, it enables reuse of your data in new analyses, increasing the impact of your work.

## Short guide: When to share what data?
<ol>
    <li>If data are completely <b>anonymous</b>, you can share them publicly in a dedicated repository, see <a href=#repository>step 1</a> or <a href=#datapaper>2</a></li>
    <li>If data cannot be completely anonymized, they are personal. You need a <b>legal basis</b> to share these data:
        <ol>
            <li><b>Informed consent</b>: what you can do with the data depends on the contents of the consent form. 
                <ul>
                    <li>If participants consented to public data sharing and their data are not very sensitive (e.g., not from children or clinical groups), publish them in a <a href=#repository>repository</a> or <a href=#datapaper>datapaper</a>.</li>
                    <li>If participants consented to sharing with restrictions, use a <a href=#repository>repository</a> that allows access restrictions or use a <a href=#casebycase>data use agreement</a> to share data case by case.</li>
                    <li>If participants did not consent to any personal data sharing, share <a href=#characteristics>characteristics or aggregated data</a>.</li>
                </ul></li>
            <li><b>Public interest</b>: In theory, most research is publicly funded, and therefore we should be able to use this as legal basis for data sharing. However, it is still unclear when we are allowed to use it. The minimal prerequities are:
                <ul>
                    <li>the personal data sharing should rely on the principles of lawfulness, fairness and transparency</li>
                    <li>informed consent was impossible to obtain, e.g., because the study took place a long time ago and consent cannot be obtained retroactively. Participants not consenting to data sharing is not a valid reason!</li>
                </ul>
            When sharing personal data using the Public interest basis, you are encouraged to share data with access restrictions, especially if your data are sensitive or highly identifiable (e.g., data from minors or clinical groups, special categories of sensitive data, etc.)</li>
            <li>If you share data with a <b>similar purpose</b> as the original research project (such as for collaborating with other researchers on a related topic), a <a href=#casebycase>data use agreement</a> suffices (not strictly necessary for EUR collaborators as they are from the same institution). Such agreement should lay out the conditions of storing, sharing and publishing the data. This falls under the scope of processing that is "compatible with the original purpose", which does not require a new/separate legal basis (GDPR Articles <a href="https://gdpr.eu/article-5-how-to-process-personal-data/" target="_blank">5(1)(b)</a>, <a href="https://gdpr.eu/article-6-how-to-process-personal-data-legally/" target="_blank">6(4)</a> and <a href="https://gdpr.eu/article-89-processing-for-archiving-purposes-scientific-or-historical-research-purposes-or-statistical-purposes/" target="_blank">89(1)</a>).</li>
        </ol>
    </li>
</ol>

----
## Ways of sharing data
Publishing data can go roughly in the following ways:

<h3 id="repository"> 1. Publish in a data repository</h3>

For example (or find one [here](https://www.re3data.org/)):

<ul>
    <li>The <a href="https://datarepository.eur.nl/" target="_blank">EUR Data Repository</a>: for publication packages at the EUR</li>
    <ul>
        <li>All data and materials accompanying a publication</li>
        <li>Only suitable for anonymous data</li>
        <li>See the <a href="pub-packages.html" target="_blank">publication packages page</a> for more information.</li>
    </ul>
<li><a href="https://dataverse.nl" target="_blank">DANS DataverseNL</a>: for publication packages at Leiden University (<a href="https://www.organisatiegids.universiteitleiden.nl/binaries/content/assets/sociale-wetenschappen/psychologie/organisatiegids/instruction-for-archiving-publication-packages.pdf" target="_blank">instructions</a>)</li>
<ul>
    <li>All data and materials accompanying a publication</li>
    <li>Not suitable for large or publication-independent datasets (max zip file size 10GB) or non-anonymous data</li>
    <li>Only accessibly via institutes that use DataverseNL</li>
</ul>
<li><a href="https://easy.dans.knaw.nl/ui/home" target="_blank">DANS EASY</a> (Dutch)</li>
<ul>
    <li>For data and materials, not necessarily accompanying a publication</li>
    <li>Has deals with the university but still some limitations to the size of the data (max. 100 GB)</li>
    <li>Is aimed more at archiving than sharing data</li>
    <li>Also has a dark archive for non-anonymous data</li>
</ul>
<li><a href="https://data.4tu.nl/portal" target="_blank">4TU Research data</a></li>
<ul>
    <li>International data repository for science, engineering and design</li>
    <li>Enables open or restricted access, private links, embargoes or even metadata-only records</li>
    <li>Up to 1 TB of storage for affiliated researchers, 10 GB for non-affiliated researchers</li>
</ul>
<li><a href="https://osf.io/" target="_blank">Open Science Framework</a></li>
<ul>
    <li>max 5 GB for private, 50 GB for public projects</li>
    <li>Choose storage location in EU: Germany</li>
    <li>Keep your data close to all other relevant files in your OSF project</li>
    <li>OSF is more aimed at project management than dissemination</li>
</ul>
<li>Other general-purpose repositories, such as:
    <ul>
        <li><a href="https://zenodo.org/" target="_blank">Zenodo</a> (free up to 50GB)</li>
        <li><a href="https://datadryad.org/" target="_blank">Dryad</a> (not free)</li>
        <li><a href="https://figshare.com/" target="_blank">Non-EUR Figshare</a> (free, max 20GB private space and 5GB per file)</li>
    </ul></li>
</ul>

In all cases, make your data [FAIR](../data-management/FAIR.md) and take [privacy considerations](gdpr.md) into account.


<h3 id="datapaper"> 2. Publish a datapaper</h3>

In a datapaper, you describe the data and the methods of collecting them, without the need to analyze them. This will get you a publication out of your data, irrespective of whether or not you publish results. This often requires that you make all described data public, because the aim of such publications is to provide access to high quality datasets and to facilitate reuse. Also, most journals have some policy in which repository you should deposit the data accompanying the datapaper. Note that a datapaper will be peer-reviewed just as well as a regular article. See <a href="https://pitt.libguides.com/findingdata/datajournals" target="_blank">this link</a> for a list of data journals.


<h3 id="casebycase">3. Share case-by-case</h3>

For data that cannot be shared publicly, you can sometimes still share the data case-by-case. This can be the case:

- For MRI-data for which you have a legal basis to share them, but you may not want to publish publicly because of the sensitivity. For this type of data, you may want to consider using a [data use agreement](dsa-template.md) as well
- For data that has not been published about
- For data that does not belong to a publication, data that is too large to share in another way or some other reason

Please note that this is only a FAIR solution if your metadata and access options are publicly findable and available (e.g., consider creating a metadata-only record in a repository).

<h3 id="characteristics"> 4. Share only characteristics of the data</h3>

If you do not want to or you can't share any real data, you can still make your data valuable:

<h4>Aggregated data</h4>
If your data are privacy-sensitive and you cannot share them, you can still share aggregated data, for example:
<ul>
    <li id="neurovault">Share first- and second level MRI data in <a href="https://neurovault.org/" target="_blank">NeuroVault</a>. You can also link this to your manuscript (and the other way around). NeuroVault allowes meta-analyses of fMRI studies, making it worthwhile to share your group MRI data there. See the <a href="https://eur-synclab.github.io/open-science/neurovault.html" target="_blank">NeuroVault page</a> for more information</li>
    <li>Share summary details of your data, such as averages and variation measures. Or make a <a href="https://shiny.rstudio.com/" target="_blank">shinyapp</a> that allows exploring the data without accessing it!
</ul>

<h4>Synthetic data</h4>

Creating a **synthetic dataset** can be useful to capture the statistical idiosyncrasies of your real dataset. This synthetic dataset can be used to reproduce the results of your analysis, without violating any privacy or intellectual property regulations. Read more:

- [Review of synthetic generation methods](https://www.ijstr.org/final-print/mar2017/A-Review-Of-Synthetic-Data-Generation-Methods-For-Privacy-Preserving-Data-Publishing.pdf)
- `synthpop`: an R package for creating synthetic data ([paper](http://dx.doi.org/10.18637/jss.v074.i11), [blog how to](https://www.dsquintana.blog/creating-and-synthetic-version-of-a-real-dataset/))
- For MRI-data, see [brainpower](https://brainpower.readthedocs.io/en/latest/simulations.html).

<h4>Federated learning</h4>

<p style="text-align:center;"><img src="../img/Sheller_etal_2020_federatedlearning.JPG" alt="Federated learning explained. Source: Sheller et al., 2020" style="zoom: 60%"></p>

Federated learning arises from the field of Artificial Intelligence and relies “on the principle of remote execution—that is, distributing copies of a machine learning algorithm to the sites or devices where the data is kept (nodes), performing training iterations locally, and returning the results of the computation (for example, updated neural network weights) to a central repository to update the main algorithm.” ([Kaissis](https://doi.org/10.1038/s42256-020-0186-1) et al., 2020). This means that you do not move your data, while still providing valuable information about it. 

Some federated learning tools and projects:

- [COINSTAC](https://github.com/trendscenter/coinstac)
- [PySyft](https://github.com/OpenMined/PySyft)
- [ENIGMA](http://enigma.ini.usc.edu/) consortium: Consortium with several working groups. Share pre- and post-processing analysis scripts, the leading site will conduct meta-analysis
- [OHDSI](https://ohdsi.org/) (Observational Health Data Sciences and Informatics): collaborative to bring out the value of health data through large-scale analytics
- [Personal Health Train](https://www.dtls.nl/fair-data/personal-health-train/), part of Health-RI (official website [here](https://pht.health-ri.nl/))

## Licensing data

With **licenses**, you specify what others are permitted to do with your product. You can see it as some kind of agreement: if someone violates the license, you have the right to sue them, just like a regular lawful agreement. For anonymous data, it is recommended to choose a **CC0** (public domain) or **CC-BY 4.0** license. These open licenses both allow others to use the data without restrictions. For non-anonymous data, use a more restrictive license (but please **don't use non-derivate (ND) or non-commercial (NC)** licenses, read why [here](https://www.openaire.eu/how-do-i-license-my-research-data-how-to-apply)) or formulate your own terms of use, for example in a [data use agreement](dsa-template.md). 

Don't know which license to choose? Use a [license selector](https://ufal.github.io/public-license-selector/)!


## Resources

- [Data management and sharing tools](https://digitalscholarship.nl/rds/faculty/faculty-of-social-and-behavioural-sciences/) (list compiled by the Leiden University Library)
- [The Turing Way - open data](https://the-turing-way.netlify.com/open_research/01/opendata.html)
- [Utrecht University information about data sharing](https://www.uu.nl/en/research/research-data-management/guides/publishing-and-sharing-data)
- [FAQ about data sharing (Donders Institute)](https://data.donders.ru.nl/doc/help/faq/publish-data.html?0#faq-dsc-prepare)
- [Decision aid choosing a repository (not exhaustive)](https://www.uu.nl/en/research/research-data-management/tools-services/tools-for-storing-and-managing-data/decision-aid-data-repositories)

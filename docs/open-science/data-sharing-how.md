# Sharing research data: how?

Sharing data is becoming the golden standard in science. It enables others to reproduce your results and prevent fraud and honest mistakes in data analysis. Moreover, it enables reuse of your data in new analyses, increasing the impact of your work.

Publishing data can go roughly in the following ways:

## 1. Publish in a data repository

For example:

<ul>
    <li>The <a href=https://datarepository.eur.nl/>EUR Data Repository</a>: for publication packages at the EUR</li>
    <ul>
        <li>All data and materials accompanying a publication</li>
        <li>Not suitable for large or publication-independent datasets or non-anonymous data</li>
        <li>See the <a href=pub-packages.html>publication packages page</a> for more information.</li>
    </ul>
<li><a href=https://dataverse.nl>DANS DataverseNL</a>: for publication packages at Leiden University</li>
<ul>
    <li>All data and materials accompanying a publication</li>
    <li>Not suitable for large or publication-independent datasets (max zip file size 10GB) or non-anonymous data</li>
</ul>
<li><a href=https://easy.dans.knaw.nl/ui/home>DANS EASY</a> (Dutch)</li>
<ul>
    <li>For data and materials, not necessarily accompanying a publication</li>
    <li>Has deals with the university but still some limitations to the size of the data (max. 100 GB)</li>
    <li>Is aimed more at archiving than sharing data</li>
</ul>
<li><a href=https://neurovault.org/>NeuroVault</a></li>
<ul>
    <li>For group-MRI data (such as t-maps) accompanying a publication</li>
    <li>Enables meta-analysis of fMRI-studies</li>
    <li>See the <a href=neurovault.md>NeuroVault page</a> for more information</li>
</ul>
<li><a href=https://osf.io/>Open Science Framework</a></li>
<ul>
    <li>max 5 GB for private, 50 GB for public projects</li>
    <li>Choose storage location in EU: Germany</li>
    <li>Keep your data close to all other relevant files in your OSF project</li>
    <li>OSF is more aimed at project management than dissemination, read more here <a href=osf.md>here</a></li>
</ul>
<li>Other general-purpose repositories, such as:
    <ul>
        <li><a href=https://zenodo.org/>Zenodo</a> (free up to 50GB)</li>
        <li><a href=https://datadryad.org/>Dryad</a> (not free)</li>
        <li><a href=https://figshare.com/>Non-EUR Figshare</a> (free, max 20GB private space and 5GB per file)</li>
    </ul></li>
</ul>



In all cases, make your data [FAIR](https://www.go-fair.org/fair-principles/), see the [data management page](../data-management/FAIR.md) and take [privacy considerations](gdpr.md) into account.


## 2. Publish a datapaper

You can also publish a dataset in a data journal without the need to add it to a publication. In a datapaper, you describe the data and the methods of collecting them, without the need to analyze them. This will get you a publication out of your data irrespective of whether or not you publish results. This however often (but not always) requires that you make all described data public, because the aim of such publications is to provide access to high quality datasets and to facilitate reuse. Also, most journals have some policy in which repository you should deposit the data accompanying the datapaper. Note that a datapaper will be peer-reviewed just as well as a regular article. See [this link](https://pitt.libguides.com/findingdata/datajournals) for a list of data journals.


## 3. Via supplementary materials in a published paper

This is better than nothing, but not recommended, because this does not adhere to the [FAIR principles](https://www.go-fair.org/fair-principles/). Also, there is often a limit to the size or number of supplementary files that a journal can host, limiting the possibilities to publish data.

## 4. Share case-by-case

For data that cannot be shared publicly, you can sometimes still share the data case-by-case. This can be the case:



- For MRI-data for which you have informed consent from the participants to share. You may not want to publish this publicly because of the sensitive nature of the data, but you can still share the data because you have consent. Of course this also goes for other kinds of sensitive data for which you have consent.
- For data that does not belong to a publication, data that is too large to share in another way or some other reason



## 5. Share only characteristics of the data

If you do not want to or you can't share any real data, you can still make your data valuable:

### Synthetic data

Creating a **synthetic dataset** can be useful to capture the statistical idiosyncrasies of your real dataset. This synthetic dataset can be used to reproduce the results of your analysis, without violating any privacy or intellectual property regulations. Read more:

- [Review of synthetic generation methods](https://www.ijstr.org/final-print/mar2017/A-Review-Of-Synthetic-Data-Generation-Methods-For-Privacy-Preserving-Data-Publishing.pdf)
- `synthpop`: an R package for creating synthetic data ([paper](http://dx.doi.org/10.18637/jss.v074.i11), [blog how to](https://www.dsquintana.blog/creating-and-synthetic-version-of-a-real-dataset/))
- For MRI-data: [brainpower](https://brainpower.readthedocs.io/en/latest/simulations.html).

### Federated learning

<p style="text-align:center;"><img src="../img/Sheller_etal_2020_federatedlearning.JPG" alt="Federated learning explained. Source: Sheller et al., 2020" style="zoom: 60%"></p>

Federated learning arises from the field of Artificial Intelligence and relies “on the principle of remote execution—that is, distributing copies of a machine learning algorithm to the sites or devices where the data is kept (nodes), performing training iterations locally, and returning the results of the computation (for example, updated neural network weights) to a central repository to update the main algorithm.” ([Kaissis](https://doi.org/10.1038/s42256-020-0186-1) et al., 2020). This means that you do not move your data, while still providing valuable information about it. 

Some federated learning tools and projects:

- [COINSTAC](https://github.com/trendscenter/coinstac)
- [PySyft](https://github.com/OpenMined/PySyft)
- [ENIGMA](http://enigma.ini.usc.edu/) consortium: Consortium with several working groups. Share pre- and post-processing analysis scripts, the leading site will conduct meta-analysis



## Copyright & licences

**Copyright** includes the rights that you automatically get when you create something, such as an article or dataset (although there are differing opinions on whether or not data is the result of a creative endeavor). The copyright on a work will always be yours, except when you explicitly (partially) give it to someone else, such as a publisher.

With **licenses**, such as [Creative Commons licenses](https://creativecommons.org/licenses/?lang=en ), you specify what others are permitted to do with your product. You can see it as some kind of agreement: if someone violates the license, you have the right to sue them, just like a regular lawful agreement. For anonymous data, it is recommended to choose a CC0 (public domain) or CC-BY 4.0 license (requires acknowledgement). These open licenses both allow others to use the data without restrictions. For non-anonymous data, use a more restrictive license (but please **don't use non-derivate (ND) or non-commercial (NC)** licenses, read why [here](https://www.openaire.eu/how-do-i-license-my-research-data-how-to-apply)) or a [data use agreement](dsa-template.md). 

Don't know which license to choose? Use a [license selector](https://ufal.github.io/public-license-selector/)!

## Resources

- An overview of data repositories can be found [here](https://www.re3data.org/)
- Information on the EUR Data Repository can be found [here](https://www.eur.nl/en/library/research-support/research-data-management-rdm/tooling/eur-data-repository)
- [Data management and sharing tools](https://digitalscholarship.nl/rds/faculty/faculty-of-social-and-behavioural-sciences/) (list compiled by the Leiden University Library)
- [The Turing Way - open data](https://the-turing-way.netlify.com/open_research/01/opendata.html)
- [Utrecht University information about data sharing](https://www.uu.nl/en/research/research-data-management/guides/publishing-and-sharing-data)
- [FAQ about data sharing (Donders Institute)](https://data.donders.ru.nl/doc/help/faq/publish-data.html?0#faq-dsc-prepare)
- List of [certified repositories](https://www.coretrustseal.org/why-certification/certified-repositories/) / [other repositories](http://v2.sherpa.ac.uk/opendoar/)
- [Decision aid choosing a repository (not exhaustive)](https://www.uu.nl/en/research/research-data-management/tools-services/tools-for-storing-and-managing-data/decision-aid-data-repositories)
- [Instructions for DataverseNL](https://www.organisatiegids.universiteitleiden.nl/binaries/content/assets/sociale-wetenschappen/psychologie/organisatiegids/instruction-for-archiving-publication-packages.pdf)

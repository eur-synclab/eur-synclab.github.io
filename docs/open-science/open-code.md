# Sharing analysis code

*“An article about computational science in a scientific publication is **not** the scholarship itself, it is merely **advertising** of the scholarship. The actual scholarship is the complete software development environment and the complete set of instructions which generated the figures.”* - Buckheit & Donoho, 1995 (see article [here](http://statweb.stanford.edu/~wavelab/Wavelab_850/wavelab.pdf)) 

This quote nicely summarizes the importance of sharing data, methods and code so that others can evaluate the actual work that was done in a research paper. Luckily, web-based technologies make it very easy to share these materials (and even to share the complete software environment using [Docker](https://www.docker.com/) and [Singularity](https://sylabs.io/singularity/) containers). However, just releasing your code without annotation is not very informative because others (and future you!) can't make a lot of sense of it. Two helpful tools to annotate your code are RMarkdown and Jupyter notebooks.  

## RMarkdown

Especially when you do your data analysis in R / RStudio, RMarkdown is a very useful tool to put your text and analysis together in one place. It is basically R + Markdown (a markup language to format text). It can be used to write a whole paper, including code to generate figures. This code can be outputted in many formats such as html, pdf and Word. For full documentation see also https://rmarkdown.rstudio.com/index.html

<p style="text-align:center"><figure style="text-align:center"><img src="https://d33wubrfki0l68.cloudfront.net/44f781299f23419d5314e5322e7c44393f7190d3/c5915/images/markdownchunk.png" alt="RMarkdown example" width="500" /><figcaption style="text-align:center">Example of RMarkdown chunk in RStudio with associated html output (from RMarkdown docs)</figcaption></figure></p> 

### Reference lists using Zotero in RMarkdown

When writing papers, it is also very useful to connect RStudio with Zotero.  
[Zotero](https://zotero.org/) is a free and open source reference manager with a very handy [browser plugin](https://www.zotero.org/download/connectors). If you have never used a reference manager before: it is a great way to keep a library of all your literature (including pdf's) together and will help you to cite papers in the right way and produce automatic reference lists in the right format for you. This can be done in a word processor like Microsoft Word, but also in RMarkdown.  
  
#### The basic steps you need to make this work:  
1. install [Zotero](https://zotero.org/) and import references (e.g., using the browser plugin)  
2. install the [Better BibTex plugin for Zotero](https://retorque.re/zotero-better-bibtex/) by clicking **Tools > Add-ons** within Zotero and follow [these instructions](https://retorque.re/zotero-better-bibtex/installation/)  
3. install the [citr R package](https://github.com/crsh/citr)  
  
#### Now when writing text in an RMarkdown file in RStudio:
- within RStudio in the toolbar click **Addins > Insert citations**  
- here you can search through your references and select the ones you want to enter
- you should also edit the YAML header (the upper part of the Rmd file with title, author, output et cetera): here the bibtex file (eg: `bibliography: references.bib`) should be listed;  
- if you also add `# References` at the end of the main text, your bibliography will be created automatically there  
- the format of the bibliography can be defined by pointing to a csl file in the YAML header (e.g, `csl: ./apa.csl`). All csl (citation style language) files can be downloaded from the internet, see also https://citationstyles.org/


## Jupyter notebooks


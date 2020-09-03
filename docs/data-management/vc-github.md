# Version control with git(hub)

## What are git & github?

-	**Git** is a version control system: it tracks the history as you change files. More specifically, it tracks who made which changes and when. It allows reverting files to a previous state. Note that it is possible to work on git projects locally without ever using github.
-	[**Github**](https://github.com/) is a platform that you can use to collaborate on projects that use git. It additionally allows for threaded discussions (issues), pull requests (see below) and several great apps. Please note that there are also **other** platforms that work similarly, such as [GitLab](https://gitlab.com/), [BitBucket](https://bitbucket.org/product) or [SourceFourge](https://sourceforge.net/).

Git and Github are most suitable for working with **relatively small files**. While originally used for code/software, you can use it for other types of small files as well, such as documentation.

<br>

## Why should I use git(hub)?

- Git is used a lot all over the globe and is free to download and use via several interfaces
- You will always be able to revert your errors - or those of someone else
- You can report which version of the files you have used for which publication. Even better, github allows exporting a snapshot (version) of your github repository (folder with files) to Zenodo, meaning you can publish your version used and give it a citable DOI.
- Github also has several other great functions, such as making a website out of your repository (such as this lab wiki!)

<br>

## Installation

- Create a [Github account](https://github.com/join)
- Install [git locally](https://git-scm.com/download/). If you don't want to use the command line, also download a GUI such as [RStudio](http://www.geo.uzh.ch/microsite/reproducible_research/post/rr-rstudio-git/) or [GitKraken](https://www.gitkraken.com/download))

Note: if you want to work with git in the command line on Windows, I can highly recommend using the **Ubuntu app** (the Linux Subsystem for Windows, downloadable via the Windows store), which may cause fewer Windows-related errors.

<br>

## The git workflow

When working on a git project (within a folder called a **git repository**), you will always perform the following steps:

-	Make changes to some file and save them like you normally would
-	**Stage** the changes: select which files you want to make a snapshot of (this step is most explicit if you work in the command line) 
-	**Commit** the changes: make a snapshot of the changes made so far. A commit (snapshot) is always accompanied by a *commit message* explaining what changes were made

Any commit gets a specific **identifier** that can be used to reverse (undo) the commit.

<br>

##### **Some stage- and commit-related commands**

- Check which files are changed but not yet staged or committed:`git status`
- Stage a file (tip: use the tab to use autocompletion): `git add filename` 
- Stage multiple files: `git add filename1 filename2 filename3`
- Stage all unstaged files in the workspace: `git add -A .` 
- Commit the change(s) you staged: `git commit -m "Change x and y to z"`
- Commit all (staged and unstaged) change(s) made in the workspace: `git commit -a -m "Change x and y and z"`

<br>

## Branches

A git repository can exist in multiple “versions” which are called **branches**. There is always a “master” branch, which you should consider the <u>clean</u> branch. Besides that, you can create other branches that are meant to make your own changes, or try something different without dirtying the clean (master) version. After you have made changes in your own branch and you think they should be incorporated in the master branch, you can then **merge** your branch with the master branch. 

<br>

##### **Some branch-related commands**

- Check which branch you are working on now (and list which branches there are): `git branch -v`
- Change branches: `git checkout branchname`
- Create a new branch: `git checkout -b newbranchname`

<br>

## Workflow on github

On Github, the workflow is a bit more extensive, because often you are **collaborating** and do not want others to just start editing the master branch right away. There are multiple methods to collaborate on a project, but we recommend the following, assuming that there is already a repository for the project and you want to contribute:

<ol>
    <li>On the repository page on Github, <b>fork</b> the repository: this creates a copy of the repository on your own Github account that you have full access to.<br>
<img src="../img/fork.png" style="zoom:75%;" align="center" /></li>
    <li>In your forked (copied) Github repository, create a <b>new branch</b> for the changes you are about to make with a short but comprehensible name, e.g. “dorienchanges”. <br> <img src="../img/githubbranch.JPG" style="zoom:75%;" align="center" /></li>
    <li>If you want to edit files locally, <b>clone</b> your repository to your local PC, creating a folder in your file explorer (the contents of which can change according to which branch you are on!). </li>
    <ul>
        <li>Via the command line: <code>git clone https://github.com/UserName/RepositoryName.git</code></li>
        <li>Via Rstudio, see <a href=https://happygitwithr.com/new-github-first.html#new-rstudio-project-via-git-clone>this link</a></li>
    </ul>
    <li><b>Edit</b> the files you want to edit and <b>commit the changes</b> (making a snapshot; include a comprehensible commit message!)</li>
    <li>You have now committed changes locally, but they are not yet visible in your <b>remote</b> repository, i.e., the online github repository on your account. In order to get the commits you made locally to be visible online, you need to <b>push</b> them to your remote repository on Github.</li>
    <ul>
        <li>Via the command line, note that the repository on your account is usually called "origin": <code>git push origin branchnameonwhichyouworked</code></li>
        <li>Via Rstudio, see <a href=https://happygitwithr.com/new-github-first.html#push-your-local-changes-to-github>this link</a></li>
    </ul>
    <li>Now the changes are visible in your own account, but not in the main repository. In order to get your changes into the main repository, you need to do a <b>pull request</b> on Github. This is a request to the owners of the original repository to <b>merge your branch with (one of) theirs</b>. Once merged by the owners, you are often prompted to remove your own branch (which is not necessary if you are planning to make more changes later). <br> <img src="../img/pullrequest.png" style="zoom:75%;" align="center"/></li>
</ol>

<br>



#### Keeping your local copy (clone) up to date

If you are working on a project with many collaborators making changes, the odds are that your own fork (online copy) and/or clone (local copy) are becoming out-of-date quite fast. Therefore, it is recommended to **update those copies** each time **before** you start making changes yourself, so you are working on the most recent versions of the files.

<ul>
    <li>In your clone (offline), you can set up the owner’s repository as the <b>"upstream"</b> repository and then <b>pull</b> all commits from the upstream repository to your local PC</li>
    <ul>
        <li>Setting up the original repository as the upstream: <code>git remote add upstream https://github.com/ownername/repositoryname.git</code></li>
        <li>Pulling changes from the upstream repository: <code>git pull upstream branchname</code></li>
        <li>See <a href=https://happygitwithr.com/upstream-changes.html>this page</a> when you use RStudio</li>
    </ul>
<li>To update your online version of the repository, simply push the changes (e.g., <code>push origin master</code> <i>after</i> pulling from the upstream</li>
</ul>

<br>

## Resources

For every piece of software, remember that **google is your best friend**. Or use one of the following other resources:

- Also a very comprehensive git guide by [The Turing Way](https://the-turing-way.netlify.app/reproducible-research/vcs/vcs-git.html)
- More info on the [Git workflow](https://githowto.com/) (especially useful if you are going to use git via the command line)
- Github guide: [git handbook](https://guides.github.com/introduction/git-handbook/) 
-  (duration ca. 1 hour)
- Using Git(hub) with Rstudio: [https://happygitwithr.com/](https://happygitwithr.com/)
- Introduction on Github by [Ana Martinovici](https://github.com/eur-synclab/githubfun) 
- Git terminology: [https://git-scm.com/docs/gitglossary](https://git-scm.com/docs/gitglossary)
- More terminology: [https://the-turing-way.netlify.app/reproducible-research/vcs/vcs-resources.html#definitions-glossary](https://the-turing-way.netlify.app/reproducible-research/vcs/vcs-resources.html#definitions-glossary)
- If you want to use Gitlab instead, here are the [materials of a comprehensive course](https://github.com/NETWAYS/gitlab-training) (ironically, on GitHub)
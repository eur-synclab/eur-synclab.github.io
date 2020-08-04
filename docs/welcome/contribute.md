# How to contribute

## Introduction to git(hub) and Markdown
### What are git & github?
-	**Git** is a version control system: it tracks the history as you change files. More specifically, it tracks who made which changes and when. It allows reverting files to a previous state. Note that it is possible to work on git projects locally without ever using github.
-	**Github** is a git hosting platform that you can use to collaborate on projects that use git. It additionally allows for threaded discussions (issues), pull requests and several github apps. 

### The git workflow
When working on a git project (within a folder called a **git repository**), you will always perform the following steps:

-	Make changes to some file
-	**Commit** the changes: make a snapshot of the changes made so far. A commit (snapshot) is always accompanied by a *commit message* explaining what changes were made

### Branches
A git repository can exist in multiple “versions” which are called **branches**. There is always a “master” branch, which you should consider the clean branch. Besides that, you can create other branches that are meant to make your own changes. After you have made changes in your own branch and you think they should be incorporated in the master branch, you can then **merge** your branch with the master branch. 

### Workflow on github
On Github, the workflow is a bit more extensive, because often you are collaborating and do not want others to just start editing the master branch right away. There are multiple methods to collaborate on a project, but we recommend the following, assuming that there is already a repository for the project and you want to contribute:

1. On the repository page on Github, **fork** the repository: this creates a copy of the repository on your own Github account that you have full access to
2. In your repository, create a new branch for the changes you are about to make with a short but comprehensible name, e.g. “dorienwritecontent”
3. You can now start editing in this branch, either on your local PC or online (in Github)
4. *Skip this step if you are editing online*: If you want to edit files locally, **clone** your repository to your local PC, creating a folder in your file explorer (the contents of which can change according to which branch you are on!). You can use the command line or a tool such as Rstudio or GitKraken to do this.
5. Edit the files you want to edit and commit the changes (making a snapshot; include a commit message!) 
6. *Skip this step if you are editing online*: You have now committed changes locally, but they are not yet visible in your “remote” repository, i.e., the online github repository on your account. In order to get the commits to be visible online, you need to **push** them to your remote.
7. Now the changes are visible in your own account, but not in the main repository. In order to get your changes into the main repository, you need to do a **pull request**. This is a request to the owners of the original repository to merge your branch with theirs. Once merged by the owners, you are often prompted to remove your own branch (which is not necessary if you are planning to make more changes later). 

#### Keeping your local copy (clone) up to date
If you are working on a project with many collaborators making changes, the odds are that your own fork (online copy) and/or clone (local copy) are becoming out-of-date quite fast. Therefore, it is recommended to update those copies each time before you start making changes yourself, so you are certain that you are working on the most recent versions of the files.

- Online (in your fork), you can do this by doing a reverse pull request: a request to yourself to merge the owner’s master branch (“upstream master”) into your own branch that you will be working in
- In your clone (offline), you can set up the owner’s master branch (“upstream master”) as the upstream master and **pull** changes from the upstream master (see [this page]( https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/merging-an-upstream-repository-into-your-fork) for command-line instructions and [this page](https://happygitwithr.com/upstream-changes.html) when you use RStudio). You are simply pulling all changes made to your local PC this way. Note that your online copy is not automatically updated!

### Further reading on git(hub)
- More info on the [Git workflow](https://githowto.com/) (especially useful if you are going to use git via the command line)
- Github guide: [git handbook](https://guides.github.com/introduction/git-handbook/)
- [Free github introduction course](https://lab.github.com/githubtraining/introduction-to-github) (duration ca. 1 hour)
- Using Git(hub) with Rstudio: https://happygitwithr.com/

### Markdown
Markdown is a markup language that you can use to add formatting elements to plaintext text documents. When you create a Markdown-formatted file, you add Markdown syntax to the text to indicate which words and phrases should look different. Every .md (Markdown) file in this repository in fact uses Markdown for formatting!

For example, to indicate a second-level header, you type:
`## Title of header`

Advantages of Markdown:

- It can be used for a lot of things, e.g., for creating html pages
- It is platform- and operating system independent
- You can type markdown in any text editor and open .md files with many programs, such as [Atom](https://atom.io/), [Zettlr](https://www.zettlr.com/), [Rstudio](https://rstudio.com/), or even online, such as in [Dillinger](https://dillinger.io/) (in contrast to, for example, Microsoft Word), see [this page]( https://www.markdownguide.org/tools/) for more tools that support Markdown.

**Markdown resources**
- [Markdown guide](https://www.markdownguide.org/getting-started/)
- [Cheatsheet](https://www.markdownguide.org/cheat-sheet/)
- [More advanced Markdown tricks](https://gist.github.com/apaskulin/1ad686e42c7165cb9c22f9fe1e389558)

## How to contribute?
#### The easy (but not recommended) way
1. `fork` this repository to your own Github account by clicking the button on the upper right of this screen
2. Make edits to the files you want to edit in your browser by clicking the pencil at the top right of a file. All editable .md files can be found in the `docs` folder
3. Write a commit message for your changes and click `Commit changes`
4. After having made all the changes you wanted, go to the tab `Pull requests` > `New pull request`
5. Make sure the base repository is `eur-synclab/sync-manual` `master` and head repository is your own repository, e.g., `DorienHuijjser/sync-manual` `branchinwhichyoumadechanges`.
6. Click `Create pull request`
7. Your pull request will now appear in the eur-synclab repository. If you want, you can assign someone to review your pull request. One of the owners of the repository will review your commits, may request changes and will finally approve the pull request and merge your changes into the eur-synclab/sync-manual master branch.


#### The better way
1. `fork` this repository to your own Github account by clicking the button on the upper right of this screen
2. Create a new branch in your forked repository which you will use to make changes in (your master branch will remain "clean" this way)
3. `clone` your forked repository to your local PC ([using the command-line](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository) or [Rstudio](https://happygitwithr.com/rstudio-git-github.html#clone-the-new-github-repository-to-your-computer-via-rstudio))
4. Make local changes (you can open a .md file in the `docs` folder with multiple text editors such as Atom, Zettlr, Rstudio, etc.) and commit your changes. They are now saved locally
5. Push your commits to your “remote” (online) repository ([using the command-line](https://www.earthdatascience.org/workshops/intro-version-control-git/basic-git-commands/), [in Rstudio](https://happygitwithr.com/rstudio-git-github.html#make-local-changes-save-commit))
5. Follow steps 4-7 explained in the Easy way


#### The most advanced way
1. Follow the installation steps for mkdocs [here](https://www.mkdocs.org/#installation)
2. Follow steps 1-4 explained in The better way
3. In your **prompt**, navigate to your repository directory with `cd C:/users/username/your/repo/directory` and run `mkdocs serve` followed by `mkdocs build`
4. If everything goes correctly, you can now open the new .html files in the `sync-manual/site` folder to see what your changes will look like in the browser
5. Follow step 5 explained in The better way
6. Follow steps 4-7 explained in The easy way


#### Issues and Projects
If you would like to see a change that requires more work or input from others before you can start editing yourself, you can open an Issue. There are some great features about Issues:

- You can assign people to the Issue who should solve it or provide input
- You can add the issue to a project. In the tab Projects, you can find our Kanban board in which we have made the columns  “To do”, “In progress” and “Done”. We made this so we have an overview of Issues that still need work and issues that are in progress.
- You can add labels to an Issue (please do so!) to specify what kind of issue you are writing
- After the issue has been solved, you can Close it manually. However, if you made a pull request that  solves the issue, you can simply comment “Closes #issuenr” in the pull request. After the pull request has been merged, the issue is automatically closed!


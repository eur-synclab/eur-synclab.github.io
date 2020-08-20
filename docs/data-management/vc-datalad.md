# Version control for datasets

Version control for data is equally important for being able to reproduce results as it is for software/code and other documentation. Git, however, is very bad at handling (a) large (amount of) data files, because every version of every file is stored in the repository. So how can we formally version our data?

## git-annex

git-annex is a command line-based version control system that can manage all file *content* is a separate directory in the repository called the *annex* (`.git/annex/objects`). Only the files names and some metadata are placed into git version control. When you push a git repository with an annex to Github, the annex is not uploaded, but can be stored in a web-hosting service. Thus, a copy (clone) of the github repository only contains the version histories and not the data files themselves. Any file content *can* be downloaded from the external storage with `git-annex get`.  



## DataLad

DataLad is a great version control system for datasets, independently of its size. It is based on git and git-annex and is relatively simple to use. It also has many more functionalities and a great and comprehensive [handbook](http://handbook.datalad.org/en/latest/). Note that DataLad is a **command line tool**, so some previous experience with command line git is advantageous. 

- If you want to learn how to use DataLad, please go to the handbook via [http://handbook.datalad.org/en/latest/](http://handbook.datalad.org/en/latest/) 
- If you find anything unclear about the handbook or want to contribute, head over to the [handbook repository](https://github.com/datalad-handbook/book) on github and open an issue or a pull request (see their [how to contribute](http://handbook.datalad.org/en/latest/contributing.html))
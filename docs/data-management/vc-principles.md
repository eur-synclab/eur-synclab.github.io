# Version control principles

Version control is a way to track changes made to a file, creating a history of the file that can be reviewed. It is important to keep different versions separated **in almost all situations**, because:

<ul>
    <li>it keeps different stages of processing/editing separated</li>
    <li>it allows you to go back to previous versions if something went wrong</li>
    <li>ideally, it allows tracking who did what and when</li>
    <li>it prevents a lot of confusion in this type of situation: <br> <img src="../img/final.JPG" style="zoom:67%;" alt="A final document is rarely really final! Source: http://phdcomics.com/comics/archive_print.php?comicid=1531" style="vertical-align:middle"/></li>
</ul>



There are both informal and formal ways of using version control for your files. However, for both ways, the typical procedure is as follows:

1. Do something with a file (create, edit, remove)
2. Save the file
3. Register the change by making a snapshot of the file status, i.e., a version

In informal ways, step 2 and 3 cannot always be separated. Sometimes, step 3 is even left out completely, which, from personal experience, I cannot recommend you to do! ​ In formal version control systems, however, step 3 is a necessary step that cannot be skipped, forcing you to create a new version each time you make a change. 



## Informal ways to use version control

It is highly recommended to make a habit out of at least one, but preferably more of the following practices if you do not (want to) use a formal version control system:

<ul>
    <li>Keep raw data separately from any processed data and document which steps have been taken to go from the former to the latter</li>
    <li>Rename a file every time you make a sizable change</li>
    <ul>
        <li>Use dates in the filename in the format YYYYMMDD</li>
        <li>Append the filename with a version number, e.g., document_v1.0, document_v1.2, etc.</li>
        <li>See <a href=https://authors.library.caltech.edu/103626/>this link</a> for a helper document for coming up with a good file naming convention</li>
    </ul>
    <li>Include a versioning history within the document, e.g., on the first page, explaining what changed in which version</li>
    <li>Use services like Google drive and Dropbox, which allow collaborative editing but also reverting to previous versions</li>
</ul>




## Formal version control systems 

There are also formal version control systems, such as:

- [Git](https://git-scm.com/)
- [Mercurial](https://www.mercurial-scm.org/)
- [SVN](https://subversion.apache.org/)

These actually need to be installed and worked with while or after you are editing files. They require some knowledge and skills of the systems, but they also reward you with perfect file histories and reverting possibilities. The next chapter will go into the most often used version control system: git.
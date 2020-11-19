# Open source software

Let's say I have an experiment or analysis code that I want to share with the world. However, I want to get acknowledgement and I don't want to reply to all separate emails asking for it. How to go about it? Create an open source project!

See also:

- FAIR software [recommendations](https://fair-software.nl/)
-  [Open source guide](https://opensource.guide/)



## 1. Create a github repository

If you want to know more about how github works, check out the [github chapter](../data-management/vc-github.md).

- Choose a recognizable name (check for projects with a similar name!)
- Choose a public repository
- Initialize a readme.md file



## 2. Include information files

- Write a comprehensive **readme file**: what does the repository contain? What is the background? Can people contribute and how can people use your software? (You can also [write one online](https://www.makeareadme.com/))
- Write **contributing guidelines**, if you are open to people contributing
- Write a **code of conduct**
- Choose a **license** for your project (see [Github docs](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/licensing-a-repository)): this is important, because it specifies how people can use your software. [MIT](https://choosealicense.com/licenses/mit/), [Apache 2.0](https://choosealicense.com/licenses/apache-2.0/), and [GPLv3](https://choosealicense.com/licenses/gpl-3.0/) are the most popular open source licenses, but there are [other options](https://choosealicense.com/). You can use this [**license selector**](https://ufal.github.io/public-license-selector/) as well.



Read about all these steps on [this website](https://opensource.guide/starting-a-project/).



## 3. Fill up the repository with your software

- use consistent code conventions and clear function/method/variable names
- comment your code!
- remove sensitive materials in the revision history, issues, or pull requests
- use logical file names and structure
- check whether your software is of [sufficient quality](https://fair-software.nl/recommendations/checklist)



## 4. Make your software citable

Despite you having specified how people can reuse your software (through the license), your software is not yet citable using a persistent identifier. Unfortunately, Github does not offer the possibility to create a persistent identifier for a repository directly. **However**, it is possible to make a **release** (a snapshot of the repository at a certain point in time) on Github that you can then publish on **Zenodo**, which will create a DOI. [Click here](https://guides.github.com/activities/citable-code/) to see how to do this.



## 5. Register your software in a community registry

This allows others to easily find and reuse your software or code. Find a registry [here](https://github.com/NLeSC/awesome-research-software-registries).
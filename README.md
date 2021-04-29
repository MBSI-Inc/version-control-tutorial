# Using Version Control

Using Version control software is one of the most important skills you can develop, as a researcher. Even if you are not familiar with the term "version control", you have likely been using some semblance of it. Think of "Track Changes" in Microsoft Word. Track Changes identifies how a document was changed relative to a previous version of document, records who made the changes, and when the changes were made; it also allows you to "undo".

## Git

Currently, the most dominant version control software is [Git](https://git-scm.com/). To my knowledge, there are not any strong alternatives to Git currently. [Mercurial](https://www.mercurial-scm.org/) is similar, simpler to use than Git but never got significant traction.

Previously, dominant version control software were [Subversion](https://subversion.apache.org/) and [Concurrent Versions System](https://en.wikipedia.org/wiki/Concurrent_Versions_System). Thee both differ from Git in that they are __centralized__: the record of changes is stored on a (typically) remote server. Git (and Mercurical) are known as __distributed__. A complete copy of the version is maintained locally. Remote servers can be used but are not required.

__MORAL:__ Learn Git now, but keep your eye out in the future for its replacement.


### Installing Git

- __On Windows__: Install [Git for Windows](https://gitforwindows.org/). This includes Git Bash, which will allow Windows users to follow along the same as Mac/Linux users.

- __On Macs__: Git should already be installed. If not,
    - Install [Xcode](https://apps.apple.com/au/app/xcode/id497799835?mt=12). Note: This is *__slow__*!
    - Install [Homebrew](https://brew.sh/)
    - `brew install git`
- __On Linux__: Git should already be installed.


### Using Git

- The first thing to remember about Git is that Git is hard to use!

![Git XKCD](https://imgs.xkcd.com/comics/git.png)

- The second thing to remember about Git is that Git likes text files and dislikes binary files.

__Activity illustrating text vs binary files__

#### The Git Workflow

1. Add
1. Commit
1. Push/Pull
1. Resolve Conflicts

### Git Practice

- __Activity:__ Create a Local Git Repository__
- __Activity:__ Create and Clone a Remote Repository
- __Activity:__ Create and resolve conflicts

#### Common Problems with Git and Jupyter Notebooks

- Jupyter notebooks are rendered at HTML in our browsers but on disk they are stored as JSON files on our computers. The JSON files contains metadata about the notebook (e.g. which kernel we are using (language, environment), the Code cells, the Markdown cells, and the output cells. Output cells may well contain binary data (e.g. images) which is a recipe for conflicts

The JSON format can be easy to mess up if we try to edit the JSOn file directly, we are likely to corrupt the JSOn format making the notebook unusable. This makes resolving git conflicts difficult, and it is best to try to avoid as many conflicts as possible.

One of the most straightforward ways of minimizing conflicts is to eliminate the output from the notebooks efore committing them. This can be done manually, but there is a tool we can install to automatically strip the output from a notebook before a changed notebook is added to the git repository.

- [nbstripout](https://pypi.org/project/nbstripout/)

There is a whole ecosystem of tools designed to hlpe with version control of Jupyter notebooks. Some of them are described [here](https://towardsdatascience.com/how-to-version-control-jupyter-notebooks-ccf0be144319).

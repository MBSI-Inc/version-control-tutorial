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

#### Common Problems with Git and Jupyter Notebooks

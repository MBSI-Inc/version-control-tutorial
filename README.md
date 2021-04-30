# Using Version Control

Using Version control software is one of the most important skills you can develop, as a researcher. Even if you are not familiar with the term "version control", you have likely been using some semblance of it. Think of "Track Changes" in Microsoft Word. Track Changes identifies how a document was changed relative to a previous version of itself, records who made the changes, and when the changes were made; it also allows you to "undo" the changes.

## Git

Currently, the most dominant version control software is [Git](https://git-scm.com/). To my knowledge, there are not any strong alternatives to Git currently. [Mercurial](https://www.mercurial-scm.org/) is similar, simpler to use than Git but never got significant traction.

Previously, dominant version control software were [Subversion](https://subversion.apache.org/) and [Concurrent Versions System](https://en.wikipedia.org/wiki/Concurrent_Versions_System). Thee both differ from Git in that they are __centralized__: the record of changes is stored on a (typically) remote server. Git (and Mercurical) are known as __distributed__. A complete copy of the version is maintained locally. Remote servers can be used but are not required.

__MORAL:__ Learn Git now, but keep your eye out in the future for its replacement, which is hopefully more user friendly.


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

Git is based on [`diff`](https://en.wikipedia.org/wiki/Diff), which shows the differences between two files.

Here are two images of myself:

![skeletal self](./media/ct3.jpg)

![skin self](./media/ct4.jpg)

They are clearly different, and `diff` recognizes them as being different, but without any details about how they differ:

```bash
diff ct3.jpg ct4.jpg
Binary files ct3.jpg and ct4.jpg differ
```

Whereas if I extract the EXIF data from the images and save as a text file, `diff` now tells me how these text files differ:

```bash
brian$ diff ct4.json ct3.json
1c1
< {"_exif_ifd_pointer": 44, "pixel_x_dimension": 1200, "pixel_y_dimension": 1202, "make": "Horos"}
\ No newline at end of file
---
> {"_exif_ifd_pointer": 26, "pixel_x_dimension": 1200, "pixel_y_dimension": 1202}
\ No newline at end of file
```

#### The Git Workflow

1. Add
    1. We add new things and we add changed things---same command for both.
1. Commit
    1. Remember git always wants a commit message!
1. Push/Pull (remote only)
1. Resolve Conflicts

Once you have committed something to your repository, the content is always there unless you delete your repository. So be careful of things like accidentally committing passwords or other confidential information.

### Git Practice

- __Activity:__ Create a Local Git Repository <sup id="a1">[1](#f1)</sup>
- __Activity:__ Create a repository on GitHub and clone this to your comptuer. <sup id="a2">[2](#f2)</sup>
- __Activity:__ Create and resolve conflicts<sup id="a3">[3](#f3)</sup>


#### Common Problems with Git and Jupyter Notebooks

- Jupyter notebooks are rendered at HTML in our browsers but on disk they are stored as JSON files on our computers. The JSON files contains metadata about the notebook (e.g. which kernel we are using (language, environment), the Code cells, the Markdown cells, and the output cells. Output cells may well contain binary data (e.g. images) which is a recipe for conflicts

The JSON format can be easy to mess up if we try to edit the JSON file directly, we are likely to corrupt the JSOn format making the notebook unusable. This makes resolving git conflicts difficult, and it is best to try to avoid as many conflicts as possible.

One of the most straightforward ways of minimizing conflicts is to eliminate the output from the notebooks before committing them. This can be done manually, but there is a tool we can install to automatically strip the output from a notebook before a changed notebook is added to the git repository.

- [nbstripout](https://pypi.org/project/nbstripout/)

My suggestion is to install `nbstripout` to be a `global` tool that git always uses when you commit a notebook. (Instructions for this are on the pypi page.)

There is a whole ecosystem of tools designed to help with version control of Jupyter notebooks. Some of them are described [here](https://towardsdatascience.com/how-to-version-control-jupyter-notebooks-ccf0be144319).


---------------
<b id="f1">1</b> This is simple. All you need to do is type `git init` in a directory that is not already a git repository. [↩](#a1)

<b id="f2">2</b> [Here is GitHub's instructions for this](https://docs.github.com/en/github/getting-started-with-github/create-a-repo) [↩](#a2)

<b id="f3">3</b> The easiest way to do this is to edit a file (e.g. the README.md file) on GitHub and on your local computer. Make sure you make incompatible changes on the same line. What I did was add the date in one format on GitHub and in a different format on my local computer.[↩](#a3)

# latex-assignment-dexy
This is a Dexified version of [latex-assignment](https://github.com/ekce/latex-assignment), a modular latex preamble for writing assignments designed to alleviate some of the problems that come with assignment writing.

The preamble is stored in the `include` directory and currently split into three parts.
* `00.main.tex` - Stores all of the main packages used.
* `10.tikz.tex` - Stores only *tikz* related packages.
* `20.commands.tex` - Stores only user-defined commands.
* `30.dexy.tex` - Stores only dexy generated commands.

Note that currently some of the commands defined in `20.commands.tex` depend on some of the packages referenced in `00.main.tex`.

Inside the sample document there is a piece of code that looks like
```tex
\newcommand{\preamblefolder}{./include}       % Preamble folder location
\input{\preamblefolder/00.main.tex}           % Main packages
\input{\preamblefolder/10.tikz.tex}           % Tikz packages
\input{\preamblefolder/20.commands.tex}       % Functions and commands
\input{\preamblefolder/30.dexy.tex}           % Dexy functions and commands
```
The first line sets the folder location where the preamble is stored. It is possible to easily change this to something else like:
```
\newcommand{\preamblefolder}{/home/user/latex/preambles/assignment}
```
The remaining commands just include each of the documents. This makes it easy to comment one out and write your own set of packages or switch from version of a file to another. It also lets you write in document specific packages without having to modify your preamble for all of your documents.

**Note:** There are some packages that should only be called in the document itself. For instance the easy-todo package.

## Workflow:
Clone the repository with
```
git clone git@github.com:ekce/latex-assignment-dexy.git .
```
Copy the *blank.tex* file and rename it to something else like *assignment.tex*. Then edit said file and run `dexy` in the directory to build. 

**Note:** The gitignore file is set up to ignore everything but the files in the repository so it will not track updates to your files.

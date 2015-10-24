# latex-assignment
This is a modular latex preamble for writing assignments together with a short manual and a sample document that's designed to alleviate some of the problems that come with assignment writing.

The preamble is stored in the `include` directory and currently split into three parts.
* `00.main.tex` - Stores all of the main packages used.
* `10.tikz.tex` - Stores only *tikz* related packages.
* `20.commands.tex` - Stores only user-defined commands.

Note that currently some of the commands defined in `20.commands.tex` depend on some of the packages referenced in `00.main.tex`.

Inside the sample document there is a piece of code that looks like
```tex
\newcommand{\preamblefolder}{./include}       %preamble folder location
\input{\preamblefolder/00.main.tex}           %main packages
\input{\preamblefolder/10.tikz.tex}           %tikz packages
\input{\preamblefolder/20.commands.tex}       %functions and commands
```
The first line sets the folder location where the preamble is stored. It is possible to easily change this to something else like:
```
\newcommand{\preamblefolder}{/home/user/latex/preambles/assignment}
```
The remaining commands just include each of the documents. This makes it easy to comment one out and write your own set of packages or switch from version of a file to another. It also lets you write in document specific packages without having to modify your preamble for all of your documents.

**Note:** There are some packages that should only be called in the document itself. For instance the easy-todo package.

The manual file gives a brief overview of why I've chosen the packages I have. I don't provide a thorough explanation of the packages as that would take too much space. I don't expect other users to agree with all of my package choices but I hope this gives them an idea of what other options exist.

The sample file presents a simple example assignment.

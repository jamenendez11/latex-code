# latex-code
Templates, bibliographies, and macros for latex

### Notes ###
For latex to find these automatically, one needs to set the `TEXMFHOME` variable to this repository. To do this, you need to edit the file `texmf.cnf`, which can be located via the following command:

`kpsewhich texmf.cnf`

In this file, there is a line specifying the `TEXMFHOME` variable. Simply set this to e.g. `~/repos/latex-code`. Thereafter, latex will automatically 
* look for packages in `~/repos/latex-code/tex/latex/`
* look for `.bib` files in `~/repos/latex-code/bibtex/bib/`

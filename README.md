# latex-code
Templates, bibliographies, and macros for latex

### How to get latex to find these files automatically ###
For latex to find these automatically, one needs to set the `TEXMFHOME` variable to this repository. To check the current value of this variable, use
```
kpsewhich -var-value=TEXMFHOME
```
To change it, you need to edit the file `texmf.cnf`, which can be located via
```
kpsewhich texmf.cnf
```
In this file, there is a line specifying the `TEXMFHOME` variable. Simply set this to e.g. `~/repos/latex-code`. Thereafter, latex will automatically 
* look for packages in `~/repos/latex-code/tex/latex/`
* look for `.bib` files in `~/repos/latex-code/bibtex/bib/`

Alternatively, you can keep the default `TEXMFHOME` location and create hard links to this repository. It is important that these be hard links -- symbolic links (i.e. `ln -s`) won't work! It is also critical that you keep the right directory structure, as mentioned above (i.e. packages go in `/tex/latex/` and `.bib` files in `/bibtex/bib/`). Here is example code to do this:
```
mkdir -p $(kpsewhich -var-value=TEXMFHOME)/tex/latex/
mkdir -p $(kpsewhich -var-value=TEXMFHOME)/bibtex/bib/
ln ~/repos/latex-code/tex/latex/* $(kpsewhich TEXMFHOME)/tex/latex/
ln ~/repos/latex-code/bibtex/bib/* $(kpsewhich TEXMFHOME)/bibtex/bib/
```
where the first two lines create the right directory structure (assuming the `TEXMFHOME` directory is empty), and the latter two create the links to this repository, assumed to be located in `~/repos/`.

For more details on the correct directory structure, see here: https://github.com/lingbib/lingbib/wiki/Setting-up-a-local-texmf-tree

For more details on the `texmf.cnf` file, see here: https://texfaq.org/FAQ-privinst


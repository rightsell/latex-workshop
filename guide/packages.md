# Some Useful LaTeX Packages

## mhchem

[https://ctan.org/pkg/mhchem](https://ctan.org/pkg/mhchem)

This package drastically simplifies entering chemical formulas, without requiring the tedious use of math mode and brackets.

### Usage

Load the package by adding `\usepackage[version=4]{mhchem}` to your preamble.

Enter formulas using the command `\ce`, e.g. `\ce{H2O}` or `\ce{Nd^3+}` which will intelligently set subscripts and superscripts for you.


## authblk

[https://ctan.org/pkg/authblk](https://ctan.org/pkg/authblk)

This package replaces the `\author` command to simplify adding affiliations to the author list of journal articles.

### Usage

Load the package with the `\usepackage{authblk}` command in your preamble.

Then, set your author list with affiliations as follows:
```
\author[1]{First Author}
\author[2]{Second Author}
\author[1,*]{Corresponding Author}
\affil[1]{Department, University, Address}
\affil[2]{Department 2, University, Address}
\affil[*]{Corresponding Author: email address}
```
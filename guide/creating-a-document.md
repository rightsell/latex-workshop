## Basics of a LaTeX document

Simply create a file with the .tex extension. The first thing a document needs is a preamble, which can be as simple as `\documentclass{article}`, followed by the body of the document inside the `\begin{document}` and `\end{document}` environment.

A very minimal document will look something like this: 
```
\documentclass{article}

\begin{document}

This is the text that will appear in the compiled document.

\end{document}
```

## Compiling the PDF

There are several compilers to choose from, but in general `latexmk` is a good option. You may need to install it using your LaTeX package manager (tlmgr or MikTeX).
To use it, either go to the options in your editor and check what compiler is set, or open a terminal in the folder of your .tex file and run `latexmk -pdf document.tex`, and you should get a file named document.pdf.

Every document compilation generates several auxiliary files. You can typically ignore these. They will make subsequent compilations of the document slightly faster, but occasionally when compilation fails for no apparent reason, you may need to clean the auxiliary files and try again. You don't need to share these files with co-authors or push them to a git repo.
To clean these files, simply run `latexmk -c`. Be careful to use a lowercase c, as uppercase C will also clean any generated PDFs as well.

## Loading a document style and packages

## Images

## Tables

## References


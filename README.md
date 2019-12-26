# Latex-Documantation-Template
A template for writing documentation in latex with example pdf file
## Packages needed
```
sudo apt-get install texlive-latex-base texlive-fonts-recommended texlive-fonts-extra texlive-latex-extra
```
## Contents of the .tex file
[Raw file here](https://raw.githubusercontent.com/BeanGreen247/Latex-Documantation-Template/master/documentation-template.tex)
```
% Setting the type of document
\documentclass[12pt,a4paper]{report}

% Packages used to enable graphics and codeblocks
\usepackage{graphicx}
\usepackage{listings}
\usepackage{xcolor}
\usepackage{inputenc}
\usepackage{emptypage}
\usepackage{etoolbox}

% Fixing the appearance of the footer in the empty pages in between chapters.
\let\origdoublepage\cleardoublepage
\renewcommand{\cleardoublepage}{%
  \clearpage
  {\pagestyle{empty}\origdoublepage}%
}
% Finished fixing appearance

% Adding syntax highlighting to codeblocks
\definecolor{codegreen}{rgb}{0,0.6,0}
\definecolor{codegray}{rgb}{0.5,0.5,0.5}
\definecolor{codepurple}{rgb}{0.58,0,0.82}
\definecolor{backcolour}{rgb}{0.95,0.95,0.92}
 
\lstdefinestyle{mystyle}{
    backgroundcolor=\color{backcolour},   
    commentstyle=\color{codegreen},
    keywordstyle=\color{magenta},
    numberstyle=\tiny\color{codegray},
    stringstyle=\color{codepurple},
    basicstyle=\ttfamily\footnotesize,
    breakatwhitespace=false,         
    breaklines=true,                 
    captionpos=b,                    
    keepspaces=true,                 
    numbers=left,                    
    numbersep=5pt,                  
    showspaces=false,                
    showstringspaces=false,
    showtabs=false,                  
    tabsize=2
}
 
\lstset{style=mystyle}
% Finished adding syntax highlighting

\begin{document}
% The title page
\begin{titlepage}
	\centering
	\vspace{1cm}
	{\scshape\LARGE  Name of organization or company name here\par}
	\vspace{1cm}
	{\scshape\Large Subject\par}
	\vspace{1.5cm}
	{\huge\bfseries Title\par}
	\vspace{2cm}
	{\Large\itshape Author\par}
\end{titlepage}

% Table of contents
\cleardoublepage
\begin{titlepage}
\tableofcontents

% First chapter or section of our document
\cleardoublepage
% if you want chapters instead of sections, jus change the section tag to chapter
\section{\scshape\Large Hello world in Python}
\vspace{0.5cm}

\begin{lstlisting}[language=Python, caption=Hello world in Python]
print('Hello world')
\end{lstlisting}

\cleardoublepage
\section{\scshape\Large Section containing a Bash codeblock}
\vspace{0.5cm}

This chapter contains a Bash codeblock
\begin{lstlisting}[language=Bash, caption=The cd command]
cd #command for changing directories
\end{lstlisting}

\cleardoublepage
\section{\scshape\Large Closing words}
\vspace{0.5cm}

\cleardoublepage
\section{\scshape\Large Sources}
\vspace{0.5cm}

% End of document
\end{document}
```
## Creating the pdf file
```
latexmk -pdf documentation-template.tex -f
```
[The created pdf file](https://github.com/BeanGreen247/Latex-Documantation-Template/blob/master/documentation-template.pdf)

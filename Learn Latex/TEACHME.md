# Learn LaTeX
## Contents
    1 What is LaTeX?
    2 Why learn LaTeX?
    3 Writing your first piece of LaTeX
    4 The preamble of a document
    5 Including title, author and date information
    6 Adding comments
    7 Bold, italics and underlining
    8 Adding images
    9 Captions, labels and references
    10 Creating lists in LaTeX
        10.1 Unordered lists
        10.2 Ordered lists
    11 Adding math to LaTeX
        11.1 Inline math mode
        11.2 Display math mode
        11.3 More complete examples
    12 Basic document structure
        12.1 Abstracts
        12.2 Paragraphs and new lines
        12.3 Chapters and sections
    13 Creating tables
        13.1 Creating a basic table in LaTeX
        13.2 Adding borders
        13.3 Captions, labels and references
    14 Adding a Table of Contents
    15 Downloading your finished document
    16 Finding and using LaTeX packages
        16.1 Loading packages
        16.2 Finding information about packages: CTAN
        16.3 Packages available on Overleaf: Introducing TeX Live


## What is LaTeX?
LaTeX is a tool for typesetting documents using plain text files and embedded commands. It allows you to focus on content while the computer handles the formatting.

## Why learn LaTeX?
Mainly used to write thesis report, journar or conference paper.

## Writing your first piece of LaTeX
Make sure that any add-on is running on or not, they may cause trouble loading the pdf, specially IDM causes problem, so it would be better if we turn of the add-ons.

you can change the pdf viewer by clicking at menu-> scrolling down to pdf viewer-> changing into the viewer you are satisfied with.
write the following command on [Overleaf](https://www.overleaf.com/project) and <font color='yellow'>Recompile</font>.
```bash
\documentclass{article}
\begin{document}
Hi, I am Doniel Tripura
\end{document}
```
The <font color='green'>\documentclass{article}</font> line determines the document type, or class, which controls the overall document appearance. Different documents require different classes. The content, or body of the document, is written between the <font color='green'>\begin{document}</font> and <font color='green'>\end{document} </font>tags. After making changes, you can view the resulting PDF by recompiling the document.The first line of code, \documentclass{article}, declares the document type, known as its class, which controls the overall appearance of the document. Different types of documents require different classes. For example, a CV/resume will require a different class than a scientific paper, which might use the standard LaTeX article class. Other types of documents may require different classes, such as book or report. The content, known as the body of the document, is written between the \begin{document} and \end{document} tags. After making changes, you can view the resulting PDF by recompiling the document.

## The preamble of a document

The screengrab above shows Overleaf storing a LaTeX document as a file called main.tex: the .tex file extension is, by convention, used when naming files containing your document’s LaTeX code.

The screengrab above displays Overleaf saving a LaTeX document as a file named main.tex. The .tex file extension is conventionally used for files containing your document’s LaTeX code. In the preamble, you define the document class, languages, and configurations. ie.,
```bash
\documentclass[12pt, letterpaper]{article}
\usepackage{graphicx}
```
where <font color='green'>\documentclass[12pt, letterpaper]{article}</font> defines the overall class (type) of document. Additional parameters, which must be separated by commas, are included in square brackets ([...]) and used to configure this instance of the article class; i.e., settings we wish to use for this particular article-class-based document.

In this example, the two parameters do the following:

* 12pt sets the font size
* letterpaper sets the paper size

Of course other font sizes, 9pt, 11pt, 12pt, can be used, but if none is specified, the default size is 10pt. As for the paper size, other possible values are a4paper and legalpaper. For further information see the article about page size and margins.

The preamble line
```bash
\usepackage{graphicx}
```
is an example of loading an external package (here, graphicx) to extend LaTeX’s capabilities, enabling it to import external graphics files. LaTeX packages are discussed in the section Finding and using LaTeX packages. 

## Including title, author and date information

Adding a title, author and date to our document requires three more lines in the preamble (not the main body of the document). Those lines are:

1. \title{My first LaTeX document}: the document title
2. \author{Hubert Farnsworth}: here you write the name of the author(s) and, optionally, the \thanks command within the curly braces:

    * \thanks{Funded by the Overleaf team.}: can be added after the name of the author, inside the braces of the author command. It will add a superscript and a footnote with the text inside the braces. Useful if you need to thank an institution in your article.

3. \date{August 2022}: you can enter the date manually or use the command \today to typeset the current date every time the document is compiled

With these lines added, your preamble should look something like this: 
```bash
\documentclass[12pt, letterpaper]{article}
\title{My first LaTeX document}
\author{Hubert Farnsworth\thanks{Funded by the Overleaf team.}}
\date{August 2022}
```
To typeset the title, author and date use the <font color='green'>\maketitle</font> command within the body of the document: 
```bash
\begin{document}
\maketitle
We have now added a title, author and date to our first \LaTeX{} document!
\end{document}
```
The preamble and body can now be combined to produce a complete document which can be opened in Overleaf: 
```bash
\documentclass[12pt, letterpaper]{article}
\title{My first LaTeX document}
\author{Hubert Farnsworth\thanks{Funded by the Overleaf team.}}
\date{August 2022}
\begin{document}
\maketitle
We have now added a title, author and date to our first \LaTeX{} document!
\end{document}
```
write the command & <font color='yellow'>Recompile</font>.
```bash
\documentclass[12pt, letterpaper]{article}
\title{My first LaTeX document}
\author{Doniel Tripura\thanks{Taught by Dr.K.M. Azharul Hasan & Sunanda Das sir.}}
\date{May 2024}

\documentclass{article}
\begin{document}
\maketitle
Hi, I am Doniel Tripura
\end{document}
```
## Adding comments
A LaTeX comment is a section of text that will not be typeset or affect the document in any way—often used to add “to do” notes; include explanatory notes; provide in-line explanations of tricky macros or comment-out lines/sections of LaTeX code when debugging.

To make a comment in LaTeX, simply write a % symbol at the beginning of the line, as shown in the following code which uses the example above:
```bash
\documentclass[12pt, letterpaper]{article}
\title{My first LaTeX document}
\author{Hubert Farnsworth\thanks{Funded by the Overleaf team.}}
\date{August 2022}
\begin{document}
\maketitle
We have now added a title, author and date to our first \LaTeX{} document!

% This line here is a comment. It will not be typeset in the document.
\end{document}
```
**Note:**
* Select the line you want to comment, then **ctrl**+**/** will automatically comment out the line.

write the command & <font color='yellow'>Recompile</font>.
```bash
\documentclass[12pt, letterpaper]{article}
\title{My first LaTeX document}
\author{Doniel Tripura\thanks{Taught by Dr.K.M. Azharul Hasan & Sunanda Das sir.}}
\date{May 2024}

\begin{document}
\maketitle

Hi, I am Doniel Tripura
% This is comment
\end{document}
```
## Bold, italics and underlining

Next, we will now look at some text formatting commands:

1. **Bold**: bold text in LaTeX is typeset using the \textbf{...} command.
2. *Italics*: italicised text is produced using the \textit{...} command.
3. <u>Underline</u>: to underline text use the \underline{...} command.

* bonus: to get newline use the  \\\\ after any line.

The next example demonstrates these commands:
```bash
Some of the \textbf{greatest}
discoveries in \underline{science} 
were made by \textbf{\textit{accident}}.
```
Another very useful command is <font color='green'>\emph{argument}</font>, whose effect on its argument depends on the context. Inside normal text, the emphasized text is italicized, but this behaviour is reversed if used inside an italicized text—see the next example:
```bash
Some of the greatest \emph{discoveries} in science 
were made by accident.

\textit{Some of the greatest \emph{discoveries} 
in science were made by accident.}

\textbf{Some of the greatest \emph{discoveries} 
in science were made by accident.}
```

write the command & <font color='yellow'>Recompile</font>.
```bash
\documentclass[12pt, letterpaper]{article}
\title{My first LaTeX document}
\author{Doniel Tripura\thanks{Taught by Dr. K. M. Azharul Hasan \& Sunanda Das sir.}}
\date{May 2024}

\begin{document}
\maketitle

Hi, I am Doniel Tripura.
This is newline:
% This is comment
\textbf{This is bold text.}
\textit{This is italic text.}
\underline{This is underline text.}
\end{document}

```
## Adding images

In this section we will look at how to add images to a LaTeX document. Overleaf supports three ways to insert images:

1. Use the Insert Figure button(The Insert Figure button on the editor toolbar), located on the editor toolbar, to insert an image into Visual Editor or Code Editor.
2. Copy and paste an image into Visual Editor or Code Editor.
3. Use Code Editor to write LaTeX code that inserts a graphic.

Options 1 and 2 automatically generate the LaTeX code required to insert images, but here we introduce option 3—note that you will need to upload those images to your Overleaf project. The following example demonstrates how to include a picture:
```bash
\documentclass{article}
\usepackage{graphicx} %LaTeX package to import graphics
\graphicspath{{images/}} %configuring the graphicx package
 
\begin{document}
The universe is immense and it seems to be homogeneous, 
on a large scale, everywhere we look.

% The \includegraphcs command is 
% provided (implemented) by the 
% graphicx package
\includegraphics{universe}  
 
There's a picture of a galaxy above.
\end{document}
```
The above example loads the graphicx package which, among many other commands, provides <font color='green'>\includegraphics{...}</font> to import graphics and <font color='green'>\graphicspath{...}</font> to advise LaTeX where the graphics are located.

To use the graphicx package, include the following line in your Overleaf document preamble:
```bash
\usepackage{graphicx}
```
In our example the command <font color='green'>\graphicspath{{images/}}</font> informs LaTeX that images are kept in a folder named images, which is contained in the current directory:

Image showing LaTeX accessing images stored in a folder

The <font color='green'>\includegraphics{universe}</font> command does the actual work of inserting the image in the document. Here, universe is the name of the image file but without its extension.

**Note:**

* Although the full file name, including its extension, is allowed in the <font color='green'>\includegraphics</font> command, it’s considered best practice to omit the file extension because it will prompt LaTeX to search for all the supported formats.
    Generally, the graphic’s file name should not contain white spaces or multiple dots; it is also recommended to use lowercase letters for the file extension when uploading image files to Overleaf.

At first, create a folder at Overleaf, name it(images), then upload any image(universe.jpeg) inside it.

write the command & <font color='yellow'>Recompile</font>.
```bash
\documentclass[12pt, letterpaper]{article}
\usepackage{graphicx}
\graphicspath{{images/}}
\title{My first LaTeX document}
\author{Doniel Tripura\thanks{Taught by Dr. K. M. Azharul Hasan \& Sunanda Das sir.}}
\date{May 2024}

\begin{document}
\maketitle

Hi, I am Doniel Tripura.
This is newline:
% This is comment
\textbf{This is bold text.}
\textit{This is italic text.}
\underline{This is underline text.}

Some of the greatest \emph{discoveries} in science 
were made by accident.

\textit{Some of the greatest \emph{discoveries} 
in science were made by accident.}

\textbf{Some of the greatest \emph{discoveries} 
in science were made by accident.}

\includegraphics{universe}
\end{document}
```
## Captions, labels and references
Images can be captioned, labelled and referenced by means of the figure environment, as shown below:
```bash
\documentclass{article}
\usepackage{graphicx}
\graphicspath{{images/}}
 
\begin{document}

\begin{figure}[h]
    \centering
    \includegraphics[width=0.75\textwidth]{universe}
    \caption{A nice plot.}
    \label{fig:universe1}
\end{figure}
 
As you can see in figure \ref{fig:universe1}, the function grows near the origin. This example is on page \pageref{fig:universe1}.

\end{document}
```
There are several noteworthy commands in the example:

1. <font color='green'>\includegraphics[width=0.75\textwidth]{universe}</font>: This form of \includegraphics instructs LaTeX to set the figure’s width to 75% of the text width—whose value is stored in the \textwidth command.

2. <font color='green'>\caption{A nice plot.}</font>: As its name suggests, this command sets the figure caption which can be placed above or below the figure. If you create a list of figures this caption will be used in that list.

3. <font color='green'>\label{fig:universe1}</font>: To reference this image within your document you give it a label using the \label command. The label is used to generate a number for the image and, combined with the next command, will allow you to reference it.

4. <font color='green'>\ref{fig:universe1}</font>: This code will be substituted by the number corresponding to the referenced figure.

Images incorporated in a LaTeX document should be placed inside a figure environment, or similar, so that LaTeX can automatically position the image at a suitable location in your document.

Read [Overleaf](https://www.overleaf.com/project) help articles for more information:

* Positioning of Figures
* Inserting Images

write the command & <font color='yellow'>Recompile</font>.
```bash
\documentclass[12pt, letterpaper]{article}
\usepackage{graphicx}
\graphicspath{{images/}}
\title{My first LaTeX document}
\author{Doniel Tripura\thanks{Taught by Dr.K.M. Azharul Hasan \& Sunanda Das sir.}}
\date{May 2024}

\begin{document}
\maketitle

Hi, I am Doniel Tripura.
This is newline:
% This is comment
\textbf{This is bold text.}
\textit{This is italic text.}
\underline{This is underline text.}

Some of the greatest \emph{discoveries} in science 
were made by accident.

\textit{Some of the greatest \emph{discoveries} 
in science were made by accident.}

\textbf{Some of the greatest \emph{discoveries} 
in science were made by accident.}

As you can see in figure \ref{fig:universe1}, the universe is beautiful. This image is on page \pageref{fig:universe1}.

\begin{figure}
    \centering
    \includegraphics[width=0.75\textwidth]{universe}
    \caption{The colorful Universe}
    \label{fig:universe1}
\end{figure}
\end{document}
```
## Creating lists in LaTeX

You can create different types of list using environments, which are used to encapsulate the LaTeX code required to implement a specific typesetting feature. An environment starts with <font color='green'>\begin{environment-name}</font> and ends with <font color='green'>\end{environment-name}</font> where environment-name might be <font color='green'>figure</font>, <font color='green'>tabular</font> or one of the list types: <font color='green'>itemize</font> for unordered lists or <font color='green'>enumerate</font> for ordered lists.
Unordered lists

Unordered lists are produced by the itemize environment. Each list entry must be preceded by the <font color='green'>\item</font> command, as shown below:
```bash
\documentclass{article}
\begin{document}
\begin{itemize}
  \item The individual entries are indicated with a black dot, a so-called bullet.
  \item The text in the entries may be of any length.
\end{itemize}
\end{document}
```
This example produces the following output:
* An example of bulleted lists in LaTeX
* You can also open this  larger Overleaf project which demonstrates various types of LaTeX list.
Ordered lists

Ordered lists use the same syntax as unordered lists but are created using the enumerate environment:
```bash
\documentclass{article}
\begin{document}
\begin{enumerate}
  \item This is the first entry in our list.
  \item The list numbers increase with each entry we add.
\end{enumerate}
\end{document}
```
This example produces the following output:
1. This is the first entry in our list.
2. The list numbers increase with each entry we add.

As with unordered lists, each entry must be preceded by the \item command which, here, automatically generates the numeric ordered-list label value, starting at 1.

For further information you can open this  larger Overleaf project which demonstrates various types of LaTeX list or visit our dedicated help article on LaTeX lists, which provides many more examples and shows how to create customized lists.



## Souce
https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes#What_is_LaTeX?
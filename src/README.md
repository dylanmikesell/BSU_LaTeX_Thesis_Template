## Boise, 09/23/15, Dylan Mikesell:

------------------------------------------------------------------------

Here's a template for BSU graduate theses. If you find problems with it, please e-mail the BSU latex users group at bsulatex@cgiss.boisestate.edu or even better would be to open an [issue](https://github.com/dylanmikesell/BSU_LaTeX_Thesis_Template/issues). If you used the template successfully, please shoot me a message, so that I can keep track.

This directory should be pretty self-contained, with the style files and such. If you miss packages in your installation of latex, go to: http://www.ctan.org/

------------------------------------------------------------------------

## HOW TO COMPILE THE DOCUMENT

Here's how you create the output of the template. On command line run:

`$ make`

This will create a pdf file called BSUmain.pdf. You can use your favorite pdf viewer to view.

Natbib.pdf in the main directory teaches you how to use the natbib package for different inline citation styles. You can compile the bibliography by running:

`$ bibtex BSUmain`

(running `make` in the previous command will also do compile the bibliography automatically!)

If you do not have `pdflatex`, `latex` will also work (see the _Makefile_ to figure out where you might interchange `pdflatex` and `latex`). After compiling you document, you need to convert the dvi output file to pdf with `dvipdf`.

#### IMPORTANT NOTE: 

Latex will tell you when it was fully successful in generating BSUmain.pdf. If you are running individual commands (e.g. `pdflatex` and `bibtex`) rather than using the `make` command then you may need to repeat both commands until the references are updated. If you are using a program like TexStudio or Kyle to _build_ your document, these packages should handle the repeated compiling so that the final pdf is updated.

------------------------------------------------------------------------

## ABOUT THE GRAPHICS

The `\includegraphics{}` command understands figures in postscript format (.ps, .eps), or pdf format (.pdf). I strongly recommend using all pdf figures.

------------------------------------------------------------------------

## ABOUT THE MARGINS & PAGE SIZE

There is a testpage.tex that comes with your installation of latex. Compile it and print the output to see if your configuration is correct for your printer.

The default paper size can be changed, in TeX Live, via tlmgr:

`$ tlmgr paper letter`

or

`$ tlmgr paper a4`

This can only be changed by 'root', so please contact your system administrator if you do not have 'root' privileges. LaTeX assumes a4 papersize out of the box!!

------------------------------------------------------------------------

## CHANGES:

- 09/22/15: (TDM) Moved to GitHub repository.
- 02/26/07: (KvW) split the MS and PhD thesis format: the MS degree does not have an external member. Not quite pleasing this way: I'm waiting for the first person with a co-advisor to write me: right now, that option is commented out in both formats.
- 11/19/07: (KvW) made numerous changes to conform with the wishes of the  graduate college. Also, merged PhD and MS style files again. The only  reason for the split was the title page, and this still requires hacking. Come see me if you cannot figure this out yourself.
- 11/28/07: (KvW) added a heading called "APPENDICES" in TOC. 

------------------------------------------------------------------------

## TO DO:

- fix the hyperlink stuff
- automate the title page for all its different options (MS, PhD, external  members, co-advisors, etc.)
- fix hyphenation for long section and subsection headings


# You want latexmk to *always* run, because make does not have all the info.
# Also, include non-file targets in .PHONY so they are run regardless of any
# file of the given name existing.
.PHONY: BSUmain.pdf all clean

# The first rule in a Makefile is the one executed by default ("make"). It
# should always be the "all" rule, so that "make" and "make all" are identical.
all: BSUmain.pdf

# CUSTOM BUILD RULES

# In case you didn't know, '$@' is a variable holding the name of the target,
# and '$<' is a variable holding the (first) dependency of a rule.
# "raw2tex" and "dat2tex" are just placeholders for whatever custom steps
# you might have.

#%.tex: %.raw
#        ./raw2tex $< > $@

#%.tex: %.dat
#        ./dat2tex $< > $@

# MAIN LATEXMK RULE

# -pdf tells latexmk to generate PDF directly (instead of DVI).
# -pdflatex="" tells latexmk to call a specific backend with specific options.
# -use-make tells latexmk to call make for generating missing files.
# -c tells latexmk to remove all regeneratable files generated by latex and bibtex or biber  except  dvi,  postscript and  pdf. 

# -interaction=nonstopmode keeps the pdflatex backend from stopping at a
# missing file reference and interactively asking you for an alternative.

BSUmain.pdf: BSUmain.tex
	latexmk -pdf -pdflatex="pdflatex -interaction=nonstopmode" -use-make BSUmain.tex
	#makeindex BSUmain.nlo -s nomencl.ist -o BSUmain.nls
	latexmk -C

#pdflatex -synctex=1 -interaction=nonstopmode %.tex|makeindex %.nlo -s nomencl.ist -o %.nls|pdflatex -synctex=1 -interaction=nonstopmode %.tex|"C:/Program Files/Adobe/Reader 11.0/Reader/AcroRd32.exe" %.pdf

# -C tells latexmk to remove all regeneratable files generated by latex and bibtex or biber
clean:
	latexmk -C BSUmain.tex

# This MAKEFILE was taken from an example at http://tex.stackexchange.com/questions/40738/how-to-properly-make-a-latex-project
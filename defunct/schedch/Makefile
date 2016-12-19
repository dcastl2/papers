##############################################################################
# variables
##############################################################################

# set latexfile to the name of the main file without the .tex
latexfile = main

# put the names of figure files here.  include the .eps
figures = 

# reference file for tarball
referencefile = ""

# commands
PDFTEX = pdflatex
TEX = latex
BIBTEX = bibtex

# support subdirectories
VPATH = figs


##############################################################################
# default rule
##############################################################################
all : main



##############################################################################
# compile PDF
##############################################################################
main : clean $(latexfile).pdf

$(latexfile).pdf : $(latexfile).ps
	ps2pdf $(latexfile).ps $(latexfile).pdf


$(latexfile).ps : $(latexfile).dvi
	dvips $(latexfile)


$(latexfile).dvi : $(figures) $(latexfile).tex $(latexfile).bbl
	$(TEX) $(latexfile); $(BIBTEX) $(latexfile); $(TEX) $(latexfile); $(TEX) $(latexfile); 



%.eps : %.fig
	fig2dev -L eps $< > $(dir $< )$@



##############################################################################
# compile short version
##############################################################################
short : short.pdf

short.pdf : clean short.tex $(latexfile).bbl
	$(PDFTEX) short; $(BIBTEX) short; $(PDFTEX) short; $(PDFTEX) short; 



##############################################################################
# compile tarball
##############################################################################

tarball: $(latexfile).tar.gz


$(latexfile).tar.gz : $(figures) $(latexfile).tex $(referencefile).bib
	tar -czvf $(latexfile).tar.gz $^



##############################################################################
# clean
##############################################################################

clean:
	$(RM) *.aux *.dvi *.log *.maf *.mtc *.mtc1 *.out *.pdf *.ps *.toc

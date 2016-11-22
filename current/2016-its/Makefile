RST  = $(filter-out bib.rst,$(wildcard *.rst))
PDF  = $(TEX:.tex=.pdf)

all: figures main.pdf

pdf: figures $(PDF) tidy

%.pdf: %.tex %.bib fig/*
	pdflatex $*
	#bibtex   $*
	#pdflatex $*
	#pdflatex $*

figures:
	$(MAKE) -C fig

clean:
	rm -f *bbl *blg *aux *toc *log *out *pdf

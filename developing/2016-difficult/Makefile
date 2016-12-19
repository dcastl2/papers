
all: main.pdf

%.pdf: %.tex
	pdflatex $*
	bibtex   $*
	pdflatex $*
	pdflatex $*

#%.tex: %.rst
#	rst2latex $^ > $@

clean:
	rm main.pdf main.bbl main.blg main.log main.out main.aux

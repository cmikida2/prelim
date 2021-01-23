TEX = pdflatex -shell-escape -interaction=nonstopmode -file-line-error
PRE =  $(TEX) -ini -job-name="preamble" "&pdflatex preamble.tex\dump"
BIB = bibtex

.PHONY: all view

all : ThesisProposal.pdf

view :
	open ThesisProposal.pdf

ThesisProposal.pdf : ThesisProposal.tex preamble.fmt ThesisProposal.bbl ThesisProposal.blg
	$(TEX) ThesisProposal.tex

ThesisProposal.bbl ThesisProposal.blg : bibliography.bib ThesisProposal.aux
	$(BIB) ThesisProposal

ThesisProposal.aux : ThesisProposal.tex
	$(TEX) ThesisProposal.tex

bibliography.bib : ThesisProposal.tex
	$(TEX) ThesisProposal.tex

clean:
	rm -f ${filename}.{ps,pdf,log,aux,out,dvi,bbl,blg}

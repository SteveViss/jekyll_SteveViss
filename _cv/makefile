TEX = pandoc
src = template.tex details_fr.yml publi.yml
FLAGS = --latex-engine=xelatex

all: publi.yml cv_fr.pdf

publi.yml: publi.bib
	pandoc-citeproc -y $< $ > $@

cv_fr.pdf : $(src)
	$(TEX)  $(filter-out $<,$^ ) -o ../assets/pdf/$@ --template=$< $(FLAGS)

.PHONY: all
clean :
	rm ref.yml ../assets/pdf/cv_fr.pdf

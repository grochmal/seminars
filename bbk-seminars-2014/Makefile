# Makefile for report
LATEX  = pdflatex
RM     = rm -f
LTFS   = *.aux *.lof *.log *.lot *.fls *.out *.toc
DOCS   = *.dvi *.pdf
BIBS   = *.bbl *.blg
IDXS   = *.idx *.ilg *.ind *.ist
BEAM   = *.nav *.snm *.vrb
OTHER  = *.acn *.acr *.glg *.glo *.gls *.brf *.lol

all: email-encryption-part-2.pdf

.PHONY: email1 email2
email1: email-encryption-part-1.pdf
email2: email-encryption-part-2.pdf

# beamer needs three passes:
# one to generate .aux
# one to generate \tableofcontents with pausesections
# and one to correct \tableofcontents with the moved pages
# after pausesections
%.pdf: %.tex
	$(LATEX) $<
	$(LATEX) $<
	$(LATEX) $<

.PRECIOUS: %.aux
%.aux: %.tex
	$(LATEX) $<

.PHONY: clean
clean:
	$(RM) $(LTFS) $(DOCS) $(BIBS) $(IDXS) $(BEAM) $(OTHER)


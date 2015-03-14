#SRC := $(shell egrep -l '^[^%]*\\input{../configuration}' [a-zA-Z0-9]*.tex)

SLIDES := $(shell ls *-slides.tex)

SLIDES_PO := $(SLIDES:%.tex=%-slides.pdf)

ENVS := slides

all: $(SLIDES_PO) clean 

%-slides.pdf: env := slides
%-slides.pdf: %.tex
	@echo compiling SLIDES $*.tex
	@pdflatex -interaction=batchmode "\def\$(env){t}\input" $*.tex > /dev/null;
	@pdflatex -interaction=batchmode "\def\$(env){t}\input" $*.tex > /dev/null;

clean:
	rm -f *.aux *.log *.bbl *.blg *.brf *.cb *.ind *.idx *.ilg *.pdfsync   \
	*.inx *.ps *.dvi *.toc *.out *.nav *.snm *.d *.bak _region* *.vrb
	rm -rf auto

mrproper: clean
	rm -f *.pdf

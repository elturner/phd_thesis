R = elturner
STY = *.cls

# rule to make everything
pdf: $(R).pdf

# just make pdf fast, may not have all references correct
fast:
	pdflatex $(R)

# rule to make bibliography file
$(R).bbl: $(R).bib
	pdflatex $(R)
	bibtex $(R)
	pdflatex $(R)
	pdflatex $(R)

# rule to make pdf (required for a4 sizes)
$(R).pdf: *.tex $(STY) $(R).bbl
	pdflatex $(R)
	pdflatex $(R)
	pdflatex $(R)

# show what's left to do
todo:
	grep -n --color=auto "TODO" $(R).tex $(R).bib

# clean all temporary files
clean:
	rm -f $(R).log $(R).aux $(R).bbl $(R).blg $(R).out $(R).dvi $(R).toc $(R).lof $(R).lot

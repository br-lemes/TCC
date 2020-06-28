PROJECT=documento
TEX=pdflatex
BIBTEX=bibtex
INDEX=makeindex
BUILDTEX=$(TEX) $(PROJECT).tex
SOURCE=conf/brasao-brasil.pdf conf/citacoes.tex conf/cores.tex \
	conf/espacamentos.tex conf/metadados.tex conf/pdf.tex conf/preambulo.tex \
	conf/tipografia.tex pos/pos-textual.tex pre/ficha-catalografica.tex \
	pre/pre-textual.tex pre/resumo.tex pre/siglas.tex bibliografia.bib \
	conteudo.tex documento.tex

CLEAN=pos/*.aux *.aux *.bbl *.blg *.brf *.fdb_latexmk *.fls *.idx *.lof *.log *.loq *.lot *.synctex.gz *.toc

all: $(PROJECT).pdf

$(PROJECT).pdf: $(SOURCE)
	$(BUILDTEX)
	$(BIBTEX) $(PROJECT)
	$(BUILDTEX)
#	$(INDEX) $(PROJECT).idx
#	$(INDEX) $(PROJECT).nlo -s nomencl.ist -o $(PROJECT).nls
	$(BUILDTEX)
	$(BUILDTEX) -interaction nonstopmode -file-line-error
	exo-open $(PROJECT).pdf

clean:
	$(RM) $(CLEAN)

.PHONY: all clean

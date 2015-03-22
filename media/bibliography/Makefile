## The LaTeX source file.
SRC = bibliography

## Determine the host the Makefile is running on.
HOST = $(shell hostname)

## Determine the path to the pdflatex binary depending on the curront host.
ifeq ($(HOST),muem_mobile)
  ## Path to the pdflatex binary for my cygwin installation on my laptop.
	PDFLATEX_BIN = "/cygdrive/c/Program Files/MiKTeX 2.9/miktex/bin/x64/pdflatex.exe"
else
  ## Otherwise we assume that we are running this Makefile on my work PC.
	PDFLATEX_BIN = pdflatex
endif

## Determine the path to the BibTeX binary depending on the current host.
ifeq ($(HOST),muem_mobile)
  ## Path to the BibTeX binary for my cygwin installation on my laptop. 
	BIBTEX_BIN = "/cygdrive/c/Program Files/MiKTeX 2.9/miktex/bin/x64/bibtex.exe"
else
  ## Otherwise we assume that we are running this Makefile on my work PC.
	BIBTEX_BIN = bibtex
endif

## Determine the path to the Biber binary depending on the current host.
ifeq ($(HOST),muem_mobile)
  ## Path to the Biber binary for my cygwin installation on my laptop. 
	BIBER_BIN = "/cygdrive/c/Program\ Files/MiKTeX\ 2.9/miktex/bin/biber.exe"
else
  ## Otherwise we assume that we are running this Makefile on my work PC.
	BIBER_BIN = "/usr/pack/texlive-2011-kgf/bin/x86_64-linux/biber"
endif


all:
	@echo "$(HOST)"
	@echo "BIBER_BIN = $(BIBER_BIN)"

pdf:
	$(PDFLATEX_BIN) $(SRC).tex

bibtex:
	$(BIBTEX_BIN) bookchapters
	$(BIBTEX_BIN) proceedings
	$(BIBTEX_BIN) others

biber:
	$(BIBER_BIN) $(SRC)

clean:
	@echo "***** Cleaning the LaTeX directory structure."
	@rm -rf *.acr *.alg *.bbl *.blg *.glg *.gls *.aux *.glo *.ist
	@rm -rf *.lof *.log *.lot *.toc *.acn *.out *.tex~ *.tex.backup
	@rm -rf *.fdb_latexmk *.fls Makefile~ pso.conv-* auto *.hst *.ver
	@rm -rf *.bcf *.run.xml

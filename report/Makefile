# Makefile for LaTeX document with Chinese support
# Requires XeLaTeX for proper Chinese font rendering

MAIN = main
ENGINE = xelatex
BIBTEX = bibtex

.PHONY: all clean view

# Default target
all: $(MAIN).pdf

# Compile LaTeX document (two passes for cross-references)
$(MAIN).pdf: $(MAIN).tex reportstyle.sty
	$(ENGINE) $(MAIN).tex
	$(ENGINE) $(MAIN).tex
	@echo "Document compiled successfully!"
	@echo "Use 'make view' to open the PDF"

# Clean auxiliary files
clean:
	rm -f $(MAIN).aux $(MAIN).log $(MAIN).out $(MAIN).toc $(MAIN).synctex.gz
	rm -f $(MAIN).fdb_latexmk $(MAIN).fls $(MAIN).xdv
	@echo "Auxiliary files cleaned"

# Clean everything including PDF
distclean: clean
	rm -f $(MAIN).pdf
	@echo "All generated files cleaned"

# Open PDF (works on most systems)
view: $(MAIN).pdf
	@if command -v xdg-open > /dev/null; then \
		xdg-open $(MAIN).pdf; \
	elif command -v open > /dev/null; then \
		open $(MAIN).pdf; \
	else \
		echo "Please open $(MAIN).pdf manually"; \
	fi

# Force rebuild
rebuild: clean all

# Show help
help:
	@echo "Available targets:"
	@echo "  all      - Compile the document (default)"
	@echo "  clean    - Remove auxiliary files"
	@echo "  distclean- Remove all generated files"
	@echo "  view     - Open the PDF"
	@echo "  rebuild  - Clean and compile"
	@echo "  help     - Show this help"

# Variables
SOURCE = lec01.tex    # Your main LaTeX file
PDF = lec01.pdf       # Output PDF file
LATEX = pdflatex     # Change to xelatex or lualatex if you use those
FLAGS = -interaction=nonstopmode -halt-on-error  # Useful flags to prevent interruptions
AUTOCOMPILE = inotifywait -e close_write $(SOURCE)  # Use inotifywait for auto-compiling

# Rules
all: $(PDF)

$(PDF): $(SOURCE)
	$(LATEX) $(FLAGS) $(SOURCE)

clean:
	rm -f *.aux *.log *.out *.toc *.pdf

# Autocompile
watch:
	while true; do \
		$(AUTOCOMPILE); \
		make; \
	done


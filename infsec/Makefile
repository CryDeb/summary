all:
	pandoc *.md -o zusammenfassung.pdf --template="../template/template.tex" variables.yaml

clean:
	rm -f zusammenfassung.pdf

rebuild: clean all

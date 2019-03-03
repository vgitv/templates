# -----------------------------------------------------------------------------------------------------------
#  variables
# -----------------------------------------------------------------------------------------------------------
# nom du projet
PROJECT = latex

# fichiers, dossier sortie, compilateur, pdf
SOURCES = preambule.tex main.tex a.tex b.tex c.tex app.tex
OUTDIR  = output
CC      = pdflatex -output-directory $(OUTDIR) -file-line-error -halt-on-error
EXEC    = main.pdf



# -----------------------------------------------------------------------------------------------------------
#  compilation rules
# -----------------------------------------------------------------------------------------------------------
#nmap <F4> :!echo -e "\033[1;36m`date`\033[00m"<CR>:make!<CR>
# exécutable
.PHONY : $(EXEC)
$(EXEC) :
	$(CC) main.tex || echo "\033[1;33m \n/!\ ERROR /!\ \033[00m"



# -----------------------------------------------------------------------------------------------------------
# phony targets
# -----------------------------------------------------------------------------------------------------------
# exécuter l'exécutable (utile pour utiliser F5 dans vim)
.PHONY : make
make :
	xdg-open $(OUTDIR)/$(EXEC)

# supprimer les fichiers objet et l'exécutable s'ils existent
.PHONY : clean
clean :
	rm -r $(OUTDIR)/*

# ouvrir les fichiers du projet dans des onglets de vim
.PHONY : open
open :
	vim -p $(SOURCES) Makefile

# clean et tarer le dossier
.PHONY : tar
tar :
	make clean
	tar -zcvf ../$(PROJECT).tar.gz ../$(PROJECT)

# sauvegarder ancienne version
.PHONY : save
save :
	make clean
	rm -rf ../old_$(PROJECT)
	cp -r ../$(PROJECT) ../old_$(PROJECT)

#
.PHONY : coffe
coffe :
	@echo "  (\n   )\n c[]"

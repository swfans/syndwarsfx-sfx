ACLOCAL_AMFLAGS = --install -I m4

sounddat_DATA = sound/sound.dat
sounddatdir = $(prefix)/$(PARENT_PACKAGE)/sound

sound/sound.dat: $(top_srcdir)/sound/filelist_eng.txt

docs_DATA = README.md sfx_config.h
docsdir = $(prefix)/$(PARENT_PACKAGE)

EXTRA_DIST = sounddat docs

sound/%.dat:
	$(MKDIR_P) "$(@D)"
	$(WAWTODAT) -o "$@" "$<"

install-data-hook:
	cd "$(DESTDIR)${prefix}/$(PARENT_PACKAGE)"; \
	mv README.md sfx_readme.md

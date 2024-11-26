
sounddat_DATA = sound/sound.dat
sounddatdir = $(prefix)/$(PARENT_PACKAGE)/sound

sound/sound.dat: $(top_srcdir)/sound/filelist_eng.txt

docs_DATA = sfx_config.h
docsdir = $(prefix)/$(PARENT_PACKAGE)

EXTRA_DIST = sounddat docs

sound/%.dat:
	$(MKDIR_P) "$(@D)"
	$(WAWTODAT) -o "$@" "$<"

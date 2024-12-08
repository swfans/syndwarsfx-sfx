ACLOCAL_AMFLAGS = --install -I m4

sounddat_DATA = sound/sound_eng.dat sound/sound_fre.dat sound/sound_ger.dat sound/sound_ita.dat sound/sound_jap.dat sound/sound_spa.dat sound/sound_swe.dat sound/syncreds.dat
sounddatdir = $(prefix)/$(PARENT_PACKAGE)/sound

sound/sound_eng.dat: $(top_srcdir)/sound/filelist_eng.txt

sound/sound_fre.dat: $(top_srcdir)/sound/filelist_fre.txt

sound/sound_ger.dat: $(top_srcdir)/sound/filelist_ger.txt

sound/sound_ita.dat: $(top_srcdir)/sound/filelist_ita.txt

sound/sound_jap.dat: $(top_srcdir)/sound/filelist_jap.txt

sound/sound_spa.dat: $(top_srcdir)/sound/filelist_spa.txt

sound/sound_swe.dat: $(top_srcdir)/sound/filelist_swe.txt

sound/syncreds.dat: $(top_srcdir)/syncreds/filelist_credits.txt

docs_DATA = README.md sfx_config.h
docsdir = $(prefix)/$(PARENT_PACKAGE)

EXTRA_DIST = sounddat docs

sound/%.dat:
	$(MKDIR_P) "$(@D)"
	$(WAWTODAT) -o "$@" "$<"

install-data-hook:
	cd "$(DESTDIR)${prefix}/$(PARENT_PACKAGE)"; \
	mv README.md sfx_readme.md

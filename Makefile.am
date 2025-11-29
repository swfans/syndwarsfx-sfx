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

instrumconf_DATA = sound/midipats.cfg
instrumconfdir = $(prefix)/$(PARENT_PACKAGE)/sound

sound/%.cfg: $(top_srcdir)/instruments/%.cfg
	$(MKDIR_P) "$(@D)"
	cp -p "$<" "$@"

instrumpats_DATA = sound/Tone_000/000_Acoustic_Grand_Piano.pat sound/Tone_000/004_Electric_Piano_1_Rhodes.pat
instrumpatsdir = $(prefix)/$(PARENT_PACKAGE)/sound/Tone_000

sound/Tone_000/%.pat: $(top_srcdir)/instruments/Tone_000/%.pat
	$(MKDIR_P) "$(@D)"
	cp -p "$<" "$@"

docs_DATA = README.md sfx_config.h
docsdir = $(prefix)/$(PARENT_PACKAGE)

EXTRA_DIST = sounddat instrumpats instrumconf docs

sound/%.dat:
	$(MKDIR_P) "$(@D)"
	$(WAWTODAT) -o "$@" "$<"

install-data-hook:
	cd "$(DESTDIR)${prefix}/$(PARENT_PACKAGE)"; \
	mv README.md sfx_readme.md

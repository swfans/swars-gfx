ACLOCAL_AMFLAGS = --install -I m4

gfxani_DATA = $(wildcard $(top_srcdir)/data/*.ani)
gfxanidir = $(prefix)/$(PARENT_PACKAGE)/data

mouse0_DATA = data/mouse0-1.dat data/mouse0-1.tab
mouse0dir = $(prefix)/$(PARENT_PACKAGE)/data

data/mouse0-1.tab: data/mouse0-1.dat

data/mouse0-1.dat: $(top_srcdir)/femouse-64/filelist-mouse0-1.txt $(top_srcdir)/data/feproj-std.pal

pointr0_DATA = data/pointr0-2.dat data/pointr0-2.tab data/pointr0-1.dat data/pointr0-1.tab data/pointr0-0.dat data/pointr0-0.tab
pointr0dir = $(prefix)/$(PARENT_PACKAGE)/data

data/pointr0-2.tab: data/pointr0-2.dat

data/pointr0-2.dat: $(top_srcdir)/pointers-128/filelist-pointr0-2.txt $(top_srcdir)/data/engine-std.pal

data/pointr0-1.tab: data/pointr0-1.dat

data/pointr0-1.dat: $(top_srcdir)/pointers-64/filelist-pointr0-1.txt $(top_srcdir)/data/engine-std.pal

data/pointr0-0.tab: data/pointr0-0.dat

data/pointr0-0.dat: $(top_srcdir)/pointers-32/filelist-pointr0-0.txt $(top_srcdir)/data/engine-std.pal

include $(srcdir)/sprites-font0-1.am
include $(srcdir)/sprites-font0-2.am
include $(srcdir)/sprites-font0-4.am

font0_DATA = $(font0_1_files) $(font0_2_files) $(font0_4_files)
font0dir = $(prefix)/$(PARENT_PACKAGE)/data

include $(srcdir)/sprites-pop0-0.am
include $(srcdir)/sprites-pop0-1.am
include $(srcdir)/sprites-pop2-1.am

include $(srcdir)/sprites-panel0-0.am
include $(srcdir)/sprites-panel0-1.am

pop0_DATA = $(pop0_0_files) $(pop0_1_files) $(pop2_1_files) $(panel0_0_files) $(panel0_1_files)
pop0dir = $(prefix)/$(PARENT_PACKAGE)/data

data/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"

docs_DATA = README.md gfx_config.h
docsdir = $(prefix)/$(PARENT_PACKAGE)

EXTRA_DIST = gfxani docs mouse0 pointr0 font0 pop0

install-data-hook:
	cd "$(DESTDIR)${prefix}/$(PARENT_PACKAGE)"; \
	mv README.md gfx_readme.md

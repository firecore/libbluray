include $(top_srcdir)/doxygen-include.am

ACLOCAL_AMFLAGS=-I m4

EXTRA_DIST = \
	bootstrap \
	doc \
	COPYING \
	player_wrappers \
	src/libbluray/bdj/build.xml \
	src/libbluray/bdj/java

dist_doc_DATA = README.txt ChangeLog

MOSTLYCLEANFILES = $(DX_CLEANFILES)

DISTCHECK_CONFIGURE_FLAGS = --enable-bdjava

AM_CFLAGS = -D_ISOC99_SOURCE -D_POSIX_C_SOURCE=200112L -D_REENTRANT \
	-I$(top_srcdir)/src -I$(top_srcdir)/src/file -I$(top_srcdir)/src/libbluray/bdnav \
	$(LIBXML2_CFLAGS) $(FT2_CFLAGS)

lib_LTLIBRARIES = libbluray.la

libbluray_la_LDFLAGS = -version-info $(LT_VERSION_INFO)
libbluray_la_LIBADD = $(LIBXML2_LIBS) $(FT2_LIBS)

libbluray_la_SOURCES = \
	src/libbluray/bluray.h \
	src/libbluray/bluray.c \
	src/libbluray/bluray_internal.h \
	src/libbluray/register.h \
	src/libbluray/register.c \
	src/libbluray/keys.h \
	src/libbluray/bdnav \
	src/libbluray/bdnav/bdparse.h \
	src/libbluray/bdnav/uo_mask_table.h \
	src/libbluray/bdnav/navigation.h \
	src/libbluray/bdnav/index_parse.c \
	src/libbluray/bdnav/navigation.c \
	src/libbluray/bdnav/sound_parse.c \
	src/libbluray/bdnav/sound_parse.h \
	src/libbluray/bdnav/mpls_parse.h \
	src/libbluray/bdnav/clpi_parse.c \
	src/libbluray/bdnav/mpls_parse.c \
	src/libbluray/bdnav/index_parse.h \
	src/libbluray/bdnav/clpi_parse.h \
	src/libbluray/bdnav/meta_data.h \
	src/libbluray/bdnav/meta_parse.c \
	src/libbluray/bdnav/meta_parse.h \
	src/libbluray/bdnav/extdata_parse.h \
	src/libbluray/bdnav/extdata_parse.c \
	src/libbluray/bdnav/bdid_parse.h \
	src/libbluray/bdnav/bdid_parse.c \
	src/libbluray/decoders \
	src/libbluray/decoders/pes_buffer.h \
	src/libbluray/decoders/pes_buffer.c \
	src/libbluray/decoders/m2ts_demux.h \
	src/libbluray/decoders/m2ts_demux.c \
	src/libbluray/decoders/overlay.h \
	src/libbluray/decoders/pg.h \
	src/libbluray/decoders/pg_decode.h \
	src/libbluray/decoders/pg_decode.c \
	src/libbluray/decoders/ig.h \
	src/libbluray/decoders/ig_decode.h \
	src/libbluray/decoders/ig_decode.c \
	src/libbluray/decoders/graphics_processor.h \
	src/libbluray/decoders/graphics_processor.c \
	src/libbluray/decoders/graphics_controller.h \
	src/libbluray/decoders/graphics_controller.c \
	src/libbluray/hdmv \
	src/libbluray/hdmv/hdmv_insn.h \
	src/libbluray/hdmv/hdmv_vm.h \
	src/libbluray/hdmv/hdmv_vm.c \
	src/libbluray/hdmv/mobj_parse.h \
	src/libbluray/hdmv/mobj_parse.c \
	src/libbluray/hdmv/mobj_print.c \
	src/file/dir_posix.c \
	src/file/file.h \
	src/file/file_posix.c \
	src/file/dl.h \
	src/file/dl_posix.c \
	src/file/filesystem.h \
	src/file/filesystem.c \
	src/util/attributes.h \
	src/util/strutl.c \
	src/util/strutl.h \
	src/util/macro.h \
	src/util/mutex.h \
	src/util/logging.c \
	src/util/log_control.h \
	src/util/bits.h \
	src/util/bits.c \
	src/util/logging.h

pkginclude_HEADERS = \
	src/file/filesystem.h \
	src/libbluray/bdnav/clpi_data.h \
	src/libbluray/bdnav/meta_data.h \
	src/libbluray/bluray-version.h \
	src/libbluray/bluray.h \
	src/libbluray/decoders/overlay.h \
	src/libbluray/keys.h \
	src/util/log_control.h

EXTRA_PROGRAMS = \
	bd_info \
	bdsplice \
	clpi_dump \
	hdmv_test \
	index_dump \
	libbluray_test \
	list_titles \
	mobj_dump \
	mpls_dump \
	sound_dump

# the overriding of CFLAGS is necessary to ensure that automake will
# rebuild different objects for different targets.

mpls_dump_CFLAGS = $(AM_CFLAGS)
mpls_dump_SOURCES = \
	src/examples/mpls_dump.c \
	src/examples/util.c \
	src/examples/util.h \
	src/util/bits.c \
	src/util/strutl.c \
	src/util/logging.c \
	src/file/file_posix.c \
	src/file/dir_posix.c \
	src/libbluray/bdnav/extdata_parse.c \
	src/libbluray/bdnav/mpls_parse.c \
	src/libbluray/bdnav/clpi_parse.c \
	src/libbluray/bdnav/navigation.c

clpi_dump_CFLAGS = $(AM_CFLAGS)
clpi_dump_SOURCES = \
	src/examples/clpi_dump.c \
	src/examples/util.c \
	src/examples/util.h \
	src/util/bits.c \
	src/util/logging.c \
	src/file/file_posix.c \
	src/libbluray/bdnav/extdata_parse.c \
	src/libbluray/bdnav/clpi_parse.c

sound_dump_CFLAGS = $(AM_CFLAGS)
sound_dump_SOURCES = \
	src/examples/sound_dump.c \
	src/util/bits.c \
	src/util/logging.c \
	src/file/file_posix.c \
	src/libbluray/bdnav/sound_parse.c

index_dump_CFLAGS = $(AM_CFLAGS)
index_dump_SOURCES = \
	src/examples/index_dump.c \
	src/util/bits.c \
	src/util/logging.c \
	src/file/file_posix.c \
	src/libbluray/bdnav/index_parse.c

mobj_dump_CFLAGS = $(AM_CFLAGS)
mobj_dump_SOURCES = \
	src/examples/mobj_dump.c \
	src/util/bits.c \
	src/util/logging.c \
	src/file/file_posix.c \
	src/libbluray/hdmv/mobj_parse.c \
	src/libbluray/hdmv/mobj_print.c

libbluray_test_CFLAGS = $(AM_CFLAGS)
libbluray_test_SOURCES = \
	src/examples/libbluray_test.c \
	src/util/logging.c
libbluray_test_LDADD = libbluray.la

list_titles_CFLAGS = $(AM_CFLAGS)
list_titles_SOURCES = \
	src/examples/list_titles.c \
	src/util/logging.c
list_titles_LDADD = libbluray.la

bdsplice_SOURCES = src/examples/bdsplice.c
bdsplice_LDADD = libbluray.la

hdmv_test_SOURCES = src/examples/hdmv_test.c
hdmv_test_LDADD = libbluray.la

bd_info_SOURCES = src/examples/bd_info.c
bd_info_LDADD = libbluray.la

bdj_test_SOURCES = src/examples/bdj_test.c
bdj_test_LDADD = libbluray.la

if USING_BDJAVA

AM_CFLAGS += $(BDJAVA_CFLAGS)

EXTRA_PROGRAMS += bdj_test

jardir = $(libdir)/libbluray/
jar_DATA = libbluray.jar

libbluray.jar:
	ant -f $(top_srcdir)/src/libbluray/bdj/build.xml \
	    -Dsrc_awt=:java-$(BDJ_TYPE) \
	    -Dbootclasspath="$(BDJ_BOOTCLASSPATH)"

libbluray_la_SOURCES += \
	src/libbluray/bdj/bdj.h \
	src/libbluray/bdj/bdj_private.h \
	src/libbluray/bdj/bdj_util.h \
	src/libbluray/bdj/bdj_util.c \
	src/libbluray/bdj/bdj.c \
	src/libbluray/bdj/bdjo_parser.h \
	src/libbluray/bdj/bdjo_parser.c \
	src/libbluray/bdj/common.h \
	src/libbluray/bdj/native/java_awt_BDGraphics.h \
	src/libbluray/bdj/native/java_awt_BDGraphics.c \
	src/libbluray/bdj/native/java_awt_BDFontMetrics.h \
	src/libbluray/bdj/native/java_awt_BDFontMetrics.c \
	src/libbluray/bdj/native/org_videolan_Libbluray.h \
	src/libbluray/bdj/native/org_videolan_Libbluray.c \
	src/libbluray/bdj/native/register_native.h \
	src/libbluray/bdj/native/register_native.c

clean-local:
	ant -f $(top_srcdir)/src/libbluray/bdj/build.xml clean
endif

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = src/libbluray.pc

if USING_EXAMPLES
noinst_PROGRAMS = $(EXTRA_PROGRAMS)
endif

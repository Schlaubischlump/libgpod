lib_LTLIBRARIES = libgpod.la

libgpod_la_SOURCES = 		\
	db-artwork-debug.c  	\
	db-artwork-parser.c 	\
	db-artwork-writer.c 	\
	db-image-parser.c   	\
	db-parse-context.c  	\
	itdb_artwork.c   	\
	itdb_chapterdata.c   	\
	itdb_device.c  		\
	itdb_hash58.c 		\
	itdb_hash72.c		\
	itdb_hashAB.c		\
	itdb_iphone.c		\
	itdb_itunesdb.c 	\
	itdb_photoalbum.c 	\
	itdb_playlist.c  	\
	itdb_plist.c		\
	itdb_sqlite.c		\
	itdb_sysinfo_extended_parser.c \
	itdb_thumb.c		\
	itdb_track.c     	\
	itdb_tzinfo.c		\
	itdb_zlib.c		\
	ithumb-writer.c 	\
	pixmaps.c 		\
	rijndael.c

libgpod_la_CFLAGS =
libgpod_la_LDFLAGS = -version-info $(LIBGPOD_SO_VERSION) -no-undefined
libgpod_la_CPPFLAGS = -DLIBGPOD_BLOB_DIR=\"$(LIBGPOD_BLOB_DIR)\"

libgpodincludebase = $(includedir)/gpod-1.0
libgpodincludedir = $(libgpodincludebase)/gpod
libgpodinclude_HEADERS = itdb.h
noinst_HEADERS = 		\
	db-artwork-debug.h	\
	db-artwork-parser.h 	\
	db-image-parser.h   	\
	db-itunes-parser.h  	\
	db-parse-context.h  	\
	itdb_device.h  		\
	itdb_endianness.h 	\
	itdb_plist.h		\
	itdb_private.h   	\
	itdb_sqlite_queries.h	\
	itdb_sysinfo_extended_parser.h \
	itdb_thumb.h		\
	itdb_tzinfo_data.h 	\
	itdb_zlib.h		\
	pixmaps.h		\
	rijndael.h

AM_CPPFLAGS=$(LIBGPOD_CFLAGS)
LIBS=$(LIBGPOD_LIBS) $(Z_LIBS) -lm

if HAVE_LIBIMOBILEDEVICE
LIBS+=$(LIBIMOBILEDEVICE_LIBS)
libgpod_la_CFLAGS+=$(LIBIMOBILEDEVICE_CFLAGS)
endif

uninstall-hook:
	-rmdir --ignore-fail-on-non-empty $(DESTDIR)$(libgpodincludedir)
	-rmdir --ignore-fail-on-non-empty $(DESTDIR)$(libgpodincludebase)

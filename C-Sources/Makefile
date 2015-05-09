# Use make if you want to compile libModelicaStandardTables.a on Windows/MinGW

CC = gcc
AR = ar -ru

CFLAGS = -O3 -I"zlib"

OBJS = \
ModelicaStandardTables.o \
ModelicaMatIO.o

ZLIB_OBJS = \
adler32.o \
compress.o \
crc32.o \
deflate.o \
gzclose.o \
gzlib.o \
gzread.o \
gzwrite.o \
infback.o \
inffast.o \
inflate.o \
inftrees.o \
trees.o \
uncompr.o \
zutil.o

ALL_OBJS = $(OBJS) $(ZLIB_OBJS)

libModelicaStandardTables.a: $(ALL_OBJS)
	$(AR) $@ $(ALL_OBJS)
	cp libModelicaStandardTables.a Library/linux64/libModelicaStandardTables.a

ModelicaStandardTables.o : ModelicaStandardTables.c
	$(CC) -c -DTABLE_SHARE=1 -DDUMMY_FUNCTION_USERTAB $(CFLAGS) ModelicaStandardTables.c

ModelicaMatIO.o : ModelicaMatIO.c
	$(CC) -c -DHAVE_ZLIB=1 $(CFLAGS) ModelicaMatIO.c

adler32.o : zlib/adler32.c
	$(CC) -c $(CFLAGS) zlib/adler32.c

compress.o : zlib/compress.c
	$(CC) -c $(CFLAGS) zlib/compress.c

crc32.o : zlib/crc32.c
	$(CC) -c $(CFLAGS) zlib/crc32.c

deflate.o : zlib/deflate.c
	$(CC) -c $(CFLAGS) zlib/deflate.c

gzclose.o : zlib/gzclose.c
	$(CC) -c $(CFLAGS) zlib/gzclose.c

gzlib.o : zlib/gzlib.c
	$(CC) -c $(CFLAGS) zlib/gzlib.c

gzread.o : zlib/gzread.c
	$(CC) -c $(CFLAGS) zlib/gzread.c

gzwrite.o : zlib/gzwrite.c
	$(CC) -c $(CFLAGS) zlib/gzwrite.c

infback.o : zlib/infback.c
	$(CC) -c $(CFLAGS) zlib/infback.c

inffast.o : zlib/inffast.c
	$(CC) -c $(CFLAGS) zlib/inffast.c

inflate.o : zlib/inflate.c
	$(CC) -c $(CFLAGS) zlib/inflate.c

inftrees.o : zlib/inftrees.c
	$(CC) -c $(CFLAGS) zlib/inftrees.c

trees.o : zlib/trees.c
	$(CC) -c $(CFLAGS) zlib/trees.c

uncompr.o : zlib/uncompr.c
	$(CC) -c $(CFLAGS) zlib/uncompr.c

zutil.o : zlib/zutil.c
	$(CC) -c $(CFLAGS) zlib/zutil.c

clean :
	rm -f $(ALL_OBJS)
	rm -f libModelicaStandardTables.a

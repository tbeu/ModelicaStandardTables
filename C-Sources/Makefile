CC = gcc
AR = ar -ru
RM = rm -f

CFLAGS = -O3
CXXFLAGS = -DNDEBUG -I"zlib"

TARGETDIR = linux64

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

libModelicaStandardTables.a: clean $(ALL_OBJS)
	$(AR) $@ $(ALL_OBJS)
	cp libModelicaStandardTables.a ../Library/$(TARGETDIR)/libModelicaStandardTables.a

ModelicaStandardTables.o: ModelicaStandardTables.c
	$(CC) -c -o $@ $< $(CFLAGS) $(CXXFLAGS) -DTABLE_SHARE=1 -DDUMMY_FUNCTION_USERTAB

ModelicaMatIO.o: ModelicaMatIO.c
	$(CC) -c -o $@ $< $(CFLAGS) $(CXXFLAGS) -DHAVE_ZLIB=1

%.o: zlib/%.c
	$(CC) -c -o $@ $< $(CFLAGS) $(CXXFLAGS)

clean:
	$(RM) $(ALL_OBJS)
	$(RM) *.a
	$(RM) ../Library/$(TARGETDIR)/libModelicaStandardTables.a

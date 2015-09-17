CC = gcc
AR = ar -ru
RM = rm -f

CFLAGS = -O3
CPPFLAGS = -DNDEBUG
INC = -I"zlib"

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
	$(CC) $(CPPFLAGS) -DTABLE_SHARE=1 -DDUMMY_FUNCTION_USERTAB $(CFLAGS) $(INC) -c -o $@ $<

ModelicaMatIO.o: ModelicaMatIO.c
	$(CC) $(CPPFLAGS) -DHAVE_ZLIB=1 $(CFLAGS) $(INC) -c -o $@ $<

%.o: zlib/%.c
	$(CC) $(CPPFLAGS) $(CFLAGS) $(INC) -c -o $@ $<

clean:
	$(RM) $(ALL_OBJS)
	$(RM) *.a
	$(RM) ../Library/$(TARGETDIR)/libModelicaStandardTables.a

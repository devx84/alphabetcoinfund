# (c) Copyright The AlphabetCoinFund Developers, 2016

# specify PYINCDIR if using non-system python
PYINCDIR = -I/usr/include/python2.7
INCDIRS = $(PYINCDIR) -I../../src
# CFLAGS = -g -Wall -pedantic -dynamiclib -fPIC
CFLAGS = -g -Wall -fPIC

VPATH = ../../src


CC = gcc
CXX = g++
LDFLAGS = -shared -fpic

PROGS = pyHash9

OBJS = blake.o bmw.o groestl.o jh.o \
       keccak.o skein.o luffa.o \
       cubehash.o shavite.o simd.o \
       echo.o hamsi.o fugue.o \
       pyHash9.o

%.o: %.c
	${CC} ${CFLAGS} ${INCDIRS} -c $<

%.o: %.cpp
	${CXX} ${CFLAGS} ${INCDIRS} -c $<

%.o: %.cpp
	${CXX} ${CFLAGS} ${INCDIRS} -c $<

all: $(PROGS)

${PROGS}: %: %.o $(OBJS)
	${CXX} ${CFLAGS} ${LDFLAGS} -o $@.so ${OBJS}

clean:
	rm -f *.so *.o

# Makefile for "stargen", a star system and planet generator

# Change the following if your C compiler isn't called 'gcc' (note that on Linux 
# the default compiler is gcc but it can still be run as cc).
#CC=gcc

# And change this to your fvorite C compiler flags:
CFLAGS = -O -g -W -Wall -D_USE_LIBM_MATH_H

# We use a lot of long doubles and Mac OS X currently warns you that they're
# thinking about changing these from 64 to 128 bits. To suppress that warning:
CFLAGS += -Wno-long-double

OBJS = main.o stargen.o accrete.o display.o enviro.o utils.o

LIBS = -lm

.c.o:
	$(CC) -c $(CFLAGS) $*.c

# on Amiga, I'm told this should be:
#   $(CC) -c $(CFLAGS) $*.c -o $*.o

all:	stargen

stargen: $(OBJS)
	$(CC) $(CFLAGS) -o stargen $(OBJS) $(LIBS)

clean:
	$(RM) $(OBJS) stargen

accrete.o:	const.h structs.h accrete.h stargen.h utils.h
display.o:	const.h structs.h enviro.h display.h stargen.h
enviro.o:	const.h structs.h enviro.h stargen.h utils.h
stargen.o:	const.h structs.h enviro.h display.h accrete.h stargen.h utils.h
utils.o:	const.h utils.h
stargen.o:	const.h structs.h enviro.h accrete.h stargen.h


CC=gcc
DEPS=main.c fuzzgoat.c
CFLAGS=-I.
LIBS=-lm

all: $(DEPS)
	$(CC) -o fuzzgoat $(CFLAGS) $^ $(LIBS)

.PHONY: clean

clean:
	rm ./fuzzgoat

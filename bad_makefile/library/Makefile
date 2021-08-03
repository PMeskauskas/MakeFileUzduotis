CC:=gcc
CFLAGS:=-Wall -g 

LIB:=libcalculator.so
SRC:=$(wildcard *.c)
OBJ:=$(SRC:.c=.o)
PREFIX?=/usr

.PRONY : all clean uninstall install

all: $(LIB)

$(LIB): $(OBJ)
	$(CC) $(CFLAGS) -fPIC -shared -o $@ $^ -lc

install: 
	 install -m 555 $(LIB) $(PREFIX)/lib

uninstall:
	 $(RM) $(PREFIX)/lib/$(LIB)

clean:
	rm -f $(LIB) $(OBJ)

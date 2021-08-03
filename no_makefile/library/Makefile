CC:=gcc
CFLAGS:=-Wall
CPPFLAGS:= -I$(PWD)
PREFIX:= /usr

LIB:=libexample.so
BIN:=main


SRCLIB:=file_reader.c	
OBJLIB:=$(SRCLIB:.c=.o)

SRC:=main.c
OBJ:=$(SRC:.c=.o)
.PHONY : all install uninstall clean

all: $(LIB) $(BIN)

$(LIB): $(OBJLIB)
	$(CC) -o $(LIB) -shared -fPIC  $<

$(BIN): $(OBJ) $(LIB)
	$(CC) $(CFLAGS) $^ $ -o $@

librarytest: $(OBJ)
	$(CC) $(CFLAGS) -o $@ $^ -L. -lexample

install:
	install -m 555 $(BIN) $(PREFIX)/bin/$(BIN)
	install -m 555 $(LIB) $(PREFIX)/lib/$(LIB)

uninstall: 
	$(RM) $(PREFIX)/bin/$(BIN)
	$(RM) $(PREFIX)/lib/$(LIB)

clean:
	rm -f $(BIN) $(OBJ) $(LIB) $(OBJLIB) librarytest
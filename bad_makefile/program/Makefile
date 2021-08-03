CC:=gcc
CFLAGS:=-Wall
CPPFLAGS:= -I$(PWD)
PREFIX:= /usr

BIN:=calculator
SRC:=$(wildcard *.c)
OBJ:=$(SRC:.c=.o)

.PHONY : all install uninstall clean

all: $(BIN)

$(BIN): $(OBJ)
	$(CC) $(CFLAGS) $^ -o $(BIN)

install:
	install -m 555 $(BIN) $(PREFIX)/bin/$(BIN)

uninstall: 
	$(RM) $(PREFIX)/bin/$(BIN)

clean:
	rm -f $(BIN) $(OBJ)
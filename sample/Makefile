MAPR_HOME    ?= /opt/mapr
MAPR_INCLUDE ?= $(MAPR_HOME)/include
MAPR_LIB     ?= $(MAPR_HOME)/lib
JRE_LIB      ?= $(JAVA_HOME)/jre/lib/amd64/server

LIBFLAGS=-L $(MAPR_LIB)
LDFLAGS=-lMapRClient
EXE=
ifneq ($(OS),Windows_NT)
  LIBFLAGS += -L $(JRE_LIB)
  LDFLAGS  += -ljvm
else
  EXE      = .exe
endif

SOURCES  = $(shell ls *.cc)
OBJECTS  = $(patsubst %.cc,%.o,$(SOURCES))
EXECUTABLE=sample$(EXE)

CC=gcc
CFLAGS=-c -Wall

all: $(EXECUTABLE)

$(EXECUTABLE): $(OBJECTS)
	$(CC) $(LIBFLAGS) $(OBJECTS) $(LDFLAGS) -o $(EXECUTABLE)

%.o: %.cc
	$(CC) $(CFLAGS) -g -O -c -I $(MAPR_INCLUDE) $< -o $@

clean:
	rm -rf $(EXECUTABLE) *.o

MAPR_HOME    ?= /opt/mapr
MAPR_INCLUDE ?= $(MAPR_HOME)/include
MAPR_LIB     ?= $(MAPR_HOME)/lib
JRE_LIB      ?= $(JAVA_HOME)/jre/lib/amd64/server

LIBFLAGS=-L $(MAPR_LIB)
LDFLAGS =-lMapRClient
DEFINES=
EXE=
ifneq ($(OS),Windows_NT)
  LIBFLAGS += -L $(JRE_LIB)
  LDFLAGS  += -ljvm
else
  DEFINES += -D_WIN32
  EXE      =.exe
endif

SOURCES    = $(shell ls *.cc)
OBJECTS    = $(patsubst %.cc,%.o,$(SOURCES))
EXECUTABLE = interactive$(EXE)

CC=g++
CFLAGS=-c -Wno-unused-result

all: $(EXECUTABLE)

$(EXECUTABLE): $(OBJECTS)
	$(CC) $(LIBFLAGS) $(OBJECTS) $(LDFLAGS) -o $(EXECUTABLE)

%.o: %.cc
	$(CC) $(DEFINES) $(CFLAGS) -g -O -c -I $(MAPR_INCLUDE) $< -o $@

clean:
	rm -rf $(EXECUTABLE) $(OBJECTS)

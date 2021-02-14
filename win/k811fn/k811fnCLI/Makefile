# Makefile for k811fn under MinGW

# You can define this path to point at your tools if you need to
# TOOLPATH = c:\cygwin\bin\ # or similar, if you're running Windows
# TOOLPATH = /pkg/mingw32msvc/i386-mingw32msvc/bin/
# TOOLPATH = i686-w64-mingw32-
TOOLPATH ?= x86_64-w64-mingw32-
CC = $(TOOLPATH)gcc
CXX = $(TOOLPATH)g++

CFLAGS += -Wall -O2 -D_WINDOWS -DDEBUG -DWIN32S_COMPAT -D_NO_OLDNAMES \
		-I../../../include
LDFLAGS = -s

all: k811fnCLI.exe

k811fnCLI.exe: k811fnCLI.cpp stdafx.cpp ../../hid.c
	$(CXX) -o $@ $? \
		$(CFLAGS) $(LDFLAGS) -l setupapi

k780fnCLI.exe: k780fnCLI.cpp stdafx.cpp ../../hid.c
	$(CXX) -o $@ $? \
		$(CFLAGS) $(LDFLAGS) -l setupapi

clean:
	rm -f *.exe

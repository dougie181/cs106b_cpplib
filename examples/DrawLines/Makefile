# Makefile for DrawLines
#****************************************************************

PROGRAM = DrawLines
OBJECTS = DrawLines.o

ROOTPATH = ../..
CPPOPTIONS = -I$(ROOTPATH)/include -fvisibility-inlines-hidden
LDOPTIONS = -L$(ROOTPATH)/lib -static-libstdc++
LIB = -lStanfordCPPLib

# ***************************************************************
# Entry to bring the package up to date
#    The "make all" entry should be the first real entry

all: $(PROGRAM) spl.jar

spl.jar:
	@ln -s $(ROOTPATH)/java/spl.jar

DrawLines: $(OBJECTS)
	g++ -o $(PROGRAM) $(LDOPTIONS) $(OBJECTS) $(LIB)

DrawLines.o: DrawLines.cpp Makefile StanfordCPPLib/libStanfordCPPLib.a
	g++ -c $(CPPOPTIONS) DrawLines.cpp


# ***************************************************************
# Standard entries to remove files from the directories
#    tidy  -- eliminate unwanted files
#    clean -- delete derived files in preparation for rebuild

tidy:
	rm -f ,* .,* *~ core a.out *.err

clean scratch: tidy
	rm -f *.o *.a $(PROGRAM) $(OBJECTS) spl.jar

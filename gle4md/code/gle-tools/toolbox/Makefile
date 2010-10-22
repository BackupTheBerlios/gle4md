-include ../make.config

.PHONY: all clean

all: libtoolbox.a 
libtb.o: libtb.cpp tbdefs.hpp
	$(CXX) -c -o libtb.o $(CCINC) libtb.cpp $(CCOPTS) 
libioparser.o: libioparser.cpp ioparser.hpp tbdefs.hpp
	$(CXX) -c -o libioparser.o $(CCINC) libioparser.cpp $(CCOPTS)
libclparser.o: libclparser.cpp clparser.hpp tbdefs.hpp
	$(CXX) -c -o libclparser.o $(CCINC) libclparser.cpp $(CCOPTS)
libfmblas.o: matrix-full-blas.hpp libfmblas.cpp
	$(CXX) -c -o libfmblas.o $(CCINC) libfmblas.cpp $(CCOPTS) 
liblinalg.o: liblinalg.cpp linalg.hpp
	$(CXX) -c -o liblinalg.o $(CCINC) liblinalg.cpp $(CCOPTS) 
libtoolbox.a: libtb.o libioparser.o libclparser.o libfmblas.o liblinalg.o 
	ar rcs libtoolbox.a libtb.o libioparser.o libclparser.o libfmblas.o liblinalg.o
clean:
	rm -f *~ *.o libtoolbox.a

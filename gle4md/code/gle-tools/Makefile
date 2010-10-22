-include make.config

.PHONY: all clean toolbox
all: gle-analyze 
toolbox:
	$(MAKE) -C toolbox libtoolbox.a
libcolor.o: libcolor.cpp color.hpp 
	$(CXX) -c -o libcolor.o $(CCINC) libcolor.cpp $(CCOPTS) 
gle-analyze: libcolor.o gle-analyze.cpp toolbox
	$(CXX) -o gle-analyze $(CCINC)  $(CCOPTS)  gle-analyze.cpp libcolor.o $(LDOPTS)
clean:
	rm -f *.o *~ gle-analyze
	$(MAKE) -C toolbox clean

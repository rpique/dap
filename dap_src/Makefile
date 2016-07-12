CPPFLAGS= -O3 -I/wsu/home/groups/piquelab/include
LDFLAGS= -L/wsu/apps/gnu-4.7.2/python/Anaconda/Anaconda-2.1.0/lib -L/wsu/home/groups/piquelab/lib -L/wsu/home/groups/piquelab/lib64 -lm -lgsl -lgslcblas -lboost_iostreams -lz

main: main.o controller.o parser.o SSLR.o
	g++  -fopenmp  $(CPPFLAGS) main.o parser.o controller.o SSLR.o ${LDFLAGS} -o dap
static:	main.o controller.o parser.o SSLR.o 
	g++  -fopenmp  $(CPPFLAGS) main.o parser.o controller.o SSLR.o ${LDFLAGS} -o dap.static
main.o: main.cc
	g++ -c $(CPPFLAGS)  main.cc
parser.o: parser.cc parser.h
	g++ -c $(CPPFLAGS) parser.cc
controller.o: controller.cc controller.h
	g++ -c $(CPPFLAGS) -fopenmp  controller.cc
SSLR.o: SSLR.h SSLR.cc
	g++ -c $(CPPFLAGS) SSLR.cc
clean:
	rm *.o dap

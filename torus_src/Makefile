CPPFLAGS= -O3 -I/wsu/home/groups/piquelab/include
LDFLAGS= -L/wsu/apps/gnu-4.7.2/python/Anaconda/Anaconda-2.1.0/lib -L/wsu/home/groups/piquelab/lib -L/wsu/home/groups/piquelab/lib64 -lm -lgsl -lgslcblas -lboost_iostreams -lz

main: main.o controller.o logistic.o 
	g++  $(CPPFLAGS) main.o controller.o logistic.o $(LDFLAGS)  -o torus 
main.o: main.cc 
	g++ -c $(CPPFLAGS) main.cc	
controller.o: controller.cc classdef.h
	g++ -c $(CPPFLAGS) controller.cc 
logistic.o: logistic.cc logistic.h
	g++ -c $(CPPFLAGS) logistic.cc -fpermissive
clean:
	rm *.o torus

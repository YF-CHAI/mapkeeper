include ../Makefile.config

EXECUTABLE = mapkeeper_rocksdb

all :
	g++ -std=c++11 -Wall -o $(EXECUTABLE) *cpp  -DHAVE_NETINET_IN_H -DHAVE_INTTYPES_H     -I $(THRIFT_DIR)/include/thrift -I $(THRIFT_DIR)/include \
        -lboost_thread -lboost_system -lpthread -lboost_filesystem -lboost_program_options -lthrift -lrocksdb -I ../thrift/gen-cpp \
    -L $(THRIFT_DIR)/lib \
        -L ../thrift/gen-cpp -lmapkeeper \
           -Wl,-rpath,\$$ORIGIN/../thrift/gen-cpp            \
           -Wl,-rpath,$(THRIFT_DIR)/lib

run:
	./$(EXECUTABLE) --sync

clean :
	- rm -rf $(THRIFT_SRC) $(EXECUTABLE) *.o 

wipe:
	- rm -rf data/*

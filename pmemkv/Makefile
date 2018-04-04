include ../Makefile.config

EXECUTABLE = mapkeeper_pmemkv

all :
	g++ -g -Wall -o $(EXECUTABLE) *cpp -I $(THRIFT_DIR)/include/thrift -I $(THRIFT_DIR)/include \
        -lboost_thread -DHAVE_NETINET_IN_H    -fpermissive -std=c++11  -lboost_system -lpmemkv -lpthread -lboost_filesystem -lboost_program_options -lthrift -lleveldb -I ../thrift/gen-cpp \
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
